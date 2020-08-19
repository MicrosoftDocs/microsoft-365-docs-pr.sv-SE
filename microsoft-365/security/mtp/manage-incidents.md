---
title: Hantera incidenter i skydd mot Microsoft Threat
description: Lär dig hur du tilldelar, uppdaterar status
keywords: incident, incidenter, aviseringar, korrelerade notifieringar, tilldela, uppdatera, status, hantera, klassificering, Microsoft, 365, m365
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
ms.openlocfilehash: 8880655ec24f20efd139b8334ab754f51146b496
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798216"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="af1cf-104">Hantera incidenter i skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="af1cf-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="af1cf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="af1cf-105">**Applies to:**</span></span>
- <span data-ttu-id="af1cf-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="af1cf-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="af1cf-107">Det är viktigt att hantera incidenter för att säkerställa att hoten är placerade och riktade.</span><span class="sxs-lookup"><span data-stu-id="af1cf-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="af1cf-108">I Microsoft Threat Protection har du åtkomst till hantering av incidenter på enheter, användare och post lådor.</span><span class="sxs-lookup"><span data-stu-id="af1cf-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="af1cf-109">Du kan hantera incidenter genom att välja en incident från **kön med incidenter**.</span><span class="sxs-lookup"><span data-stu-id="af1cf-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="af1cf-110">Du kan redigera namnet på en olycka, lösa det och ange dess klassificering och analys.</span><span class="sxs-lookup"><span data-stu-id="af1cf-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="af1cf-111">Du kan också koppla dig själv, lägga till incident märkningar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="af1cf-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="af1cf-112">I de fall där du skulle vilja flytta aviseringar från en incident till en annan kan du även göra det på fliken aviseringar och på så sätt skapa en större eller mindre olycka som innehåller alla relevanta aviseringar.</span><span class="sxs-lookup"><span data-stu-id="af1cf-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="af1cf-113">Redigera incident namn</span><span class="sxs-lookup"><span data-stu-id="af1cf-113">Edit incident name</span></span>
<span data-ttu-id="af1cf-114">Incidenter tilldelas automatiskt ett namn baserat på notifieringsregler, till exempel antalet slut punkter som påverkas, användare som påverkas, identifierings källor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="af1cf-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="af1cf-115">Då kan du snabbt förstå omfattningen av incidenten.</span><span class="sxs-lookup"><span data-stu-id="af1cf-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="af1cf-116">Till exempel: *flera händelser på flera faser som rapporter ATS av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="af1cf-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="af1cf-117">Du kan ändra namnet på incidenten så att det passar bättre.</span><span class="sxs-lookup"><span data-stu-id="af1cf-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="af1cf-118">Incidenter som fanns före lanseringen av funktionen för automatisk anmälan av tillbud behåller sitt namn.</span><span class="sxs-lookup"><span data-stu-id="af1cf-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="af1cf-119">Koppla incidenter</span><span class="sxs-lookup"><span data-stu-id="af1cf-119">Assign incidents</span></span>
<span data-ttu-id="af1cf-120">Om en olycka ännu inte har tilldelats kan du välja **tilldela till mig** för att koppla dig själv.</span><span class="sxs-lookup"><span data-stu-id="af1cf-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="af1cf-121">Detta innebär att ägandet av inte bara är det som är associerat med den.</span><span class="sxs-lookup"><span data-stu-id="af1cf-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="af1cf-122">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="af1cf-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="af1cf-123">Incident status</span><span class="sxs-lookup"><span data-stu-id="af1cf-123">Incident status</span></span>
<span data-ttu-id="af1cf-124">Du kan kategorisera incidenter (som **aktiva**eller **stängda**) genom att ändra deras status allteftersom undersökningen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="af1cf-124">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="af1cf-125">Det hjälper dig att organisera och hantera hur ditt team kan reagera på händelser.</span><span class="sxs-lookup"><span data-stu-id="af1cf-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="af1cf-126">Ditt SOC analytiker kan till exempel granska brådskande **aktiva** tillbud för dagen och besluta att tilldela dem själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="af1cf-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="af1cf-127">Alternativt kan SOC analytiker ställa in händelsen som **löst** om incidenten har åtgärd ATS.</span><span class="sxs-lookup"><span data-stu-id="af1cf-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="af1cf-128">När du löser ett samtal stängs alla aviseringar som är en del av incidenten och fortfarande öppen.</span><span class="sxs-lookup"><span data-stu-id="af1cf-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="af1cf-129">Klassificering och bestämning</span><span class="sxs-lookup"><span data-stu-id="af1cf-129">Classification and determination</span></span>
<span data-ttu-id="af1cf-130">Du kan välja att inte ange en klassificering eller välja om en incident är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="af1cf-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="af1cf-131">Om du gör det kan teamet se mönster och lära sig mer om dem.</span><span class="sxs-lookup"><span data-stu-id="af1cf-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="af1cf-132">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="af1cf-132">Add comments</span></span>
<span data-ttu-id="af1cf-133">Du kan lägga till kommentarer och Visa historiska händelser om en olycka för att se tidigare gjorda ändringar.</span><span class="sxs-lookup"><span data-stu-id="af1cf-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="af1cf-134">När en ändring eller kommentar görs i en avisering sparas den i avsnittet kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="af1cf-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="af1cf-135">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="af1cf-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="af1cf-136">Lägga till incident koder</span><span class="sxs-lookup"><span data-stu-id="af1cf-136">Add incident tags</span></span>
<span data-ttu-id="af1cf-137">Du kan lägga till egna taggar till en olycka, till exempel för att flagga en grupp med incidenter med gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="af1cf-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="af1cf-138">Du kan senare filtrera händelse kön för alla händelser som innehåller en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="af1cf-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>