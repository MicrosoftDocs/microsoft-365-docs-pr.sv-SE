---
title: Översikt över anpassade identifieringar i Microsoft Threat Protection
description: Förstå hur du kan använda avancerad jakt för att skapa anpassade identifieringar och generera aviseringar
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498357"
---
# <a name="custom-detections-overview"></a>Översikt över anpassade identifieringar

**Gäller:**
- Microsoft Hotskydd

Med anpassade identifieringar kan du proaktivt övervaka och svara på olika händelser och systemtillstånd, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter. Detta möjliggörs genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar samt svarsåtgärder.

Anpassade identifieringar fungerar med [avancerad jakt](advanced-hunting-overview.md), som ger ett kraftfullt, flexibelt frågespråk som täcker en bred uppsättning händelse- och systeminformation från nätverket. Du kan ställa in dem så att de körs med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

Anpassade identifieringar ger:
- Varningar för regelbaserade identifieringar som skapats från avancerade jaktfrågor
- Automatiska svarsåtgärder

## <a name="related-topic"></a>Relaterat ämne
- [Skapa och hantera anpassade identifieringsregler](custom-detection-rules.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)