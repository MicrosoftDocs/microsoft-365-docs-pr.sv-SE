---
title: Släpp enheten från isolations-API:t
description: Använd detta API för att skapa anrop som relaterar till att frigöra en enhet från isolering.
keywords: apis, graph api, API som stöds, ta bort enheten från isolation
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771279"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="bd9b9-104">Släpp enheten från isolations-API:t</span><span class="sxs-lookup"><span data-stu-id="bd9b9-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd9b9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bd9b9-105">**Applies to:**</span></span> 
- [<span data-ttu-id="bd9b9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd9b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bd9b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd9b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="bd9b9-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bd9b9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd9b9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="bd9b9-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="bd9b9-110">API description</span></span>
<span data-ttu-id="bd9b9-111">Ångra avgränsning av en enhet.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="bd9b9-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="bd9b9-112">Limitations</span></span>
1. <span data-ttu-id="bd9b9-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="bd9b9-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="bd9b9-114">Permissions</span></span>
<span data-ttu-id="bd9b9-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bd9b9-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bd9b9-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bd9b9-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="bd9b9-117">Permission type</span></span> |   <span data-ttu-id="bd9b9-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="bd9b9-118">Permission</span></span>  |   <span data-ttu-id="bd9b9-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="bd9b9-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bd9b9-120">Program</span><span class="sxs-lookup"><span data-stu-id="bd9b9-120">Application</span></span> |   <span data-ttu-id="bd9b9-121">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="bd9b9-121">Machine.Isolate</span></span> |   <span data-ttu-id="bd9b9-122">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="bd9b9-122">'Isolate machine'</span></span>
<span data-ttu-id="bd9b9-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="bd9b9-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="bd9b9-124">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="bd9b9-124">Machine.Isolate</span></span> |   <span data-ttu-id="bd9b9-125">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="bd9b9-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="bd9b9-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="bd9b9-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="bd9b9-127">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="bd9b9-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="bd9b9-128">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="bd9b9-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="bd9b9-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="bd9b9-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="bd9b9-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="bd9b9-130">Request headers</span></span>

<span data-ttu-id="bd9b9-131">Namn</span><span class="sxs-lookup"><span data-stu-id="bd9b9-131">Name</span></span> | <span data-ttu-id="bd9b9-132">Typ</span><span class="sxs-lookup"><span data-stu-id="bd9b9-132">Type</span></span> | <span data-ttu-id="bd9b9-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bd9b9-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="bd9b9-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="bd9b9-134">Authorization</span></span> | <span data-ttu-id="bd9b9-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="bd9b9-135">String</span></span> | <span data-ttu-id="bd9b9-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-136">Bearer {token}.</span></span> <span data-ttu-id="bd9b9-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="bd9b9-137">**Required**.</span></span>
<span data-ttu-id="bd9b9-138">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="bd9b9-138">Content-Type</span></span> | <span data-ttu-id="bd9b9-139">sträng</span><span class="sxs-lookup"><span data-stu-id="bd9b9-139">string</span></span> | <span data-ttu-id="bd9b9-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-140">application/json.</span></span> <span data-ttu-id="bd9b9-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="bd9b9-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="bd9b9-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="bd9b9-142">Request body</span></span>
<span data-ttu-id="bd9b9-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="bd9b9-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="bd9b9-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd9b9-144">Parameter</span></span> | <span data-ttu-id="bd9b9-145">Typ</span><span class="sxs-lookup"><span data-stu-id="bd9b9-145">Type</span></span>    | <span data-ttu-id="bd9b9-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bd9b9-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="bd9b9-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="bd9b9-147">Comment</span></span> |   <span data-ttu-id="bd9b9-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="bd9b9-148">String</span></span> |    <span data-ttu-id="bd9b9-149">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-149">Comment to associate with the action.</span></span> <span data-ttu-id="bd9b9-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="bd9b9-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="bd9b9-151">Svar</span><span class="sxs-lookup"><span data-stu-id="bd9b9-151">Response</span></span>
<span data-ttu-id="bd9b9-152">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="bd9b9-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="bd9b9-153">Example</span></span>

<span data-ttu-id="bd9b9-154">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="bd9b9-154">**Request**</span></span>

<span data-ttu-id="bd9b9-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="bd9b9-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="bd9b9-156">Information om hur du isolerar en enhet finns [i Isolera enhet](isolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="bd9b9-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

