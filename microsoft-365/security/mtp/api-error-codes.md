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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719220"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="de46e-104">Vanliga API-felkoder för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de46e-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="de46e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="de46e-105">**Applies to:**</span></span>

- <span data-ttu-id="de46e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="de46e-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de46e-107">Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs.</span><span class="sxs-lookup"><span data-stu-id="de46e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="de46e-108">Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.</span><span class="sxs-lookup"><span data-stu-id="de46e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="de46e-109">Felkoder kan returneras av en åtgärd med Microsoft 365 Defender API: er.</span><span class="sxs-lookup"><span data-stu-id="de46e-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="de46e-110">Varje fel svar kommer att innehålla ett fel meddelande som kan hjälpa dig att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="de46e-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="de46e-111">Kolumnen fel meddelande i avsnittet tabell innehåller några exempel meddelanden.</span><span class="sxs-lookup"><span data-stu-id="de46e-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="de46e-112">Innehållet i faktiska meddelanden varierar beroende på faktorer som utlöste svaret.</span><span class="sxs-lookup"><span data-stu-id="de46e-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="de46e-113">Variabel innehåll anges i tabellen med vinkelparenteser.</span><span class="sxs-lookup"><span data-stu-id="de46e-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="de46e-114">Felkoder</span><span class="sxs-lookup"><span data-stu-id="de46e-114">Error codes</span></span>

