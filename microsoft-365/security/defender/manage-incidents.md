---
title: Hantera ärenden i Microsoft 365 Defender
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
ms.openlocfilehash: 725e6226a56b3aae3670cde18969afdda1ec1940
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530844"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="9a287-104">Hantera ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a287-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9a287-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9a287-105">**Applies to:**</span></span>
- <span data-ttu-id="9a287-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a287-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9a287-107">Incidenthantering är viktigt för att säkerställa att hoten finns och hanteras.</span><span class="sxs-lookup"><span data-stu-id="9a287-107">Incident management is critical in ensuring that threats are contained and addressed.</span></span>

<span data-ttu-id="9a287-108">Du hanterar incidenter **från & och > incidenter** i snabbstarten av säkerhetscentret i Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9a287-108">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="9a287-109">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9a287-109">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exempel på incidentkön":::

<span data-ttu-id="9a287-111">Du kan hantera dina incidenter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="9a287-111">Here are the ways you can manage your incidents:</span></span>

- [<span data-ttu-id="9a287-112">Redigera incidentens namn</span><span class="sxs-lookup"><span data-stu-id="9a287-112">Edit the incident name</span></span>](#edit-the-incident-name)
- [<span data-ttu-id="9a287-113">Lägg till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="9a287-113">Add incident tags</span></span>](#add-incident-tags)
- [<span data-ttu-id="9a287-114">Tilldela incidenten till ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="9a287-114">Assign the incident to a user account</span></span>](#assign-incidents)
- [<span data-ttu-id="9a287-115">Lösa dem</span><span class="sxs-lookup"><span data-stu-id="9a287-115">Resolve them</span></span>](#resolve-an-incident)
- [<span data-ttu-id="9a287-116">Ange dess klassificering och avgörande</span><span class="sxs-lookup"><span data-stu-id="9a287-116">Set its classification and determination</span></span>](#set-the-classification-and-determination)
- [<span data-ttu-id="9a287-117">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="9a287-117">Add comments</span></span>](#add-comments)

<span data-ttu-id="9a287-118">Du kan hantera incidenter i **fönstret Hantera** incidenter för ett incident.</span><span class="sxs-lookup"><span data-stu-id="9a287-118">You can manage incidents from the **Manage incident** pane for an incident.</span></span> <span data-ttu-id="9a287-119">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="9a287-119">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exempel på fönstret Hantera incident för en händelse":::

<span data-ttu-id="9a287-121">Du kan visa det här fönstret från **länken Hantera** incident på:</span><span class="sxs-lookup"><span data-stu-id="9a287-121">You can display this pane from the **Manage incident** link on the:</span></span>

- <span data-ttu-id="9a287-122">Egenskapsfönster för en incident i incidentkön.</span><span class="sxs-lookup"><span data-stu-id="9a287-122">Properties pane of an incident in the incident queue.</span></span>
- <span data-ttu-id="9a287-123">**Sammanfattningssida** för en incident.</span><span class="sxs-lookup"><span data-stu-id="9a287-123">**Summary** page of an incident.</span></span>

<span data-ttu-id="9a287-124">I de fall du vill flytta aviseringar från en händelse till  en annan kan du även göra det från fliken Aviseringar, vilket innebär att en större eller mindre incident som inkluderar alla relevanta aviseringar skapas.</span><span class="sxs-lookup"><span data-stu-id="9a287-124">In cases where you want to move alerts from one incident to another, you can also do so from the **Alerts** tab, thus creating a larger or smaller incident that includes all relevant alerts.</span></span>

## <a name="edit-the-incident-name"></a><span data-ttu-id="9a287-125">Redigera incidentens namn</span><span class="sxs-lookup"><span data-stu-id="9a287-125">Edit the incident name</span></span>

<span data-ttu-id="9a287-126">Microsoft 365 Defender tilldelar automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="9a287-126">Microsoft 365 Defender automatically assigns a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="9a287-127">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="9a287-127">This allows you to quickly understand the scope of the incident.</span></span> <span data-ttu-id="9a287-128">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="9a287-128">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="9a287-129">Du kan redigera incidentnamnet från **fältet Incidentnamn** i **fönstret Hantera** incident.</span><span class="sxs-lookup"><span data-stu-id="9a287-129">You can edit the incident name from the **Incident name** field on the **Manage incident** pane.</span></span>

> [!NOTE]
> <span data-ttu-id="9a287-130">Incidenter som fanns innan namnfunktionen för automatiska incidenter distribuerades behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="9a287-130">Incidents that existed before the rollout of the automatic incident naming feature will retain their name.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="9a287-131">Lägg till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="9a287-131">Add incident tags</span></span>

<span data-ttu-id="9a287-132">Du kan lägga till anpassade taggar för en händelse, till exempel för att flagga en grupp med incidenter med en gemensam egenskap.</span><span class="sxs-lookup"><span data-stu-id="9a287-132">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristic.</span></span> <span data-ttu-id="9a287-133">Du kan senare filtrera incidentkön för alla incidenter som innehåller en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="9a287-133">You can later filter the incident queue for all incidents that contain a specific tag.</span></span>

<span data-ttu-id="9a287-134">När du börjar skriva kan du välja i en lista med valda taggar.</span><span class="sxs-lookup"><span data-stu-id="9a287-134">When you start typing, you have the option to select from a list of selected tags.</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="9a287-135">Tilldela ärenden</span><span class="sxs-lookup"><span data-stu-id="9a287-135">Assign incidents</span></span>

<span data-ttu-id="9a287-136">Om en incident ännu inte har tilldelats kan du välja **Tilldela till** och ange användarkontot.</span><span class="sxs-lookup"><span data-stu-id="9a287-136">If an incident has not yet been assigned, you can select **Assign to** and specify the user account.</span></span> <span data-ttu-id="9a287-137">Då tilldelas ägarskap för incidenten och alla aviseringar som är kopplade till den.</span><span class="sxs-lookup"><span data-stu-id="9a287-137">Doing so assigns ownership of the incident and all the alerts associated with it.</span></span>

## <a name="resolve-an-incident"></a><span data-ttu-id="9a287-138">Lösa ett problem</span><span class="sxs-lookup"><span data-stu-id="9a287-138">Resolve an incident</span></span>

<span data-ttu-id="9a287-139">Om incidenten har åtgärdats väljer du **Lös incidenten** för att flytta reglaget till höger.</span><span class="sxs-lookup"><span data-stu-id="9a287-139">If the incident has been remediated, select **Resolve incident** to move the toggle to the right.</span></span> <span data-ttu-id="9a287-140">Tänk på att när du löser en incident åtgärdas även alla länkade och aktiva aviseringar som är relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="9a287-140">Note that resolving an incident also resolves all the linked and active alerts related to the incident.</span></span>

<span data-ttu-id="9a287-141">En incident som inte åtgärdas visas som **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="9a287-141">An incident that is not resolved displays as **Active**.</span></span>

## <a name="set-the-classification-and-determination"></a><span data-ttu-id="9a287-142">Ange klassificering och avgörande</span><span class="sxs-lookup"><span data-stu-id="9a287-142">Set the classification and determination</span></span>

<span data-ttu-id="9a287-143">Incidentklassificeringshändelsen är oavsett om det var en verklig avisering eller en falsk avisering som du konfigurerar från **fältet** Klassificering.</span><span class="sxs-lookup"><span data-stu-id="9a287-143">The incident classification is whether it was a true alert or a false alert, which you configure from the **Classification** field.</span></span> 

<span data-ttu-id="9a287-144">Om det var en verklig varning bör du också ange vilken typ av hot det var med **fältet Determination.**</span><span class="sxs-lookup"><span data-stu-id="9a287-144">If it was a true alert, you should also specify what type of threat it was with the **Determination** field.</span></span> <span data-ttu-id="9a287-145">Om du anger hottypen kan säkerhetsteamet se hotmönster och agera för att försvara organisationen från dem.</span><span class="sxs-lookup"><span data-stu-id="9a287-145">Specifying the threat type helps your security team see threat patterns and act to defend your organization from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="9a287-146">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="9a287-146">Add comments</span></span>

<span data-ttu-id="9a287-147">Du kan lägga till flera kommentarer till en händelse med **fältet** Kommentar.</span><span class="sxs-lookup"><span data-stu-id="9a287-147">You can add multiple comments to an incident with the **Comment** field.</span></span> <span data-ttu-id="9a287-148">Varje kommentar läggs till i de historiska händelserna för händelsen.</span><span class="sxs-lookup"><span data-stu-id="9a287-148">Each comment gets added to the historical events of the incident.</span></span> <span data-ttu-id="9a287-149">Du kan se kommentarer och historik för en händelse via **länken Kommentarer och historik** på **sidan** Sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="9a287-149">You can see the comments and history of an incident from the **Comments and history** link on the **Summary** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a287-150">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="9a287-150">Next steps</span></span>

<span data-ttu-id="9a287-151">Påbörja din undersökning för nya [incidenter.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="9a287-151">For new incidents, begin your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="9a287-152">Fortsätt din undersökning för pågående [ärenden.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="9a287-152">For in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

<span data-ttu-id="9a287-153">För lösta incidenter utför du [en granskning efter incidenten.](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="9a287-153">For resolved incidents, perform a [post-incident review](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a287-154">Se även</span><span class="sxs-lookup"><span data-stu-id="9a287-154">See also</span></span>

- [<span data-ttu-id="9a287-155">Översikt över incidenter</span><span class="sxs-lookup"><span data-stu-id="9a287-155">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="9a287-156">Prioritera incidenter</span><span class="sxs-lookup"><span data-stu-id="9a287-156">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="9a287-157">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="9a287-157">Investigate incidents</span></span>](investigate-incidents.md)
