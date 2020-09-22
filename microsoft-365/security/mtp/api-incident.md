---
title: Resurs typ för incidenten i Microsoft Threat Protection API
description: Lär dig mer om metoderna och egenskaperna för resurs typen incident i Microsoft Threat Protection
keywords: incident, incidenter, API
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201309"
---
# <a name="incident-resource-type"></a><span data-ttu-id="a5151-104">Resurs typ för incident</span><span class="sxs-lookup"><span data-stu-id="a5151-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a5151-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5151-105">**Applies to:**</span></span>
- <span data-ttu-id="a5151-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="a5151-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="a5151-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="a5151-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a5151-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="a5151-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="a5151-109">Verifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="a5151-109">Methods</span></span>

<span data-ttu-id="a5151-110">Metod</span><span class="sxs-lookup"><span data-stu-id="a5151-110">Method</span></span> |<span data-ttu-id="a5151-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="a5151-111">Return Type</span></span> |<span data-ttu-id="a5151-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5151-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="a5151-113">Lista incidenter</span><span class="sxs-lookup"><span data-stu-id="a5151-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="a5151-114">[Incident](api-incident.md) lista</span><span class="sxs-lookup"><span data-stu-id="a5151-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="a5151-115">Få en lista över incidenter.</span><span class="sxs-lookup"><span data-stu-id="a5151-115">Get a list of incidents.</span></span>
[<span data-ttu-id="a5151-116">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="a5151-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="a5151-117">Händelse</span><span class="sxs-lookup"><span data-stu-id="a5151-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="a5151-118">Uppdatera specifik incident.</span><span class="sxs-lookup"><span data-stu-id="a5151-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="a5151-119">Fjärråtkomstsegenskaper</span><span class="sxs-lookup"><span data-stu-id="a5151-119">Properties</span></span>

<span data-ttu-id="a5151-120">Egenskap</span><span class="sxs-lookup"><span data-stu-id="a5151-120">Property</span></span> |    <span data-ttu-id="a5151-121">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="a5151-121">Type</span></span>    |    <span data-ttu-id="a5151-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5151-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="a5151-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="a5151-123">incidentId</span></span> | <span data-ttu-id="a5151-124">tids</span><span class="sxs-lookup"><span data-stu-id="a5151-124">long</span></span> | <span data-ttu-id="a5151-125">Unikt ID för incidenten.</span><span class="sxs-lookup"><span data-stu-id="a5151-125">Incident unique ID.</span></span>
<span data-ttu-id="a5151-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="a5151-126">redirectIncidentId</span></span> | <span data-ttu-id="a5151-127">null-värde långa</span><span class="sxs-lookup"><span data-stu-id="a5151-127">nullable long</span></span> | <span data-ttu-id="a5151-128">Incident-ID för den aktuella incidenten slogs samman till.</span><span class="sxs-lookup"><span data-stu-id="a5151-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="a5151-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="a5151-129">incidentName</span></span> | <span data-ttu-id="a5151-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a5151-130">string</span></span> | <span data-ttu-id="a5151-131">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="a5151-131">The name of the Incident.</span></span>
<span data-ttu-id="a5151-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="a5151-132">createdTime</span></span> | <span data-ttu-id="a5151-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a5151-133">DateTimeOffset</span></span> | <span data-ttu-id="a5151-134">Datum och tid (i UTC) då incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="a5151-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="a5151-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="a5151-135">lastUpdateTime</span></span> | <span data-ttu-id="a5151-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="a5151-136">DateTimeOffset</span></span> | <span data-ttu-id="a5151-137">Datum och tid (i UTC) då incidenten senast uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="a5151-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="a5151-138">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="a5151-138">assignedTo</span></span> | <span data-ttu-id="a5151-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="a5151-139">string</span></span> | <span data-ttu-id="a5151-140">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="a5151-140">Owner of the Incident.</span></span>
<span data-ttu-id="a5151-141">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="a5151-141">severity</span></span> | <span data-ttu-id="a5151-142">Enum</span><span class="sxs-lookup"><span data-stu-id="a5151-142">Enum</span></span> | <span data-ttu-id="a5151-143">Allvarlighets grad för incidenten.</span><span class="sxs-lookup"><span data-stu-id="a5151-143">Severity of the Incident.</span></span> <span data-ttu-id="a5151-144">Möjliga värden är: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` och ```High``` .</span><span class="sxs-lookup"><span data-stu-id="a5151-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="a5151-145">status</span><span class="sxs-lookup"><span data-stu-id="a5151-145">status</span></span> | <span data-ttu-id="a5151-146">Enum</span><span class="sxs-lookup"><span data-stu-id="a5151-146">Enum</span></span> | <span data-ttu-id="a5151-147">Anger den aktuella statusen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="a5151-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="a5151-148">Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="a5151-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="a5151-149">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="a5151-149">classification</span></span> | <span data-ttu-id="a5151-150">Enum</span><span class="sxs-lookup"><span data-stu-id="a5151-150">Enum</span></span> | <span data-ttu-id="a5151-151">Specifikation av felet.</span><span class="sxs-lookup"><span data-stu-id="a5151-151">Specification of the incident.</span></span> <span data-ttu-id="a5151-152">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="a5151-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="a5151-153">bedömning</span><span class="sxs-lookup"><span data-stu-id="a5151-153">determination</span></span> | <span data-ttu-id="a5151-154">Enum</span><span class="sxs-lookup"><span data-stu-id="a5151-154">Enum</span></span> | <span data-ttu-id="a5151-155">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="a5151-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="a5151-156">Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="a5151-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="a5151-157">taggen</span><span class="sxs-lookup"><span data-stu-id="a5151-157">tags</span></span> | <span data-ttu-id="a5151-158">sträng lista</span><span class="sxs-lookup"><span data-stu-id="a5151-158">string List</span></span> | <span data-ttu-id="a5151-159">Lista över incident koder.</span><span class="sxs-lookup"><span data-stu-id="a5151-159">List of Incident tags.</span></span>
<span data-ttu-id="a5151-160">larm</span><span class="sxs-lookup"><span data-stu-id="a5151-160">alerts</span></span> | <span data-ttu-id="a5151-161">Aviserings lista</span><span class="sxs-lookup"><span data-stu-id="a5151-161">Alert List</span></span> | <span data-ttu-id="a5151-162">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="a5151-162">List of related alerts.</span></span> <span data-ttu-id="a5151-163">Se exemplen på API-dokumentation för [samtal](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="a5151-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
