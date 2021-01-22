---
title: Prioritera ärenden i Microsoft 365 Defender
description: Lär dig hur du filtrerar incidentköer i Microsoft 365 Defender
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929300"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioritera ärenden i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Microsoft 365 Defender tillämpar korrelationsanalyser och lägger till alla relaterade varningar och undersökningar från olika produkter i en incident. Microsoft 365 Defender utlöser även unika aviseringar för aktiviteter som bara kan identifieras som skadliga givet den synlighet från end-to-end som Microsoft 365 Defender har över hela webbplatsen och produktsviten. Den här vyn ger dina säkerhetsåtgärder analytiker en bredare attack story, som hjälper dem att bättre förstå och hantera komplexa hot i hela organisationen.


I **kön Incidenter** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor. Det hjälper dig att sortera incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.


![Bild på incidentkö](../../media/incidents-queue.png) 

Som standard visar kön i Microsoft 365 säkerhetscenter incidenter som har setts de senaste 30 dagarna. Den senaste incidenten visas högst upp i listan så att du kan se den först.

Incidentkön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper för incidenten eller de enheter som finns. På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter att hantera.

Om du snabbt vill kunna se fler incidenter genererar namn på incidenter automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

> [!NOTE]
> Incidenter som fanns innan de automatiska namngivningarna för incidenter ändrades inte.

I incidentkön visas också flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller bestämma dig för att fokusera på ett visst scenario eller hot. Genom att tillämpa filter på incidentkön kan du avgöra vilken händelse som kräver omedelbar uppmärksamhet. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="assigned-to"></a>Tilldelad till
Du kan välja att visa aviseringar som har tilldelats dig eller de som hanteras automatiskt.

### <a name="categories"></a>Kategorier
Välj kategorier för att fokusera på specifika taktiker, tekniker eller attackkomponenter som visas. 

### <a name="classification"></a>Klassificering
Filtrera incidenter baserat på de inställda klassificeringarna för relaterade aviseringar. Värdena inkluderar sanna varningar, falska aviseringar eller inte har angetts.

### <a name="data-sensitivity"></a>Datakänslighet
Vissa attacker fokuserar på att rikta in för att föra ut känsliga eller värdefulla data. Genom att använda ett filter för att se om det finns känslig information om händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriteras mot dessa incidenter.

>[!NOTE]
>Endast tillämpligt om Microsoft InformationSskydd är aktiverat.

### <a name="device-group"></a>Enhetsgrupp
Filtrera efter definierade enhetsgrupper.

### <a name="investigation-state"></a>Undersökningstillstånd
Filtrera incidenter efter status för automatiserad undersökning. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed kan orsaka mer skada. 

### <a name="multiple-service-sources"></a>Flera tjänstkällor 
Filter för att bara se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).

### <a name="os-platform"></a>OS-plattform
Begränsa incidentkövyn efter operativsystem.

### <a name="service-sources"></a>Tjänstkällor
Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. 

### <a name="severity"></a>Allvarlighetsgrad
Hur allvarlig en händelse är är att den är viktig för den inverkan den kan ha på dina tillgångar. Ju högre allvarlighetsgrad, desto större påverkan blir det vanligtvis och kräver i regel mest omedelbar uppmärksamhet. 

### <a name="status"></a>Status
Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.




## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken händelse som kräver högsta prioritet kan du fortsätta att göra ytterligare arbete med en händelse.
- [Undersöka incidenter](investigate-incidents.md)


## <a name="see-also"></a>Se även
- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
