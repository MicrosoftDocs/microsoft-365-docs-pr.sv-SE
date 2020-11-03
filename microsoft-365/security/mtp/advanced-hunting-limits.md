---
title: Avancerade jakt kvoter och användnings parametrar i Microsoft 365 Defender
description: Förstå olika kvoter och användnings parametrar (tjänst begränsningar) som håller den avancerade jakt tjänsten tillgänglig
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, kusto, processor gräns, maxgräns, resurser, högsta resultat, kvot, parametrar, tilldelning
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847374"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Avancerade jakt kvoter och användnings parametrar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

För att hålla tjänsten igång och svarar kan de avancerade jaktarna ange olika kvoter och användnings parametrar (kallas även "tjänst gränser"). Dessa kvoter och parametrar gäller för frågor som körs manuellt och efter [anpassade identifierings regler](custom-detection-rules.md). Kunder som ofta kör flera frågor bör spåra förbrukning och [tillämpa optimerings metod tips](advanced-hunting-best-practices.md) för att minimera störningar.

Se tabellen nedan för att förstå befintliga kvoter och användnings parametrar.

| Kvot eller parameter | Storlek | Uppdaterings cykel | Beskrivning |
|--|--|--|--|
| Data område | 30 dagar | Alla frågor | Varje fråga kan slå upp data från de senaste 30 dagarna. |
| Resultat uppsättning | 10 000 rader | Alla frågor | Varje fråga kan returnera upp till 10 000 poster. |
| Kort | 10 minuter | Alla frågor | Alla frågor kan köras i upp till 10 minuter. Om den inte slutförs inom 10 minuter visas ett fel.
| CPU-resurser | Baserat på innehavarens storlek | -På timme och sedan var 15: e minut<br>-Per dag 12 midnatt | Tjänsten tillämpar den dagliga och 15-minuters kvoten separat. För varje kvot [visas ett fel](advanced-hunting-errors.md) när en fråga körs och innehavaren har konsumerat över 10% av tilldelade resurser. Frågor blockeras om klient organisationen har nått 100% fram till efter nästa dagliga eller 15 minuter. |

>[!NOTE] 
>En separat uppsättning kvoter och parametrar gäller för avancerade frågor som utförs via API. [Läsa om avancerade API: er för jakt](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Relaterade ämnen

- [Avancerade råd om att få råd](advanced-hunting-best-practices.md)
- [Hantera avancerade jakt fel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Översikt över anpassade identifieringar](custom-detections-overview.md)