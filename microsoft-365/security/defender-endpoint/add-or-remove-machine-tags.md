---
title: Api för att lägga till eller ta bort maskintaggar
description: Lär dig hur du använder API:t för att lägga till eller ta bort maskintaggar för att lägga till eller ta bort en tagg för en dator i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, taggar, maskintaggar
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
ms.openlocfilehash: 3818fc0050790b2c3b307f95ee0760c516cbf893
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769827"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="83180-104">Api för att lägga till eller ta bort maskintaggar</span><span class="sxs-lookup"><span data-stu-id="83180-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="83180-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="83180-105">**Applies to:**</span></span>

- [<span data-ttu-id="83180-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="83180-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="83180-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="83180-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83180-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="83180-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="83180-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="83180-109">API description</span></span>

<span data-ttu-id="83180-110">Lägger till eller tar bort en tagg till en viss [dator.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="83180-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="83180-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="83180-111">Limitations</span></span>

1. <span data-ttu-id="83180-112">Du kan publicera på datorer som senast sågs enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="83180-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="83180-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="83180-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="83180-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="83180-114">Permissions</span></span>

<span data-ttu-id="83180-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="83180-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="83180-116">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="83180-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="83180-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="83180-117">Permission type</span></span> |    <span data-ttu-id="83180-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="83180-118">Permission</span></span>    |    <span data-ttu-id="83180-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="83180-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="83180-120">Program</span><span class="sxs-lookup"><span data-stu-id="83180-120">Application</span></span> |    <span data-ttu-id="83180-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="83180-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="83180-122">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="83180-122">'Read and write all machine information'</span></span>
<span data-ttu-id="83180-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="83180-123">Delegated (work or school account)</span></span> | <span data-ttu-id="83180-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="83180-124">Machine.ReadWrite</span></span> | <span data-ttu-id="83180-125">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="83180-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="83180-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="83180-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="83180-127">Användaren måste ha minst följande rollbehörighet: "Hantera säkerhetsinställning".</span><span class="sxs-lookup"><span data-stu-id="83180-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="83180-128">Mer information finns i [Skapa och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="83180-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="83180-129">Användaren måste ha åtkomst till datorn baserat på datorns gruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera datorgrupper)</span><span class="sxs-lookup"><span data-stu-id="83180-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="83180-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="83180-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="83180-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="83180-131">Request headers</span></span>

<span data-ttu-id="83180-132">Namn</span><span class="sxs-lookup"><span data-stu-id="83180-132">Name</span></span> | <span data-ttu-id="83180-133">Typ</span><span class="sxs-lookup"><span data-stu-id="83180-133">Type</span></span> | <span data-ttu-id="83180-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="83180-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="83180-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="83180-135">Authorization</span></span> | <span data-ttu-id="83180-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="83180-136">String</span></span> | <span data-ttu-id="83180-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="83180-137">Bearer {token}.</span></span> <span data-ttu-id="83180-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="83180-138">**Required**.</span></span>
<span data-ttu-id="83180-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="83180-139">Content-Type</span></span> | <span data-ttu-id="83180-140">sträng</span><span class="sxs-lookup"><span data-stu-id="83180-140">string</span></span> | <span data-ttu-id="83180-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="83180-141">application/json.</span></span> <span data-ttu-id="83180-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="83180-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="83180-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="83180-143">Request body</span></span>

<span data-ttu-id="83180-144">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="83180-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="83180-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="83180-145">Parameter</span></span> |    <span data-ttu-id="83180-146">Typ</span><span class="sxs-lookup"><span data-stu-id="83180-146">Type</span></span>    | <span data-ttu-id="83180-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="83180-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="83180-148">Värde</span><span class="sxs-lookup"><span data-stu-id="83180-148">Value</span></span> |    <span data-ttu-id="83180-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="83180-149">String</span></span> |    <span data-ttu-id="83180-150">Taggnamnet.</span><span class="sxs-lookup"><span data-stu-id="83180-150">The tag name.</span></span> <span data-ttu-id="83180-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="83180-151">**Required**.</span></span>
<span data-ttu-id="83180-152">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="83180-152">Action</span></span>    | <span data-ttu-id="83180-153">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="83180-153">Enum</span></span> |    <span data-ttu-id="83180-154">Lägg till eller ta bort.</span><span class="sxs-lookup"><span data-stu-id="83180-154">Add or Remove.</span></span> <span data-ttu-id="83180-155">Tillåtna värden är: "Lägg till" eller "Ta bort".</span><span class="sxs-lookup"><span data-stu-id="83180-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="83180-156">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="83180-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="83180-157">Svar</span><span class="sxs-lookup"><span data-stu-id="83180-157">Response</span></span>

<span data-ttu-id="83180-158">Om svaret lyckas returnerar den här metoden 200 – OK-svarskod och den uppdaterade datorn i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="83180-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="83180-159">Exempel</span><span class="sxs-lookup"><span data-stu-id="83180-159">Example</span></span>

<span data-ttu-id="83180-160">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="83180-160">**Request**</span></span>

<span data-ttu-id="83180-161">Här är ett exempel på en begäran som lägger till en maskintagg.</span><span class="sxs-lookup"><span data-stu-id="83180-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="83180-162">Om du vill ta bort datortaggen ställer du in åtgärden på Ta bort i stället för Lägg till i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="83180-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
