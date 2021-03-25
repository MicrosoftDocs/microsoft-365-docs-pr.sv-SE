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
ms.technology: mde
ms.openlocfilehash: 42bab0a9d20d5e1ef78b98b3538cef209240d890
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187363"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="f8ba6-104">Indikator-API för Skicka eller uppdatera</span><span class="sxs-lookup"><span data-stu-id="f8ba6-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8ba6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8ba6-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8ba6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8ba6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8ba6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8ba6-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f8ba6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f8ba6-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="f8ba6-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-110">API description</span></span>
<span data-ttu-id="f8ba6-111">Skickar eller uppdaterar ny [indikator entitet.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="f8ba6-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="f8ba6-112">CIDR-notation för IP-adresser stöds inte.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="f8ba6-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="f8ba6-113">Limitations</span></span>
1. <span data-ttu-id="f8ba6-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="f8ba6-115">Det finns en gräns på 15 000 aktiva indikatorer per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="f8ba6-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="f8ba6-116">Permissions</span></span>
<span data-ttu-id="f8ba6-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f8ba6-118">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f8ba6-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="f8ba6-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="f8ba6-119">Permission type</span></span> |   <span data-ttu-id="f8ba6-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="f8ba6-120">Permission</span></span>  |   <span data-ttu-id="f8ba6-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="f8ba6-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f8ba6-122">Program</span><span class="sxs-lookup"><span data-stu-id="f8ba6-122">Application</span></span> |   <span data-ttu-id="f8ba6-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f8ba6-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="f8ba6-124">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-124">'Read and write Indicators'</span></span>
<span data-ttu-id="f8ba6-125">Program</span><span class="sxs-lookup"><span data-stu-id="f8ba6-125">Application</span></span> |   <span data-ttu-id="f8ba6-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f8ba6-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="f8ba6-127">"Läsa och skriva alla indikatorer"</span><span class="sxs-lookup"><span data-stu-id="f8ba6-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="f8ba6-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="f8ba6-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="f8ba6-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f8ba6-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="f8ba6-130">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="f8ba6-131">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="f8ba6-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="f8ba6-132">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="f8ba6-132">Request headers</span></span>

<span data-ttu-id="f8ba6-133">Namn</span><span class="sxs-lookup"><span data-stu-id="f8ba6-133">Name</span></span> | <span data-ttu-id="f8ba6-134">Skriv</span><span class="sxs-lookup"><span data-stu-id="f8ba6-134">Type</span></span> | <span data-ttu-id="f8ba6-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8ba6-136">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="f8ba6-136">Authorization</span></span> | <span data-ttu-id="f8ba6-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-137">String</span></span> | <span data-ttu-id="f8ba6-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-138">Bearer {token}.</span></span> <span data-ttu-id="f8ba6-139">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-139">**Required**.</span></span>
<span data-ttu-id="f8ba6-140">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="f8ba6-140">Content-Type</span></span> | <span data-ttu-id="f8ba6-141">sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-141">string</span></span> | <span data-ttu-id="f8ba6-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-142">application/json.</span></span> <span data-ttu-id="f8ba6-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f8ba6-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="f8ba6-144">Request body</span></span>
<span data-ttu-id="f8ba6-145">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="f8ba6-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="f8ba6-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8ba6-146">Parameter</span></span> | <span data-ttu-id="f8ba6-147">Skriv</span><span class="sxs-lookup"><span data-stu-id="f8ba6-147">Type</span></span>    | <span data-ttu-id="f8ba6-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="f8ba6-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="f8ba6-149">indicatorValue</span></span> | <span data-ttu-id="f8ba6-150">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-150">String</span></span> | <span data-ttu-id="f8ba6-151">Identiteten för [indikatorenheten.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="f8ba6-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="f8ba6-152">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-152">**Required**</span></span>
<span data-ttu-id="f8ba6-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="f8ba6-153">indicatorType</span></span> | <span data-ttu-id="f8ba6-154">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-154">Enum</span></span> | <span data-ttu-id="f8ba6-155">Typ av indikator.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-155">Type of the indicator.</span></span> <span data-ttu-id="f8ba6-156">Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url".</span><span class="sxs-lookup"><span data-stu-id="f8ba6-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="f8ba6-157">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-157">**Required**</span></span>
<span data-ttu-id="f8ba6-158">åtgärd</span><span class="sxs-lookup"><span data-stu-id="f8ba6-158">action</span></span> | <span data-ttu-id="f8ba6-159">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-159">Enum</span></span> | <span data-ttu-id="f8ba6-160">Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="f8ba6-161">Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet".</span><span class="sxs-lookup"><span data-stu-id="f8ba6-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="f8ba6-162">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-162">**Required**</span></span>
<span data-ttu-id="f8ba6-163">program</span><span class="sxs-lookup"><span data-stu-id="f8ba6-163">application</span></span> | <span data-ttu-id="f8ba6-164">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-164">String</span></span> | <span data-ttu-id="f8ba6-165">Programmet som är kopplat till indikatorn.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-165">The application associated with the indicator.</span></span> <span data-ttu-id="f8ba6-166">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-166">**Optional**</span></span>
<span data-ttu-id="f8ba6-167">rubrik</span><span class="sxs-lookup"><span data-stu-id="f8ba6-167">title</span></span> | <span data-ttu-id="f8ba6-168">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-168">String</span></span> | <span data-ttu-id="f8ba6-169">Indikatoraviseringens rubrik.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-169">Indicator alert title.</span></span> <span data-ttu-id="f8ba6-170">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-170">**Required**</span></span>
<span data-ttu-id="f8ba6-171">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-171">description</span></span> | <span data-ttu-id="f8ba6-172">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-172">String</span></span> | <span data-ttu-id="f8ba6-173">Beskrivning av indikatorn.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-173">Description of the indicator.</span></span> <span data-ttu-id="f8ba6-174">**Obligatoriskt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-174">**Required**</span></span>
<span data-ttu-id="f8ba6-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="f8ba6-175">expirationTime</span></span> | <span data-ttu-id="f8ba6-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f8ba6-176">DateTimeOffset</span></span> | <span data-ttu-id="f8ba6-177">Indikatorns utgångstid.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-177">The expiration time of the indicator.</span></span> <span data-ttu-id="f8ba6-178">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-178">**Optional**</span></span>
<span data-ttu-id="f8ba6-179">allvarlighetsgrad</span><span class="sxs-lookup"><span data-stu-id="f8ba6-179">severity</span></span> | <span data-ttu-id="f8ba6-180">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="f8ba6-180">Enum</span></span> | <span data-ttu-id="f8ba6-181">Indikatorns allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-181">The severity of the indicator.</span></span> <span data-ttu-id="f8ba6-182">Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="f8ba6-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="f8ba6-183">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-183">**Optional**</span></span>
<span data-ttu-id="f8ba6-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="f8ba6-184">recommendedActions</span></span> | <span data-ttu-id="f8ba6-185">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-185">String</span></span> | <span data-ttu-id="f8ba6-186">Rekommenderade åtgärder för TI-indikatoraviseringar.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="f8ba6-187">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-187">**Optional**</span></span>
<span data-ttu-id="f8ba6-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="f8ba6-188">rbacGroupNames</span></span> | <span data-ttu-id="f8ba6-189">Sträng</span><span class="sxs-lookup"><span data-stu-id="f8ba6-189">String</span></span> | <span data-ttu-id="f8ba6-190">Kommaavgränsade listor med namn på RBAC-grupper indikatorn skulle tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="f8ba6-191">**Valfritt**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="f8ba6-192">Svar</span><span class="sxs-lookup"><span data-stu-id="f8ba6-192">Response</span></span>
- <span data-ttu-id="f8ba6-193">Om det lyckas returnerar den här metoden 200 – OK-svarskod och den skapade/uppdaterade [indikatorentiteten](ti-indicator.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="f8ba6-194">Om det inte lyckas: den här metoden returnerar 400 – Bad Request.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="f8ba6-195">Felaktig begäran anger vanligtvis felaktigt brödtext.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="f8ba6-196">Exempel</span><span class="sxs-lookup"><span data-stu-id="f8ba6-196">Example</span></span>

<span data-ttu-id="f8ba6-197">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="f8ba6-197">**Request**</span></span>

<span data-ttu-id="f8ba6-198">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="f8ba6-198">Here is an example of the request.</span></span>

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

## <a name="related-topic"></a><span data-ttu-id="f8ba6-199">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="f8ba6-199">Related topic</span></span>
- [<span data-ttu-id="f8ba6-200">Hantera indikatorer</span><span class="sxs-lookup"><span data-stu-id="f8ba6-200">Manage indicators</span></span>](manage-indicators.md)
