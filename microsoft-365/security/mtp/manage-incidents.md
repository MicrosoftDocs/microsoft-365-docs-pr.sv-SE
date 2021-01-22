---
title: Hantera ärenden i Microsoft 365 Defender
description: Lär dig hur du tilldelar, uppdaterar status,
keywords: incident, incidenter, varningar, korrelerade aviseringar, tilldela, uppdatera, status, hantera, klassificering, microsoft, 365, m365
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
ms.openlocfilehash: 90d9d397b8baf0ffdb9844a0f068f142a5c7fd48
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930636"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="401e2-104">Hantera ärenden i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="401e2-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="401e2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="401e2-105">**Applies to:**</span></span>
- <span data-ttu-id="401e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="401e2-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="401e2-107">Det är viktigt att hantera incidenter för att säkerställa att hoten är inneslutna och hanteras.</span><span class="sxs-lookup"><span data-stu-id="401e2-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="401e2-108">I Microsoft 365 Defender har du tillgång till att hantera incidenter på enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="401e2-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="401e2-109">Du kan hantera incidenter genom att välja en incident i **kön Incidenter.**</span><span class="sxs-lookup"><span data-stu-id="401e2-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="401e2-110">Du kan redigera namnet på en händelse, lösa den, ange klassificering och avgörande.</span><span class="sxs-lookup"><span data-stu-id="401e2-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="401e2-111">Du kan också tilldela incidenten till dig själv, lägga till incidenttaggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="401e2-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="401e2-112">I fall där du under en undersökning vill flytta aviseringar från en händelse till en annan kan du också göra det från fliken Aviseringar, vilket innebär att en större eller mindre incident skapas som inkluderar alla relevanta aviseringar.</span><span class="sxs-lookup"><span data-stu-id="401e2-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="401e2-113">Redigera incidentnamn</span><span class="sxs-lookup"><span data-stu-id="401e2-113">Edit incident name</span></span>
<span data-ttu-id="401e2-114">Incidenter tilldelas automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="401e2-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="401e2-115">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="401e2-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="401e2-116">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="401e2-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="401e2-117">Du kan ändra incidentnamnet så att det bättre överensstämmer med de namngivningskonventioner du föredrar.</span><span class="sxs-lookup"><span data-stu-id="401e2-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="401e2-118">Incidenter som fanns innan den automatiska namnefunktionen för incidenter distribuerades behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="401e2-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="401e2-119">Tilldela ärenden</span><span class="sxs-lookup"><span data-stu-id="401e2-119">Assign incidents</span></span>
<span data-ttu-id="401e2-120">Om en incident ännu inte har tilldelats kan du välja Tilldela till **mig** för att tilldela incidenten till dig själv.</span><span class="sxs-lookup"><span data-stu-id="401e2-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="401e2-121">Då förutsätts ägarskap till inte bara incidenten, utan även alla aviseringar som är kopplade till den.</span><span class="sxs-lookup"><span data-stu-id="401e2-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="401e2-122">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="401e2-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="401e2-123">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="401e2-123">Incident status</span></span>
<span data-ttu-id="401e2-124">Du kan kategorisera incidenter (som **aktiva** **eller lösta)** genom att ändra deras status allt eftersom undersökningen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="401e2-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="401e2-125">På så sätt kan du organisera och hantera hur din grupp kan svara på incidenter.</span><span class="sxs-lookup"><span data-stu-id="401e2-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="401e2-126">Din SOC-analytiker kan till exempel granska dagens brådskande **aktiva** ärenden och bestämma att de ska tilldelas till hon själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="401e2-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="401e2-127">Alternativt kan din SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="401e2-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="401e2-128">När du löser en händelse stängs automatiskt alla aviseringar som är en del av incidenten och är fortfarande öppna.</span><span class="sxs-lookup"><span data-stu-id="401e2-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="401e2-129">Klassificering och avgörande</span><span class="sxs-lookup"><span data-stu-id="401e2-129">Classification and determination</span></span>
<span data-ttu-id="401e2-130">Du kan välja att inte ange någon klassificering eller att ange om en incident är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="401e2-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="401e2-131">På så sätt kan teamet se mönster och lära sig av dem.</span><span class="sxs-lookup"><span data-stu-id="401e2-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="401e2-132">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="401e2-132">Add comments</span></span>
<span data-ttu-id="401e2-133">Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar som gjorts i den.</span><span class="sxs-lookup"><span data-stu-id="401e2-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="401e2-134">När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="401e2-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="401e2-135">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="401e2-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="401e2-136">Lägga till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="401e2-136">Add incident tags</span></span>
<span data-ttu-id="401e2-137">Du kan lägga till anpassade taggar för ett incidenter, till exempel för att flagga en grupp ärenden med gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="401e2-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="401e2-138">Du kan senare filtrera ärendekön för alla incidenter som innehåller en specifik tagg.</span><span class="sxs-lookup"><span data-stu-id="401e2-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
