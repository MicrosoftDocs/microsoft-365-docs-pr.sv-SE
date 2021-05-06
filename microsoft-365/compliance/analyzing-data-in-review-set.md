---
title: Analysera data i en granskningsuppsättning i Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Läs mer om tillgängliga verktyg för att ordna dokumentuppsättningar när du analyserar ett Advanced eDiscovery ärende.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161716"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analysera data i en granskningsuppsättning i Advanced eDiscovery

När antalet insamlade dokument är stort kan det vara svårt att granska alla. Advanced eDiscovery finns ett antal verktyg för att analysera dokumenten för att minska mängden dokument som ska granskas utan förlust av information, och för att ordna dokumenten sammanhängande. Mer information om de här funktionerna finns i:

- [Identifiering av nästan dubbletter](near-duplicate-detection-in-advanced-ediscovery.md)

- [E-posttrådar](email-threading-in-advanced-ediscovery.md)

- [Teman](themes-in-advanced-ediscovery.md)

Så här analyserar du data i en granskningsuppsättning:

1. Konfigurera analysinställningar för ditt ärende. Mer information finns i Konfigurera [sök- och analysinställningar.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)

2. Öppna den granskningsuppsättning du vill analysera.

3. Klicka **på Hantera granskningsuppsättning**.

4. Klicka **på Kör analys för granskningsuppsättningen**.

Du kan kontrollera förloppet för analysen på **fliken** Jobb för ärendet.

 När analysen är klar kan du visa analysrapporten, köra frågor i din granskningsuppsättning på resultatet av analysen (se Fråga i din granskningsuppsättning [)](review-set-search.md)och se relaterade dokument i ett visst dokument (se Granska data i [granskningsuppsättning](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Analysrapport

Så här visar du en analysrapport för en granskningsuppsättning:

1. Öppna granskningsuppsättningen.

2. Klicka **på Hantera granskningsuppsättning**.

3. Klicka **på Visa rapport**.

Rapporten innehåller sju komponenter från analysen:

- **Målpopulation:** Antalet e-postmeddelanden, bifogade filer och lösa dokument som finns i granskningsuppsättningen.

- **Dokument (exklusive bifogade filer):** Antalet lösa dokument som är pivot, unika nästan dubbletter av en pivot eller en exakt dubblett av ett annat dokument.

- **E-postmeddelanden:** Antalet e-postmeddelanden som är inklusive kopior, inklusive minustecken eller inget av ovanstående.

- **Bifogade filer:** Antalet e-postbilagor som är unika eller dubbletter av en annan e-postbilaga i granskningsuppsättningen.

- **Antal filer efter typ:** Antalet filer som identifieras med filnamnstillägget.

- **Dokument efter källa:** En sammanfattning av innehållet efter dess ursprungliga datakälla.

- **Dokument aggregerade efter process:** En sammanfattning av innehåll efter processerna för granskningsuppsättning. 
