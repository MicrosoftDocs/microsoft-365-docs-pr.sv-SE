---
title: Få expert utbildning om avancerad jakt
description: Gratis utbildning och vägledning från avancerade jakt experter
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, språk, utbildning, scenarier, grundläggande för Avancerat, videoklipp, steg-för-steg
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
ms.openlocfilehash: 7db1854534964928b622a7c2f47d07654472f048
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197971"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Få expert utbildning om avancerad jakt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

Öka dina kunskaper om Avancerat jakt snabbt med _spårning av adversary_, en webb sändnings serie för nya säkerhets analyser och hotade hot Hunters. Serien vägleder dig genom grunderna för att skapa dina egna avancerade frågor. Börja med den första videon på grunderna eller gå till mer avancerade videor som passar din upplevelse.


| Title | Beskrivning | Watch | Under | 
|--|--|--|--|
| Avsnitt 1: grundläggande om Keyword | I det här avsnittet beskrivs de grundläggande funktionerna i den avancerade jakten i Microsoft Threat Protection. Läs mer om tillgängliga avancerade jakt data och grundläggande Keyword-syntax och-operatörer. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [CSL-fil](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Avsnitt 2: kopplingar | Fortsätt att lära sig mer om data i avancerad jakt och hur du ansluter samman tabeller. Lär dig mer om `inner` , `outer` , `unique` och `semi` kopplingar och förstå Nuances för standard Kusto- `innerunique` kopplingen. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [CSL-fil](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Avsnitt 3: summera, pivotera och visualisera data | Nu när du har lärt dig att filtrera, hantera och koppla data är det dags att summera, kvantifiera, pivotera och visualisera. I det här avsnittet beskrivs `summarize` operatorn och olika beräkningar, medan fler tabeller i schemat introduceras. Du får också lära dig att omvandla data mängder till diagram som kan hjälpa dig att extrahera inblick. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [CSL-fil](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Avsnitt 4: Låt oss titta! Använda Keyword i händelse spårning | I det här avsnittet lär du dig hur du spårar vissa angrepps aktiviteter. Vi använder vår förbättrade förståelse av Kusto och avancerad jakt för att spåra ett angrepp. Lär dig mer om faktiska stick som används i fältet, inklusive ABCs för Cybersecurity och hur du ska tillämpa dem på händelsens svar. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [CSL-fil](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Använda CSL-filen
Innan du startar ett avsnitt kan du gå till motsvarande [KUSTO CSL-fil på GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) och kopiera dess innehåll till den avancerade Frågeredigeraren. När du tittar på ett avsnitt kan du använda det kopierade innehållet för att följa högtalaren och köra frågor. 

Följande utdrag från en CSL-fil visar en omfattande uppsättning vägledningar som är markerade som kommentarer med `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Samma CSL-fil innehåller frågor före och efter kommentarerna enligt nedan. Om du vill köra en specifik fråga med [flera frågor i redigeraren](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)flyttar du markören till frågan och väljer **Kör fråga**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig mer om det avancerade frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
