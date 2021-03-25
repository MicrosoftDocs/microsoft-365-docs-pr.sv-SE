---
title: API för batchuppdateringsaviseringsenheter
description: Lär dig hur du uppdaterar Microsoft Defender för slutpunktsaviseringar i en batch med hjälp av detta API. Du kan uppdatera status, determination, klassificering och tilldeladeTill-egenskaper.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167086"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="32bb8-105">Batchuppdateringsaviseringar</span><span class="sxs-lookup"><span data-stu-id="32bb8-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="32bb8-106">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="32bb8-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="32bb8-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="32bb8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="32bb8-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="32bb8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="32bb8-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="32bb8-109">API description</span></span>
<span data-ttu-id="32bb8-110">Uppdaterar egenskaper för en batch med befintliga [aviseringar.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="32bb8-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="32bb8-111">**Kommentarsinskick** är tillgängligt med eller utan uppdatering av egenskaper.</span><span class="sxs-lookup"><span data-stu-id="32bb8-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="32bb8-112">Egenskaper som kan uppdateras är: `status` `determination` , och `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="32bb8-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="32bb8-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="32bb8-113">Limitations</span></span>
1. <span data-ttu-id="32bb8-114">Du kan uppdatera aviseringar som är tillgängliga i API:et.</span><span class="sxs-lookup"><span data-stu-id="32bb8-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="32bb8-115">Mer information finns i Listaviseringar. [](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="32bb8-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="32bb8-116">Begränsningar i kursen för detta API är 10 samtal per minut och 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="32bb8-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="32bb8-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="32bb8-117">Permissions</span></span>
<span data-ttu-id="32bb8-118">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="32bb8-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="32bb8-119">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="32bb8-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="32bb8-120">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="32bb8-120">Permission type</span></span> |   <span data-ttu-id="32bb8-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="32bb8-121">Permission</span></span>  |   <span data-ttu-id="32bb8-122">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="32bb8-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="32bb8-123">Program</span><span class="sxs-lookup"><span data-stu-id="32bb8-123">Application</span></span> |   <span data-ttu-id="32bb8-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="32bb8-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="32bb8-125">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="32bb8-125">'Read and write all alerts'</span></span>
<span data-ttu-id="32bb8-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="32bb8-126">Delegated (work or school account)</span></span> | <span data-ttu-id="32bb8-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="32bb8-127">Alert.ReadWrite</span></span> | <span data-ttu-id="32bb8-128">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="32bb8-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="32bb8-129">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="32bb8-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="32bb8-130">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="32bb8-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="32bb8-131">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="32bb8-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="32bb8-132">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="32bb8-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="32bb8-133">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="32bb8-133">Request headers</span></span>

<span data-ttu-id="32bb8-134">Namn</span><span class="sxs-lookup"><span data-stu-id="32bb8-134">Name</span></span> | <span data-ttu-id="32bb8-135">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="32bb8-135">Type</span></span> | <span data-ttu-id="32bb8-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="32bb8-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="32bb8-137">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="32bb8-137">Authorization</span></span> | <span data-ttu-id="32bb8-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-138">String</span></span> | <span data-ttu-id="32bb8-139">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="32bb8-139">Bearer {token}.</span></span> <span data-ttu-id="32bb8-140">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="32bb8-140">**Required**.</span></span>
<span data-ttu-id="32bb8-141">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="32bb8-141">Content-Type</span></span> | <span data-ttu-id="32bb8-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-142">String</span></span> | <span data-ttu-id="32bb8-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="32bb8-143">application/json.</span></span> <span data-ttu-id="32bb8-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="32bb8-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="32bb8-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="32bb8-145">Request body</span></span>
<span data-ttu-id="32bb8-146">Ange i meddelandetexten för begäran de aviseringar som ska uppdateras och värdena för de relevanta fält som du vill uppdatera för dessa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="32bb8-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="32bb8-147">Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="32bb8-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="32bb8-148">För bästa prestanda bör du inte inkludera befintliga värden som inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="32bb8-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="32bb8-149">Egenskap</span><span class="sxs-lookup"><span data-stu-id="32bb8-149">Property</span></span> | <span data-ttu-id="32bb8-150">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="32bb8-150">Type</span></span> | <span data-ttu-id="32bb8-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="32bb8-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="32bb8-152">alertids</span><span class="sxs-lookup"><span data-stu-id="32bb8-152">alertIds</span></span> | <span data-ttu-id="32bb8-153">&lt;Liststräng&gt;</span><span class="sxs-lookup"><span data-stu-id="32bb8-153">List&lt;String&gt;</span></span>| <span data-ttu-id="32bb8-154">En lista med DE IDENTIFIERINGS-identifieringar av aviseringar som ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="32bb8-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="32bb8-155">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="32bb8-155">**Required**</span></span>
<span data-ttu-id="32bb8-156">status</span><span class="sxs-lookup"><span data-stu-id="32bb8-156">status</span></span> | <span data-ttu-id="32bb8-157">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-157">String</span></span> | <span data-ttu-id="32bb8-158">Anger uppdaterad status för angivna aviseringar.</span><span class="sxs-lookup"><span data-stu-id="32bb8-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="32bb8-159">Egenskapsvärdena är: "Ny", "InProgress" och "Löst".</span><span class="sxs-lookup"><span data-stu-id="32bb8-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="32bb8-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="32bb8-160">assignedTo</span></span> | <span data-ttu-id="32bb8-161">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-161">String</span></span> | <span data-ttu-id="32bb8-162">Ägare av angivna aviseringar</span><span class="sxs-lookup"><span data-stu-id="32bb8-162">Owner of the specified alerts</span></span>
<span data-ttu-id="32bb8-163">klassificering</span><span class="sxs-lookup"><span data-stu-id="32bb8-163">classification</span></span> | <span data-ttu-id="32bb8-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-164">String</span></span> | <span data-ttu-id="32bb8-165">Anger specifikationen för de angivna aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="32bb8-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="32bb8-166">Egenskapsvärdena är: "Okänt", "FalsktPositiv", "SantPositiv".</span><span class="sxs-lookup"><span data-stu-id="32bb8-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="32bb8-167">determination</span><span class="sxs-lookup"><span data-stu-id="32bb8-167">determination</span></span> | <span data-ttu-id="32bb8-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-168">String</span></span> | <span data-ttu-id="32bb8-169">Anger vilka aviseringar som ska avgöras.</span><span class="sxs-lookup"><span data-stu-id="32bb8-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="32bb8-170">Egenskapsvärdena är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="32bb8-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="32bb8-171">kommentar</span><span class="sxs-lookup"><span data-stu-id="32bb8-171">comment</span></span> | <span data-ttu-id="32bb8-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="32bb8-172">String</span></span> | <span data-ttu-id="32bb8-173">Kommentar som ska läggas till i de angivna aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="32bb8-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="32bb8-174">Svar</span><span class="sxs-lookup"><span data-stu-id="32bb8-174">Response</span></span>
<span data-ttu-id="32bb8-175">Om det lyckas returnerar den här metoden 200 OK, med en tom svarstext.</span><span class="sxs-lookup"><span data-stu-id="32bb8-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="32bb8-176">Exempel</span><span class="sxs-lookup"><span data-stu-id="32bb8-176">Example</span></span>

<span data-ttu-id="32bb8-177">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="32bb8-177">**Request**</span></span>

<span data-ttu-id="32bb8-178">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="32bb8-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
