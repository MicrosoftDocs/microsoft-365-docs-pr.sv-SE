---
title: Prioritera incidenter i Microsoft 365 Defender
description: Lär dig hur du filtrerar incidenter från incident kön i Microsoft 365 Defender
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409261"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioritera incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Microsoft 365 Defender använder korrelations analys och aggregerar alla relaterade varningar och undersökningar från olika produkter i en olycka. Microsoft 365 Defender utlöser också unika aviseringar för aktiviteter som endast kan identifieras som skadlig från slut punkt till slut punkt som Microsoft 365 Defender har på hela egendomen och produkt serien. Den här vyn ger säkerhets åtgärder som analyserar den större angrepps berättelsen som hjälper dem att förstå och hantera komplexa hot i organisationen.


**Incident kön** visar en samling händelser som har flaggats från mellan enheter, användare och post lådor. Det hjälper dig att sortera genom tillbud för att prioritera och skapa ett välinformerat Cybersecurity.


![Bild av kön för incidenter](../../media/incidents-queue.png) 

Som standard visar kön i Microsoft 365 säkerhets Center de händelser som visas under de senaste 30 dagarna. Den senaste incidenten är högst upp i listan så att du kan se den först.

Incident kön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper för incidenten eller de inneslutna entiteterna. Det hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter att hantera.

Om du vill ha mer insyn är det lätt att ge automatisk fel sökning namn som baseras på notifieringsregler, till exempel hur många slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier. Då kan du snabbt förstå omfattningen av incidenten.

Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*

> [!NOTE]
> Händelser som fanns före installationen av automatisk incident namn har inte ändrats.

I tillbuds kön visas också flera filtrerings alternativ, som används för att göra en bred borttagning av alla befintliga incidenter i miljön eller bestämma dig för ett visst scenario eller hot. Om du använder filter i kön för incidenter kan du avgöra vilken händelse som kräver omedelbar åtgärd. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="assigned-to"></a>Tilldelad till
Du kan välja att visa meddelanden som har tilldelats dig eller de som hanteras via Automation.

### <a name="categories"></a>Klasser
Välj kategorier för att fokusera på specifika taktiker, tekniker eller angrepps komponenter som visas. 

### <a name="classification"></a>Nomenklatur
Filtrera incidenter baserat på ange klassificeringar för relaterade aviseringar. Värdena inkluderar True Alerts, false Alerts eller inte.

### <a name="data-sensitivity"></a>Data känslighet
Vissa attacker fokuserar på att rikta mot exfiltrate känsliga eller värdefulla data. Genom att använda ett filter för att se om känslig information är involverad i en olycka kan du snabbt avgöra om den känsliga informationen är potentiellt utsatt för att hantera dessa tillbud.

>[!NOTE]
>Gäller endast om Microsoft Information Protection är aktiverat.

### <a name="device-group"></a>Enhets grupp
Filtrera efter definierade enhets grupper.

### <a name="investigation-state"></a>Gransknings status
Filtrera incidenter genom att automatisera den automatiska undersökningen. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att bara se händelser som har mappats till flera kategorier och det kan leda till större skador. 

### <a name="multiple-service-sources"></a>Flera tjänst källor 
Filtrera för att se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slut punkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).

### <a name="os-platform"></a>OS-plattform
Begränsa vyn för incident kön efter operativ system.

### <a name="service-sources"></a>Tjänste källor
Genom att välja en specifik källa kan du fokusera på händelser som innehåller minst en avisering från den valda källan. 

### <a name="severity"></a>Allvarlighets grad
Allvarlighets graden för en olycka är att det påverkar vilken inverkan den kan ha på dina till gångar. Ju högre allvarlighets grad desto större betydelse och det är vanligt vis mycket direkt uppmärksamhet. 

### <a name="status"></a>Status
Du kan välja att begränsa listan med incidenter baserat på deras status för att se vilka som är aktiva eller stängda.




## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken händelse som kräver den högsta prioriteten kan du fortsätta att göra ytterligare utredningar på en olycka.
- [Undersöka incidenter](investigate-incidents.md)


## <a name="see-also"></a>Se även
- [Incident översikt](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
