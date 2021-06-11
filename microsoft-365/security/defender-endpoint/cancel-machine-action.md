---
title: Api:t Avbryt datoråtgärd
description: Lär dig hur du avbryter en maskinåtgärd som redan startats
keywords: apis, graph api,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879802"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="1da11-104">Api:t Avbryt datoråtgärd</span><span class="sxs-lookup"><span data-stu-id="1da11-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1da11-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1da11-105">**Applies to:**</span></span>
- [<span data-ttu-id="1da11-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1da11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="1da11-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1da11-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1da11-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1da11-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1da11-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="1da11-109">API description</span></span>

<span data-ttu-id="1da11-110">Avbryta en maskinåtgärd som redan startats och som ännu inte är i slutänden (slutförd, avbruten, misslyckades).</span><span class="sxs-lookup"><span data-stu-id="1da11-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="1da11-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="1da11-111">Limitations</span></span>

1.  <span data-ttu-id="1da11-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="1da11-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="1da11-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1da11-113">Permissions</span></span>

<span data-ttu-id="1da11-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="1da11-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1da11-115">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1da11-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="1da11-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="1da11-116">Permission    type</span></span>     |     <span data-ttu-id="1da11-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="1da11-117">Permission</span></span>     |    <span data-ttu-id="1da11-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="1da11-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="1da11-119">Program</span><span class="sxs-lookup"><span data-stu-id="1da11-119">Application</span></span>    |    <br><span data-ttu-id="1da11-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="1da11-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="1da11-121">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="1da11-121">Machine.Isolate</span></span>   <br><span data-ttu-id="1da11-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="1da11-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="1da11-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="1da11-123">Machine.Scan</span></span><br>   <span data-ttu-id="1da11-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="1da11-124">Machine.Offboard</span></span><br>   <span data-ttu-id="1da11-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="1da11-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="1da11-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="1da11-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="1da11-127">Samla in en forensisk information</span><span class="sxs-lookup"><span data-stu-id="1da11-127">Collect   forensics</span></span>   <br><span data-ttu-id="1da11-128">Isolera datorn</span><span class="sxs-lookup"><span data-stu-id="1da11-128">Isolate   machine</span></span><br><span data-ttu-id="1da11-129">Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="1da11-129">Restrict   code execution</span></span><br>  <span data-ttu-id="1da11-130">Skanna dator</span><span class="sxs-lookup"><span data-stu-id="1da11-130">Scan   machine</span></span><br>  <span data-ttu-id="1da11-131">Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="1da11-131">Offboard   machine</span></span><br>   <span data-ttu-id="1da11-132">Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="1da11-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="1da11-133">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="1da11-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="1da11-134">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1da11-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="1da11-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="1da11-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="1da11-136">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="1da11-136">Machine.Isolate</span></span>    <br><span data-ttu-id="1da11-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="1da11-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="1da11-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="1da11-138">Machine.Scan</span></span><br>   <span data-ttu-id="1da11-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="1da11-139">Machine.Offboard</span></span><br>   <span data-ttu-id="1da11-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="1da11-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="1da11-141">Samla in en forensisk information</span><span class="sxs-lookup"><span data-stu-id="1da11-141">Collect   forensics</span></span><br>   <span data-ttu-id="1da11-142">Isolera datorn</span><span class="sxs-lookup"><span data-stu-id="1da11-142">Isolate   machine</span></span><br>  <span data-ttu-id="1da11-143">Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="1da11-143">Restrict   code execution</span></span><br> <span data-ttu-id="1da11-144">Skanna dator</span><span class="sxs-lookup"><span data-stu-id="1da11-144">Scan   machine</span></span><br><span data-ttu-id="1da11-145">Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="1da11-145">Offboard   machine</span></span><br> <span data-ttu-id="1da11-146">Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="1da11-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="1da11-147">Köra livesvar på en viss dator</span><span class="sxs-lookup"><span data-stu-id="1da11-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="1da11-148">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="1da11-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="1da11-149">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="1da11-149">Request headers</span></span>

| <span data-ttu-id="1da11-150">Namn</span><span class="sxs-lookup"><span data-stu-id="1da11-150">Name</span></span>      | <span data-ttu-id="1da11-151">Typ</span><span class="sxs-lookup"><span data-stu-id="1da11-151">Type</span></span> | <span data-ttu-id="1da11-152">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1da11-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="1da11-153">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="1da11-153">Authorization</span></span> | <span data-ttu-id="1da11-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="1da11-154">String</span></span>   | <span data-ttu-id="1da11-155">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1da11-155">Bearer {token}.</span></span> <span data-ttu-id="1da11-156">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="1da11-156">Required.</span></span>   |
| <span data-ttu-id="1da11-157">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="1da11-157">Content-Type</span></span>  | <span data-ttu-id="1da11-158">sträng</span><span class="sxs-lookup"><span data-stu-id="1da11-158">string</span></span>   | <span data-ttu-id="1da11-159">application/json.</span><span class="sxs-lookup"><span data-stu-id="1da11-159">application/json.</span></span> <span data-ttu-id="1da11-160">Obligatoriskt.</span><span class="sxs-lookup"><span data-stu-id="1da11-160">Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="1da11-161">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="1da11-161">Request body</span></span>

| <span data-ttu-id="1da11-162">Parameter</span><span class="sxs-lookup"><span data-stu-id="1da11-162">Parameter</span></span> | <span data-ttu-id="1da11-163">Typ</span><span class="sxs-lookup"><span data-stu-id="1da11-163">Type</span></span> | <span data-ttu-id="1da11-164">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1da11-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="1da11-165">Kommentar</span><span class="sxs-lookup"><span data-stu-id="1da11-165">Comment</span></span>       | <span data-ttu-id="1da11-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="1da11-166">String</span></span>   | <span data-ttu-id="1da11-167">Kommentar som ska kopplas till annulleringsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="1da11-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="1da11-168">Svar</span><span class="sxs-lookup"><span data-stu-id="1da11-168">Response</span></span>

<span data-ttu-id="1da11-169">Om det lyckas returnerar den här metoden 200, OK-svarskod med en datoråtgärdsentitet.</span><span class="sxs-lookup"><span data-stu-id="1da11-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="1da11-170">Om maskinåtgärdsentitet med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="1da11-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="1da11-171">Exempel</span><span class="sxs-lookup"><span data-stu-id="1da11-171">Example</span></span>

<span data-ttu-id="1da11-172">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="1da11-172">**Request**</span></span>

<span data-ttu-id="1da11-173">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="1da11-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="1da11-174">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="1da11-174">Related topic</span></span>

- [<span data-ttu-id="1da11-175">Skaffa API för maskinåtgärd</span><span class="sxs-lookup"><span data-stu-id="1da11-175">Get machine action API</span></span>](get-machineaction-object.md)