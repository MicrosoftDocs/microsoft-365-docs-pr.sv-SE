---
title: Prioritera incidenter i Microsoft Threat Protection
description: Läs om hur du prioriterar incidenter från incidentkön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter
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
ms.openlocfilehash: ef10eede38128bbf9b23537d860113b71f603089
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810762"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Prioritera incidenter i Microsoft Threat Protection

**Gäller:**
- Skydd av Hot mot Microsoft



Microsoft Threat Protection tillämpar korrelationsanalys och sammanställer alla relaterade aviseringar och undersökningar från olika produkter till en incident. Microsoft Threat Protection utlöser också unika varningar om aktiviteter som endast kan identifieras som skadliga med tanke på den synlighet som Microsoft Threat Protection har över hela egendomen och produktsviten. Genom att göra så berättar Microsoft Threat Protection den bredare attackhistorien, vilket gör det möjligt för en säkerhetsverksamhetanalytiker att förstå och hantera komplexa hot i hela organisationen.


**I kön Tillbud** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor. Det hjälper dig att sortera igenom incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.


![Bild av incidenter kö](../../media/incidents-queue.png) 

Som standard visar kön i Microsoft 365 security center incidenter som setts under de senaste 30 dagarna, med den senaste incidenten som visas högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.

Incidentkön exponerar anpassningsbara kolumner som ger dig insyn i olika egenskaper hos incidenten eller de innehållna entiteterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera. 

Incidentkön exponerar också flera filtreringsalternativ, som när den används, gör att du kan välja att utföra ett brett svep av alla befintliga incidenter i din miljö, eller besluta att fokusera på ett visst scenario eller hot. Om du använder filter i incidentkön kan du avgöra vilken incident som kräver omedelbar uppmärksamhet. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="status"></a>Status
Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.

### <a name="severity"></a>Svårighetsgrad
Allvarligheten av en incident är ett tecken på vilken inverkan det kan ha i dina tillgångar. Ju högre svårighetsgrad desto större inverkan och vanligtvis kräver den mest omedelbara uppmärksamheten. 

### <a name="assigned-to-owner"></a>Tilldelad (ägare)
Du kan välja att filtrera listan genom att välja tilldelat till alla eller de som har tilldelats dig.

### <a name="multiple-alerts"></a>Flera aviseringar 
Filtrera om du bara vill se incidenter som innehåller mer än en avisering. Detta kan vara en indikation för en attack som är mer komplex eller utvecklats i dödskedjan. 


### <a name="multiple-service-sources"></a>Flera tjänstkällor 
Filtrera om du bara vill se incidenter som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Servicekällor
Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att bara se incidenter som har mappats till flera kategorier av dödskedjan och kan orsaka mer skada. 

### <a name="categories"></a>Kategorier
Välj specifika kategorier att fokusera på ett specifikt steg i dödskedjan

### <a name="data-sensitivity"></a>Datakänslighet
Vissa attacker fokuserar på att rikta för att exfiltrera känsliga eller värdefulla data. Genom att använda ett filter för att se om känsliga data är inblandade i incidenten kan du snabbt avgöra om känslig information eventuellt har komprometterats och prioritera att hantera dessa incidenter.

>[!NOTE]
>Gäller endast om MicrosoftS informationsskydd är aktiverat.


## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken händelse som kräver högsta prioritet kan du fortsätta att göra ytterligare utredningsarbete med en incident.
- [Utreda incidenter](investigate-incidents.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över incidenter](incidents-overview.md)
- [Utreda incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
