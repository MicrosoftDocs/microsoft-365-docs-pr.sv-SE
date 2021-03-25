---
title: Isolera dator-API
description: Lär dig hur du använder Isolate machine API till att isolera en enhet från att komma åt externt nätverk i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, isolera enhet
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
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187842"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="16f0b-104">Isolera dator-API</span><span class="sxs-lookup"><span data-stu-id="16f0b-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="16f0b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="16f0b-105">**Applies to:**</span></span>
- [<span data-ttu-id="16f0b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="16f0b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16f0b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16f0b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="16f0b-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="16f0b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16f0b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="16f0b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="16f0b-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="16f0b-110">API description</span></span>
<span data-ttu-id="16f0b-111">Isolerar en enhet från att komma åt externa nätverk.</span><span class="sxs-lookup"><span data-stu-id="16f0b-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="16f0b-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="16f0b-112">Limitations</span></span>
1. <span data-ttu-id="16f0b-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="16f0b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="16f0b-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="16f0b-114">Permissions</span></span>
<span data-ttu-id="16f0b-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="16f0b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="16f0b-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="16f0b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="16f0b-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="16f0b-117">Permission type</span></span> |   <span data-ttu-id="16f0b-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="16f0b-118">Permission</span></span>  |   <span data-ttu-id="16f0b-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="16f0b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="16f0b-120">Program</span><span class="sxs-lookup"><span data-stu-id="16f0b-120">Application</span></span> |   <span data-ttu-id="16f0b-121">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="16f0b-121">Machine.Isolate</span></span> |   <span data-ttu-id="16f0b-122">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="16f0b-122">'Isolate machine'</span></span>
<span data-ttu-id="16f0b-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="16f0b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="16f0b-124">Dator.Isolera</span><span class="sxs-lookup"><span data-stu-id="16f0b-124">Machine.Isolate</span></span> |  <span data-ttu-id="16f0b-125">'Isolerad maskin'</span><span class="sxs-lookup"><span data-stu-id="16f0b-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="16f0b-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="16f0b-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="16f0b-127">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="16f0b-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="16f0b-128">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="16f0b-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="16f0b-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="16f0b-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="16f0b-130">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="16f0b-130">Request headers</span></span>

<span data-ttu-id="16f0b-131">Namn</span><span class="sxs-lookup"><span data-stu-id="16f0b-131">Name</span></span> | <span data-ttu-id="16f0b-132">Skriv</span><span class="sxs-lookup"><span data-stu-id="16f0b-132">Type</span></span> | <span data-ttu-id="16f0b-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="16f0b-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="16f0b-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="16f0b-134">Authorization</span></span> | <span data-ttu-id="16f0b-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="16f0b-135">String</span></span> | <span data-ttu-id="16f0b-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="16f0b-136">Bearer {token}.</span></span> <span data-ttu-id="16f0b-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="16f0b-137">**Required**.</span></span>
<span data-ttu-id="16f0b-138">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="16f0b-138">Content-Type</span></span> | <span data-ttu-id="16f0b-139">sträng</span><span class="sxs-lookup"><span data-stu-id="16f0b-139">string</span></span> | <span data-ttu-id="16f0b-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="16f0b-140">application/json.</span></span> <span data-ttu-id="16f0b-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="16f0b-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="16f0b-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="16f0b-142">Request body</span></span>
<span data-ttu-id="16f0b-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="16f0b-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="16f0b-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="16f0b-144">Parameter</span></span> | <span data-ttu-id="16f0b-145">Skriv</span><span class="sxs-lookup"><span data-stu-id="16f0b-145">Type</span></span>    | <span data-ttu-id="16f0b-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="16f0b-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="16f0b-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="16f0b-147">Comment</span></span> |   <span data-ttu-id="16f0b-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="16f0b-148">String</span></span> |    <span data-ttu-id="16f0b-149">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="16f0b-149">Comment to associate with the action.</span></span> <span data-ttu-id="16f0b-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="16f0b-150">**Required**.</span></span>
<span data-ttu-id="16f0b-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="16f0b-151">IsolationType</span></span>   | <span data-ttu-id="16f0b-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="16f0b-152">String</span></span> |  <span data-ttu-id="16f0b-153">Typ av avgränsning.</span><span class="sxs-lookup"><span data-stu-id="16f0b-153">Type of the isolation.</span></span> <span data-ttu-id="16f0b-154">Tillåtna värden är: Fullständiga eller Selektiva.</span><span class="sxs-lookup"><span data-stu-id="16f0b-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="16f0b-155">**IsolationType** styr vilken typ av avgränsning som ska utföras och kan vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="16f0b-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="16f0b-156">Fullständig – fullständig avgränsning</span><span class="sxs-lookup"><span data-stu-id="16f0b-156">Full – Full isolation</span></span>
- <span data-ttu-id="16f0b-157">Selektiv – Begränsa endast begränsad uppsättning program från att komma åt nätverket (mer information finns [i Isolera](respond-machine-alerts.md#isolate-devices-from-the-network) enheter från nätverket)</span><span class="sxs-lookup"><span data-stu-id="16f0b-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="16f0b-158">Svar</span><span class="sxs-lookup"><span data-stu-id="16f0b-158">Response</span></span>
<span data-ttu-id="16f0b-159">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="16f0b-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="16f0b-160">Exempel</span><span class="sxs-lookup"><span data-stu-id="16f0b-160">Example</span></span>

<span data-ttu-id="16f0b-161">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="16f0b-161">**Request**</span></span>

<span data-ttu-id="16f0b-162">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="16f0b-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="16f0b-163">Information om hur du släpper en enhet från isolation finns [i Släpp enheten från isolering](unisolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="16f0b-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
