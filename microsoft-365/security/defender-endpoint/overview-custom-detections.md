---
title: Översikt över anpassade identifieringar i Microsoft Defender ATP
ms.reviewer: ''
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: anpassade identifieringar, aviseringar, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, intervall, mdatp, microsoft defender atp
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069049"
---
# <a name="custom-detections-overview"></a>Översikt över anpassade identifieringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Med anpassade identifieringar kan du proaktivt övervaka för och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade enheter. Du kan göra detta med anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.

Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket. Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

Anpassade identifieringar ger:
- Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor
- Automatiska svarsåtgärder som gäller för filer och enheter

## <a name="related-topics"></a>Relaterade ämnen
- [Skapa identifieringsregler](custom-detection-rules.md)
- [Visa och hantera identifieringsregler](custom-detections-manage.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
