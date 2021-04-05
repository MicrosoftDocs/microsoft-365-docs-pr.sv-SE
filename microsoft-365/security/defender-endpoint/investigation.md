---
title: Resurstyp för undersökning
description: Microsoft Defender för entitet för undersökning av slutpunkt.
keywords: apis, graph api, api som stöds, skaffa, aviseringar, undersökningar
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 3872976717a5b472ab8d471db7eff9975dbc2258
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587689"
---
# <a name="investigation-resource-type"></a><span data-ttu-id="f2b54-104">Resurstyp för undersökning</span><span class="sxs-lookup"><span data-stu-id="f2b54-104">Investigation resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f2b54-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f2b54-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2b54-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2b54-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f2b54-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2b54-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2b54-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f2b54-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2b54-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f2b54-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f2b54-110">Representerar en automatiserad undersökningsentitet i Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="f2b54-110">Represent an Automated Investigation entity in Defender for Endpoint.</span></span>
<br> <span data-ttu-id="f2b54-111">Mer information [finns i Översikt över](automated-investigations.md) automatiserade undersökningar.</span><span class="sxs-lookup"><span data-stu-id="f2b54-111">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>

## <a name="methods"></a><span data-ttu-id="f2b54-112">Metoder</span><span class="sxs-lookup"><span data-stu-id="f2b54-112">Methods</span></span>
<span data-ttu-id="f2b54-113">Metod</span><span class="sxs-lookup"><span data-stu-id="f2b54-113">Method</span></span>|<span data-ttu-id="f2b54-114">Returtyp</span><span class="sxs-lookup"><span data-stu-id="f2b54-114">Return Type</span></span> |<span data-ttu-id="f2b54-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f2b54-115">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f2b54-116">Listundersökningar</span><span class="sxs-lookup"><span data-stu-id="f2b54-116">List Investigations</span></span>](get-investigation-collection.md) | <span data-ttu-id="f2b54-117">Samling för undersökning</span><span class="sxs-lookup"><span data-stu-id="f2b54-117">Investigation collection</span></span> | <span data-ttu-id="f2b54-118">Hämta undersökningssamling</span><span class="sxs-lookup"><span data-stu-id="f2b54-118">Get collection of Investigation</span></span>
[<span data-ttu-id="f2b54-119">Få en enda undersökning</span><span class="sxs-lookup"><span data-stu-id="f2b54-119">Get single Investigation</span></span>](get-investigation-object.md) | <span data-ttu-id="f2b54-120">Undersökningsentitet</span><span class="sxs-lookup"><span data-stu-id="f2b54-120">Investigation entity</span></span> | <span data-ttu-id="f2b54-121">Får en enda undersökningsentitet.</span><span class="sxs-lookup"><span data-stu-id="f2b54-121">Gets single Investigation entity.</span></span>
[<span data-ttu-id="f2b54-122">Starta undersökning</span><span class="sxs-lookup"><span data-stu-id="f2b54-122">Start Investigation</span></span>](initiate-autoir-investigation.md) | <span data-ttu-id="f2b54-123">Undersökningsentitet</span><span class="sxs-lookup"><span data-stu-id="f2b54-123">Investigation entity</span></span> | <span data-ttu-id="f2b54-124">Startar undersökning på en enhet.</span><span class="sxs-lookup"><span data-stu-id="f2b54-124">Starts Investigation on a device.</span></span>


