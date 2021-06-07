---
title: API för insamling av undersökningspaket
description: Använd detta API för att skapa anrop som är relaterade till insamling av ett undersökningspaket från en enhet.
keywords: apis, graph api, api som stöds, paket för insamling av undersökning
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0083d806f3e52307e6dce30f74e255073a09c16a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770511"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="a7b2b-104">API för insamling av undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="a7b2b-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a7b2b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a7b2b-105">**Applies to:**</span></span>
- [<span data-ttu-id="a7b2b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a7b2b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a7b2b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a7b2b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="a7b2b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a7b2b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a7b2b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a7b2b-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="a7b2b-110">API description</span></span>
<span data-ttu-id="a7b2b-111">Samla in undersökningspaket från en enhet.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="a7b2b-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="a7b2b-112">Limitations</span></span>
1. <span data-ttu-id="a7b2b-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a7b2b-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a7b2b-114">Permissions</span></span>
<span data-ttu-id="a7b2b-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a7b2b-116">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a7b2b-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a7b2b-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="a7b2b-117">Permission type</span></span> |   <span data-ttu-id="a7b2b-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a7b2b-118">Permission</span></span>  |   <span data-ttu-id="a7b2b-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="a7b2b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a7b2b-120">Program</span><span class="sxs-lookup"><span data-stu-id="a7b2b-120">Application</span></span> |   <span data-ttu-id="a7b2b-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="a7b2b-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="a7b2b-122">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="a7b2b-122">'Collect forensics'</span></span>
<span data-ttu-id="a7b2b-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a7b2b-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="a7b2b-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="a7b2b-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="a7b2b-125">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="a7b2b-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="a7b2b-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="a7b2b-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a7b2b-127">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="a7b2b-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a7b2b-128">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="a7b2b-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a7b2b-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="a7b2b-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="a7b2b-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="a7b2b-130">Request headers</span></span>

<span data-ttu-id="a7b2b-131">Namn</span><span class="sxs-lookup"><span data-stu-id="a7b2b-131">Name</span></span> | <span data-ttu-id="a7b2b-132">Typ</span><span class="sxs-lookup"><span data-stu-id="a7b2b-132">Type</span></span> | <span data-ttu-id="a7b2b-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a7b2b-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7b2b-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="a7b2b-134">Authorization</span></span> | <span data-ttu-id="a7b2b-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="a7b2b-135">String</span></span> | <span data-ttu-id="a7b2b-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-136">Bearer {token}.</span></span> <span data-ttu-id="a7b2b-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a7b2b-137">**Required**.</span></span>
<span data-ttu-id="a7b2b-138">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="a7b2b-138">Content-Type</span></span> | <span data-ttu-id="a7b2b-139">sträng</span><span class="sxs-lookup"><span data-stu-id="a7b2b-139">string</span></span> | <span data-ttu-id="a7b2b-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-140">application/json.</span></span> <span data-ttu-id="a7b2b-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a7b2b-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a7b2b-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="a7b2b-142">Request body</span></span>
<span data-ttu-id="a7b2b-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="a7b2b-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a7b2b-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7b2b-144">Parameter</span></span> | <span data-ttu-id="a7b2b-145">Typ</span><span class="sxs-lookup"><span data-stu-id="a7b2b-145">Type</span></span>    | <span data-ttu-id="a7b2b-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a7b2b-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="a7b2b-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="a7b2b-147">Comment</span></span> |   <span data-ttu-id="a7b2b-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="a7b2b-148">String</span></span> |    <span data-ttu-id="a7b2b-149">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-149">Comment to associate with the action.</span></span> <span data-ttu-id="a7b2b-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a7b2b-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="a7b2b-151">Svar</span><span class="sxs-lookup"><span data-stu-id="a7b2b-151">Response</span></span>
<span data-ttu-id="a7b2b-152">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="a7b2b-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="a7b2b-153">Example</span></span>

<span data-ttu-id="a7b2b-154">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="a7b2b-154">**Request**</span></span>

<span data-ttu-id="a7b2b-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="a7b2b-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
