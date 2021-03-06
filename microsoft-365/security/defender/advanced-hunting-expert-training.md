---
title: Få expertutbildning om avancerad sökning
description: Kostnadsfri utbildning och vägledning från avancerade experter på sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, language, training, scenarios, basic to advanced, videos, step-by-step
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0b816956442408c9a61f662827f1fd45d9b6511f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538861"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Få expertutbildning om avancerad sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

Förbättra dina kunskaper om avancerad sökning snabbt med Tracking _the adversary_, en webcast-serie för nya säkerhetsanalytiker och rutinerade hot. Serien leder dig genom grunderna hela vägen till att skapa dina egna avancerade frågor. Börja med den första videon som är grundläggande, eller gå till mer avancerade videor som passar din upplevelse.

| Title | Beskrivning | Titta | Frågor | 
|--|--|--|--|
| Avsnitt 1: Grunderna i KQL | Det här avsnittet beskriver grunderna i avancerad sökning i Microsoft 365 Defender. Läs mer om tillgängliga avancerade data för sökning och grundläggande KQL-syntax och -operatorer. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.txt) |
| Avsnitt 2: Kopplingar | Fortsätt med utbildning om data i avancerad sökning och hur du sammanfogar tabeller. Läs mer `inner` om , , och `outer` `unique` `semi` kopplingar, och förstå nyanserna i standardkopplingen till `innerunique` Kusto. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.txt) |
| Avsnitt 3: Sammanfatta, pivotera och visualisera data | Nu när du har lärt dig att filtrera, manipulera och sammanfoga data är det dags att sammanfatta, analysera, pivotera och visualisera. I det här avsnittet diskuteras `summarize` operatorn och olika beräkningar, samtidigt som ytterligare tabeller introduceras i schemat. Du får också lära dig att omvandla datauppsättningar till diagram som kan hjälpa dig att extrahera insikter. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.txt) |
| Avsnitt 4: Vi jagar! Tillämpa KQL på incidentspårning | I det här avsnittet får du lära dig att spåra vissa attacker. Vi använder vår förbättrade förståelse av Kusto och avancerad sökning för att spåra en attack. Lär dig mer om faktiska trick som används inom fältet, bland annat abcs för cybersäkerhet och hur du tillämpar dem på incidentsvar. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.txt) 


Få mer expertutbildning med *L33TSP3AK:* Avancerad sökning i Microsoft 365 Defender , en webcast-serie för analytiker som vill utöka sina tekniska kunskaper och praktiska kunskaper i att utföra säkerhetsundersökningar med avancerad sökning i Microsoft 365 Defender. 

| Title | Beskrivning | Titta | Frågor | 
|--|--|--|--|
| Avsnitt 1  | I det här avsnittet får du lära dig olika metodtips för att köra avancerade sökfrågor. Bland ämnena som behandlas finns: hur du optimerar dina frågor, använder avancerad sökning för utpressningstrojaner, hanterar JSON som en dynamisk typ och arbetar med externa dataoperatorer. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.txt) |
| Avsnitt 2 | I det här avsnittet får du lära dig att undersöka och svara på misstänkta eller ovanliga inloggningsplatser och datainloggning via regler för vidarebefordran av inkorgen. Sebastien Molendijk, Senior Program Manager for Cloud Security CxE, delar med sig av hur du använder avancerad sökning för att undersöka flerstegsincidenter med Microsoft Cloud App Security data. | [YouTube](https://www.youtube.com/watch?v=QaUxdtNfbd8) (57:07) | [Textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/MCAS%20-%20The%20Hunt.txt)


## <a name="how-to-use-the-csl-file"></a>Så här använder du CSL-filen
Innan du påbörjar ett avsnitt öppnar du motsvarande [textfil](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Webcasts) på GitHub kopierar innehållet till den avancerade frågeredigeraren för sökning. När du tittar på ett avsnitt kan du använda det kopierade innehållet för att följa talaren och köra frågor. 

Följande utdrag från en textfil som innehåller frågorna visar en omfattande uppsättning vägledning markerad som kommentarer med `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

Samma textfil innehåller frågor före och efter kommentarerna som visas nedan. Om du vill köra en specifik [fråga med flera frågor i redigeraren](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)flyttar du markören till den frågan och väljer Kör **fråga**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

CloudAppEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig språket för avancerad fråga om sökning](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jaga över olika enheter, e-postmeddelanden, appar och identiteter](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
