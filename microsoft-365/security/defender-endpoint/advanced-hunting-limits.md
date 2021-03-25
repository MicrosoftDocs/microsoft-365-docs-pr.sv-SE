---
title: Avancerade begränsningar för sökning i Microsoft Defender ATP
description: Förstå olika tjänstbegränsningar som ser till att din avancerade service för sökning är dynamisk
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075985"
---
# <a name="advanced-hunting-service-limits"></a>Avancerade servicebegränsningar för söktjänster

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

För att tjänsten ska kunna köras snabbt och snabbt, anger avancerad sökning olika begränsningar för frågor som körs manuellt och enligt [anpassade identifieringsregler.](custom-detection-rules.md) Se följande tabell för att förstå de här begränsningarna.

| Gräns | Storlek | Uppdatera cykler | Beskrivning |
|--|--|--|--|
| Dataområde | 30 dagar | Varje fråga | Varje fråga kan slå upp data från de senaste 30 dagarna. |
| Resultatuppsättning | 10 000 rader | Varje fråga | Varje fråga kan returnera upp till 10 000 poster. |
| Timeout | 10 minuter | Varje fråga | Varje fråga kan köras i upp till 10 minuter. Om det inte är klart inom 10 minuter visar tjänsten ett fel.
| CPU-resurser | Baserat på klientorganisationens storlek | - I timmen och sedan var 15:e minut<br>- Dagligen vid 12 midnatt | Tjänsten tillämpar den dagliga och 15-minutersgränsen separat. För varje gräns visas ett [fel i portalen](advanced-hunting-errors.md) när en fråga körs och klientorganisationen har förbrukat över 10 % av de tilldelade resurserna. Frågor blockeras om klientorganisationen har nått 100 % till efter nästa dagliga eller 15-minuterscykel. |

>[!NOTE] 
>En separat uppsättning begränsningar gäller för avancerade sökningsfrågor som utförs via API:t. [Läs mer om avancerade API:er för sökning](run-advanced-query-api.md)

Kunder som kör flera frågor regelbundet [](advanced-hunting-best-practices.md) bör spåra förbrukning och använda optimeringstips för att minimera avbrottet, till följd av att de överskrider dessa gränser.

## <a name="related-topics"></a>Relaterade ämnen

- [Avancerade metodtips för sökning](advanced-hunting-best-practices.md)
- [Hantera avancerade sökfel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Anpassade identifieringsregler](custom-detection-rules.md)
