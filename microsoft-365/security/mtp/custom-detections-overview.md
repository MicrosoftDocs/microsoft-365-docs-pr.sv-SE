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
ms.openlocfilehash: a9ba61650b69e3c42506735c90ae05b917a53209
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931750"
---
# <a name="custom-detections-overview"></a>Översikt över anpassade identifieringar

**Gäller:**
- Microsofts hotskydd

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Med anpassade identifieringar kan du proaktivt övervaka och svara på olika händelser och systemtillstånd, inklusive misstänkt intrångsaktivitet och felkonfigurerade slutpunkter. Detta möjliggörs genom anpassningsbara identifieringsregler som automatiskt utlöser aviseringar samt svarsåtgärder.

Anpassade identifieringar fungerar med [avancerad jakt](advanced-hunting-overview.md), som ger ett kraftfullt, flexibelt frågespråk som täcker en bred uppsättning händelse- och systeminformation från nätverket. Du kan ställa in dem så att de körs med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.

Anpassade identifieringar ger:
- Varningar för regelbaserade identifieringar som skapats från avancerade jaktfrågor
- Automatiska svarsåtgärder

## <a name="related-topic"></a>Relaterat ämne
- [Skapa och hantera anpassade identifieringsregler](custom-detection-rules.md)
- [Avancerad jaktöversikt](advanced-hunting-overview.md)