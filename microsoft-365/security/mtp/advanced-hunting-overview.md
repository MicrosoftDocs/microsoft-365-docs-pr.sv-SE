---
title: Översikt - Avancerad jakt
description: Lär dig mer om avancerade jaktfrågor i Microsoft 365 och hur du använder dem för att proaktivt hitta hot och svagheter i nätverket
keywords: avancerad jakt, hotjakt, cyberhotjakt, Microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, anpassade upptäckter, schema, kusto, microsoft 365, Microsoft Threat Protection
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48850c76176d79e4f90581bfbab804f4649998cc
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049638"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Proaktivt jakt efter hot med avancerad jakt i Microsoft Threat Protection

**Gäller:**
- Microsoft Hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Avancerad jakt är ett frågebaserat hotjaktsverktyg som låter dig utforska upp till 30 dagars rådata. Du kan proaktivt granska händelser i nätverket för att hitta intressanta indikatorer och entiteter. Den flexibla tillgången till data underlättar obegränsad jakt på både kända och potentiella hot.

Du kan använda samma frågor om hot-jakt för att skapa anpassade identifieringsregler. Dessa regler körs automatiskt för att söka efter och svara på olika händelser och systemtillstånd, inklusive misstänkt överträdelseaktivitet och felkonfigurerade datorer.

I säkerhetscentret Microsoft 365 stöder avancerad jakt frågor som undersöker data från olika arbetsytor, inklusive data om enheter, e-postmeddelanden, appar och identiteter från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP. Om du vill använda avancerad jakt [aktiverar du Microsoft Threat Protection](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Kom igång med avancerad jakt

Vi rekommenderar att du går igenom flera steg för att snabbt komma igång med avancerad jakt.

| Lärandemål | Beskrivning | Resurs |
|--|--|--|
| **Få en känsla för språket** | Avancerad jakt baseras på [Kusto-frågespråket](https://docs.microsoft.com/azure/kusto/query/), som stöder samma syntax och operatorer. Börja lära dig frågespråket genom att köra den första frågan. | [Översikt över frågespråk](advanced-hunting-query-language.md) |
| **Lär dig hur du använder frågeresultaten** | Lär dig mer om diagram och olika sätt att visa eller exportera dina resultat. Utforska hur du snabbt kan justera frågor och öka detaljnivån för att få rikare information. | [Arbeta med frågeresultat](advanced-hunting-query-results.md) |
| **Förstå schemat** | Få en bra förståelse på hög nivå av tabellerna i schemat och deras kolumner. Detta hjälper dig att avgöra var du ska leta efter data och hur du skapar dina frågor. | [Schemareferens](advanced-hunting-schema-tables.md) |
| **Utnyttja fördefinierade frågor** | Utforska samlingar av fördefinierade frågor som täcker olika hotjaktsscenarier. | - [Använda delade frågor](advanced-hunting-shared-queries.md)<br>- [Gå och jaga](advanced-hunting-go-hunt.md) |
| **Optimera frågor** | Förstå hur du skapar effektiva frågor och frågor som kombinerar data från e-postmeddelanden och enheter. | - [Metodtips för frågor](advanced-hunting-shared-queries.md) <br>- [Jaga mellan enheter och e-postmeddelanden](advanced-hunting-best-practices.md) |
| **Skapa anpassade identifieringsregler** | Förstå hur du kan använda avancerade jaktfrågor för att utlösa aviseringar och tillämpa svarsåtgärder automatiskt. | - [Översikt över anpassade identifieringar](custom-detections-overview.md)<br>- [Regler för anpassad identifiering](custom-detection-rules.md) |

## <a name="get-access"></a>Få åtkomst
Om du vill använda avancerade jaktfunktioner eller andra [Microsoft Threat Protection-funktioner](microsoft-threat-protection.md) måste du tilldelas en lämplig roll i Azure AD. Observera att din åtkomst till slutpunktsdata påverkas av rollbaserade inställningar för åtkomstkontroll i Microsoft Defender ATP. [Läs om hur du hanterar åtkomst till Microsoft Threat Protection](mtp-permissions.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Jakten på hot på olika enheter och e-postmeddelanden](advanced-hunting-query-emails-devices.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
