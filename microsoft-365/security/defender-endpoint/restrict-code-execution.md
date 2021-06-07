---
title: API för att begränsa programkörning
description: Använd det här API:et för att skapa anrop som begränsar ett program så att det inte körs.
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
ms.openlocfilehash: 7195e91a3a9b7aef6977c925f2c8689d3e461815
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771579"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="34750-104">API för att begränsa programkörning</span><span class="sxs-lookup"><span data-stu-id="34750-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34750-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="34750-105">**Applies to:**</span></span>
- [<span data-ttu-id="34750-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="34750-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34750-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34750-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="34750-108">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="34750-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="34750-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="34750-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="34750-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="34750-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="34750-111">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="34750-111">API description</span></span>
<span data-ttu-id="34750-112">Begränsa körningen av alla program på enheten utom en fördefinierad uppsättning.</span><span class="sxs-lookup"><span data-stu-id="34750-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="34750-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="34750-113">Limitations</span></span>
1. <span data-ttu-id="34750-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="34750-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="34750-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="34750-115">Permissions</span></span>
<span data-ttu-id="34750-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="34750-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34750-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="34750-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="34750-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="34750-118">Permission type</span></span> |   <span data-ttu-id="34750-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="34750-119">Permission</span></span>  |   <span data-ttu-id="34750-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="34750-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="34750-121">Program</span><span class="sxs-lookup"><span data-stu-id="34750-121">Application</span></span> |   <span data-ttu-id="34750-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="34750-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="34750-123">Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="34750-123">'Restrict code execution'</span></span>
<span data-ttu-id="34750-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="34750-124">Delegated (work or school account)</span></span> | <span data-ttu-id="34750-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="34750-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="34750-126">Begränsa kodkörning</span><span class="sxs-lookup"><span data-stu-id="34750-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="34750-127">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="34750-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="34750-128">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="34750-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="34750-129">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="34750-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="34750-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="34750-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="34750-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="34750-131">Request headers</span></span>

<span data-ttu-id="34750-132">Namn</span><span class="sxs-lookup"><span data-stu-id="34750-132">Name</span></span> | <span data-ttu-id="34750-133">Typ</span><span class="sxs-lookup"><span data-stu-id="34750-133">Type</span></span> | <span data-ttu-id="34750-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="34750-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="34750-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="34750-135">Authorization</span></span> | <span data-ttu-id="34750-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="34750-136">String</span></span> | <span data-ttu-id="34750-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="34750-137">Bearer {token}.</span></span> <span data-ttu-id="34750-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="34750-138">**Required**.</span></span>
<span data-ttu-id="34750-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="34750-139">Content-Type</span></span> | <span data-ttu-id="34750-140">sträng</span><span class="sxs-lookup"><span data-stu-id="34750-140">string</span></span> | <span data-ttu-id="34750-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="34750-141">application/json.</span></span> <span data-ttu-id="34750-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="34750-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="34750-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="34750-143">Request body</span></span>
<span data-ttu-id="34750-144">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="34750-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="34750-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="34750-145">Parameter</span></span> | <span data-ttu-id="34750-146">Typ</span><span class="sxs-lookup"><span data-stu-id="34750-146">Type</span></span>    | <span data-ttu-id="34750-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="34750-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="34750-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="34750-148">Comment</span></span> |   <span data-ttu-id="34750-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="34750-149">String</span></span> |    <span data-ttu-id="34750-150">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="34750-150">Comment to associate with the action.</span></span> <span data-ttu-id="34750-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="34750-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="34750-152">Svar</span><span class="sxs-lookup"><span data-stu-id="34750-152">Response</span></span>
<span data-ttu-id="34750-153">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="34750-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="34750-154">Exempel</span><span class="sxs-lookup"><span data-stu-id="34750-154">Example</span></span>

<span data-ttu-id="34750-155">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="34750-155">**Request**</span></span>

<span data-ttu-id="34750-156">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="34750-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="34750-157">Information om hur du tar bort kodkörningsbegränsningar från en enhet finns [i Ta bort appbegränsning](unrestrict-code-execution.md).</span><span class="sxs-lookup"><span data-stu-id="34750-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
