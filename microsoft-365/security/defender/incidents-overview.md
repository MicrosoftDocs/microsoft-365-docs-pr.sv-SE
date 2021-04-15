---
title: Incidenter i Microsoft 365 Defender
description: Undersök incidenter som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
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
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759509"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="67e6c-104">Incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67e6c-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="67e6c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="67e6c-105">**Applies to:**</span></span>
- <span data-ttu-id="67e6c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67e6c-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="67e6c-107">Vill du uppleva Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="67e6c-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="67e6c-108">Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="67e6c-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="67e6c-109">En incident i Microsoft 365 Defender är en samling korrelerade aviseringar och associerade data som utgör attackens historia.</span><span class="sxs-lookup"><span data-stu-id="67e6c-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="67e6c-110">I Microsoft 365-tjänster och -appar skapas aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet.</span><span class="sxs-lookup"><span data-stu-id="67e6c-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="67e6c-111">Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack.</span><span class="sxs-lookup"><span data-stu-id="67e6c-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="67e6c-112">Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="67e6c-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="67e6c-113">Resultatet är flera aviseringar för flera enheter i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="67e6c-114">Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack aggregerar Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.</span><span class="sxs-lookup"><span data-stu-id="67e6c-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

<span data-ttu-id="67e6c-116">Titta på den här korta översikten över incidenter i Microsoft 365 Defender (4 minuter).</span><span class="sxs-lookup"><span data-stu-id="67e6c-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="67e6c-117">Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack.</span><span class="sxs-lookup"><span data-stu-id="67e6c-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="67e6c-118">Du kan till exempel se:</span><span class="sxs-lookup"><span data-stu-id="67e6c-118">For example, you can see:</span></span>

- <span data-ttu-id="67e6c-119">Var attacken började.</span><span class="sxs-lookup"><span data-stu-id="67e6c-119">Where the attack started.</span></span>
- <span data-ttu-id="67e6c-120">Vilka taktiker användes.</span><span class="sxs-lookup"><span data-stu-id="67e6c-120">What tactics were used.</span></span>
- <span data-ttu-id="67e6c-121">Hur långt attacken har varit i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="67e6c-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="67e6c-122">Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades.</span><span class="sxs-lookup"><span data-stu-id="67e6c-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="67e6c-123">Alla data som är associerade med attacken.</span><span class="sxs-lookup"><span data-stu-id="67e6c-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="67e6c-124">Om [den](m365d-enable.md)är aktiverad kan Microsoft 365 Defender automatiskt undersöka och åtgärda varningar med hjälp av automatisering och artificiell intelligens.</span><span class="sxs-lookup"><span data-stu-id="67e6c-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="67e6c-125">Du kan också utföra ytterligare åtgärdssteg för att lösa attacken.</span><span class="sxs-lookup"><span data-stu-id="67e6c-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="67e6c-126">Incidenter och aviseringar i Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="67e6c-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="67e6c-127">Du hanterar incidenter **från & och > incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="67e6c-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="67e6c-128">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="67e6c-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Säkerhetscenter för Microsoft 365":::

<span data-ttu-id="67e6c-130">När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="67e6c-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i säkerhetscentret i Microsoft 365":::

<span data-ttu-id="67e6c-132">Ytterligare flikar för en händelse är:</span><span class="sxs-lookup"><span data-stu-id="67e6c-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="67e6c-133">Varningar</span><span class="sxs-lookup"><span data-stu-id="67e6c-133">Alerts</span></span> 

  <span data-ttu-id="67e6c-134">Alla aviseringar som rör händelsen och deras information.</span><span class="sxs-lookup"><span data-stu-id="67e6c-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="67e6c-135">Enheter</span><span class="sxs-lookup"><span data-stu-id="67e6c-135">Devices</span></span>

  <span data-ttu-id="67e6c-136">Alla enheter som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="67e6c-137">Användare</span><span class="sxs-lookup"><span data-stu-id="67e6c-137">Users</span></span>

  <span data-ttu-id="67e6c-138">Alla användare som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="67e6c-139">Postlådor</span><span class="sxs-lookup"><span data-stu-id="67e6c-139">Mailboxes</span></span>

  <span data-ttu-id="67e6c-140">Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="67e6c-141">Undersökningar</span><span class="sxs-lookup"><span data-stu-id="67e6c-141">Investigations</span></span>

  <span data-ttu-id="67e6c-142">Alla automatiserade undersökningar som utlösts av aviseringar i händelsen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="67e6c-143">Bevis och svar</span><span class="sxs-lookup"><span data-stu-id="67e6c-143">Evidence and Response</span></span>

  <span data-ttu-id="67e6c-144">Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.</span><span class="sxs-lookup"><span data-stu-id="67e6c-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="67e6c-145">Här är förhållandet mellan en incident och dess data och flikarna för ett incident i Säkerhetscenter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67e6c-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relationen mellan en händelse och dess data till flikarna för en händelse i Säkerhetscenter i Microsoft 365":::

## <a name="next-step"></a><span data-ttu-id="67e6c-147">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="67e6c-147">Next step</span></span>

<span data-ttu-id="67e6c-148">I incidentkön på **sidan Incidenter** visas de senaste incidenterna.</span><span class="sxs-lookup"><span data-stu-id="67e6c-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="67e6c-149">Härifrån kan du:</span><span class="sxs-lookup"><span data-stu-id="67e6c-149">From here, you can:</span></span>

- <span data-ttu-id="67e6c-150">Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer.</span><span class="sxs-lookup"><span data-stu-id="67e6c-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="67e6c-151">Undersöka [en](investigate-incidents.md) händelse.</span><span class="sxs-lookup"><span data-stu-id="67e6c-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="67e6c-152">[Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldela dem, klassificera och lägga till taggar för arbetsflödet för incidenthantering.</span><span class="sxs-lookup"><span data-stu-id="67e6c-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
