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
ms.technology: mde
ms.openlocfilehash: 036eb6f589c13fb9232557c45619829149179148
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199339"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="52c07-104">Släpp enheten från isolations-API:t</span><span class="sxs-lookup"><span data-stu-id="52c07-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52c07-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="52c07-105">**Applies to:**</span></span> 
- [<span data-ttu-id="52c07-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="52c07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="52c07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52c07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="52c07-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="52c07-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="52c07-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="52c07-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="52c07-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="52c07-110">API description</span></span>
<span data-ttu-id="52c07-111">Ångra avgränsning av en enhet.</span><span class="sxs-lookup"><span data-stu-id="52c07-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="52c07-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="52c07-112">Limitations</span></span>
1. <span data-ttu-id="52c07-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="52c07-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="52c07-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="52c07-114">Permissions</span></span>
<span data-ttu-id="52c07-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="52c07-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52c07-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="52c07-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="52c07-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="52c07-117">Permission type</span></span> |   <span data-ttu-id="52c07-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="52c07-118">Permission</span></span>  |   <span data-ttu-id="52c07-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="52c07-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="52c07-120">Program</span><span class="sxs-lookup"><span data-stu-id="52c07-120">Application</span></span> |   <span data-ttu-id="52c07-121">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="52c07-121">Machine.Isolate</span></span> |   <span data-ttu-id="52c07-122">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="52c07-122">'Isolate machine'</span></span>
<span data-ttu-id="52c07-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="52c07-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="52c07-124">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="52c07-124">Machine.Isolate</span></span> |   <span data-ttu-id="52c07-125">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="52c07-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="52c07-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="52c07-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="52c07-127">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="52c07-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="52c07-128">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="52c07-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="52c07-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="52c07-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="52c07-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="52c07-130">Request headers</span></span>

<span data-ttu-id="52c07-131">Namn</span><span class="sxs-lookup"><span data-stu-id="52c07-131">Name</span></span> | <span data-ttu-id="52c07-132">Skriv</span><span class="sxs-lookup"><span data-stu-id="52c07-132">Type</span></span> | <span data-ttu-id="52c07-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="52c07-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="52c07-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="52c07-134">Authorization</span></span> | <span data-ttu-id="52c07-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="52c07-135">String</span></span> | <span data-ttu-id="52c07-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="52c07-136">Bearer {token}.</span></span> <span data-ttu-id="52c07-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="52c07-137">**Required**.</span></span>
<span data-ttu-id="52c07-138">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="52c07-138">Content-Type</span></span> | <span data-ttu-id="52c07-139">sträng</span><span class="sxs-lookup"><span data-stu-id="52c07-139">string</span></span> | <span data-ttu-id="52c07-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="52c07-140">application/json.</span></span> <span data-ttu-id="52c07-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="52c07-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="52c07-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="52c07-142">Request body</span></span>
<span data-ttu-id="52c07-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="52c07-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="52c07-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="52c07-144">Parameter</span></span> | <span data-ttu-id="52c07-145">Skriv</span><span class="sxs-lookup"><span data-stu-id="52c07-145">Type</span></span>    | <span data-ttu-id="52c07-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="52c07-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="52c07-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="52c07-147">Comment</span></span> |   <span data-ttu-id="52c07-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="52c07-148">String</span></span> |    <span data-ttu-id="52c07-149">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="52c07-149">Comment to associate with the action.</span></span> <span data-ttu-id="52c07-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="52c07-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="52c07-151">Svar</span><span class="sxs-lookup"><span data-stu-id="52c07-151">Response</span></span>
<span data-ttu-id="52c07-152">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="52c07-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="52c07-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="52c07-153">Example</span></span>

<span data-ttu-id="52c07-154">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="52c07-154">**Request**</span></span>

<span data-ttu-id="52c07-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="52c07-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="52c07-156">Information om hur du isolerar en enhet finns [i Isolera enhet](isolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="52c07-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

