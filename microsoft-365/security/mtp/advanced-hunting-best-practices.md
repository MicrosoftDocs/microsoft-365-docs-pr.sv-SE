---
title: Avancerad jaktpraxis i Microsofts hotskydd
description: Lär dig hur du konstruerar snabba, effektiva och felfria hotjaktsfrågor när du använder avancerad jakt
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, undvika timeout, kommandorader, process-ID
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
ms.openlocfilehash: a859aa201b43813d6c66a797cbfee160051d5103
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807803"
---
# <a name="advanced-hunting-query-best-practices"></a>Metodtips för avancerad jaktfråga

**Gäller:**
- Microsofts hotskydd



## <a name="optimize-query-performance"></a>Optimera frågeprestanda
Använd dessa rekommendationer för att få resultat snabbare och undvika timeout när du kör komplexa frågor:
- När du provar nya `limit` frågor, använd alltid för att undvika extremt stora resultatuppsättningar. Du kan också först bedöma storleken på `count`resultatuppsättningen med .
- Använd tidsfilter först. Begränsa dina frågor till jämna dagar.
- Placera filter som förväntas ta bort de flesta data i början av frågan, direkt efter tidsfiltret.
- Använd `has` operatorn `contains` över när du letar efter fullständiga tokens.
- Titta i en viss kolumn i stället för att köra fulltextsökningar i alla kolumner.
- När du sammanfogar tabeller anger du tabellen med färre rader först.
- `project`bara nödvändiga kolumner från tabeller som du har gått med i.

>[!Tip]
>Mer information om hur du förbättrar frågeprestanda finns i [bästa praxis för Kusto-frågor](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Frågetips och fallgropar

### <a name="queries-with-process-ids"></a>Frågor med process-ID
Process-ID (PID) återvinns i Windows och återanvänds för nya processer. På egen hand kan de inte fungera som unika identifierare för specifika processer.

Om du vill få en unik identifierare för en process på en viss dator använder du process-ID:t tillsammans med processens skapandetid. När du sammanfogar eller summerar data runt processer, `DeviceId` `DeviceName`inkludera kolumner för`ProcessId` maskinidentifieraren (antingen eller ), process-ID (eller `InitiatingProcessId`), och processens skapandetid (`ProcessCreationTime` eller `InitiatingProcessCreationTime`)

Följande exempelfråga hittar processer som kommer åt mer än 10 IP-adresser över port 445 (SMB), eventuellt genomsökning efter filresurser.

Exempelfråga:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattas med `InitiatingProcessId` `InitiatingProcessCreationTime` båda och så att den tittar på en enda process, utan att blanda flera processer med samma process-ID.

### <a name="queries-with-command-lines"></a>Frågor med kommandorader

Kommandorader kan variera. I förekommande fall filtrera på filnamn och gör suddig matchning.

Det finns många sätt att skapa en kommandorad för att utföra en uppgift. En angripare kan till exempel referera till en bildfil med eller utan sökväg, utan filtillägg, använda miljövariabler eller med citattecken. Dessutom kan angriparen också ändra ordningen på parametrar eller lägga till flera citattecken och blanksteg.

Om du vill skapa mer varaktiga frågor med kommandorader använder du följande metoder:

- Identifiera kända processer (till exempel *net.exe* eller *psexec.exe)* genom att matcha i filnamnsfälten i stället för att filtrera i kommandoradsfältet.
- När du frågar efter kommandoradsargument ska du inte leta efter en exakt matchning på flera orelaterade argument i en viss ordning. Använd i stället reguljära uttryck eller använd flera separata operatorer.
- Använd skiftläge okänsliga matchningar. Använd till `=~`exempel `in~`, `contains` och `==` `in`i stället för , och`contains_cs`
- Om du vill minska DOS-kommandoradsfördunklingstekniker bör du överväga att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera på varandra följande blanksteg med ett enda blanksteg. Observera att det finns mer komplexa DOS-fördunklingstekniker som kräver andra metoder, men dessa kan hjälpa till att ta itu med de vanligaste.

I följande exempel visas olika sätt att skapa en fråga som söker efter filen *net.exe* för att stoppa windows defender-brandväggen:

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
- [Proaktivt jakt efter hot](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
