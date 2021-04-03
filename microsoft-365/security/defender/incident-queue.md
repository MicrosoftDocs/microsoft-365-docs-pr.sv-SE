---
title: Prioritera incidenter i Microsoft 365 Defender
description: Läs om hur du filtrerar incidentköer i Microsoft 365 Defender
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: 5aba1ab4bed0eeb5f6127ab865ceea674e8d5902
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500994"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioritera incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender



Microsoft 365 Defender tillämpar korrelationsanalyser och lägger till alla relaterade aviseringar och undersökningar från olika produkter i ett incident. Microsoft 365 Defender utlöser även unika aviseringar om aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har över hela webbplatsen och produktsviten. Den här vyn ger din säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i hela organisationen.


I **kön Incidenter** visas en samling incidenter som har flaggats från olika enheter, användare och postlådor. Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.


![Bild på incidentköer](../../media/incidents-queue.png) 

Som standard visar kön i Microsoft 365 säkerhetscenter incidenter som har setts de senaste 30 dagarna. Det senaste incidenten visas högst upp i listan så att du kan se den först.

Incidentkön visar anpassningsbara kolumner som ger dig insyn i olika egenskaper för incidenten eller de enheter som finns. På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter som ska hanteras.

Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

> [!NOTE]
> De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.

I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot. Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet. 

## <a name="available-filters"></a>Tillgängliga filter

### <a name="assigned-to"></a>Tilldelad till
Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt.

### <a name="categories"></a>Kategorier
Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas. 

### <a name="classification"></a>Klassificering
Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar. Värdena omfattar sant varningar, falska aviseringar eller inte har angetts.

### <a name="data-sensitivity"></a>Datakänslighet
Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data. Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna.

>[!NOTE]
>Gäller endast om Microsoft informationsskydd är aktiverat.

### <a name="device-group"></a>Enhetsgrupp
Filtrera efter definierade enhetsgrupper.

### <a name="investigation-state"></a>Undersökningstillstånd
Filtrera ärenden efter status för automatiserad undersökning. 

### <a name="multiple-categories"></a>Flera kategorier 
Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada. 

### <a name="multiple-service-sources"></a>Flera tjänstkällor 
Filtrera för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365).

### <a name="os-platform"></a>OS-plattform
Begränsa vyn för incidentköer efter operativsystem.

### <a name="service-sources"></a>Tjänstkällor
Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. 

### <a name="severity"></a>Allvarlighetsgrad
Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar. Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet. 

### <a name="status"></a>Status
Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.




## <a name="next-steps"></a>Nästa steg
När du har fastställt vilken händelse som kräver högsta prioritet kan du fortsätta att undersöka en händelse ytterligare.
- [Undersöka incidenter](investigate-incidents.md)


## <a name="see-also"></a>Se även
- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
