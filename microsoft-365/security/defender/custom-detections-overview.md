---
title: Översikt över anpassade identifieringar i Microsoft 365 Defender
description: Förstå hur du kan använda avancerad sökning för att skapa anpassade identifieringar och generera aviseringar
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, microsoft 365, Microsoft Threat Protection
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4a4b601b5f8b9a21d7e7260fcadf9fecd0e37c5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068970"
---
# <a name="custom-detections-overview"></a>Översikt över anpassade identifieringar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Med anpassade identifieringar kan du proaktivt övervaka efter och svara på olika händelser och systemhändelser, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter. Det här görs möjligt genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar och svarsåtgärder.

Anpassade identifieringar fungerar med [avancerad](advanced-hunting-overview.md)sökning , som ger ett kraftfullt, flexibelt frågespråk som omfattar en omfattande uppsättning händelse- och systeminformation från nätverket. Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

Anpassade identifieringar ger:
- Aviseringar för regelbaserade identifieringar som skapats från avancerade sökfrågor
- Automatiska svarsåtgärder

## <a name="see-also"></a>Se även
- [Skapa och hantera anpassade identifieringsregler](custom-detection-rules.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint](advanced-hunting-migrate-from-mde.md)
