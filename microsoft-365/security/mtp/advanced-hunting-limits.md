---
title: Avancerade kvoter för sökning och användningsparametrar i Microsoft 365 Defender
description: Förstå olika kvoter och användningsparametrar (tjänstbegränsningar) som ser till att tjänsten för avancerad sökning är dynamisk
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
ms.openlocfilehash: 862d295739f952a6a5db06f5cfdfbc5aa481de9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909028"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Avancerade kvoter för sökning och användningsparametrar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

För att hålla tjänstens prestanda och responsiva, anger avancerad sökning olika kvoter och användningsparametrar (kallas även "tjänstbegränsningar"). De här kvoter och parametrar som gäller för frågor körs manuellt och av [anpassade identifieringsregler.](custom-detection-rules.md) Kunder som kör flera frågor regelbundet bör spåra förbrukning och [använda optimeringstips för](advanced-hunting-best-practices.md) att minimera störningar.

Se följande tabell för att förstå befintliga kvoter och användningsparametrar.

| Kvot eller parameter | Storlek | Uppdatera cykler | Beskrivning |
|--|--|--|--|
| Dataområde | 30 dagar | Varje fråga | Varje fråga kan slå upp data från de senaste 30 dagarna. |
| Resultatuppsättning | 10 000 rader | Varje fråga | Varje fråga kan returnera upp till 10 000 poster. |
| Timeout | 10 minuter | Varje fråga | Varje fråga kan köras i upp till 10 minuter. Om det inte är klart inom 10 minuter visar tjänsten ett fel.
| CPU-resurser | Baserat på klientorganisationens storlek | - I timmen och sedan var 15:e minut<br>- Dagligen vid 12 midnatt | Tjänsten tillämpar den dagliga kvoten och 15-minuterskvoten separat. För varje kvot visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av de tilldelade resurserna. Frågor blockeras om klientorganisationen har nått 100 % till efter nästa dagliga eller 15-minuterscykel. |

>[!NOTE] 
>En separat uppsättning kvoter och parametrar gäller för avancerade sökningsfrågor som utförs via API:t. [Läs mer om avancerade API:er för sökning](./api-advanced-hunting.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Avancerade metodtips för sökning](advanced-hunting-best-practices.md)
- [Hantera avancerade sökfel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)