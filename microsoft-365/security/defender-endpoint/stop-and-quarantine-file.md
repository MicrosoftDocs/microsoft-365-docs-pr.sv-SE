---
title: API:t för att stoppa och sätta i karantän
description: Lär dig hur du slutar köra en fil på en enhet och ta bort filen i Microsoft Defender för Slutpunkt. Se ett exempel.
keywords: apis, graph api, API som stöds, stoppa och sätt filen i karantän
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199735"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="6d1c0-105">API:t för att stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="6d1c0-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d1c0-106">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6d1c0-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6d1c0-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6d1c0-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d1c0-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6d1c0-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d1c0-109">API description</span></span>
<span data-ttu-id="6d1c0-110">Sluta utföra en fil på en enhet och ta bort den.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="6d1c0-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="6d1c0-111">Limitations</span></span>
1. <span data-ttu-id="6d1c0-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="6d1c0-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="6d1c0-113">Permissions</span></span>
<span data-ttu-id="6d1c0-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6d1c0-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6d1c0-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="6d1c0-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="6d1c0-116">Permission type</span></span> |   <span data-ttu-id="6d1c0-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="6d1c0-117">Permission</span></span>  |   <span data-ttu-id="6d1c0-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="6d1c0-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6d1c0-119">Program</span><span class="sxs-lookup"><span data-stu-id="6d1c0-119">Application</span></span> |   <span data-ttu-id="6d1c0-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="6d1c0-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="6d1c0-121">Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="6d1c0-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="6d1c0-122">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="6d1c0-122">Delegated (work or school account)</span></span> | <span data-ttu-id="6d1c0-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="6d1c0-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="6d1c0-124">Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="6d1c0-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="6d1c0-125">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="6d1c0-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="6d1c0-126">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="6d1c0-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="6d1c0-127">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="6d1c0-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="6d1c0-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="6d1c0-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="6d1c0-129">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="6d1c0-129">Request headers</span></span>

<span data-ttu-id="6d1c0-130">Namn</span><span class="sxs-lookup"><span data-stu-id="6d1c0-130">Name</span></span> | <span data-ttu-id="6d1c0-131">Skriv</span><span class="sxs-lookup"><span data-stu-id="6d1c0-131">Type</span></span> | <span data-ttu-id="6d1c0-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d1c0-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="6d1c0-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="6d1c0-133">Authorization</span></span> | <span data-ttu-id="6d1c0-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="6d1c0-134">String</span></span> | <span data-ttu-id="6d1c0-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-135">Bearer {token}.</span></span> <span data-ttu-id="6d1c0-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6d1c0-136">**Required**.</span></span>
<span data-ttu-id="6d1c0-137">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="6d1c0-137">Content-Type</span></span> | <span data-ttu-id="6d1c0-138">sträng</span><span class="sxs-lookup"><span data-stu-id="6d1c0-138">string</span></span> | <span data-ttu-id="6d1c0-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-139">application/json.</span></span> <span data-ttu-id="6d1c0-140">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6d1c0-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6d1c0-141">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="6d1c0-141">Request body</span></span>
<span data-ttu-id="6d1c0-142">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="6d1c0-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6d1c0-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d1c0-143">Parameter</span></span> | <span data-ttu-id="6d1c0-144">Skriv</span><span class="sxs-lookup"><span data-stu-id="6d1c0-144">Type</span></span>    | <span data-ttu-id="6d1c0-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6d1c0-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="6d1c0-146">Kommentar</span><span class="sxs-lookup"><span data-stu-id="6d1c0-146">Comment</span></span> |   <span data-ttu-id="6d1c0-147">Sträng</span><span class="sxs-lookup"><span data-stu-id="6d1c0-147">String</span></span> |    <span data-ttu-id="6d1c0-148">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-148">Comment to associate with the action.</span></span> <span data-ttu-id="6d1c0-149">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6d1c0-149">**Required**.</span></span>
<span data-ttu-id="6d1c0-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="6d1c0-150">Sha1</span></span> |  <span data-ttu-id="6d1c0-151">Sträng</span><span class="sxs-lookup"><span data-stu-id="6d1c0-151">String</span></span>   | <span data-ttu-id="6d1c0-152">Skuggning1 av filen för att stoppa och sätta i karantän på enheten.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="6d1c0-153">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="6d1c0-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="6d1c0-154">Svar</span><span class="sxs-lookup"><span data-stu-id="6d1c0-154">Response</span></span>
<span data-ttu-id="6d1c0-155">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="6d1c0-156">Exempel</span><span class="sxs-lookup"><span data-stu-id="6d1c0-156">Example</span></span>

<span data-ttu-id="6d1c0-157">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="6d1c0-157">**Request**</span></span>

<span data-ttu-id="6d1c0-158">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="6d1c0-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
