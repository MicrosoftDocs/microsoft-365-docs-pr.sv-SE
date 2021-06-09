---
title: Hämta API för användarrelaterade datorer
description: Läs om hur du använder API:t hämta användarrelaterade maskiner för att hämta en samling enheter som är relaterade till ett användar-ID i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, användare, användarrelaterade aviseringar
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
ms.openlocfilehash: 230af2311c52437e01cdb28d823236347cf34b8f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769908"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="1d48a-104">Hämta API för användarrelaterade datorer</span><span class="sxs-lookup"><span data-stu-id="1d48a-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d48a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1d48a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d48a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1d48a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1d48a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d48a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1d48a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1d48a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1d48a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1d48a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1d48a-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d48a-110">API description</span></span>
<span data-ttu-id="1d48a-111">Hämtar en samling enheter som är relaterade till ett visst användar-ID.</span><span class="sxs-lookup"><span data-stu-id="1d48a-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="1d48a-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="1d48a-112">Limitations</span></span>
1. <span data-ttu-id="1d48a-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="1d48a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1d48a-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1d48a-114">Permissions</span></span>
<span data-ttu-id="1d48a-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="1d48a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d48a-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1d48a-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1d48a-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="1d48a-117">Permission type</span></span> |   <span data-ttu-id="1d48a-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="1d48a-118">Permission</span></span>  |   <span data-ttu-id="1d48a-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="1d48a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1d48a-120">Program</span><span class="sxs-lookup"><span data-stu-id="1d48a-120">Application</span></span> |   <span data-ttu-id="1d48a-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="1d48a-121">Machine.Read.All</span></span> |  <span data-ttu-id="1d48a-122">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="1d48a-122">'Read all machine profiles'</span></span>
<span data-ttu-id="1d48a-123">Program</span><span class="sxs-lookup"><span data-stu-id="1d48a-123">Application</span></span> |   <span data-ttu-id="1d48a-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1d48a-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="1d48a-125">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="1d48a-125">'Read and write all machine information'</span></span>
<span data-ttu-id="1d48a-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1d48a-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1d48a-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="1d48a-127">Machine.Read</span></span> | <span data-ttu-id="1d48a-128">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="1d48a-128">'Read machine information'</span></span>
<span data-ttu-id="1d48a-129">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1d48a-129">Delegated (work or school account)</span></span> | <span data-ttu-id="1d48a-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1d48a-130">Machine.ReadWrite</span></span> | <span data-ttu-id="1d48a-131">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="1d48a-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="1d48a-132">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="1d48a-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1d48a-133">Användaren måste ha minst följande rollbehörighet: "Visa data".</span><span class="sxs-lookup"><span data-stu-id="1d48a-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="1d48a-134">Mer information finns i [Skapa och hantera roller](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="1d48a-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="1d48a-135">Svaret omfattar endast enheter som användaren kan komma åt, baserat på enhetens gruppinställningar.</span><span class="sxs-lookup"><span data-stu-id="1d48a-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="1d48a-136">Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="1d48a-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="1d48a-137">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="1d48a-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="1d48a-138">**ID:t är inte det fullständiga UPN, utan bara användarnamnet. (Till exempel för att hämta datorer för user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="1d48a-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="1d48a-139">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="1d48a-139">Request headers</span></span>

<span data-ttu-id="1d48a-140">Namn</span><span class="sxs-lookup"><span data-stu-id="1d48a-140">Name</span></span> | <span data-ttu-id="1d48a-141">Typ</span><span class="sxs-lookup"><span data-stu-id="1d48a-141">Type</span></span> | <span data-ttu-id="1d48a-142">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1d48a-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="1d48a-143">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="1d48a-143">Authorization</span></span> | <span data-ttu-id="1d48a-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="1d48a-144">String</span></span> | <span data-ttu-id="1d48a-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1d48a-145">Bearer {token}.</span></span> <span data-ttu-id="1d48a-146">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="1d48a-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1d48a-147">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="1d48a-147">Request body</span></span>
<span data-ttu-id="1d48a-148">Tom</span><span class="sxs-lookup"><span data-stu-id="1d48a-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1d48a-149">Svar</span><span class="sxs-lookup"><span data-stu-id="1d48a-149">Response</span></span>
<span data-ttu-id="1d48a-150">Om det lyckas och användaren finns - 200 OK med en lista [över maskinenheter](machine.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="1d48a-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="1d48a-151">Om användaren inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="1d48a-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="1d48a-152">Exempel</span><span class="sxs-lookup"><span data-stu-id="1d48a-152">Example</span></span>

<span data-ttu-id="1d48a-153">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="1d48a-153">**Request**</span></span>

<span data-ttu-id="1d48a-154">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="1d48a-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
