---
title: Uppdatera API för avisering entitet
description: Lär dig hur du uppdaterar en Microsoft Defender för slutpunktsavisering med hjälp av detta API. Du kan uppdatera status, determination, klassificering och tilldeladeTill-egenskaper.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768936"
---
# <a name="update-alert"></a><span data-ttu-id="4dfd4-105">Uppdateringsavisering</span><span class="sxs-lookup"><span data-stu-id="4dfd4-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4dfd4-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4dfd4-106">**Applies to:**</span></span>
- [<span data-ttu-id="4dfd4-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4dfd4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="4dfd4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4dfd4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4dfd4-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="4dfd4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4dfd4-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4dfd4-111">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="4dfd4-111">API description</span></span>
<span data-ttu-id="4dfd4-112">Uppdaterar egenskaper för befintlig [avisering](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="4dfd4-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="4dfd4-113">**Kommentarsinskick** är tillgängligt med eller utan uppdatering av egenskaper.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="4dfd4-114">Egenskaper som kan uppdateras är: ```status``` ```determination``` , och ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="4dfd4-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="4dfd4-115">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="4dfd4-115">Limitations</span></span>
1. <span data-ttu-id="4dfd4-116">Du kan uppdatera aviseringar som är tillgängliga i API:et.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="4dfd4-117">Mer information finns i Listaviseringar. [](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="4dfd4-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="4dfd4-118">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4dfd4-119">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="4dfd4-119">Permissions</span></span>
<span data-ttu-id="4dfd4-120">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4dfd4-121">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4dfd4-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4dfd4-122">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="4dfd4-122">Permission type</span></span> |   <span data-ttu-id="4dfd4-123">Behörighet</span><span class="sxs-lookup"><span data-stu-id="4dfd4-123">Permission</span></span>  |   <span data-ttu-id="4dfd4-124">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="4dfd4-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4dfd4-125">Program</span><span class="sxs-lookup"><span data-stu-id="4dfd4-125">Application</span></span> |   <span data-ttu-id="4dfd4-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4dfd4-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="4dfd4-127">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="4dfd4-127">'Read and write all alerts'</span></span>
<span data-ttu-id="4dfd4-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="4dfd4-128">Delegated (work or school account)</span></span> | <span data-ttu-id="4dfd4-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4dfd4-129">Alert.ReadWrite</span></span> | <span data-ttu-id="4dfd4-130">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="4dfd4-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="4dfd4-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="4dfd4-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4dfd4-132">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="4dfd4-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4dfd4-133">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4dfd4-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4dfd4-134">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="4dfd4-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="4dfd4-135">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="4dfd4-135">Request headers</span></span>

<span data-ttu-id="4dfd4-136">Namn</span><span class="sxs-lookup"><span data-stu-id="4dfd4-136">Name</span></span> | <span data-ttu-id="4dfd4-137">Typ</span><span class="sxs-lookup"><span data-stu-id="4dfd4-137">Type</span></span> | <span data-ttu-id="4dfd4-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4dfd4-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="4dfd4-139">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="4dfd4-139">Authorization</span></span> | <span data-ttu-id="4dfd4-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-140">String</span></span> | <span data-ttu-id="4dfd4-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-141">Bearer {token}.</span></span> <span data-ttu-id="4dfd4-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="4dfd4-142">**Required**.</span></span>
<span data-ttu-id="4dfd4-143">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="4dfd4-143">Content-Type</span></span> | <span data-ttu-id="4dfd4-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-144">String</span></span> | <span data-ttu-id="4dfd4-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-145">application/json.</span></span> <span data-ttu-id="4dfd4-146">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="4dfd4-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4dfd4-147">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="4dfd4-147">Request body</span></span>
<span data-ttu-id="4dfd4-148">Ange värden för de relevanta fält som ska uppdateras i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="4dfd4-149">Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="4dfd4-150">För bästa prestanda bör du inte inkludera befintliga värden som inte ändras.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="4dfd4-151">Egenskap</span><span class="sxs-lookup"><span data-stu-id="4dfd4-151">Property</span></span> | <span data-ttu-id="4dfd4-152">Typ</span><span class="sxs-lookup"><span data-stu-id="4dfd4-152">Type</span></span> | <span data-ttu-id="4dfd4-153">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4dfd4-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="4dfd4-154">status</span><span class="sxs-lookup"><span data-stu-id="4dfd4-154">status</span></span> | <span data-ttu-id="4dfd4-155">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-155">String</span></span> | <span data-ttu-id="4dfd4-156">Anger aktuell status för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="4dfd4-157">Egenskapsvärdena är: "Ny", "InProgress" och "Löst".</span><span class="sxs-lookup"><span data-stu-id="4dfd4-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="4dfd4-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="4dfd4-158">assignedTo</span></span> | <span data-ttu-id="4dfd4-159">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-159">String</span></span> | <span data-ttu-id="4dfd4-160">Ägaren av aviseringen</span><span class="sxs-lookup"><span data-stu-id="4dfd4-160">Owner of the alert</span></span>
<span data-ttu-id="4dfd4-161">klassificering</span><span class="sxs-lookup"><span data-stu-id="4dfd4-161">classification</span></span> | <span data-ttu-id="4dfd4-162">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-162">String</span></span> | <span data-ttu-id="4dfd4-163">Anger specifikationen för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="4dfd4-164">Egenskapsvärdena är: "Okänt", "FalsktPositiv", "SantPositiv".</span><span class="sxs-lookup"><span data-stu-id="4dfd4-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="4dfd4-165">determination</span><span class="sxs-lookup"><span data-stu-id="4dfd4-165">determination</span></span> | <span data-ttu-id="4dfd4-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-166">String</span></span> | <span data-ttu-id="4dfd4-167">Anger om aviseringen är bestämd.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="4dfd4-168">Egenskapsvärdena är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="4dfd4-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="4dfd4-169">kommentar</span><span class="sxs-lookup"><span data-stu-id="4dfd4-169">comment</span></span> | <span data-ttu-id="4dfd4-170">Sträng</span><span class="sxs-lookup"><span data-stu-id="4dfd4-170">String</span></span> | <span data-ttu-id="4dfd4-171">Kommentar som ska läggas till i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="4dfd4-172">Svar</span><span class="sxs-lookup"><span data-stu-id="4dfd4-172">Response</span></span>
<span data-ttu-id="4dfd4-173">Om det lyckas returnerar den här metoden [](alerts.md) 200 OK, och aviseringsentitet i svarstexten med de uppdaterade egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="4dfd4-174">Om aviseringen med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4dfd4-175">Exempel</span><span class="sxs-lookup"><span data-stu-id="4dfd4-175">Example</span></span>

<span data-ttu-id="4dfd4-176">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="4dfd4-176">**Request**</span></span>

<span data-ttu-id="4dfd4-177">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="4dfd4-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
