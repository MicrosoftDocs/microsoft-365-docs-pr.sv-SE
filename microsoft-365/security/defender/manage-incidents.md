---
title: Hantera incidenter i Microsoft 365 Defender
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, aviseringar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760074"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Hantera incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Incidenthantering är viktigt för att säkerställa att hoten finns och hanteras.

Du hanterar incidenter **från & och > incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com) Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

Du kan hantera dina incidenter på följande sätt:

- Ändra incidentens namn
- Lägg till incidenttaggar.
- Tilldela incidenten till ett användarkonto
- Lösa dem 
- Ange dess klassificering och avgörande
- Lägg till kommentarer.

Du kan hantera incidenter i **fönstret Hantera** incidenter för ett incident. Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exempel på fönstret Hantera incident för en händelse":::

Du kan visa det här fönstret från **länken Hantera** incident på:

- Egenskapsfönster för en incident i incidentkön.
- **Sammanfattningssida** för en incident.

I de fall du undersöker när du undersöker om du vill flytta  aviseringar från en händelse till en annan kan du även göra det från fliken Aviseringar, vilket innebär att en större eller mindre händelse som inkluderar alla relevanta aviseringar skapas.

## <a name="edit-the-incident-name"></a>Redigera incidentens namn

Incidenter tilldelas automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier. På så sätt kan du snabbt förstå incidentens omfattning. Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*

Du kan redigera incidentnamnet från **fältet Incidentnamn** i **fönstret Hantera** incident.

> [!NOTE]
> Incidenter som fanns innan de automatiska namnnamnen för incidenter distribuerades kommer att behålla sitt namn.

## <a name="add-incident-tags"></a>Lägg till incidenttaggar

Du kan lägga till anpassade taggar för en händelse, till exempel för att flagga en grupp med incidenter med en gemensam egenskap. Du kan senare filtrera incidentkön för alla incidenter som innehåller en viss tagg.

När du börjar skriva kan du välja i en lista med valda taggar.

## <a name="assign-incidents"></a>Tilldela ärenden

Om en incident ännu inte har tilldelats kan du välja **Tilldela till** och ange användarkontot. Då tilldelas ägarskap för incidenten och alla aviseringar som är kopplade till den.

## <a name="resolve-incident"></a>Lös incident

Om incidenten har åtgärdats väljer du **Lös incidenten** för att flytta reglaget till höger. Tänk på att när du löser en incident åtgärdas även alla länkade och aktiva aviseringar som är relaterade till händelsen.

En incident som inte åtgärdas visas som **Aktiv**.

## <a name="set-the-classification-and-determination"></a>Ange klassificering och avgörande

Incidentklassificeringshändelsen är oavsett om det var en verklig avisering eller en falsk avisering som du konfigurerar från **fältet** Klassificering. 

Om det var en verklig varning bör du också ange vilken typ av hot det var med **fältet Determination.** Om du anger hottypen kan säkerhetsteamet se hotmönster och agera för att försvara organisationen från dem. 

## <a name="add-comments"></a>Lägga till kommentarer

Du kan lägga till flera kommentarer till en händelse med **fältet** Kommentar. Varje kommentar läggs till i de historiska händelserna för händelsen. Du kan se kommentarer och historik för en händelse via **länken Kommentarer och historik** på **sidan** Sammanfattning.
