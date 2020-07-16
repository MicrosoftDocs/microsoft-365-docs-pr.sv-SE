---
title: Prioritera incidenter i Microsofts hotskydd
description: Lär dig hur du prioriterar incidenter från incidentkön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, brevlåda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148142"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Prioritera incidenter i Microsofts hotskydd

**Gäller:**
- Microsoft Hotskydd



Microsoft Threat Protection tillämpar korrelationsanalys och sammanställer alla relaterade aviseringar och undersökningar från olika produkter till en incident. Microsoft Threat Protection utlöser också unika aviseringar om aktiviteter som endast kan identifieras som skadliga med tanke på den heltäckande synlighet som Microsoft Threat Protection har över hela dödsboet och produktpaketet. På så sätt berättar Microsoft Threat Protection den bredare attackhistorien, vilket gör det möjligt för en säkerhetsoperationsanalytiker att förstå och hantera komplexa hot i hela organisationen.


**I kön Incidenter** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor. Det hjälper dig att sortera igenom incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhetssvar.


![Bild av incidentkö](../../media/incidents-queue.png) 

Som standard visar kön i Säkerhetscentret Microsoft 365 incidenter som har setts under de senaste 30 dagarna, med den senaste incidenten som visas högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.

Incidentkön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper hos incidenten eller de inneslutna entiteterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.

För ytterligare synlighet via ett ögonkast genererar automatisk incidentnamn, som för närvarande finns i offentlig förhandsversion, incidentnamn baserat på varningsattribut som antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå omfattningen av incidenten.

Till exempel: *Flerstegsincident på flera slutpunkter som rapporterats av flera källor.*

> [!NOTE]
> Incidenter som fanns före utrullningen av automatisk incidentnamn kommer inte att få sitt namn ändrat.

Läs mer om [hur du aktiverar förhandsgranskningsfunktioner](preview.md#turn-on-preview-features).

Incidentkön visar också flera filtreringsalternativ, som när du används, gör att du kan välja att utföra ett brett svep av alla befintliga incidenter i din miljö, eller besluta att fokusera på ett visst scenario eller hot. Om du använder filter i incidentkön kan du avgöra vilken incident som kräver omedelbar uppmärksamhet. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="status"></a>Status
Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.

### <a name="severity"></a>Svårighetsgrad
Hur allvarlig en incident är är ett tecken på vilken inverkan den kan ha i dina tillgångar. Ju högre svårighetsgrad desto större inverkan och vanligtvis kräver den mest omedelbara uppmärksamhet. 

### <a name="assigned-to-owner"></a>Tilldelad till (ägare)
Du kan välja att filtrera listan genom att välja tilldelad till någon eller de som har tilldelats dig.

### <a name="multiple-alerts"></a>Flera aviseringar 
Filtrera om du bara vill visa incidenter som innehåller mer än en avisering. Detta kan vara en indikation på en attack som är mer komplex eller utvecklats i dödskedjan. 


### <a name="multiple-service-sources"></a>Flera tjänstkällor 
Filter för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Tjänstkällor
Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att bara se incidenter som har mappats till flera kategorier av dödskedjan och som potentiellt kan orsaka mer skada. 

### <a name="categories"></a>Kategorier
Välj specifika kategorier för att fokusera på ett visst steg i dödskedjan

### <a name="data-sensitivity"></a>Datakänslighet
Vissa attacker fokuserar på inriktning för att exfiltrate känsliga eller värdefulla data. Genom att använda ett filter för att se om känsliga data är inblandade i incidenten kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioritera att åtgärda dessa incidenter.

>[!NOTE]
>Gäller endast om Microsofts informationsskydd är aktiverat.


## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken incident som kräver högsta prioritet kan du fortsätta att utföra ytterligare utredningsarbete om en incident.
- [Undersöka incidenter](investigate-incidents.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
