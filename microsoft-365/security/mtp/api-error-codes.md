---
title: Vanliga API-felkoder för Microsoft 365 Defender
description: Lär dig mer om de gemensamma API-felkoderna för Microsoft 365 Defender
keywords: API, fel, koder, vanliga fel, MTP, API-felkoder
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846014"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="7f272-104">Vanliga API-felkoder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f272-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7f272-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7f272-105">**Applies to:**</span></span>
- <span data-ttu-id="7f272-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f272-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="7f272-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="7f272-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7f272-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="7f272-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7f272-109">Felkoderna som visas i följande tabell kan returneras av en åtgärd med Microsoft 365 Defender API: er.</span><span class="sxs-lookup"><span data-stu-id="7f272-109">The error codes listed in the following table may be returned by an operation on any of Microsoft 365 Defender APIs.</span></span>

<span data-ttu-id="7f272-110">Alla fel meddelanden innehåller ett fel meddelande som kan hjälpa dig att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="7f272-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="7f272-111">Meddelandet är en fri text som du kan ändra.</span><span class="sxs-lookup"><span data-stu-id="7f272-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="7f272-112">Längst ned på sidan hittar du svars exempel.</span><span class="sxs-lookup"><span data-stu-id="7f272-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="7f272-113">Felkod</span><span class="sxs-lookup"><span data-stu-id="7f272-113">Error code</span></span> |<span data-ttu-id="7f272-114">HTTP-statuskod</span><span class="sxs-lookup"><span data-stu-id="7f272-114">HTTP status code</span></span> |<span data-ttu-id="7f272-115">Meddelande</span><span class="sxs-lookup"><span data-stu-id="7f272-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="7f272-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="7f272-116">BadRequest</span></span> | <span data-ttu-id="7f272-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-117">BadRequest (400)</span></span> | <span data-ttu-id="7f272-118">Allmänt fel meddelande om felaktig begäran.</span><span class="sxs-lookup"><span data-stu-id="7f272-118">General Bad Request error message.</span></span>
<span data-ttu-id="7f272-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="7f272-119">ODataError</span></span> | <span data-ttu-id="7f272-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-120">BadRequest (400)</span></span> | <span data-ttu-id="7f272-121">Ogiltig OData URI-fråga (det specifika felet har angetts).</span><span class="sxs-lookup"><span data-stu-id="7f272-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="7f272-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="7f272-122">InvalidInput</span></span> | <span data-ttu-id="7f272-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-123">BadRequest (400)</span></span> | <span data-ttu-id="7f272-124">Ogiltig inmatning {ogiltigt värde}.</span><span class="sxs-lookup"><span data-stu-id="7f272-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="7f272-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="7f272-125">InvalidRequestBody</span></span> | <span data-ttu-id="7f272-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-126">BadRequest (400)</span></span> | <span data-ttu-id="7f272-127">Ogiltigt brödtext för begäran.</span><span class="sxs-lookup"><span data-stu-id="7f272-127">Invalid request body.</span></span>
<span data-ttu-id="7f272-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="7f272-128">InvalidHashValue</span></span> | <span data-ttu-id="7f272-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-129">BadRequest (400)</span></span> | <span data-ttu-id="7f272-130">Hash-värde {ogiltigt hash} är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="7f272-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="7f272-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="7f272-131">InvalidDomainName</span></span> | <span data-ttu-id="7f272-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-132">BadRequest (400)</span></span> | <span data-ttu-id="7f272-133">Domän namn {den ogiltiga domänen} är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="7f272-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="7f272-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="7f272-134">InvalidIpAddress</span></span> | <span data-ttu-id="7f272-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-135">BadRequest (400)</span></span> | <span data-ttu-id="7f272-136">IP-adress {ogiltigt IP} är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="7f272-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="7f272-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="7f272-137">InvalidUrl</span></span> | <span data-ttu-id="7f272-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-138">BadRequest (400)</span></span> | <span data-ttu-id="7f272-139">URL {ogiltig URL} är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="7f272-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="7f272-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="7f272-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="7f272-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-141">BadRequest (400)</span></span> | <span data-ttu-id="7f272-142">Maximal batchstorlek har överskridits.</span><span class="sxs-lookup"><span data-stu-id="7f272-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="7f272-143">Mottaget: {batch-storlek mottaget}, tillåts: {batchstorlek tillåts}.</span><span class="sxs-lookup"><span data-stu-id="7f272-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="7f272-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="7f272-144">MissingRequiredParameter</span></span> | <span data-ttu-id="7f272-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-145">BadRequest (400)</span></span> | <span data-ttu-id="7f272-146">Parameter {den saknade parametern} saknas.</span><span class="sxs-lookup"><span data-stu-id="7f272-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="7f272-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="7f272-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="7f272-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-148">BadRequest (400)</span></span> | <span data-ttu-id="7f272-149">OS-plattform {OS-plattformen} stöds inte för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="7f272-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="7f272-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="7f272-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="7f272-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="7f272-151">BadRequest (400)</span></span> | <span data-ttu-id="7f272-152">{Den begärda åtgärden} stöds för klient version {-kompatibel klient version} och senare.</span><span class="sxs-lookup"><span data-stu-id="7f272-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="7f272-153">Saknas</span><span class="sxs-lookup"><span data-stu-id="7f272-153">Unauthorized</span></span> | <span data-ttu-id="7f272-154">Ej behörig (401)</span><span class="sxs-lookup"><span data-stu-id="7f272-154">Unauthorized (401)</span></span> | <span data-ttu-id="7f272-155">Ej behörig (vanligt vis ogiltigt eller Förfallet godkännande rubrik).</span><span class="sxs-lookup"><span data-stu-id="7f272-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="7f272-156">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="7f272-156">Forbidden</span></span> | <span data-ttu-id="7f272-157">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="7f272-157">Forbidden (403)</span></span> | <span data-ttu-id="7f272-158">Förbjuden (giltig token men otillräcklig behörighet för åtgärden).</span><span class="sxs-lookup"><span data-stu-id="7f272-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="7f272-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="7f272-159">DisabledFeature</span></span> | <span data-ttu-id="7f272-160">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="7f272-160">Forbidden (403)</span></span> | <span data-ttu-id="7f272-161">Klient funktionen är inte aktive rad.</span><span class="sxs-lookup"><span data-stu-id="7f272-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="7f272-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="7f272-162">DisallowedOperation</span></span> | <span data-ttu-id="7f272-163">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="7f272-163">Forbidden (403)</span></span> | <span data-ttu-id="7f272-164">{åtgärden är inte tillåten och anledningen}.</span><span class="sxs-lookup"><span data-stu-id="7f272-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="7f272-165">NotFound</span><span class="sxs-lookup"><span data-stu-id="7f272-165">NotFound</span></span> | <span data-ttu-id="7f272-166">Hittas inte (404)</span><span class="sxs-lookup"><span data-stu-id="7f272-166">Not Found (404)</span></span> | <span data-ttu-id="7f272-167">Allmänt meddelande visas inte.</span><span class="sxs-lookup"><span data-stu-id="7f272-167">General Not Found error message.</span></span>
<span data-ttu-id="7f272-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="7f272-168">ResourceNotFound</span></span> | <span data-ttu-id="7f272-169">Hittas inte (404)</span><span class="sxs-lookup"><span data-stu-id="7f272-169">Not Found (404)</span></span> | <span data-ttu-id="7f272-170">Resurs {den begärda resursen} hittades inte.</span><span class="sxs-lookup"><span data-stu-id="7f272-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="7f272-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="7f272-171">InternalServerError</span></span> | <span data-ttu-id="7f272-172">Internt Server fel (500)</span><span class="sxs-lookup"><span data-stu-id="7f272-172">Internal Server Error (500)</span></span> | <span data-ttu-id="7f272-173">(Inget fel meddelande, försök igen eller kontakta oss om det inte löses)</span><span class="sxs-lookup"><span data-stu-id="7f272-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="7f272-174">Text parametrar är Skift läges känsliga</span><span class="sxs-lookup"><span data-stu-id="7f272-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="7f272-175">De skickade huvud parametrarna är för närvarande Skift läges känsliga.</span><span class="sxs-lookup"><span data-stu-id="7f272-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="7f272-176">Om du stöter på ett **InvalidRequestBody** -eller **MissingRequiredParameter** -fel kan det bero på felaktig tecken parameter eller gemen.</span><span class="sxs-lookup"><span data-stu-id="7f272-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="7f272-177">Vi rekommenderar att du granskar sidan API-dokumentation och kontrollerar att de skickade parametrarna stämmer överens med det relevanta exemplet.</span><span class="sxs-lookup"><span data-stu-id="7f272-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="7f272-178">Korrelations-ID</span><span class="sxs-lookup"><span data-stu-id="7f272-178">Correlation request ID</span></span>

<span data-ttu-id="7f272-179">Varje fel svar innehåller en parameter med unikt ID för spårning.</span><span class="sxs-lookup"><span data-stu-id="7f272-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="7f272-180">Egenskaps namnet för den här parametern är "mål".</span><span class="sxs-lookup"><span data-stu-id="7f272-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="7f272-181">När vi kontaktar oss om ett fel kan du hitta orsaken till problemet genom att bifoga detta ID.</span><span class="sxs-lookup"><span data-stu-id="7f272-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="7f272-182">Exempel</span><span class="sxs-lookup"><span data-stu-id="7f272-182">Examples</span></span>

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

