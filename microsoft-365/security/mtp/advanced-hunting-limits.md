---
title: Avancerade jakt begränsningar i Microsoft Threat Protection
description: Förstå olika tjänst begränsningar som håller den avancerade jakt tjänsten tillgänglig
keywords: Avancerad jakt, Hot jakt, cyberterrorism Threat stöldskydd, Microsoft Threat Protection, Microsoft 365, MTP, m365, Sök, fråga, telemetri, schema, kusto, processor gräns, sessionsgräns, resurser, högsta resultat
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
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199883"
---
# <a name="advanced-hunting-service-limits"></a>Begränsningar för avancerad jakt tjänst

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd

För att hålla tjänsten igång och svarar kan avancerade jakt uppsättningar olika gränser för frågor som körs manuellt och enligt [anpassade identifierings regler](custom-detection-rules.md). Se tabellen nedan för att förstå dessa gränser.

| Sten | Storlek | Uppdaterings cykel | Beskrivning |
|--|--|--|--|
| Data område | 30 dagar | Alla frågor | Varje fråga kan slå upp data från de senaste 30 dagarna. |
| Resultat uppsättning | 10 000 rader | Alla frågor | Varje fråga kan returnera upp till 10 000 poster. |
| Kort | 10 minuter | Alla frågor | Alla frågor kan köras i upp till 10 minuter. Om den inte slutförs inom 10 minuter visas ett fel.
| CPU-resurser | Baserat på innehavarens storlek | -På timme och sedan var 15: e minut<br>-Per dag 12 midnatt | Tjänsten tillämpar varje dag och 15-minuters gräns separat. För varje gräns [visas ett fel](advanced-hunting-errors.md) när en fråga körs och innehavaren har konsumerat över 10% av tilldelade resurser. Frågor blockeras om klient organisationen har nått 100% fram till efter nästa dagliga eller 15 minuter. |

>[!NOTE] 
>En separat uppsättning begränsningar gäller för avancerade frågor som genomförs via API. [Läsa om avancerade API: er för jakt](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

Kunder som ofta kör flera frågor bör spåra förbrukningen och [tillämpa optimerings metod tips](advanced-hunting-best-practices.md) för att minimera störningar som orsakas av de här gränserna.

## <a name="related-topics"></a>Relaterade ämnen

- [Avancerade råd om att få råd](advanced-hunting-best-practices.md)
- [Hantera avancerade jakt fel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)
