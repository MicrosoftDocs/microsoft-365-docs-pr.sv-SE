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
ms.openlocfilehash: b8f7e3bbb6d2348c3f19e8df251d700d8adf8e33
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808134"
---
# <a name="manage-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="ec201-104">Hantera incidenter i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ec201-104">Manage incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="ec201-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="ec201-105">**Applies to:**</span></span>
- <span data-ttu-id="ec201-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="ec201-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="ec201-107">Hanteringen av incidenter är avgörande för att säkerställa att hoten begränsas och åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="ec201-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="ec201-108">I Microsoft Threat Protection har du åtkomst till hantering av incidenter på enheter, användare och postlådor.</span><span class="sxs-lookup"><span data-stu-id="ec201-108">In Microsoft Threat Protection, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="ec201-109">Du kan hantera incidenter genom att välja en incident från **kön Incidenter**.</span><span class="sxs-lookup"><span data-stu-id="ec201-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="ec201-110">Du kan redigera namnet på en incident, lösa den, ange dess klassificering och bestämning.</span><span class="sxs-lookup"><span data-stu-id="ec201-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="ec201-111">Du kan också tilldela händelsen till dig själv, lägga till incidenttaggar och kommentarer.</span><span class="sxs-lookup"><span data-stu-id="ec201-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="ec201-112">I de fall där du under utredningen vill flytta aviseringar från en incident till en annan kan du också göra det från fliken Aviseringar, vilket skapar en större eller mindre incident som innehåller alla relevanta aviseringar.</span><span class="sxs-lookup"><span data-stu-id="ec201-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="ec201-113">Redigera incidentnamn</span><span class="sxs-lookup"><span data-stu-id="ec201-113">Edit incident name</span></span>
<span data-ttu-id="ec201-114">Som standard tilldelas en incident ett nummer.</span><span class="sxs-lookup"><span data-stu-id="ec201-114">By default, an incident is assigned a number.</span></span> <span data-ttu-id="ec201-115">Du kan ändra incidentnamnet så att det stämmer överens med den namngivningskonvention som du föredrar.</span><span class="sxs-lookup"><span data-stu-id="ec201-115">You can modify the incident name to better align with your preferred naming convention.</span></span>
 
## <a name="assign-incidents"></a><span data-ttu-id="ec201-116">Tilldela incidenter</span><span class="sxs-lookup"><span data-stu-id="ec201-116">Assign incidents</span></span>
<span data-ttu-id="ec201-117">Om en incident ännu inte har tilldelats kan du välja **Tilldela mig** för att tilldela händelsen till dig själv.</span><span class="sxs-lookup"><span data-stu-id="ec201-117">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="ec201-118">Detta förutsätter ägandet av inte bara händelsen, men också alla varningar i samband med den.</span><span class="sxs-lookup"><span data-stu-id="ec201-118">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="ec201-119">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="ec201-119">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="ec201-120">Status för incident</span><span class="sxs-lookup"><span data-stu-id="ec201-120">Incident status</span></span>
<span data-ttu-id="ec201-121">Du kan kategorisera incidenter (som **Aktiv**eller **Löst)** genom att ändra deras status under utredningens gång.</span><span class="sxs-lookup"><span data-stu-id="ec201-121">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="ec201-122">Detta hjälper dig att organisera och hantera hur ditt team kan svara på incidenter.</span><span class="sxs-lookup"><span data-stu-id="ec201-122">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="ec201-123">Till exempel kan din SOC-analytiker granska de brådskande **aktiva** incidenter för dagen och besluta att tilldela dem till sig själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="ec201-123">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="ec201-124">Alternativt kan din SOC-analytiker ange incidenten som **Löst** om incidenten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="ec201-124">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="ec201-125">Om du löser en incident stängs alla aviseringar som ingår i incidenten automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ec201-125">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="ec201-126">Klassificering och bestämning</span><span class="sxs-lookup"><span data-stu-id="ec201-126">Classification and determination</span></span>
<span data-ttu-id="ec201-127">Du kan välja att inte ange en klassificering eller bestämma dig för att ange om en incident är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="ec201-127">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="ec201-128">Detta hjälper teamet att se mönster och lära av dem.</span><span class="sxs-lookup"><span data-stu-id="ec201-128">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="ec201-129">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="ec201-129">Add comments</span></span>
<span data-ttu-id="ec201-130">Du kan lägga till kommentarer och visa historiska händelser om en incident för att se tidigare ändringar som gjorts i den.</span><span class="sxs-lookup"><span data-stu-id="ec201-130">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="ec201-131">När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="ec201-131">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="ec201-132">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="ec201-132">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="ec201-133">Lägga till incidenttaggar</span><span class="sxs-lookup"><span data-stu-id="ec201-133">Add incident tags</span></span>
<span data-ttu-id="ec201-134">Du kan lägga till anpassade taggar i en incident, till exempel för att flagga en grupp incidenter med gemensamma egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ec201-134">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="ec201-135">Du kan senare filtrera incidentkön för alla incidenter som innehåller en specifik tagg.</span><span class="sxs-lookup"><span data-stu-id="ec201-135">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>

