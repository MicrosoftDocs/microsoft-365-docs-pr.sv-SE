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
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072714"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="cc8e8-104">Hantera incidenter i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc8e8-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cc8e8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cc8e8-105">**Applies to:**</span></span>
- <span data-ttu-id="cc8e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc8e8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="cc8e8-107">Det är viktigt att hantera incidenter för att säkerställa att hoten finns och hanteras.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="cc8e8-108">I Microsoft 365 Defender har du åtkomst till att hantera incidenter på enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="cc8e8-109">Du kan hantera incidenter genom att välja en incident från **kön Incidenter.**</span><span class="sxs-lookup"><span data-stu-id="cc8e8-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="cc8e8-110">Du kan redigera namnet på en händelse, lösa den, ange dess klassificering och avgörande.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="cc8e8-111">Du kan också tilldela incidenten till dig själv, lägga till incidenttaggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="cc8e8-112">I fall där du medan du undersöker vill flytta aviseringar från en händelse till en annan kan du också göra det från fliken Aviseringar, vilket innebär att en större eller mindre händelse som inkluderar alla relevanta aviseringar skapas.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="cc8e8-113">Redigera incidentens namn</span><span class="sxs-lookup"><span data-stu-id="cc8e8-113">Edit incident name</span></span>
<span data-ttu-id="cc8e8-114">Incidenter tilldelas automatiskt ett namn baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="cc8e8-115">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="cc8e8-116">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="cc8e8-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="cc8e8-117">Du kan ändra incidentnamnet så att det bättre överensstämmer med dina föredragna namngivningskonventioner.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="cc8e8-118">Incidenter som fanns innan de automatiska namnnamnen för incidenter distribuerades kommer att behålla sitt namn.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="cc8e8-119">Tilldela ärenden</span><span class="sxs-lookup"><span data-stu-id="cc8e8-119">Assign incidents</span></span>
<span data-ttu-id="cc8e8-120">Om en incident ännu inte har tilldelats kan du välja Tilldela **till mig** och tilldela incidenten till dig själv.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="cc8e8-121">När du gör det förutsätts att du äger inte bara händelsen utan även alla aviseringar som hör till den.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="cc8e8-122">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="cc8e8-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="cc8e8-123">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="cc8e8-123">Incident status</span></span>
<span data-ttu-id="cc8e8-124">Du kan kategorisera incidenter (som **Aktiva** eller **lösta**) genom att ändra deras status allt eftersom undersökningen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="cc8e8-125">På så sätt kan du organisera och hantera hur ditt team kan svara på incidenter.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="cc8e8-126">Din SOC-analytiker kan till  exempel granska brådskande aktiva incidenter för dagen och bestämma sig för att tilldela dem till själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="cc8e8-127">Alternativt kan SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="cc8e8-128">När du löser en händelse stängs automatiskt alla aviseringar som är en del av incidenten och är fortfarande öppna.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="cc8e8-129">Klassificering och determination</span><span class="sxs-lookup"><span data-stu-id="cc8e8-129">Classification and determination</span></span>
<span data-ttu-id="cc8e8-130">Du kan välja att inte ange någon klassificering eller att ange om incidenten är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="cc8e8-131">Det gör det lättare för teamet att se mönster och lära sig av dem.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="cc8e8-132">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="cc8e8-132">Add comments</span></span>
<span data-ttu-id="cc8e8-133">Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar i den.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="cc8e8-134">När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="cc8e8-135">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="cc8e8-136">Lägg till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="cc8e8-136">Add incident tags</span></span>
<span data-ttu-id="cc8e8-137">Du kan lägga till anpassade taggar för en händelse, till exempel för att flagga en grupp incidenter med gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="cc8e8-138">Du kan senare filtrera incidentkön för alla ärenden som innehåller en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="cc8e8-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
