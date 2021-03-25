---
title: Hitta enheter med tagg-API
description: Hitta alla enheter som innehåller specifc-tagg
keywords: apis, API som stöds, skaffa, enhet, hitta, hitta enhet, efter tagg, tagg
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200155"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="15e57-104">Hitta enheter med tagg-API</span><span class="sxs-lookup"><span data-stu-id="15e57-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15e57-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="15e57-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="15e57-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="15e57-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15e57-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="15e57-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="15e57-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="15e57-108">API description</span></span>
<span data-ttu-id="15e57-109">Hitta [datorer](machine.md) efter [tagg.](machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="15e57-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="15e57-110">```startswith``` stöds.</span><span class="sxs-lookup"><span data-stu-id="15e57-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="15e57-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="15e57-111">Limitations</span></span>
1. <span data-ttu-id="15e57-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="15e57-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="15e57-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="15e57-113">Permissions</span></span>
<span data-ttu-id="15e57-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="15e57-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15e57-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="15e57-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="15e57-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="15e57-116">Permission type</span></span> |   <span data-ttu-id="15e57-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="15e57-117">Permission</span></span>  |   <span data-ttu-id="15e57-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="15e57-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15e57-119">Program</span><span class="sxs-lookup"><span data-stu-id="15e57-119">Application</span></span> |   <span data-ttu-id="15e57-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="15e57-120">Machine.Read.All</span></span> |  <span data-ttu-id="15e57-121">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="15e57-121">'Read all machine profiles'</span></span>
<span data-ttu-id="15e57-122">Program</span><span class="sxs-lookup"><span data-stu-id="15e57-122">Application</span></span> |   <span data-ttu-id="15e57-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="15e57-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="15e57-124">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="15e57-124">'Read and write all machine information'</span></span>
<span data-ttu-id="15e57-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="15e57-125">Delegated (work or school account)</span></span> | <span data-ttu-id="15e57-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="15e57-126">Machine.Read</span></span> | <span data-ttu-id="15e57-127">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="15e57-127">'Read machine information'</span></span>
<span data-ttu-id="15e57-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="15e57-128">Delegated (work or school account)</span></span> | <span data-ttu-id="15e57-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="15e57-129">Machine.ReadWrite</span></span> | <span data-ttu-id="15e57-130">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="15e57-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="15e57-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="15e57-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="15e57-132">Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="15e57-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="15e57-133">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="15e57-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="15e57-134">Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="15e57-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="15e57-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="15e57-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="15e57-136">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="15e57-136">Request headers</span></span>

<span data-ttu-id="15e57-137">Namn</span><span class="sxs-lookup"><span data-stu-id="15e57-137">Name</span></span> | <span data-ttu-id="15e57-138">Skriv</span><span class="sxs-lookup"><span data-stu-id="15e57-138">Type</span></span> | <span data-ttu-id="15e57-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="15e57-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="15e57-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="15e57-140">Authorization</span></span> | <span data-ttu-id="15e57-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="15e57-141">String</span></span> | <span data-ttu-id="15e57-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="15e57-142">Bearer {token}.</span></span> <span data-ttu-id="15e57-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="15e57-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="15e57-144">Begär URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="15e57-144">Request URI parameters</span></span>

<span data-ttu-id="15e57-145">Namn</span><span class="sxs-lookup"><span data-stu-id="15e57-145">Name</span></span> | <span data-ttu-id="15e57-146">Skriv</span><span class="sxs-lookup"><span data-stu-id="15e57-146">Type</span></span> | <span data-ttu-id="15e57-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="15e57-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="15e57-148">tagg</span><span class="sxs-lookup"><span data-stu-id="15e57-148">tag</span></span> | <span data-ttu-id="15e57-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="15e57-149">String</span></span> | <span data-ttu-id="15e57-150">Taggnamnet.</span><span class="sxs-lookup"><span data-stu-id="15e57-150">The tag name.</span></span> <span data-ttu-id="15e57-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="15e57-151">**Required**.</span></span>
<span data-ttu-id="15e57-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="15e57-152">useStartsWithFilter</span></span> | <span data-ttu-id="15e57-153">Boolesk</span><span class="sxs-lookup"><span data-stu-id="15e57-153">Boolean</span></span> | <span data-ttu-id="15e57-154">När denna är autent inställd på sant hittar sökningen alla enheter med taggnamn som börjar med den givna taggen i frågan.</span><span class="sxs-lookup"><span data-stu-id="15e57-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="15e57-155">Falskt som standard.</span><span class="sxs-lookup"><span data-stu-id="15e57-155">Defaults to false.</span></span> <span data-ttu-id="15e57-156">**Valfritt.**</span><span class="sxs-lookup"><span data-stu-id="15e57-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="15e57-157">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="15e57-157">Request body</span></span>
<span data-ttu-id="15e57-158">Tom</span><span class="sxs-lookup"><span data-stu-id="15e57-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="15e57-159">Svar</span><span class="sxs-lookup"><span data-stu-id="15e57-159">Response</span></span>
<span data-ttu-id="15e57-160">Om det lyckas – 200 OK med en lista över maskinerna i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="15e57-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="15e57-161">Exempel</span><span class="sxs-lookup"><span data-stu-id="15e57-161">Example</span></span>

<span data-ttu-id="15e57-162">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="15e57-162">**Request**</span></span>

<span data-ttu-id="15e57-163">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="15e57-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```