---
title: Uppdatera API för avisering entitet
description: Lär dig hur du uppdaterar en Microsoft Defender ATP-avisering med hjälp av detta API. Du kan uppdatera status, determination, klassificering och tilldeladeTill-egenskaper.
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
ms.openlocfilehash: 7dd3ab3da34efa6cb954db2a596d7a1e48efedf1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199315"
---
# <a name="update-alert"></a><span data-ttu-id="56e25-105">Uppdateringsavisering</span><span class="sxs-lookup"><span data-stu-id="56e25-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56e25-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="56e25-106">**Applies to:**</span></span>
- [<span data-ttu-id="56e25-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="56e25-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="56e25-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56e25-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="56e25-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="56e25-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56e25-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="56e25-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="56e25-111">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="56e25-111">API description</span></span>
<span data-ttu-id="56e25-112">Uppdaterar egenskaper för befintlig [avisering](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="56e25-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="56e25-113">**Kommentarsinskick** är tillgängligt med eller utan uppdatering av egenskaper.</span><span class="sxs-lookup"><span data-stu-id="56e25-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="56e25-114">Egenskaper som kan uppdateras är: ```status``` ```determination``` , och ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="56e25-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="56e25-115">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="56e25-115">Limitations</span></span>
1. <span data-ttu-id="56e25-116">Du kan uppdatera aviseringar som är tillgängliga i API:et.</span><span class="sxs-lookup"><span data-stu-id="56e25-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="56e25-117">Mer information finns i Listaviseringar. [](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="56e25-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="56e25-118">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="56e25-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="56e25-119">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="56e25-119">Permissions</span></span>
<span data-ttu-id="56e25-120">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="56e25-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="56e25-121">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="56e25-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="56e25-122">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="56e25-122">Permission type</span></span> |   <span data-ttu-id="56e25-123">Behörighet</span><span class="sxs-lookup"><span data-stu-id="56e25-123">Permission</span></span>  |   <span data-ttu-id="56e25-124">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="56e25-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="56e25-125">Program</span><span class="sxs-lookup"><span data-stu-id="56e25-125">Application</span></span> |   <span data-ttu-id="56e25-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="56e25-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="56e25-127">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="56e25-127">'Read and write all alerts'</span></span>
<span data-ttu-id="56e25-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="56e25-128">Delegated (work or school account)</span></span> | <span data-ttu-id="56e25-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="56e25-129">Alert.ReadWrite</span></span> | <span data-ttu-id="56e25-130">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="56e25-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="56e25-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="56e25-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="56e25-132">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="56e25-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="56e25-133">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="56e25-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="56e25-134">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="56e25-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="56e25-135">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="56e25-135">Request headers</span></span>

<span data-ttu-id="56e25-136">Namn</span><span class="sxs-lookup"><span data-stu-id="56e25-136">Name</span></span> | <span data-ttu-id="56e25-137">Skriv</span><span class="sxs-lookup"><span data-stu-id="56e25-137">Type</span></span> | <span data-ttu-id="56e25-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="56e25-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="56e25-139">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="56e25-139">Authorization</span></span> | <span data-ttu-id="56e25-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-140">String</span></span> | <span data-ttu-id="56e25-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="56e25-141">Bearer {token}.</span></span> <span data-ttu-id="56e25-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="56e25-142">**Required**.</span></span>
<span data-ttu-id="56e25-143">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="56e25-143">Content-Type</span></span> | <span data-ttu-id="56e25-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-144">String</span></span> | <span data-ttu-id="56e25-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="56e25-145">application/json.</span></span> <span data-ttu-id="56e25-146">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="56e25-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="56e25-147">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="56e25-147">Request body</span></span>
<span data-ttu-id="56e25-148">Ange värden för de relevanta fält som ska uppdateras i begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="56e25-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="56e25-149">Befintliga egenskaper som inte ingår i begärans brödtext behåller sina tidigare värden eller beräknas om baserat på ändringar av andra egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="56e25-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="56e25-150">För bästa prestanda bör du inte inkludera befintliga värden som inte ändras.</span><span class="sxs-lookup"><span data-stu-id="56e25-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="56e25-151">Egenskap</span><span class="sxs-lookup"><span data-stu-id="56e25-151">Property</span></span> | <span data-ttu-id="56e25-152">Skriv</span><span class="sxs-lookup"><span data-stu-id="56e25-152">Type</span></span> | <span data-ttu-id="56e25-153">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="56e25-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="56e25-154">status</span><span class="sxs-lookup"><span data-stu-id="56e25-154">status</span></span> | <span data-ttu-id="56e25-155">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-155">String</span></span> | <span data-ttu-id="56e25-156">Anger aktuell status för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="56e25-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="56e25-157">Egenskapsvärdena är: "Ny", "InProgress" och "Löst".</span><span class="sxs-lookup"><span data-stu-id="56e25-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="56e25-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="56e25-158">assignedTo</span></span> | <span data-ttu-id="56e25-159">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-159">String</span></span> | <span data-ttu-id="56e25-160">Ägaren av aviseringen</span><span class="sxs-lookup"><span data-stu-id="56e25-160">Owner of the alert</span></span>
<span data-ttu-id="56e25-161">klassificering</span><span class="sxs-lookup"><span data-stu-id="56e25-161">classification</span></span> | <span data-ttu-id="56e25-162">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-162">String</span></span> | <span data-ttu-id="56e25-163">Anger specifikationen för aviseringen.</span><span class="sxs-lookup"><span data-stu-id="56e25-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="56e25-164">Egenskapsvärdena är: "Okänt", "FalsktPositiv", "SantPositiv".</span><span class="sxs-lookup"><span data-stu-id="56e25-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="56e25-165">determination</span><span class="sxs-lookup"><span data-stu-id="56e25-165">determination</span></span> | <span data-ttu-id="56e25-166">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-166">String</span></span> | <span data-ttu-id="56e25-167">Anger om aviseringen är bestämd.</span><span class="sxs-lookup"><span data-stu-id="56e25-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="56e25-168">Egenskapsvärdena är: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="56e25-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="56e25-169">kommentar</span><span class="sxs-lookup"><span data-stu-id="56e25-169">comment</span></span> | <span data-ttu-id="56e25-170">Sträng</span><span class="sxs-lookup"><span data-stu-id="56e25-170">String</span></span> | <span data-ttu-id="56e25-171">Kommentar som ska läggas till i aviseringen.</span><span class="sxs-lookup"><span data-stu-id="56e25-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="56e25-172">Svar</span><span class="sxs-lookup"><span data-stu-id="56e25-172">Response</span></span>
<span data-ttu-id="56e25-173">Om det lyckas returnerar den här metoden [](alerts.md) 200 OK, och aviseringsentitet i svarstexten med de uppdaterade egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="56e25-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="56e25-174">Om aviseringen med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="56e25-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="56e25-175">Exempel</span><span class="sxs-lookup"><span data-stu-id="56e25-175">Example</span></span>

<span data-ttu-id="56e25-176">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="56e25-176">**Request**</span></span>

<span data-ttu-id="56e25-177">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="56e25-177">Here is an example of the request.</span></span>

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
