---
title: Avancerade kvoter för sökning och användningsparametrar i Microsoft 365 Defender
description: Förstå olika kvoter och användningsparametrar (servicebegränsningar) som håller den avancerade söktjänsten responsiv
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929796"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Avancerade kvoter för sökning och användningsparametrar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

För att hålla tjänstens prestanda och responsiva, ställer avancerad sökning in olika kvoter och användningsparametrar (kallas även "servicebegränsningar"). De här kvoter och parametrar som gäller för frågor körs manuellt och med [anpassade identifieringsregler.](custom-detection-rules.md) Kunder som kör flera frågor regelbundet bör spåra förbrukning och tillämpa [metodtips för optimering](advanced-hunting-best-practices.md) för att minimera störningar.

I följande tabell finns information om befintliga kvoter och användningsparametrar.

| Kvot eller parameter | Storlek | Uppdatera cykel | Beskrivning |
|--|--|--|--|
| Dataområde | 30 dagar | Varje fråga | Varje fråga kan slå upp data från de senaste 30 dagarna. |
| Resultatuppsättning | 10 000 rader | Varje fråga | Varje fråga kan returnera upp till 10 000 poster. |
| Timeout | 10 minuter | Varje fråga | Varje fråga kan köras i upp till 10 minuter. Om den inte slutförs inom 10 minuter visas ett fel i tjänsten.
| CPU-resurser | Baserat på klientorganisationens storlek | - I timmen och sedan var 15:e minut<br>- Dagligen vid 12 midnatt | Tjänsten tillämpar den dagliga kvoten och 15-minuterskvoten separat. För varje kvot visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av tilldelade resurser. Frågor blockeras om klientorganisationen har nått 100 % tills nästa dag eller 15-minuterscykel. |

>[!NOTE] 
>En separat uppsättning kvoter och parametrar gäller för avancerade sökningsfrågor som utförs via API:t. [Läs mer om avancerade API:er för sökning](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Relaterade ämnen

- [Avancerade söktips](advanced-hunting-best-practices.md)
- [Hantera avancerade sökfel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)