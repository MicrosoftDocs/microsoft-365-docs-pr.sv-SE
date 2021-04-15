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
ms.openlocfilehash: 12207d69b0a1565caf762a265c1a0d32158ca291
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759859"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioritera incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Microsoft 365 Defender tillämpar korrelationsanalyser och aggregerar relaterade aviseringar och automatiska undersökningar från olika produkter för ett incident. Microsoft 365 Defender utlöser även unika aviseringar om aktiviteter som bara kan identifieras som skadliga givet den end-to-end-synlighet som Microsoft 365 Defender har i hela produktsviten. Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.

I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor. Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet. 

Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

Som standard visar kön i Microsoft 365 säkerhetscenter incidenter som har setts under de senaste sex månaderna. Det senaste incidenten visas högst upp i listan så att du kan se den först.

Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter. Det hjälper dig att fatta ett välgrundat beslut om prioritering av incidenter för anaylsis.

Om du vill ha bättre insyn genererar namn på automatiska incidenter incidentnamn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning.

Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

> [!NOTE]
> De incidenter som tidigare fanns innan de automatiska namngivningarna för incidenter ändrades inte.

I incidentkön visas även flera filtreringsalternativ, som när de används kan du rensa alla befintliga incidenter i din miljö eller välja att fokusera på ett visst scenario eller ett specifikt hot. Genom att använda filter på incidentkön kan du avgöra vilket ärende som kräver omedelbar uppmärksamhet. 

## <a name="available-filters"></a>Tillgängliga filter

Från standardkön för incidenter  kan du välja Filter för att visa ett filterfönster där du kan visa en filtrerad uppsättning incidenter. Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Exempel på filterfönstret för incidentkön":::

I den här tabellen visas de tillgängliga filternamnen.

| Filternamn | Beskrivning |
|:-------|:-----|
| Tilldelad till | Du kan välja att visa aviseringar som tilldelats dig eller de som hanteras automatiskt. |
| Kategorier | Välj kategorier om du vill fokusera på specifika taktiker, tekniker eller attackkomponenter som visas. |
| Klassificering | Filtrera incidenter baserat på de inställda klassificeringarna av relaterade aviseringar. Värdena omfattar sant varningar, falska aviseringar eller inte har angetts. |
| Datakänslighet | Vissa attacker fokuserar på att rikta för att föra in känsliga eller värdefulla data. Genom att använda ett filter för att se om känsliga data är inblandade i händelsen kan du snabbt avgöra om känslig information potentiellt har komprometterats och prioriterat de incidenterna. <br><br> Gäller endast om Microsoft informationsskydd är aktiverat.|
| Enhetsgrupp | Filtrera efter definierade enhetsgrupper. |
| Undersökningstillstånd | Filtrera ärenden efter status för automatiserad undersökning.  |
| Flera kategorier | Du kan välja att endast visa incidenter som har mappats till flera kategorier och därmed potentiellt kan orsaka mer skada. |
| Flera tjänstkällor  | Filtrera för att bara se incidenter som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365). |
| OS-plattform | Begränsa vyn för incidentköer efter operativsystem. |
| Tjänstkällor | Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. |
| Allvarlighetsgrad | Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar. Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet. |
| Status | Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta. |
|||

## <a name="incident-response-workflow"></a>Arbetsflöde för incidentsvar

Här är ett vanligt arbetsflöde för att svara på incidenter:

1. Identifiera och prioritera ärenden med högst prioritet för undersökning och lösning.
2. Påbörja en undersökning för varje incident med hög [prioritet:](investigate-incidents.md)

   a. Visa sammanfattningen av incidenten för att förstå dess omfattning, vilka enheter som påverkas och allvarlighetsgrad **(fliken** Sammanfattning).

   b. Börja titta på aviseringarna för att förstå deras ursprung, omfattning och allvarlighetsgrad **(fliken Aviseringar).**

   c. Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**

   d. Se hur Microsoft 365 Defender automatiskt har löst vissa aviseringar **(fliken Undersökningar).**
   
   e. Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).

När du undersöker bör du vara orolig:

- Inneslutning: Minska eventuella ytterligare påverkan på klientorganisationen.
- Överflödigt: Ta bort säkerhetshotet.
- Återställning: Återställa klientorganisationens resurser till det läge de var i före attacken.

När du har löst problemet bör du ta en stund att lära dig från den för att:

- Förstå typen av attack och dess påverkan.
- Undersöka säkerhetsgemenskapen efter en trend för säkerhetsattacker.
- Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden och plalböcker efter behov.

Här följer en sammanfattning av grunderna.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Grundläggande process för att undersöka ärenden":::

## <a name="next-step"></a>Nästa steg

När du har fastställt vilken händelse som kräver högsta prioritet markerar du den och påbörjar [din undersökning](investigate-incidents.md).

## <a name="see-also"></a>Se även
- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
