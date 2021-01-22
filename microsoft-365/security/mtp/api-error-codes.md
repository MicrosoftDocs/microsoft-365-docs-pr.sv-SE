---
title: Vanliga felkoder för Microsoft 365 Defender REST API
description: Läs mer om de vanliga felkoderna i Microsoft 365 Defender REST API
keywords: api, fel, koder, vanliga fel, mtp, api-felkoder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928396"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="5bfde-104">Vanliga felkoder för Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="5bfde-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5bfde-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5bfde-105">**Applies to:**</span></span>

- <span data-ttu-id="5bfde-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5bfde-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bfde-107">Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="5bfde-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5bfde-108">Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.</span><span class="sxs-lookup"><span data-stu-id="5bfde-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5bfde-109">Felkoder kan returneras av en åtgärd på någon av Microsoft 365 Defender-API:er.</span><span class="sxs-lookup"><span data-stu-id="5bfde-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="5bfde-110">Varje felsvar kommer att innehålla ett felmeddelande som kan hjälpa dig att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="5bfde-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="5bfde-111">Kolumnen med felmeddelanden i tabellavsnittet innehåller några exempelmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="5bfde-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="5bfde-112">Innehållet i faktiska meddelanden varierar beroende på de faktorer som utlöste svaret.</span><span class="sxs-lookup"><span data-stu-id="5bfde-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="5bfde-113">Variabelt innehåll anges i tabellen med vinkelparenteser.</span><span class="sxs-lookup"><span data-stu-id="5bfde-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="5bfde-114">Felkoder</span><span class="sxs-lookup"><span data-stu-id="5bfde-114">Error codes</span></span>