## <a name="properties"></a><span data-ttu-id="f2b54-125">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="f2b54-125">Properties</span></span>
<span data-ttu-id="f2b54-126">Egenskap</span><span class="sxs-lookup"><span data-stu-id="f2b54-126">Property</span></span> |  <span data-ttu-id="f2b54-127">Skriv</span><span class="sxs-lookup"><span data-stu-id="f2b54-127">Type</span></span>    |   <span data-ttu-id="f2b54-128">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f2b54-128">Description</span></span>
:---|:---|:---
<span data-ttu-id="f2b54-129">id</span><span class="sxs-lookup"><span data-stu-id="f2b54-129">id</span></span> | <span data-ttu-id="f2b54-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-130">String</span></span> | <span data-ttu-id="f2b54-131">Identiteten för undersökningsentitet.</span><span class="sxs-lookup"><span data-stu-id="f2b54-131">Identity of the investigation entity.</span></span> 
<span data-ttu-id="f2b54-132">startTime</span><span class="sxs-lookup"><span data-stu-id="f2b54-132">startTime</span></span> | <span data-ttu-id="f2b54-133">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="f2b54-133">DateTime Nullable</span></span> | <span data-ttu-id="f2b54-134">Datum och tid då undersökningen skapades.</span><span class="sxs-lookup"><span data-stu-id="f2b54-134">The date and time when the investigation was created.</span></span> 
<span data-ttu-id="f2b54-135">endTime</span><span class="sxs-lookup"><span data-stu-id="f2b54-135">endTime</span></span> | <span data-ttu-id="f2b54-136">DateTime Nullable</span><span class="sxs-lookup"><span data-stu-id="f2b54-136">DateTime Nullable</span></span> | <span data-ttu-id="f2b54-137">Datum och tid då undersökningen slutfördes.</span><span class="sxs-lookup"><span data-stu-id="f2b54-137">The date and time when the investigation was completed.</span></span> 
<span data-ttu-id="f2b54-138">cancelledBy</span><span class="sxs-lookup"><span data-stu-id="f2b54-138">cancelledBy</span></span> | <span data-ttu-id="f2b54-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-139">String</span></span> | <span data-ttu-id="f2b54-140">ID för den användare/det program som avbröt undersökningen.</span><span class="sxs-lookup"><span data-stu-id="f2b54-140">The ID of the user/application that canceled that investigation.</span></span> 
<span data-ttu-id="f2b54-141">investigationState</span><span class="sxs-lookup"><span data-stu-id="f2b54-141">investigationState</span></span> | <span data-ttu-id="f2b54-142">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="f2b54-142">Enum</span></span> | <span data-ttu-id="f2b54-143">Den aktuella undersökningstillståndet.</span><span class="sxs-lookup"><span data-stu-id="f2b54-143">The current state of the investigation.</span></span> <span data-ttu-id="f2b54-144">Möjliga värden är: "Okänt", "Avslutat", "SuccessfullyRemediated", 'SuppressedAlert', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="f2b54-144">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="f2b54-145">statusDetaljer</span><span class="sxs-lookup"><span data-stu-id="f2b54-145">statusDetails</span></span> | <span data-ttu-id="f2b54-146">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-146">String</span></span> | <span data-ttu-id="f2b54-147">Ytterligare information om undersökningstillståndet.</span><span class="sxs-lookup"><span data-stu-id="f2b54-147">Additional information about the state of the investigation.</span></span>
<span data-ttu-id="f2b54-148">machineId</span><span class="sxs-lookup"><span data-stu-id="f2b54-148">machineId</span></span> | <span data-ttu-id="f2b54-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-149">String</span></span> | <span data-ttu-id="f2b54-150">ID för enheten där undersökningen utförs.</span><span class="sxs-lookup"><span data-stu-id="f2b54-150">The ID of the device on which the investigation is executed.</span></span>
<span data-ttu-id="f2b54-151">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="f2b54-151">computerDnsName</span></span> | <span data-ttu-id="f2b54-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-152">String</span></span> | <span data-ttu-id="f2b54-153">Namnet på enheten där undersökningen utförs.</span><span class="sxs-lookup"><span data-stu-id="f2b54-153">The name of the device on which the investigation is executed.</span></span>
<span data-ttu-id="f2b54-154">triggeringAlertId</span><span class="sxs-lookup"><span data-stu-id="f2b54-154">triggeringAlertId</span></span> | <span data-ttu-id="f2b54-155">Sträng</span><span class="sxs-lookup"><span data-stu-id="f2b54-155">String</span></span> | <span data-ttu-id="f2b54-156">ID för den varning som utlöste undersökningen.</span><span class="sxs-lookup"><span data-stu-id="f2b54-156">The ID of the alert that triggered the investigation.</span></span>


## <a name="json-representation"></a><span data-ttu-id="f2b54-157">Json-representation</span><span class="sxs-lookup"><span data-stu-id="f2b54-157">Json representation</span></span>

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
