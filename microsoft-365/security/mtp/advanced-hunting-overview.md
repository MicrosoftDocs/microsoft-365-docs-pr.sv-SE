---
title: Översikt över avancerad jakt i Microsoft Threat Protection
description: Lär dig mer om avancerade jaktfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: dc91b97f48d6a5ca76c405e4c1006dceb9dc0b34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929034"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proaktivt jakt efter hot med avancerad jakt i Microsoft Threat Protection

**Gäller:**
- Microsofts hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Avancerad jakt är ett frågebaserat hotjaktverktyg som låter dig utforska upp till 30 dagars rådata. Du kan proaktivt granska händelser i nätverket för att hitta intressanta indikatorer och entiteter. Den flexibla tillgången till data underlättar obegränsad jakt på både kända och potentiella hot.

Du kan använda samma frågor om hotjakt för att skapa anpassade identifieringsregler. Dessa regler körs automatiskt för att söka efter och svara på olika händelser och systemtillstånd, inklusive misstänkt överträdelseaktivitet och felkonfigurerade datorer.

I säkerhetscentret Microsoft 365 stöder avancerad jakt frågor som undersöker data från olika arbetsytor, inklusive data om enheter, e-postmeddelanden, appar och identiteter från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure Atp. Om du vill använda avancerad jakt [aktiverar du Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Kom igång med avancerad jakt

Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad jakt.

| Lärandemål | Beskrivning | Resurs |
|--|--|--|
| **Få en känsla för språket** | Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/), som stöder samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultaten** | Lär dig mer om diagram och olika sätt att visa eller exportera dina resultat. Utforska hur du snabbt kan justera frågor och öka detaljnivån för att få rikare information. | [Arbeta med frågeresultat](advanced-hunting-query-results.md) |
| **Förstå schemat** | Få en bra förståelse på hög nivå av tabellerna i schemat och deras kolumner. Detta hjälper dig att avgöra var du ska leta efter data och hur du skapar dina frågor. | [Schemareferens](advanced-hunting-schema-tables.md) |
| **Utnyttja fördefinierade frågor** | Utforska samlingar av fördefinierade frågor som täcker olika hotjaktsscenarier. | [Använda delade frågor](advanced-hunting-shared-queries.md) |
| **Optimera frågor** | Förstå hur du skapar effektiva frågor och frågor som kombinerar data från e-postmeddelanden och enheter. | - [Metodtips för frågor](advanced-hunting-shared-queries.md) <br>- [Jaga mellan enheter och e-postmeddelanden](advanced-hunting-best-practices.md) |
| **Skapa anpassade identifieringsregler** | Förstå hur du kan använda avancerade jaktfrågor för att utlösa aviseringar och tillämpa svarsåtgärder automatiskt. | - [Översikt över anpassade identifieringar](custom-detections-overview.md)<br>- [Regler för anpassad identifiering](custom-detection-rules.md) |

## <a name="get-help-as-you-write-queries"></a>Få hjälp när du skriver frågor
Dra nytta av följande funktioner för att skriva frågor snabbare:
- **Autosuggest** - när du skriver frågor, avancerad jakt ger förslag från IntelliSense. 
- **Schemareferens** – en schemareferens som innehåller listan över tabeller och deras kolumner finns bredvid arbetsområdet. Om du vill ha mer information håller du muspekaren över ett objekt. Dubbelklicka på ett objekt om du vill infoga det i frågeredigeraren.


## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Tillämpa metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)