---
title: Visa och ordna incidentkö
ms.reviewer: ''
description: Se listan över incidenter och lär dig hur du använder filter för att begränsa listan och få en mer fokuserad vy.
keywords: visa, organisera, incidenter, aggregera, undersökningar, kö, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499940"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Visa och ordna kön Microsoft Defender för slutpunktsincidenter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

I **kön Incidenter** visas en samling incidenter som har flaggats från enheter i nätverket. Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet.

Som standard visar kön incidenter som visats de senaste 30 dagarna, med det senaste incidenten högst upp i listan, vilket hjälper dig att se de senaste incidenterna först.

Du kan välja mellan flera alternativ för att anpassa vyn Incidentköer. 

I det övre navigeringsfältet kan du:
- Anpassa kolumner för att lägga till eller ta bort kolumner 
- Ändra antalet objekt som ska visas per sida
- Markera de objekt som ska visas per sida
- Batchvälj de incidenter du vill tilldela 
- Navigera mellan sidor
- Använda filter

![Bild på incidentköer](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>Sortera och filtrera incidentkön
Du kan använda följande filter för att begränsa listan över incidenter och få en mer fokuserad vy.

### <a name="severity"></a>Allvarlighetsgrad

Incidentens allvarlighetsgrad | Beskrivning
:---|:---
Högsta </br>(Röd) | Hot som ofta associeras med avancerade fortlöpande hot (APT). De här incidenterna anger en hög risk på grund av hur allvarlig skada de kan orsaka på enheter.
Medel </br>(Orange) | Hot som sällan observeras i organisationen, till exempel avvikande registerändring, körning av misstänkta filer och observerade beteenden som är typiska för attackfaser.
Låg </br>(Gul) | Hot som är associerade med vanlig skadlig programvara och hack-verktyg som inte nödvändigtvis indikerar ett avancerat hot som riktar sig till organisationen.
Information </br>(Grå) | Informationstillbud anses kanske inte vara skadliga för nätverket men de kan vara bra att hålla reda på.

## <a name="assigned-to"></a>Tilldelad till
Du kan välja att filtrera listan genom att välja tilldelade till alla eller sådana som har tilldelats till dig.

### <a name="category"></a>Kategori
Incidenter kategoriseras utifrån beskrivningen av det steg i vilket man ligger med en killkedja för cybersäkerhet. Den här vyn hjälper hotanalytiker att fastställa prioritet, brådskande och motsvarande svarsstrategi för distribution utifrån kontext.

### <a name="status"></a>Status
Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta.

### <a name="data-sensitivity"></a>Datakänslighet
Använd det här filtret för att visa incidenter som innehåller känslighetsetiketter.

## <a name="incident-naming"></a>Namn på incidenter

För att du snabbt ska förstå incidentens omfattning genereras incidentnamn automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

> [!NOTE]
> Incidenter som tidigare fanns före automatisk namngivning för incidenter behåller sitt namn.


## <a name="see-also"></a>Se även
- [Incidentkö](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Hantera incidenter](manage-incidents.md)
- [Undersöka incidenter](investigate-incidents.md)

