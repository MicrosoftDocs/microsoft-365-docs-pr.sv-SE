---
title: Hantera incidenter i Microsoft 365 Defender
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, analysera, svar, aviseringar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.openlocfilehash: 5f66189979f401430353f4c15978a85276b48840
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939760"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="64b9d-104">Hantera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64b9d-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="64b9d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="64b9d-105">**Applies to:**</span></span>
- <span data-ttu-id="64b9d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64b9d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="64b9d-107">Incidenthantering är viktigt för att säkerställa att hoten finns och hanteras.</span><span class="sxs-lookup"><span data-stu-id="64b9d-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="64b9d-108">Du hanterar incidenter **från & och > incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="64b9d-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="64b9d-109">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="64b9d-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="64b9d-111">Du kan hantera dina incidenter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="64b9d-111">Here are the ways you can manage your incidents:</span></span>

- <span data-ttu-id="64b9d-112">Ändra incidentens namn</span><span class="sxs-lookup"><span data-stu-id="64b9d-112">Change the incident name</span></span>
- <span data-ttu-id="64b9d-113">Lägg till incidenttaggar.</span><span class="sxs-lookup"><span data-stu-id="64b9d-113">Add incident tags.</span></span>
- <span data-ttu-id="64b9d-114">Tilldela incidenten till ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="64b9d-114">Assign the incident to a user account</span></span>
- <span data-ttu-id="64b9d-115">Lösa dem</span><span class="sxs-lookup"><span data-stu-id="64b9d-115">Resolve them</span></span> 
- <span data-ttu-id="64b9d-116">Ange dess klassificering och avgörande</span><span class="sxs-lookup"><span data-stu-id="64b9d-116">Set its classification and determination</span></span>
- <span data-ttu-id="64b9d-117">Lägg till kommentarer.</span><span class="sxs-lookup"><span data-stu-id="64b9d-117">Add comments.</span></span>

<span data-ttu-id="64b9d-118">Du kan hantera incidenter i **fönstret Hantera** incidenter för ett incident.</span><span class="sxs-lookup"><span data-stu-id="64b9d-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="64b9d-119">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="64b9d-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exempel på fönstret Hantera incident för en händelse":::

<span data-ttu-id="64b9d-121">Du kan visa det här fönstret från **länken Hantera** incident på:</span><span class="sxs-lookup"><span data-stu-id="64b9d-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="64b9d-122">Egenskapsfönster för en incident i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="64b9d-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="64b9d-123">**Sammanfattningssida** för en incident.</span><span class="sxs-lookup"><span data-stu-id="64b9d-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="64b9d-124">I fall där du genom att analysera vill flytta aviseringar från en händelse  till en annan kan du även göra det från fliken Aviseringar, och på så sätt skapa en större eller mindre incident som inkluderar alla relevanta aviseringar.</span><span class="sxs-lookup"><span data-stu-id="64b9d-124">In cases where, while analyzing you would like to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="64b9d-125">Redigera incidentens namn</span><span class="sxs-lookup"><span data-stu-id="64b9d-125">Edit the incident name</span></span>

<span data-ttu-id="64b9d-126">Microsoft 365 Defender tilldelar automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="64b9d-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="64b9d-127">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="64b9d-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="64b9d-128">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="64b9d-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="64b9d-129">Du kan redigera incidentnamnet från **fältet Incidentnamn** i **fönstret Hantera** incident.</span><span class="sxs-lookup"><span data-stu-id="64b9d-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="64b9d-130">Incidenter som fanns innan namnfunktionen för automatiska incidenter distribuerades behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="64b9d-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="64b9d-131">Lägg till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="64b9d-131">Add incident tags</span></span>

<span data-ttu-id="64b9d-132">Du kan lägga till anpassade taggar för en händelse, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="64b9d-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="64b9d-133">Du kan senare filtrera incidentkön för alla incidenter som innehåller en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="64b9d-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="64b9d-134">När du börjar skriva kan du välja i en lista med valda taggar.</span><span class="sxs-lookup"><span data-stu-id="64b9d-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="64b9d-135">Tilldela ärenden</span><span class="sxs-lookup"><span data-stu-id="64b9d-135">Assign incidents</span></span>

<span data-ttu-id="64b9d-136">Om en incident ännu inte har tilldelats kan du välja **Tilldela till** och ange användarkontot.</span><span class="sxs-lookup"><span data-stu-id="64b9d-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="64b9d-137">Då tilldelas ägarskap för incidenten och alla aviseringar som är kopplade till den.</span><span class="sxs-lookup"><span data-stu-id="64b9d-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-incident"></a><span data-ttu-id="64b9d-138">Lös incident</span><span class="sxs-lookup"><span data-stu-id="64b9d-138">Resolve incident</span></span>

<span data-ttu-id="64b9d-139">Om incidenten har åtgärdats väljer du **Lös incidenten** för att flytta reglaget till höger.</span><span class="sxs-lookup"><span data-stu-id="64b9d-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="64b9d-140">Tänk på att när du löser en incident åtgärdas även alla länkade och aktiva aviseringar som är relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="64b9d-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="64b9d-141">En incident som inte åtgärdas visas som **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="64b9d-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="64b9d-142">Ange klassificering och avgörande</span><span class="sxs-lookup"><span data-stu-id="64b9d-142">Set the classification and determination</span></span>

<span data-ttu-id="64b9d-143">Incidentklassificeringshändelsen är oavsett om det var en verklig avisering eller en falsk avisering som du konfigurerar från **fältet** Klassificering.</span><span class="sxs-lookup"><span data-stu-id="64b9d-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="64b9d-144">Om det var en verklig varning bör du också ange vilken typ av hot det var med **fältet Determination.**</span><span class="sxs-lookup"><span data-stu-id="64b9d-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="64b9d-145">Om du anger hottypen kan säkerhetsteamet se hotmönster och agera för att försvara organisationen från dem.</span><span class="sxs-lookup"><span data-stu-id="64b9d-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="64b9d-146">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="64b9d-146">Add comments</span></span>

<span data-ttu-id="64b9d-147">Du kan lägga till flera kommentarer till en händelse med **fältet** Kommentar.</span><span class="sxs-lookup"><span data-stu-id="64b9d-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="64b9d-148">Varje kommentar läggs till i de historiska händelserna för händelsen.</span><span class="sxs-lookup"><span data-stu-id="64b9d-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="64b9d-149">Du kan se kommentarer och historik för en händelse via **länken Kommentarer och historik** på **sidan** Sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="64b9d-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64b9d-150">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="64b9d-150">Related topics</span></span>

- [<span data-ttu-id="64b9d-151">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="64b9d-151">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="64b9d-152">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="64b9d-152">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="64b9d-153">Analysera incidenter</span><span class="sxs-lookup"><span data-stu-id="64b9d-153">Analyze incidents</span></span>](investigate-incidents.md)
