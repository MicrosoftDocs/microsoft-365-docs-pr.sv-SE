---
title: Hantera incidenter i Microsoft Threat Protection
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, varningar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f711cc2ff38f15dfd22097e37a1dec42719eb5aa
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148120"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="5d359-104">Hantera incidenter i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5d359-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="5d359-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="5d359-105">**Applies to:**</span></span>
- <span data-ttu-id="5d359-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="5d359-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5d359-107">Hanteringen av incidenter är avgörande för att säkerställa att hoten begränsas och åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="5d359-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="5d359-108">I Microsoft Threat Protection har du åtkomst till hantering av incidenter på enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="5d359-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="5d359-109">Du kan hantera incidenter genom att välja en incident från **kön Incidenter**.</span><span class="sxs-lookup"><span data-stu-id="5d359-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="5d359-110">Du kan redigera namnet på en incident, lösa den, ange dess klassificering och bestämning.</span><span class="sxs-lookup"><span data-stu-id="5d359-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="5d359-111">Du kan också tilldela incidenten till dig själv, lägga till incidenttaggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="5d359-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="5d359-112">I de fall där du under utredningen vill flytta aviseringar från en incident till en annan kan du också göra det från fliken Aviseringar, vilket skapar en större eller mindre incident som innehåller alla relevanta aviseringar.</span><span class="sxs-lookup"><span data-stu-id="5d359-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="5d359-113">Redigera incidentnamn</span><span class="sxs-lookup"><span data-stu-id="5d359-113">Edit incident name</span></span>
<span data-ttu-id="5d359-114">Som standard tilldelas en incident ett nummer.</span><span class="sxs-lookup"><span data-stu-id="5d359-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="5d359-115">Du kan ändra incidentnamnet så att det stämmer överens med den namngivningskonvention som du föredrar.</span><span class="sxs-lookup"><span data-stu-id="5d359-115">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!TIP]
> <span data-ttu-id="5d359-116">För ytterligare synlighet via ett ögonkast genererar automatisk incidentnamn, som för närvarande finns i offentlig förhandsversion, incidentnamn baserat på varningsattribut som antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="5d359-116">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="5d359-117">På så sätt kan du snabbt förstå omfattningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="5d359-117">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="5d359-118">Till exempel: *Flerstegsincident på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="5d359-118">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="5d359-119">Incidenter som fanns före utrullningen av automatisk incidentnamn kommer inte att få sitt namn ändrat.</span><span class="sxs-lookup"><span data-stu-id="5d359-119">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>
>
> <span data-ttu-id="5d359-120">Läs mer om [hur du aktiverar förhandsgranskningsfunktioner](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="5d359-120">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

## <a name="assign-incidents"></a><span data-ttu-id="5d359-121">Tilldela incidenter</span><span class="sxs-lookup"><span data-stu-id="5d359-121">Assign incidents</span></span>
<span data-ttu-id="5d359-122">Om en incident ännu inte har tilldelats kan du välja **Tilldela mig** för att tilldela händelsen till dig själv.</span><span class="sxs-lookup"><span data-stu-id="5d359-122">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="5d359-123">Detta förutsätter ägandet av inte bara händelsen, men också alla varningar i samband med den.</span><span class="sxs-lookup"><span data-stu-id="5d359-123">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="5d359-124">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="5d359-124">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="5d359-125">Status för incident</span><span class="sxs-lookup"><span data-stu-id="5d359-125">Incident status</span></span>
<span data-ttu-id="5d359-126">Du kan kategorisera incidenter (som **Aktiv**eller **Löst)** genom att ändra deras status under utredningens gång.</span><span class="sxs-lookup"><span data-stu-id="5d359-126">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="5d359-127">Detta hjälper dig att organisera och hantera hur ditt team kan svara på incidenter.</span><span class="sxs-lookup"><span data-stu-id="5d359-127">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="5d359-128">Till exempel kan din SOC-analytiker granska de brådskande **aktiva** incidenter för dagen och besluta att tilldela dem till sig själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="5d359-128">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="5d359-129">Alternativt kan din SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="5d359-129">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="5d359-130">Om du löser en incident stängs alla aviseringar som ingår i incidenten automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5d359-130">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="5d359-131">Klassificering och bestämning</span><span class="sxs-lookup"><span data-stu-id="5d359-131">Classification and determination</span></span>
<span data-ttu-id="5d359-132">Du kan välja att inte ange en klassificering eller bestämma dig för att ange om en incident är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="5d359-132">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="5d359-133">Detta hjälper teamet att se mönster och lära av dem.</span><span class="sxs-lookup"><span data-stu-id="5d359-133">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="5d359-134">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="5d359-134">Add comments</span></span>
<span data-ttu-id="5d359-135">Du kan lägga till kommentarer och visa historiska händelser om en incident för att se tidigare ändringar som gjorts i den.</span><span class="sxs-lookup"><span data-stu-id="5d359-135">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="5d359-136">När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="5d359-136">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="5d359-137">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="5d359-137">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="5d359-138">Lägga till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="5d359-138">Add incident tags</span></span>
<span data-ttu-id="5d359-139">Du kan lägga till anpassade taggar i en incident, till exempel för att flagga en grupp incidenter med gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="5d359-139">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="5d359-140">Du kan senare filtrera incidentkön för alla incidenter som innehåller en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="5d359-140">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>