---
title: Vanliga Microsoft Defender för slutpunkts-API-fel
description: Lista över vanliga Microsoft Defender för Endpoint API-fel med beskrivningar.
keywords: API:er, Microsoft Defender för slutpunkts-API, fel, felsökning
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
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771015"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="ff0d1-104">Vanliga REST API-felkoder</span><span class="sxs-lookup"><span data-stu-id="ff0d1-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="ff0d1-105">Felkoderna som visas i följande tabell kan returneras av en åtgärd på någon av Microsoft Defender för slutpunkts-API:er.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="ff0d1-106">Utöver felkoden innehåller varje felsvar ett felmeddelande, som kan hjälpa dig att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="ff0d1-107">Meddelandet är en kostnadsfri text som kan ändras.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="ff0d1-108">Längst ned på sidan finns svarsexempel.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="ff0d1-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ff0d1-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ff0d1-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="ff0d1-111">Felkod</span><span class="sxs-lookup"><span data-stu-id="ff0d1-111">Error code</span></span> |<span data-ttu-id="ff0d1-112">HTTP-statuskod</span><span class="sxs-lookup"><span data-stu-id="ff0d1-112">HTTP status code</span></span> |<span data-ttu-id="ff0d1-113">Meddelande</span><span class="sxs-lookup"><span data-stu-id="ff0d1-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="ff0d1-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="ff0d1-114">BadRequest</span></span> | <span data-ttu-id="ff0d1-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-115">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-116">Felmeddelande för allmän felbegäran.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-116">General Bad Request error message.</span></span>
<span data-ttu-id="ff0d1-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="ff0d1-117">ODataError</span></span> | <span data-ttu-id="ff0d1-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-118">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-119">Ogiltig OData-URI-fråga (det specifika felet har angetts).</span><span class="sxs-lookup"><span data-stu-id="ff0d1-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="ff0d1-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="ff0d1-120">InvalidInput</span></span> | <span data-ttu-id="ff0d1-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-121">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-122">Ogiltiga indata {the invalid input}.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="ff0d1-123">InvalidRequest Det här är ett måste</span><span class="sxs-lookup"><span data-stu-id="ff0d1-123">InvalidRequestBody</span></span> | <span data-ttu-id="ff0d1-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-124">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-125">Ogiltig begärans brödtext.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-125">Invalid request body.</span></span>
<span data-ttu-id="ff0d1-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="ff0d1-126">InvalidHashValue</span></span> | <span data-ttu-id="ff0d1-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-127">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-128">Hashvärdet {the invalid hash} är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="ff0d1-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="ff0d1-129">InvalidDomainName</span></span> | <span data-ttu-id="ff0d1-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-130">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-131">Domännamnet {the invalid domain} är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="ff0d1-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="ff0d1-132">InvalidIpAddress</span></span> | <span data-ttu-id="ff0d1-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-133">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-134">IP-adressen {the invalid IP} är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="ff0d1-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="ff0d1-135">InvalidUrl</span></span> | <span data-ttu-id="ff0d1-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-136">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-137">URL {the invalid URL} är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="ff0d1-138">MaximumBatchSizeExceededed</span><span class="sxs-lookup"><span data-stu-id="ff0d1-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="ff0d1-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-139">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-140">Maximal överskriden batchstorlek.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="ff0d1-141">Mottaget: {batchstorlek mottaget}, tillåtet: {batchstorlek tillåten}.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="ff0d1-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="ff0d1-142">MissingRequiredParameter</span></span> | <span data-ttu-id="ff0d1-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-143">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-144">Parametern {the missing parameter} saknas.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="ff0d1-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="ff0d1-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="ff0d1-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-146">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-147">OS-plattformen {the client OS Platform} stöds inte för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="ff0d1-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="ff0d1-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="ff0d1-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-149">BadRequest (400)</span></span> | <span data-ttu-id="ff0d1-150">{The requested action} stöds i klientversionen {supported client version} eller senare.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="ff0d1-151">Obehörig</span><span class="sxs-lookup"><span data-stu-id="ff0d1-151">Unauthorized</span></span> | <span data-ttu-id="ff0d1-152">Obehörig (401)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-152">Unauthorized (401)</span></span> | <span data-ttu-id="ff0d1-153">Obehörig (ogiltig eller utgången auktoriseringsrubrik).</span><span class="sxs-lookup"><span data-stu-id="ff0d1-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="ff0d1-154">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="ff0d1-154">Forbidden</span></span> | <span data-ttu-id="ff0d1-155">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-155">Forbidden (403)</span></span> | <span data-ttu-id="ff0d1-156">Åtkomst nekas (giltig token men otillräcklig behörighet för åtgärden).</span><span class="sxs-lookup"><span data-stu-id="ff0d1-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="ff0d1-157">Inaktiveradfeature</span><span class="sxs-lookup"><span data-stu-id="ff0d1-157">DisabledFeature</span></span> | <span data-ttu-id="ff0d1-158">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-158">Forbidden (403)</span></span> | <span data-ttu-id="ff0d1-159">Klientorganisationsfunktionen är inte aktiverad.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="ff0d1-160">OtillåtenOperation</span><span class="sxs-lookup"><span data-stu-id="ff0d1-160">DisallowedOperation</span></span> | <span data-ttu-id="ff0d1-161">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-161">Forbidden (403)</span></span> | <span data-ttu-id="ff0d1-162">{den otillåtna åtgärden och orsaken}.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="ff0d1-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="ff0d1-163">NotFound</span></span> | <span data-ttu-id="ff0d1-164">Hittades inte (404)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-164">Not Found (404)</span></span> | <span data-ttu-id="ff0d1-165">Felmeddelandet Allmänt hittades inte.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-165">General Not Found error message.</span></span>
<span data-ttu-id="ff0d1-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="ff0d1-166">ResourceNotFound</span></span> | <span data-ttu-id="ff0d1-167">Hittades inte (404)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-167">Not Found (404)</span></span> | <span data-ttu-id="ff0d1-168">Resurs {den begärda resursen} hittades inte.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="ff0d1-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="ff0d1-169">InternalServerError</span></span> | <span data-ttu-id="ff0d1-170">Internt serverfel (500)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-170">Internal Server Error (500)</span></span> | <span data-ttu-id="ff0d1-171">(Inget felmeddelande, försök igen)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="ff0d1-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="ff0d1-172">TooManyRequests</span></span> | <span data-ttu-id="ff0d1-173">För många begäranden (429)</span><span class="sxs-lookup"><span data-stu-id="ff0d1-173">Too Many Requests (429)</span></span> | <span data-ttu-id="ff0d1-174">Svar representerar att nå kvotgränsen antingen genom antal begäranden eller av CPU.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="ff0d1-175">Parametrar för brödtext är case-sensitive</span><span class="sxs-lookup"><span data-stu-id="ff0d1-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="ff0d1-176">Parametrarna för inskickade brödtext är för närvarande ärendekänsliga.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="ff0d1-177">Om du får ett **InvalidRequest Gemener-** eller **MissingRequiredParameter-fel** kan det bero på fel versaler eller gemener.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="ff0d1-178">Granska dokumentationen för API och kontrollera att de skickade parametrarna matchar det relevanta exemplet.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="ff0d1-179">Id för korrelationsbegäran</span><span class="sxs-lookup"><span data-stu-id="ff0d1-179">Correlation request ID</span></span>

<span data-ttu-id="ff0d1-180">Varje felsvar innehåller en unik ID-parameter för spårning.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="ff0d1-181">Egenskapsnamnet för den här parametern är "target".</span><span class="sxs-lookup"><span data-stu-id="ff0d1-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="ff0d1-182">När du kontaktar oss om ett fel kan du bifoga det här ID:t för att hitta orsaken till problemet.</span><span class="sxs-lookup"><span data-stu-id="ff0d1-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="ff0d1-183">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff0d1-183">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```


```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```
