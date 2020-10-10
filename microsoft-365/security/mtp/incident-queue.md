---
title: Prioritera incidenter i Microsoft Threat Protection
description: Lär dig hur du prioriterar incidenter från incident kön i Microsoft Threat Protection
keywords: incident, kö, översikt, enheter, identiteter, användare, post låda, e-post, incidenter
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 79cdf68bb5de95fd910e5ba0b616b18e6a272b68
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412208"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Prioritera incidenter i Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



Microsoft Threat Protection använder korrelations analys och aggregerar alla relaterade varningar och undersökningar från olika produkter i en olycka. Microsoft Threat Protection utlöser också unika aviseringar för aktiviteter som endast kan identifieras som skadlig från slut punkt till slut punkt som Microsoft Threat Protection har på hela egendomen och serien med produkter. Genom att göra så får du ett hot-skydd som gör den bredare angrepps berättelsen så att en säkerhets åtgärd kan analyseras för att förstå och hantera komplexa hot i organisationen.


**Incident kön** visar en samling händelser som har flaggats från mellan enheter, användare och post lådor. Det hjälper dig att sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity.


![Bild av kön för incidenter](../../media/incidents-queue.png) 

Som standard visar kön i Microsoft 365 säkerhets Center de händelser som visas under de senaste 30 dagarna, med den senaste incident som visas högst upp i listan så att du kan se de senaste incidenterna först.

Incident kön visar anpassningsbara kolumner som gör att du kan visa olika egenskaper för incidenten eller de inneslutna enheterna, vilket hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.

Om du vill ha mer insyn är det lätt att namnge fel söknings namn baserat på notifieringsregler, till exempel hur många slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier. Då kan du snabbt förstå omfattningen av incidenten.

Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*

> [!NOTE]
> Händelser som fanns före installationen av automatisk incident namn har inte ändrats.

Incident kön visar också flera filtrerings alternativ, som när den används, gör det möjligt för dig att välja att genomföra en bred borttagning av alla befintliga incidenter i miljön eller bestämma dig för ett visst scenario eller hot. Om du använder filter i kön för incidenter kan du avgöra vilken händelse som kräver omedelbar åtgärd. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="status"></a>Status
Du kan välja att begränsa listan med incidenter baserat på deras status för att se vilka som är aktiva eller stängda.

### <a name="severity"></a>Allvarlighets grad
Allvarlighets graden för en olycka är att det påverkar vilken inverkan den kan ha på dina till gångar. Ju högre allvarlighets grad desto större effekt och kräver vanligt vis omedelbar uppmärksamhet. 

### <a name="assigned-to-owner"></a>Tilldelad (ägare)
Du kan välja att filtrera listan genom att välja tilldelad till vem som helst eller som är tilldelad till dig.

### <a name="multiple-alerts"></a>Flera aviseringar 
Filtrera för att se endast händelser som innehåller fler än en avisering. Detta kan vara en indikation på ett angrepp som är mer komplicerat eller som behandlas i Kill-kedjan. 


### <a name="multiple-service-sources"></a>Flera tjänst källor 
Filtrera för att se endast händelser som innehåller aviseringar från olika källor (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)
### <a name="service-sources"></a>Tjänste källor
Genom att välja en specifik källa kan du fokusera på händelser som innehåller minst en avisering från den valda källan. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att bara se händelser som har mappats till flera kategorier av Kill-kedjan och kan orsaka mer skada. 

### <a name="categories"></a>Klasser
Välja specifika kategorier för att fokusera på ett specifikt steg i Kill-kedjan

### <a name="data-sensitivity"></a>Data känslighet
Vissa attacker fokuserar på att rikta mot exfiltrate känsliga eller värdefulla data. Genom att använda ett filter för att se om känslig information är involverad i en olycka kan du snabbt avgöra om den känsliga informationen är potentiellt utsatt för att hantera dessa tillbud.

>[!NOTE]
>Gäller endast om Microsoft Information Protection är aktiverat.


## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken händelse som kräver den högsta prioriteten kan du fortsätta att göra ytterligare utredningar på en olycka.
- [Undersöka incidenter](investigate-incidents.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Incident översikt](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
