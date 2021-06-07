---
title: Indikator-API för Skicka eller uppdatera
description: Lär dig hur du använder indikator-API:t för skicka eller uppdatera för att skicka eller uppdatera en ny indikator i Microsoft Defender för slutpunkt.
keywords: apis, graph api, apis som stöds, skicka, ti, indikator, uppdatera
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771711"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="8ec2c-104">Indikator-API för Skicka eller uppdatera</span><span class="sxs-lookup"><span data-stu-id="8ec2c-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ec2c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8ec2c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ec2c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ec2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ec2c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8ec2c-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8ec2c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8ec2c-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8ec2c-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-110">API description</span></span>
<span data-ttu-id="8ec2c-111">Skickar eller uppdaterar ny [indikator entitet.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="8ec2c-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="8ec2c-112">CIDR-notation för IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="8ec2c-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="8ec2c-113">Limitations</span></span>
1. <span data-ttu-id="8ec2c-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="8ec2c-115">Det finns en gräns på 15 000 aktiva indikatorer per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="8ec2c-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="8ec2c-116">Permissions</span></span>
<span data-ttu-id="8ec2c-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ec2c-118">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ec2c-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="8ec2c-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="8ec2c-119">Permission type</span></span> |   <span data-ttu-id="8ec2c-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="8ec2c-120">Permission</span></span>  |   <span data-ttu-id="8ec2c-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="8ec2c-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8ec2c-122">Program</span><span class="sxs-lookup"><span data-stu-id="8ec2c-122">Application</span></span> |   <span data-ttu-id="8ec2c-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8ec2c-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="8ec2c-124">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-124">'Read and write Indicators'</span></span>
<span data-ttu-id="8ec2c-125">Program</span><span class="sxs-lookup"><span data-stu-id="8ec2c-125">Application</span></span> |   <span data-ttu-id="8ec2c-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8ec2c-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="8ec2c-127">"Läsa och skriva alla indikatorer"</span><span class="sxs-lookup"><span data-stu-id="8ec2c-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="8ec2c-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="8ec2c-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="8ec2c-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8ec2c-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="8ec2c-130">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="8ec2c-131">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8ec2c-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="8ec2c-132">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="8ec2c-132">Request headers</span></span>

<span data-ttu-id="8ec2c-133">Namn</span><span class="sxs-lookup"><span data-stu-id="8ec2c-133">Name</span></span> | <span data-ttu-id="8ec2c-134">Typ</span><span class="sxs-lookup"><span data-stu-id="8ec2c-134">Type</span></span> | <span data-ttu-id="8ec2c-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ec2c-136">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="8ec2c-136">Authorization</span></span> | <span data-ttu-id="8ec2c-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-137">String</span></span> | <span data-ttu-id="8ec2c-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-138">Bearer {token}.</span></span> <span data-ttu-id="8ec2c-139">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-139">**Required**.</span></span>
<span data-ttu-id="8ec2c-140">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="8ec2c-140">Content-Type</span></span> | <span data-ttu-id="8ec2c-141">sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-141">string</span></span> | <span data-ttu-id="8ec2c-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-142">application/json.</span></span> <span data-ttu-id="8ec2c-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8ec2c-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="8ec2c-144">Request body</span></span>
<span data-ttu-id="8ec2c-145">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="8ec2c-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="8ec2c-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ec2c-146">Parameter</span></span> | <span data-ttu-id="8ec2c-147">Typ</span><span class="sxs-lookup"><span data-stu-id="8ec2c-147">Type</span></span>    | <span data-ttu-id="8ec2c-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="8ec2c-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="8ec2c-149">indicatorValue</span></span> | <span data-ttu-id="8ec2c-150">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-150">String</span></span> | <span data-ttu-id="8ec2c-151">Identiteten för [indikatorenheten.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="8ec2c-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="8ec2c-152">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-152">**Required**</span></span>
<span data-ttu-id="8ec2c-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="8ec2c-153">indicatorType</span></span> | <span data-ttu-id="8ec2c-154">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-154">Enum</span></span> | <span data-ttu-id="8ec2c-155">Typ av indikator.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-155">Type of the indicator.</span></span> <span data-ttu-id="8ec2c-156">Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url".</span><span class="sxs-lookup"><span data-stu-id="8ec2c-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="8ec2c-157">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-157">**Required**</span></span>
<span data-ttu-id="8ec2c-158">åtgärd</span><span class="sxs-lookup"><span data-stu-id="8ec2c-158">action</span></span> | <span data-ttu-id="8ec2c-159">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-159">Enum</span></span> | <span data-ttu-id="8ec2c-160">Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="8ec2c-161">Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet".</span><span class="sxs-lookup"><span data-stu-id="8ec2c-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="8ec2c-162">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-162">**Required**</span></span>
<span data-ttu-id="8ec2c-163">program</span><span class="sxs-lookup"><span data-stu-id="8ec2c-163">application</span></span> | <span data-ttu-id="8ec2c-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-164">String</span></span> | <span data-ttu-id="8ec2c-165">Programmet som är kopplat till indikatorn.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-165">The application associated with the indicator.</span></span> <span data-ttu-id="8ec2c-166">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-166">**Optional**</span></span>
<span data-ttu-id="8ec2c-167">rubrik</span><span class="sxs-lookup"><span data-stu-id="8ec2c-167">title</span></span> | <span data-ttu-id="8ec2c-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-168">String</span></span> | <span data-ttu-id="8ec2c-169">Indikatoraviseringens rubrik.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-169">Indicator alert title.</span></span> <span data-ttu-id="8ec2c-170">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-170">**Required**</span></span>
<span data-ttu-id="8ec2c-171">beskrivning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-171">description</span></span> | <span data-ttu-id="8ec2c-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-172">String</span></span> | <span data-ttu-id="8ec2c-173">Beskrivning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-173">Description of the indicator.</span></span> <span data-ttu-id="8ec2c-174">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-174">**Required**</span></span>
<span data-ttu-id="8ec2c-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="8ec2c-175">expirationTime</span></span> | <span data-ttu-id="8ec2c-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8ec2c-176">DateTimeOffset</span></span> | <span data-ttu-id="8ec2c-177">Indikatorns utgångstid.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-177">The expiration time of the indicator.</span></span> <span data-ttu-id="8ec2c-178">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-178">**Optional**</span></span>
<span data-ttu-id="8ec2c-179">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="8ec2c-179">severity</span></span> | <span data-ttu-id="8ec2c-180">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="8ec2c-180">Enum</span></span> | <span data-ttu-id="8ec2c-181">Indikatorns allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-181">The severity of the indicator.</span></span> <span data-ttu-id="8ec2c-182">Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="8ec2c-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="8ec2c-183">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-183">**Optional**</span></span>
<span data-ttu-id="8ec2c-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="8ec2c-184">recommendedActions</span></span> | <span data-ttu-id="8ec2c-185">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-185">String</span></span> | <span data-ttu-id="8ec2c-186">Rekommenderade åtgärder för TI-indikatoraviseringar.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="8ec2c-187">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-187">**Optional**</span></span>
<span data-ttu-id="8ec2c-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="8ec2c-188">rbacGroupNames</span></span> | <span data-ttu-id="8ec2c-189">Sträng</span><span class="sxs-lookup"><span data-stu-id="8ec2c-189">String</span></span> | <span data-ttu-id="8ec2c-190">Kommaavgränsade listor med namn på RBAC-grupper indikatorn skulle tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="8ec2c-191">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="8ec2c-192">Svar</span><span class="sxs-lookup"><span data-stu-id="8ec2c-192">Response</span></span>
- <span data-ttu-id="8ec2c-193">Om det lyckas returnerar den här metoden 200 – OK-svarskod och den skapade/uppdaterade [indikatorentiteten](ti-indicator.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="8ec2c-194">Om det inte lyckas: den här metoden returnerar 400 – Bad Request.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="8ec2c-195">Felaktig begäran anger vanligtvis felaktigt brödtext.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="8ec2c-196">Exempel</span><span class="sxs-lookup"><span data-stu-id="8ec2c-196">Example</span></span>

<span data-ttu-id="8ec2c-197">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="8ec2c-197">**Request**</span></span>

<span data-ttu-id="8ec2c-198">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="8ec2c-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="8ec2c-199">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="8ec2c-199">Related topic</span></span>
- [<span data-ttu-id="8ec2c-200">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="8ec2c-200">Manage indicators</span></span>](manage-indicators.md)