<span data-ttu-id="de46e-115">Felkod</span><span class="sxs-lookup"><span data-stu-id="de46e-115">Error code</span></span> | <span data-ttu-id="de46e-116">HTTP-statuskod</span><span class="sxs-lookup"><span data-stu-id="de46e-116">HTTP status code</span></span> | <span data-ttu-id="de46e-117">Meddelande</span><span class="sxs-lookup"><span data-stu-id="de46e-117">Message</span></span>
-|-|-
<span data-ttu-id="de46e-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="de46e-118">BadRequest</span></span> | <span data-ttu-id="de46e-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-119">BadRequest (400)</span></span> | <span data-ttu-id="de46e-120">Allmänt fel meddelande om felaktig begäran.</span><span class="sxs-lookup"><span data-stu-id="de46e-120">General Bad Request error message.</span></span>
<span data-ttu-id="de46e-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="de46e-121">ODataError</span></span> | <span data-ttu-id="de46e-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-122">BadRequest (400)</span></span> | <span data-ttu-id="de46e-123">Ogiltig OData URI-fråga \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="de46e-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="de46e-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="de46e-124">InvalidInput</span></span> | <span data-ttu-id="de46e-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-125">BadRequest (400)</span></span> | <span data-ttu-id="de46e-126">Ogiltiga indata \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="de46e-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="de46e-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="de46e-127">InvalidRequestBody</span></span> | <span data-ttu-id="de46e-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-128">BadRequest (400)</span></span> | <span data-ttu-id="de46e-129">Ogiltigt brödtext för begäran.</span><span class="sxs-lookup"><span data-stu-id="de46e-129">Invalid request body.</span></span>
<span data-ttu-id="de46e-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="de46e-130">InvalidHashValue</span></span> | <span data-ttu-id="de46e-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-131">BadRequest (400)</span></span> | <span data-ttu-id="de46e-132">Ogiltigt hashvärde \<the invalid hash\> .</span><span class="sxs-lookup"><span data-stu-id="de46e-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="de46e-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="de46e-133">InvalidDomainName</span></span> | <span data-ttu-id="de46e-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-134">BadRequest (400)</span></span> | <span data-ttu-id="de46e-135">Domän namnet \<the invalid domain\> är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="de46e-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="de46e-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="de46e-136">InvalidIpAddress</span></span> | <span data-ttu-id="de46e-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-137">BadRequest (400)</span></span> | <span data-ttu-id="de46e-138">IP-adressen \<the invalid IP\> är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="de46e-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="de46e-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="de46e-139">InvalidUrl</span></span> | <span data-ttu-id="de46e-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-140">BadRequest (400)</span></span> | <span data-ttu-id="de46e-141">Webb adressen \<the invalid URL\> är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="de46e-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="de46e-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="de46e-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="de46e-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-143">BadRequest (400)</span></span> | <span data-ttu-id="de46e-144">Maximal batchstorlek har överskridits.</span><span class="sxs-lookup"><span data-stu-id="de46e-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="de46e-145">Mottaget: \<batch size received\> tillåts: {grupp storlek tillåts}.</span><span class="sxs-lookup"><span data-stu-id="de46e-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="de46e-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="de46e-146">MissingRequiredParameter</span></span> | <span data-ttu-id="de46e-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-147">BadRequest (400)</span></span> | <span data-ttu-id="de46e-148">Parameter \<the missing parameter\> saknas.</span><span class="sxs-lookup"><span data-stu-id="de46e-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="de46e-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="de46e-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="de46e-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-150">BadRequest (400)</span></span> | <span data-ttu-id="de46e-151">Operativ system plattformen \<the client OS Platform\> stöder inte den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="de46e-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="de46e-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="de46e-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="de46e-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="de46e-153">BadRequest (400)</span></span> | <span data-ttu-id="de46e-154">\<The requested action\> stöds på klient versionen \<supported client version\> och senare.</span><span class="sxs-lookup"><span data-stu-id="de46e-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="de46e-155">Saknas</span><span class="sxs-lookup"><span data-stu-id="de46e-155">Unauthorized</span></span> | <span data-ttu-id="de46e-156">Ej behörig (401)</span><span class="sxs-lookup"><span data-stu-id="de46e-156">Unauthorized (401)</span></span> | <span data-ttu-id="de46e-157">Saknas</span><span class="sxs-lookup"><span data-stu-id="de46e-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="de46e-158">*Obs! det beror vanligt vis på ett ogiltigt eller Förfallet godkännande huvud.*</span><span class="sxs-lookup"><span data-stu-id="de46e-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="de46e-159">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="de46e-159">Forbidden</span></span> | <span data-ttu-id="de46e-160">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="de46e-160">Forbidden (403)</span></span> | <span data-ttu-id="de46e-161">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="de46e-161">Forbidden</span></span> <br /><br /><span data-ttu-id="de46e-162">*Obs! giltig token men otillräcklig behörighet för åtgärden*.</span><span class="sxs-lookup"><span data-stu-id="de46e-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="de46e-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="de46e-163">DisabledFeature</span></span> | <span data-ttu-id="de46e-164">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="de46e-164">Forbidden (403)</span></span> | <span data-ttu-id="de46e-165">Klient funktionen är inte aktive rad.</span><span class="sxs-lookup"><span data-stu-id="de46e-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="de46e-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="de46e-166">DisallowedOperation</span></span> | <span data-ttu-id="de46e-167">Förbjuden (403)</span><span class="sxs-lookup"><span data-stu-id="de46e-167">Forbidden (403)</span></span> | <span data-ttu-id="de46e-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="de46e-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="de46e-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="de46e-169">NotFound</span></span> | <span data-ttu-id="de46e-170">Hittas inte (404)</span><span class="sxs-lookup"><span data-stu-id="de46e-170">Not Found (404)</span></span> | <span data-ttu-id="de46e-171">Allmänt meddelande visas inte.</span><span class="sxs-lookup"><span data-stu-id="de46e-171">General Not Found error message.</span></span>
<span data-ttu-id="de46e-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="de46e-172">ResourceNotFound</span></span> | <span data-ttu-id="de46e-173">Hittas inte (404)</span><span class="sxs-lookup"><span data-stu-id="de46e-173">Not Found (404)</span></span> | <span data-ttu-id="de46e-174">Resursen \<the requested resource\> hittades inte.</span><span class="sxs-lookup"><span data-stu-id="de46e-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="de46e-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="de46e-175">InternalServerError</span></span> | <span data-ttu-id="de46e-176">Internt Server fel (500)</span><span class="sxs-lookup"><span data-stu-id="de46e-176">Internal Server Error (500)</span></span> | <span data-ttu-id="de46e-177">*Obs! inga fel meddelanden, försök igen eller kontakta Microsoft om det inte löses*</span><span class="sxs-lookup"><span data-stu-id="de46e-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="de46e-178">Exempel</span><span class="sxs-lookup"><span data-stu-id="de46e-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="de46e-179">Body-parametrar</span><span class="sxs-lookup"><span data-stu-id="de46e-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de46e-180">Text parametrar är Skift läges känsliga.</span><span class="sxs-lookup"><span data-stu-id="de46e-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="de46e-181">Om du upplever ett *InvalidRequestBody* -eller *MissingRequiredParameter* -fel kan det bero på ett stavfel.</span><span class="sxs-lookup"><span data-stu-id="de46e-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="de46e-182">Granska API-dokumentationen och kontrol lera att de skickade parametrarna stämmer överens med det relevanta exemplet.</span><span class="sxs-lookup"><span data-stu-id="de46e-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="de46e-183">Spårnings-ID</span><span class="sxs-lookup"><span data-stu-id="de46e-183">Tracking ID</span></span>

<span data-ttu-id="de46e-184">Varje fel svar innehåller en parameter med unikt ID för spårning.</span><span class="sxs-lookup"><span data-stu-id="de46e-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="de46e-185">Egenskaps namnet för den här parametern är *mål*.</span><span class="sxs-lookup"><span data-stu-id="de46e-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="de46e-186">När vi kontaktar oss angående ett fel hjälper vi till med att hitta orsaken till problemet.</span><span class="sxs-lookup"><span data-stu-id="de46e-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="de46e-187">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="de46e-187">Related articles</span></span>

- [<span data-ttu-id="de46e-188">Översikt över Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="de46e-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="de46e-189">Microsoft 365 Defender API: er som stöds</span><span class="sxs-lookup"><span data-stu-id="de46e-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="de46e-190">Gå till API för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de46e-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="de46e-191">Läs mer om API-begränsningar och licensiering</span><span class="sxs-lookup"><span data-stu-id="de46e-191">Learn about API limits and licensing</span></span>](api-terms.md)
