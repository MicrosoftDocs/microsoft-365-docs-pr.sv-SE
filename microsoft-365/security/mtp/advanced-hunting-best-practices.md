---
title: Avancerad jakt metod tips för Microsoft Threat Protection
description: Lär dig hur du skapar snabba, effektiva och problem med hotfrågor när du använder avancerad jakt
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, schema, kusto, undvika tids gräns, kommando rader, process-ID
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f66b17fbdaaa58cf12bd0373d0fece59349c3a48
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649505"
---
# <a name="advanced-hunting-query-best-practices"></a>Metod tips för avancerad jakt frågor

**Gäller för:**
- Microsoft Hotskydd



## <a name="optimize-query-performance"></a>Optimera frågeresultatet
Använd dessa rekommendationer för att få snabbare resultat och undvika tids gränser när du kör komplexa frågor:
- När du försöker med nya frågor bör `limit` du alltid använda för att undvika extremt stora resultat mängder. Du kan också börja med att bedöma storleken på resultatet som används `count` .
- Använd tids filter först. Det bästa är att begränsa dina frågor till ännu dagar.
- Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tids filtret.
- Använd `has` operatorn `contains` när du letar efter fullständiga token.
- Leta i en viss kolumn i stället för att köra fullständig text ökning i alla kolumner.
- När du kopplar tabeller ska du ange tabellen med färre rader först.
- `project`endast kolumner från tabeller som du har anslutit till.

>[!Tip]
>För mer information om hur du förbättrar frågeresultatet kan du läsa [Kusto metod tips](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Tips för frågor och fall GRO par

### <a name="queries-with-process-ids"></a>Frågor med process-ID: n
Process-ID: n återvinns i Windows och återanvänds för nya processer. De kan inte fungera som unika identifierare för specifika processer.

Om du vill ha en unik identifierare för en process på en specifik dator använder du process-ID: t tillsammans med processen för skapande av process. När du ansluter till eller sammanfattar data i processer inkluderar du kolumner för datorns ID (antingen `DeviceId` eller `DeviceName` ), process-ID ( `ProcessId` eller `InitiatingProcessId` ) och processens skapelse tid ( `ProcessCreationTime` eller `InitiatingProcessCreationTime` )

I följande exempel fråga hittas processer med åtkomst till fler än 10 IP-adresser över Port 445 (SMB), eventuellt genomsökning efter fil resurser.

Exempel fråga:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattar både efter båda `InitiatingProcessId` och `InitiatingProcessCreationTime` så att den ser ut på en enstaka gång, utan att flera processer med samma process-ID kan blandas.

### <a name="queries-with-command-lines"></a>Frågor med kommando rader

Kommando rader kan variera. I tillämpliga fall filtrerar du efter fil namn och utför fuzzy-matchning.

Det finns många olika sätt att skapa en kommando rad för att utföra en uppgift. En angripare kan till exempel referera till en bildfil med eller utan en sökväg, utan fil namns tillägg, med hjälp av miljövariabler eller med citat tecken. Dessutom kan angriparen också ändra ordningen på parametrar eller lägga till flera citat tecken och blank steg.

Gör så här om du vill skapa fler beständiga frågor med kommando rader:

- Identifiera kända processer (till exempel *net.exe* eller *psexec.exe*) genom att matcha fil namns fälten i stället för filtrering i kommando rads fältet.
- Leta inte efter en exakt matchning på flera icke relaterade argument i en viss ordning när du frågar efter kommando rads argument. Använd i stället vanliga uttryck eller Använd flera separata innehåller operatorer.
- Använd Skift läges okänsliga träffar. Till exempel använda `=~` , `in~` och `contains` i stället för `==` , `in` och`contains_cs`
- Om du vill minska DOS-obfuscation metoder kan du ta bort citat tecken, ersätta kommatecken med blank steg och ersätta flera sammanhängande blank steg med ett enda blank steg. Observera att det finns mer komplexa DOS obfuscation-tekniker som kräver andra metoder, men dessa kan hjälpa till med att adressera de vanligaste.

Följande exempel visar olika sätt att skapa en fråga som söker efter filen *net.exe* att stoppa Windows Defender Firewall-tjänsten:

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
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
