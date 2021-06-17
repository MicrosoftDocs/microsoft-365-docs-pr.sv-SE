---
title: Uppdatera API för dator entitet
description: Lär dig hur du uppdaterar datortaggar med hjälp av detta API. Du kan uppdatera egenskaperna för taggar och enhetsvärde.
keywords: apis, graph api, API som stöds, skaffa, avisering, information, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985772"
---
# <a name="update-machine"></a><span data-ttu-id="897ee-105">Uppdatera dator</span><span class="sxs-lookup"><span data-stu-id="897ee-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="897ee-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="897ee-106">**Applies to:**</span></span>
- [<span data-ttu-id="897ee-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="897ee-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="897ee-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="897ee-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="897ee-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="897ee-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="897ee-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="897ee-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="897ee-111">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="897ee-111">API description</span></span>
<span data-ttu-id="897ee-112">Uppdaterar egenskaper för befintlig [dator.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="897ee-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="897ee-113">Egenskaper som kan uppdateras är: ```machineTags``` och ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="897ee-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="897ee-114">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="897ee-114">Limitations</span></span>
1. <span data-ttu-id="897ee-115">Du kan uppdatera datorer som är tillgängliga i API:et.</span><span class="sxs-lookup"><span data-stu-id="897ee-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="897ee-116">Update machine lägger bara till taggar i taggsamlingen.</span><span class="sxs-lookup"><span data-stu-id="897ee-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="897ee-117">Om det finns taggar måste de inkluderas i taggsamlingen i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="897ee-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="897ee-118">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="897ee-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="897ee-119">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="897ee-119">Permissions</span></span>
<span data-ttu-id="897ee-120">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="897ee-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="897ee-121">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="897ee-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="897ee-122">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="897ee-122">Permission type</span></span> |   <span data-ttu-id="897ee-123">Behörighet</span><span class="sxs-lookup"><span data-stu-id="897ee-123">Permission</span></span>  |   <span data-ttu-id="897ee-124">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="897ee-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="897ee-125">Program</span><span class="sxs-lookup"><span data-stu-id="897ee-125">Application</span></span> |   <span data-ttu-id="897ee-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="897ee-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="897ee-127">"Läsa och skriva maskininformation för alla datorer"</span><span class="sxs-lookup"><span data-stu-id="897ee-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="897ee-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="897ee-128">Delegated (work or school account)</span></span> | <span data-ttu-id="897ee-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="897ee-129">Machine.ReadWrite</span></span> | <span data-ttu-id="897ee-130">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="897ee-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="897ee-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="897ee-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="897ee-132">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar".</span><span class="sxs-lookup"><span data-stu-id="897ee-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="897ee-133">Mer information finns i Skapa [och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="897ee-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="897ee-134">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetens gruppinställningar.</span><span class="sxs-lookup"><span data-stu-id="897ee-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="897ee-135">Mer information finns i Skapa [och hantera enhetsgrupper](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="897ee-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="897ee-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="897ee-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="897ee-137">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="897ee-137">Request headers</span></span>

<span data-ttu-id="897ee-138">Namn</span><span class="sxs-lookup"><span data-stu-id="897ee-138">Name</span></span> | <span data-ttu-id="897ee-139">Typ</span><span class="sxs-lookup"><span data-stu-id="897ee-139">Type</span></span> | <span data-ttu-id="897ee-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="897ee-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="897ee-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="897ee-141">Authorization</span></span> | <span data-ttu-id="897ee-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="897ee-142">String</span></span> | <span data-ttu-id="897ee-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="897ee-143">Bearer {token}.</span></span> <span data-ttu-id="897ee-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="897ee-144">**Required**.</span></span>
<span data-ttu-id="897ee-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="897ee-145">Content-Type</span></span> | <span data-ttu-id="897ee-146">Sträng</span><span class="sxs-lookup"><span data-stu-id="897ee-146">String</span></span> | <span data-ttu-id="897ee-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="897ee-147">application/json.</span></span> <span data-ttu-id="897ee-148">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="897ee-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="897ee-149">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="897ee-149">Request body</span></span>
<span data-ttu-id="897ee-150">Ange värden för de relevanta fält som ska uppdateras i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="897ee-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="897ee-151">Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="897ee-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="897ee-152">För bästa prestanda bör du inte inkludera befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="897ee-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="897ee-153">Egenskap</span><span class="sxs-lookup"><span data-stu-id="897ee-153">Property</span></span> | <span data-ttu-id="897ee-154">Typ</span><span class="sxs-lookup"><span data-stu-id="897ee-154">Type</span></span> | <span data-ttu-id="897ee-155">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="897ee-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="897ee-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="897ee-156">machineTags</span></span> | <span data-ttu-id="897ee-157">Strängsamling</span><span class="sxs-lookup"><span data-stu-id="897ee-157">String collection</span></span> | <span data-ttu-id="897ee-158">Uppsättning [maskintaggar.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="897ee-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="897ee-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="897ee-159">deviceValue</span></span> | <span data-ttu-id="897ee-160">Nullbar uppräkning</span><span class="sxs-lookup"><span data-stu-id="897ee-160">Nullable Enum</span></span> | <span data-ttu-id="897ee-161">Enhetens [värde.](tvm-assign-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="897ee-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="897ee-162">Möjliga värden är: "Normal", "Låg" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="897ee-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="897ee-163">Svar</span><span class="sxs-lookup"><span data-stu-id="897ee-163">Response</span></span>
<span data-ttu-id="897ee-164">Om det lyckas returnerar den här metoden 200 OK, [och](machine.md) datorenheten i svarstexten med de uppdaterade egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="897ee-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="897ee-165">Om insamling av maskintaggar i brödtexten inte innehåller befintliga maskintaggar – 400 ogiltiga indata och ett meddelande om saknade taggar.</span><span class="sxs-lookup"><span data-stu-id="897ee-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="897ee-166">Om ingen dator med det angivna ID:t hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="897ee-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="897ee-167">Exempel</span><span class="sxs-lookup"><span data-stu-id="897ee-167">Example</span></span>

<span data-ttu-id="897ee-168">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="897ee-168">**Request**</span></span>

<span data-ttu-id="897ee-169">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="897ee-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