<span data-ttu-id="5bfde-115">Felkod</span><span class="sxs-lookup"><span data-stu-id="5bfde-115">Error code</span></span> | <span data-ttu-id="5bfde-116">HTTP-statuskod</span><span class="sxs-lookup"><span data-stu-id="5bfde-116">HTTP status code</span></span> | <span data-ttu-id="5bfde-117">Meddelande</span><span class="sxs-lookup"><span data-stu-id="5bfde-117">Message</span></span>
-|-|-
<span data-ttu-id="5bfde-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="5bfde-118">BadRequest</span></span> | <span data-ttu-id="5bfde-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-119">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-120">Felmeddelande för allmän begäran.</span><span class="sxs-lookup"><span data-stu-id="5bfde-120">General Bad Request error message.</span></span>
<span data-ttu-id="5bfde-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="5bfde-121">ODataError</span></span> | <span data-ttu-id="5bfde-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-122">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-123">Ogiltig OData-URI-fråga. \<the specific error is specified\></span><span class="sxs-lookup"><span data-stu-id="5bfde-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="5bfde-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="5bfde-124">InvalidInput</span></span> | <span data-ttu-id="5bfde-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-125">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-126">Ogiltiga \<the invalid input\> indata.</span><span class="sxs-lookup"><span data-stu-id="5bfde-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="5bfde-127">InvalidRequest Entitet</span><span class="sxs-lookup"><span data-stu-id="5bfde-127">InvalidRequestBody</span></span> | <span data-ttu-id="5bfde-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-128">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-129">Ogiltigt brödtext för begäran.</span><span class="sxs-lookup"><span data-stu-id="5bfde-129">Invalid request body.</span></span>
<span data-ttu-id="5bfde-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="5bfde-130">InvalidHashValue</span></span> | <span data-ttu-id="5bfde-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-131">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-132">Hash-värdet \<the invalid hash\> är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="5bfde-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="5bfde-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="5bfde-133">InvalidDomainName</span></span> | <span data-ttu-id="5bfde-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-134">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-135">Domännamnet \<the invalid domain\> är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="5bfde-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="5bfde-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="5bfde-136">InvalidIpAddress</span></span> | <span data-ttu-id="5bfde-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-137">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-138">IP-adressen \<the invalid IP\> är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="5bfde-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="5bfde-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="5bfde-139">InvalidUrl</span></span> | <span data-ttu-id="5bfde-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-140">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-141">URL \<the invalid URL\> är ogiltig.</span><span class="sxs-lookup"><span data-stu-id="5bfde-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="5bfde-142">MaximumBatchSizeExceededed</span><span class="sxs-lookup"><span data-stu-id="5bfde-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="5bfde-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-143">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-144">Maximal överskriden batchstorlek.</span><span class="sxs-lookup"><span data-stu-id="5bfde-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="5bfde-145">Mottaget: \<batch size received\> , tillåtet: {batchstorlek tillåten}.</span><span class="sxs-lookup"><span data-stu-id="5bfde-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="5bfde-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="5bfde-146">MissingRequiredParameter</span></span> | <span data-ttu-id="5bfde-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-147">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-148">Parametern \<the missing parameter\> saknas.</span><span class="sxs-lookup"><span data-stu-id="5bfde-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="5bfde-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="5bfde-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="5bfde-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-150">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-151">\<the client OS Platform\>OS-plattformen stöds inte för den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5bfde-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="5bfde-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="5bfde-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="5bfde-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="5bfde-153">BadRequest (400)</span></span> | <span data-ttu-id="5bfde-154">\<The requested action\> stöds i både \<supported client version\> klientversion och senare.</span><span class="sxs-lookup"><span data-stu-id="5bfde-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="5bfde-155">Obehörig</span><span class="sxs-lookup"><span data-stu-id="5bfde-155">Unauthorized</span></span> | <span data-ttu-id="5bfde-156">Obehörig (401)</span><span class="sxs-lookup"><span data-stu-id="5bfde-156">Unauthorized (401)</span></span> | <span data-ttu-id="5bfde-157">Obehörig</span><span class="sxs-lookup"><span data-stu-id="5bfde-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="5bfde-158">*Obs! Detta orsakas vanligtvis av ett ogiltigt eller utgånget auktoriseringshuvud.*</span><span class="sxs-lookup"><span data-stu-id="5bfde-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="5bfde-159">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="5bfde-159">Forbidden</span></span> | <span data-ttu-id="5bfde-160">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="5bfde-160">Forbidden (403)</span></span> | <span data-ttu-id="5bfde-161">Förbjudet</span><span class="sxs-lookup"><span data-stu-id="5bfde-161">Forbidden</span></span> <br /><br /><span data-ttu-id="5bfde-162">*Obs! Giltig token men otillräcklig behörighet för åtgärden.*</span><span class="sxs-lookup"><span data-stu-id="5bfde-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="5bfde-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="5bfde-163">DisabledFeature</span></span> | <span data-ttu-id="5bfde-164">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="5bfde-164">Forbidden (403)</span></span> | <span data-ttu-id="5bfde-165">Klientorganisationsfunktionen är inte aktiverad.</span><span class="sxs-lookup"><span data-stu-id="5bfde-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="5bfde-166">Inte tillåtetOperation</span><span class="sxs-lookup"><span data-stu-id="5bfde-166">DisallowedOperation</span></span> | <span data-ttu-id="5bfde-167">Förbjudet (403)</span><span class="sxs-lookup"><span data-stu-id="5bfde-167">Forbidden (403)</span></span> | <span data-ttu-id="5bfde-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="5bfde-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="5bfde-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="5bfde-169">NotFound</span></span> | <span data-ttu-id="5bfde-170">Hittades inte (404)</span><span class="sxs-lookup"><span data-stu-id="5bfde-170">Not Found (404)</span></span> | <span data-ttu-id="5bfde-171">Felmeddelandet Allmänt hittades inte.</span><span class="sxs-lookup"><span data-stu-id="5bfde-171">General Not Found error message.</span></span>
<span data-ttu-id="5bfde-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="5bfde-172">ResourceNotFound</span></span> | <span data-ttu-id="5bfde-173">Hittades inte (404)</span><span class="sxs-lookup"><span data-stu-id="5bfde-173">Not Found (404)</span></span> | <span data-ttu-id="5bfde-174">Resursen \<the requested resource\> hittades inte.</span><span class="sxs-lookup"><span data-stu-id="5bfde-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="5bfde-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="5bfde-175">InternalServerError</span></span> | <span data-ttu-id="5bfde-176">Internt serverfel (500)</span><span class="sxs-lookup"><span data-stu-id="5bfde-176">Internal Server Error (500)</span></span> | <span data-ttu-id="5bfde-177">*Obs! Inget felmeddelande, försök igen eller kontakta Microsoft om problemet inte åtgärdas*</span><span class="sxs-lookup"><span data-stu-id="5bfde-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="5bfde-178">Exempel</span><span class="sxs-lookup"><span data-stu-id="5bfde-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="5bfde-179">Parametrar för brödtext</span><span class="sxs-lookup"><span data-stu-id="5bfde-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5bfde-180">Parametrar för brödtext är case-sensitive.</span><span class="sxs-lookup"><span data-stu-id="5bfde-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="5bfde-181">Om du får *ett InvalidRequest Parameter-* eller *MissingRequiredParameter-fel* kan det bero på ett stavfel.</span><span class="sxs-lookup"><span data-stu-id="5bfde-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="5bfde-182">Granska API-dokumentationen och kontrollera att de inskickade parametrarna matchar det relevanta exemplet.</span><span class="sxs-lookup"><span data-stu-id="5bfde-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="5bfde-183">Spårnings-ID</span><span class="sxs-lookup"><span data-stu-id="5bfde-183">Tracking ID</span></span>

<span data-ttu-id="5bfde-184">Varje felsvar innehåller en unik ID-parameter för spårning.</span><span class="sxs-lookup"><span data-stu-id="5bfde-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="5bfde-185">Egenskapsnamnet för den här parametern är *mål.*</span><span class="sxs-lookup"><span data-stu-id="5bfde-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="5bfde-186">När du kontaktar oss om ett fel kan du bifoga detta ID för att hitta orsaken till problemet.</span><span class="sxs-lookup"><span data-stu-id="5bfde-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5bfde-187">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="5bfde-187">Related articles</span></span>

- [<span data-ttu-id="5bfde-188">Översikt över API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bfde-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5bfde-189">Microsoft 365 Defender API: er som stöds</span><span class="sxs-lookup"><span data-stu-id="5bfde-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="5bfde-190">Få åtkomst till API:er för Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bfde-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="5bfde-191">Läs mer om API-begränsningar och -licensiering</span><span class="sxs-lookup"><span data-stu-id="5bfde-191">Learn about API limits and licensing</span></span>](api-terms.md)
