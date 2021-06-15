---
title: Prioritera ärenden i Microsoft 365 Defender
description: Lär dig hur du filtrerar incidenter från incidentkön i Microsoft 365 Defender
keywords: incident, kö, översikt, enheter, identiteter, användare, postlåda, e-post, incidenter, analysera, svara
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
ms.openlocfilehash: 07a49fcdcfa7ea401b16b293b4831244253d2b28
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925893"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Prioritera ärenden i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Microsoft 365 Defender tillämpar korrelationsanalyser och sammanställer relaterade aviseringar och automatiska undersökningar från olika produkter till ett incident. Microsoft 365 Defender utlöser även unika aviseringar för aktiviteter som bara kan identifieras som skadliga givet den synlighet från end-to-end som Microsoft 365 Defender har i hela produktsviten. Den här vyn ger dina säkerhetsanalytiker den bredare attack storyn, som hjälper dem att bättre förstå och hantera komplexa hot i organisationen.

I **kön Incident** visas en samling incidenter som har skapats på olika enheter, användare och postlådor. Det hjälper dig att sortera olika incidenter för att prioritera och skapa ett välgrundat beslut om cybersäkerhet. 

Du kommer till incidentkön från **Incidenter & aviseringar > Incidenter** i snabbstarten av Microsoft 365 säkerhetscenter [(security.microsoft.com).](https://security.microsoft.com) Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

I **avsnittet Senaste incidenter och aviseringar** visas ett diagram över antalet aviseringar som tagits emot och incidenter som skapats de senaste 24 timmarna.

Som standard visar incidentkön i säkerhetscentret Microsoft 365 incidenter som har inträffat under de senaste sex månaderna. Det senaste incidenten visas högst upp i listan så att du kan se den först.

Incidentkön har anpassningsbara kolumner (välj **Välj** kolumner) som ger dig insyn i olika egenskaper för incidenten eller berörda enheter. På så sätt kan du fatta ett välgrundat beslut om prioritering av incidenter för analys.

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
| Flera tjänstkällor  | Filtrera för att bara se händelser som innehåller aviseringar från olika källor (Microsoft Defender för slutpunkt, Microsoft Cloud App Security, Microsoft Defender för identitet, Microsoft Defender för Office 365). |
| OS-plattform | Begränsa vyn för incidentköer efter operativsystem. |
| Tjänstkällor | Genom att välja en viss källa kan du fokusera på incidenter som innehåller minst en avisering från den valda källan. |
| Allvarlighetsgrad | Händelsens allvarlighetsgrad är samma som den inverkan den kan ha på dina tillgångar. Ju högre allvarlighetsgrad, desto större påverkan är det och kräver vanligtvis den mest omedelbarta uppmärksamhet. |
| Status | Du kan välja att begränsa listan över incidenter som visas baserat på deras status för att se vilka som är aktiva eller lösta. |
|||

## <a name="save-defined-filters-as-urls"></a>Spara definierade filter som URL-adresser

När du har konfigurerat ett användbart filter i kön med incidenter kan du bokmärka URL-adressen till webbläsarfliken eller på annat sätt spara den som en länk på en webbsida, ett Word-dokument eller en valfri plats. Det ger dig enkelklicksåtkomst till viktiga vyer av incidentkön, till exempel:

- Nya ärenden
- Incidenter med hög allvarlighetsgrad
- Incidenter som inte tilldelats
- Hög allvarlighetsgrad, incidenter som inte tilldelats
- Incidenter som tilldelats till mig
- Incidenter som tilldelats till mig och för Microsoft Defender för Endpoint
- Ärenden med en viss tagg eller taggar
- Ärenden med en specifik hotkategori
- Ärenden med specifika associerade hot
- Incidenter med en specifik aktör

När du har sammanställt och lagrat listan med användbara filtervyer som URL-adresser [](manage-incidents.md) kan du använda den för att snabbt bearbeta och prioritera incidenterna i kön och hantera dem för efterföljande analys.

## <a name="next-steps"></a>Nästa steg

När du har fastställt vilken händelse som kräver högst prioritet, markerar du den och gör följande:

- [Hantera](manage-incidents.md) egenskaperna för incidenten för taggar, tilldelning, omedelbar lösning för falska positiva incidenter och kommentarer.
- Påbörja din [undersökningar](investigate-incidents.md).

## <a name="see-also"></a>Se även
- [Översikt över incidenter](incidents-overview.md)
- [Hantera incidenter](manage-incidents.md)
- [Undersöka incidenter](investigate-incidents.md)
