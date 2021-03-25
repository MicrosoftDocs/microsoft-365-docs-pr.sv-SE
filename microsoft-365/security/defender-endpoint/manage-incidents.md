---
title: Hantera MICROSOFT Defender ATP-incidenter
description: Hantera ärenden genom att tilldela den, uppdatera dess status eller ange dess klassificering.
keywords: incidenter, hantera, tilldela, status, klassificering, sant meddelande, falsk avisering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185821"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="cc6b0-104">Hantera Microsoft Defender för slutpunktsincidenter</span><span class="sxs-lookup"><span data-stu-id="cc6b0-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cc6b0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cc6b0-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc6b0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc6b0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc6b0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc6b0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cc6b0-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cc6b0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc6b0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cc6b0-110">Hantering av incidenter är en viktig del av varje cybersäkerhetsåtgärd.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="cc6b0-111">Du kan hantera incidenter genom att välja en incident **i kön Incidenter** eller **i fönstret Incidenthantering.**</span><span class="sxs-lookup"><span data-stu-id="cc6b0-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="cc6b0-112">Om du väljer en incident **i kön Incidenter** visas **fönstret Incidenthantering** där du kan öppna incidentsidan för mer information.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Bild av hanteringsfönstret för incidenter](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="cc6b0-114">Du kan tilldela incidenter till dig själv, ändra status och klassificering, byta namn på eller kommentera dem för att hålla reda på förloppet.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="cc6b0-115">För att du snabbt ska kunna se fler incidentnamn genereras incidentnamn automatiskt baserat på aviseringsattribut, till exempel antalet slutpunkter som påverkas, användare som påverkas, identifieringskällor eller kategorier.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="cc6b0-116">På så sätt kan du snabbt förstå incidentens omfattning.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="cc6b0-117">Till exempel: *Incident i flera steg på flera slutpunkter som rapporterats av flera källor.*</span><span class="sxs-lookup"><span data-stu-id="cc6b0-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="cc6b0-118">Incidenter som tidigare fanns före automatisk namngivning för incidenter behåller sina namn.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Bild på informationssidan om incidenter](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="cc6b0-120">Tilldela ärenden</span><span class="sxs-lookup"><span data-stu-id="cc6b0-120">Assign incidents</span></span>
<span data-ttu-id="cc6b0-121">Om en incident inte har tilldelats ännu kan du välja Tilldela **till mig och** tilldela incidenten till dig själv.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="cc6b0-122">När du gör det förutsätts att du äger inte bara händelsen utan även alla aviseringar som hör till den.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="cc6b0-123">Ange status och klassificering</span><span class="sxs-lookup"><span data-stu-id="cc6b0-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="cc6b0-124">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="cc6b0-124">Incident status</span></span>
<span data-ttu-id="cc6b0-125">Du kan kategorisera incidenter (som **Aktiva** eller **lösta**) genom att ändra deras status allt eftersom undersökningen fortskrider.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="cc6b0-126">På så sätt kan du organisera och hantera hur ditt team kan svara på incidenter.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="cc6b0-127">Din SOC-analytiker kan till  exempel granska brådskande aktiva incidenter för dagen och bestämma sig för att tilldela dem till sig själv för undersökning.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="cc6b0-128">Alternativt kan soc-analytikern ange incidenten som **Löst** om incidenten har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="cc6b0-129">Klassificering</span><span class="sxs-lookup"><span data-stu-id="cc6b0-129">Classification</span></span>
<span data-ttu-id="cc6b0-130">Du kan välja att inte ange någon klassificering eller att ange om incidenten är sann eller falsk.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="cc6b0-131">Det gör det lättare för teamet att se mönster och lära sig av dem.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="cc6b0-132">Lägga till kommentarer</span><span class="sxs-lookup"><span data-stu-id="cc6b0-132">Add comments</span></span>
<span data-ttu-id="cc6b0-133">Du kan lägga till kommentarer och visa historiska händelser om en händelse om du vill se tidigare ändringar i den.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="cc6b0-134">När en ändring eller kommentar görs i en avisering registreras den i avsnittet Kommentarer och historik.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="cc6b0-135">Tillagda kommentarer visas direkt i fönstret.</span><span class="sxs-lookup"><span data-stu-id="cc6b0-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="cc6b0-136">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="cc6b0-136">Related topics</span></span>
- [<span data-ttu-id="cc6b0-137">Incidentkö</span><span class="sxs-lookup"><span data-stu-id="cc6b0-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="cc6b0-138">Visa och ordna kö för incidenter</span><span class="sxs-lookup"><span data-stu-id="cc6b0-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="cc6b0-139">Undersöka incidenter</span><span class="sxs-lookup"><span data-stu-id="cc6b0-139">Investigate incidents</span></span>](investigate-incidents.md)
