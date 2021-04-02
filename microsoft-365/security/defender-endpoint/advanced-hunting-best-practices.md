---
title: Metodtips för frågor för avancerad sökning
description: Lär dig att konstruera snabba, effektiva och felfria sökning efter hot när du använder avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499262"
---
# <a name="advanced-hunting-query-best-practices"></a>Avancerade metodtips för sökningsfrågor

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Optimera frågeprestanda

Använd de här rekommendationerna för att få resultat snabbare och undvika tidsgränser när du kör komplexa frågor.

- Undvik alltid extremt stora resultatuppsättningar när du `limit` försöker skapa nya frågor. Du kan också börja med att bedöma storleken på resultatuppsättningen med hjälp av `count` .
- Använd tidsfilter först. Under idealiska tider bör du begränsa dina frågor till sju dagar.
- Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tidsfiltret.
- Använd `has` operatorn över `contains` när du letar efter fullständiga token.
- Titta i en specifik kolumn i stället för att köra fullständiga textsökningar i alla kolumner.
- När du sammanfogar tabeller anger du först tabellen med färre rader.
- `project` Endast kolumner från tabeller som du har anslutit till är nödvändiga.

>[!TIP]
>Mer vägledning om hur du förbättrar frågeprestanda finns [i Metodtips för Kusto-frågor.](https://docs.microsoft.com/azure/kusto/query/best-practices)

## <a name="query-tips-and-pitfalls"></a>Frågetips och fallgropar

### <a name="queries-with-process-ids"></a>Frågor med process-IDs

Process-ID:n (PID) återanvänds i Windows och återanvänds för nya processer. De kan på egen hand inte fungera som unika identifierare för specifika processer. Om du vill få en unik identifierare för en process på en viss enhet kan du använda process-ID:t tillsammans med den tid då processen skapades. När du sammanfogar eller sammanfattar data runt processer tar du med kolumner för enhetsidentifieraren (antingen eller `DeviceId` `DeviceName` ), process-ID ( eller ) och tiden då processen skapades `ProcessId` ( eller `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).

Följande exempelfråga hittar processer som har åtkomst till fler än 10 IP-adresser via port 445 (SMB), eventuellt genomsökning efter filresurser.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattas av båda och så att den tittar på en enda `InitiatingProcessId` `InitiatingProcessCreationTime` process, utan att blanda flera processer med samma process-ID.

### <a name="queries-with-command-lines"></a>Frågor med kommandorader

Kommandorader kan variera. I förekommande fall kan du filtrera fram filnamnen och göra fuzzy-matchningen.

Det finns flera sätt att skapa en kommandorad för att utföra en aktivitet. En attackerare kan till exempel referera till en bildfil med eller utan en sökväg, utan filnamnstillägg, med hjälp av miljövariabler eller med citattecken. Dessutom kan attackerarna ändra ordning på parametrarna eller lägga till flera citattecken och blanksteg.

Så här skapar du mer beständiga frågor med hjälp av kommandorader:

- Identifiera de kända processerna (till *exempelnet.exe* eller *psexec.exe)* genom att matcha i filnamnsfälten, i stället för att filtrera på kommandoradsfältet.
- Vid sökning efter kommandoradsargument bör du inte söka efter en exakt matchning för flera orelaterade argument i en viss ordning. I stället kan du använda reguljära uttryck eller använda flera separata operatorer.
- Använd fallkänsliga matchningar. Använd till exempel `=~` , och i stället för `in~` `contains` `==` `in` och `contains_cs`
- Överväg att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera efterföljande blanksteg med ett enda blanksteg för att minimera DOS-teknikerna för att begränsa doS-obfuseringsteknik. Observera att det finns mer komplexa DOS-metoder som kräver andra metoder, men dessa kan hjälpa dig att lösa de vanligaste.

Följande exempel visar olika sätt att skapa en fråga som söker efter filen eller *net.exe* för att stoppa Windows Defender-brandväggstjänsten:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
