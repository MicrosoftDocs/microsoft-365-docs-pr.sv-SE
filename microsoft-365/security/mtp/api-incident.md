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
ms.openlocfilehash: 310e3105c973223ea79373d770eb10f7753b917e
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650582"
---
# <a name="incident-resource-type"></a><span data-ttu-id="13bf8-104">Resurs typ för incident</span><span class="sxs-lookup"><span data-stu-id="13bf8-104">Incident resource type</span></span>

<span data-ttu-id="13bf8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="13bf8-105">**Applies to:**</span></span>
- <span data-ttu-id="13bf8-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="13bf8-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="13bf8-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="13bf8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="13bf8-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="13bf8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="13bf8-109">Verifieringsmetoder</span><span class="sxs-lookup"><span data-stu-id="13bf8-109">Methods</span></span>

<span data-ttu-id="13bf8-110">Metod</span><span class="sxs-lookup"><span data-stu-id="13bf8-110">Method</span></span> |<span data-ttu-id="13bf8-111">Returtyp</span><span class="sxs-lookup"><span data-stu-id="13bf8-111">Return Type</span></span> |<span data-ttu-id="13bf8-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="13bf8-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="13bf8-113">List händelser</span><span class="sxs-lookup"><span data-stu-id="13bf8-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="13bf8-114">[Incident](api-incident.md) lista</span><span class="sxs-lookup"><span data-stu-id="13bf8-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="13bf8-115">Få en lista över incidenter.</span><span class="sxs-lookup"><span data-stu-id="13bf8-115">Get a list of incidents.</span></span>
[<span data-ttu-id="13bf8-116">Uppdatera incident</span><span class="sxs-lookup"><span data-stu-id="13bf8-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="13bf8-117">Händelse</span><span class="sxs-lookup"><span data-stu-id="13bf8-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="13bf8-118">Uppdatera specifik incident.</span><span class="sxs-lookup"><span data-stu-id="13bf8-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="13bf8-119">Fjärråtkomstsegenskaper</span><span class="sxs-lookup"><span data-stu-id="13bf8-119">Properties</span></span>

<span data-ttu-id="13bf8-120">Egenskap</span><span class="sxs-lookup"><span data-stu-id="13bf8-120">Property</span></span> |    <span data-ttu-id="13bf8-121">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="13bf8-121">Type</span></span>    |    <span data-ttu-id="13bf8-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="13bf8-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="13bf8-123">incidentId</span><span class="sxs-lookup"><span data-stu-id="13bf8-123">incidentId</span></span> | <span data-ttu-id="13bf8-124">tids</span><span class="sxs-lookup"><span data-stu-id="13bf8-124">long</span></span> | <span data-ttu-id="13bf8-125">Unikt ID för incidenten.</span><span class="sxs-lookup"><span data-stu-id="13bf8-125">Incident unique ID.</span></span>
<span data-ttu-id="13bf8-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="13bf8-126">redirectIncidentId</span></span> | <span data-ttu-id="13bf8-127">null-värde långa</span><span class="sxs-lookup"><span data-stu-id="13bf8-127">nullable long</span></span> | <span data-ttu-id="13bf8-128">Incident-ID för den aktuella incidenten slogs samman till.</span><span class="sxs-lookup"><span data-stu-id="13bf8-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="13bf8-129">incidentName</span><span class="sxs-lookup"><span data-stu-id="13bf8-129">incidentName</span></span> | <span data-ttu-id="13bf8-130">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="13bf8-130">string</span></span> | <span data-ttu-id="13bf8-131">Namnet på incidenten.</span><span class="sxs-lookup"><span data-stu-id="13bf8-131">The name of the Incident.</span></span>
<span data-ttu-id="13bf8-132">createdTime</span><span class="sxs-lookup"><span data-stu-id="13bf8-132">createdTime</span></span> | <span data-ttu-id="13bf8-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="13bf8-133">DateTimeOffset</span></span> | <span data-ttu-id="13bf8-134">Datum och tid (i UTC) då incidenten skapades.</span><span class="sxs-lookup"><span data-stu-id="13bf8-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="13bf8-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="13bf8-135">lastUpdateTime</span></span> | <span data-ttu-id="13bf8-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="13bf8-136">DateTimeOffset</span></span> | <span data-ttu-id="13bf8-137">Datum och tid (i UTC) då incidenten senast uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="13bf8-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="13bf8-138">Tilldelat</span><span class="sxs-lookup"><span data-stu-id="13bf8-138">assignedTo</span></span> | <span data-ttu-id="13bf8-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="13bf8-139">string</span></span> | <span data-ttu-id="13bf8-140">Ägaren till incidenten.</span><span class="sxs-lookup"><span data-stu-id="13bf8-140">Owner of the Incident.</span></span>
<span data-ttu-id="13bf8-141">allvarlighets grad</span><span class="sxs-lookup"><span data-stu-id="13bf8-141">severity</span></span> | <span data-ttu-id="13bf8-142">Enum</span><span class="sxs-lookup"><span data-stu-id="13bf8-142">Enum</span></span> | <span data-ttu-id="13bf8-143">Allvarlighets grad för incidenten.</span><span class="sxs-lookup"><span data-stu-id="13bf8-143">Severity of the Incident.</span></span> <span data-ttu-id="13bf8-144">Möjliga värden är: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` och ```High``` .</span><span class="sxs-lookup"><span data-stu-id="13bf8-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="13bf8-145">status</span><span class="sxs-lookup"><span data-stu-id="13bf8-145">status</span></span> | <span data-ttu-id="13bf8-146">Enum</span><span class="sxs-lookup"><span data-stu-id="13bf8-146">Enum</span></span> | <span data-ttu-id="13bf8-147">Anger den aktuella statusen för incidenten.</span><span class="sxs-lookup"><span data-stu-id="13bf8-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="13bf8-148">Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="13bf8-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="13bf8-149">nomenklatur</span><span class="sxs-lookup"><span data-stu-id="13bf8-149">classification</span></span> | <span data-ttu-id="13bf8-150">Enum</span><span class="sxs-lookup"><span data-stu-id="13bf8-150">Enum</span></span> | <span data-ttu-id="13bf8-151">Specifikation av felet.</span><span class="sxs-lookup"><span data-stu-id="13bf8-151">Specification of the incident.</span></span> <span data-ttu-id="13bf8-152">Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .</span><span class="sxs-lookup"><span data-stu-id="13bf8-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="13bf8-153">bedömning</span><span class="sxs-lookup"><span data-stu-id="13bf8-153">determination</span></span> | <span data-ttu-id="13bf8-154">Enum</span><span class="sxs-lookup"><span data-stu-id="13bf8-154">Enum</span></span> | <span data-ttu-id="13bf8-155">Anger hur incidenten ska visas.</span><span class="sxs-lookup"><span data-stu-id="13bf8-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="13bf8-156">Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .</span><span class="sxs-lookup"><span data-stu-id="13bf8-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="13bf8-157">taggen</span><span class="sxs-lookup"><span data-stu-id="13bf8-157">tags</span></span> | <span data-ttu-id="13bf8-158">sträng lista</span><span class="sxs-lookup"><span data-stu-id="13bf8-158">string List</span></span> | <span data-ttu-id="13bf8-159">Lista över incident koder.</span><span class="sxs-lookup"><span data-stu-id="13bf8-159">List of Incident tags.</span></span>
<span data-ttu-id="13bf8-160">larm</span><span class="sxs-lookup"><span data-stu-id="13bf8-160">alerts</span></span> | <span data-ttu-id="13bf8-161">Aviserings lista</span><span class="sxs-lookup"><span data-stu-id="13bf8-161">Alert List</span></span> | <span data-ttu-id="13bf8-162">Lista med relaterade aviseringar.</span><span class="sxs-lookup"><span data-stu-id="13bf8-162">List of related alerts.</span></span> <span data-ttu-id="13bf8-163">Se exemplen på API-dokumentation för [samtal](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="13bf8-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>