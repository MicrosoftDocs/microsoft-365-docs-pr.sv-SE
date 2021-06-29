---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Använd REST API för att ta bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177243"
---
# <a name="batchdelete"></a><span data-ttu-id="aedc8-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="aedc8-103">BatchDelete</span></span>

<span data-ttu-id="aedc8-104">Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="aedc8-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="aedc8-105">Observera att en modell måste tas bort från alla bibliotek innan den ska kunna tas bort (se [exempel](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="aedc8-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="aedc8-106">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="aedc8-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="aedc8-107">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="aedc8-107">URI parameters</span></span>

<span data-ttu-id="aedc8-108">Ingen</span><span class="sxs-lookup"><span data-stu-id="aedc8-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="aedc8-109">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="aedc8-109">Request headers</span></span>

| <span data-ttu-id="aedc8-110">Rubrik</span><span class="sxs-lookup"><span data-stu-id="aedc8-110">Header</span></span> | <span data-ttu-id="aedc8-111">Värde</span><span class="sxs-lookup"><span data-stu-id="aedc8-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="aedc8-112">Acceptera</span><span class="sxs-lookup"><span data-stu-id="aedc8-112">Accept</span></span>|<span data-ttu-id="aedc8-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="aedc8-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="aedc8-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="aedc8-114">Content-Type</span></span>|<span data-ttu-id="aedc8-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="aedc8-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="aedc8-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="aedc8-116">x-requestdigest</span></span>|<span data-ttu-id="aedc8-117">Den lämpliga sammanfattningen för aktuell webbplats.</span><span class="sxs-lookup"><span data-stu-id="aedc8-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="aedc8-118">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="aedc8-118">Request body</span></span>

| <span data-ttu-id="aedc8-119">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-119">Name</span></span> | <span data-ttu-id="aedc8-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="aedc8-120">Required</span></span> | <span data-ttu-id="aedc8-121">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-121">Type</span></span> | <span data-ttu-id="aedc8-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="aedc8-123">Publikationer</span><span class="sxs-lookup"><span data-stu-id="aedc8-123">Publications</span></span>|<span data-ttu-id="aedc8-124">ja</span><span class="sxs-lookup"><span data-stu-id="aedc8-124">yes</span></span>|<span data-ttu-id="aedc8-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="aedc8-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="aedc8-126">Samlingen MachineLearningPublicationEntityData som var och en anger modell- och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="aedc8-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="aedc8-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="aedc8-128">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-128">Name</span></span> | <span data-ttu-id="aedc8-129">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="aedc8-129">Required</span></span> | <span data-ttu-id="aedc8-130">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-130">Type</span></span> | <span data-ttu-id="aedc8-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="aedc8-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="aedc8-132">ModelUniqueId</span></span>|<span data-ttu-id="aedc8-133">ja</span><span class="sxs-lookup"><span data-stu-id="aedc8-133">yes</span></span>|<span data-ttu-id="aedc8-134">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-134">string</span></span>|<span data-ttu-id="aedc8-135">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="aedc8-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="aedc8-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-136">TargetSiteUrl</span></span>|<span data-ttu-id="aedc8-137">ja</span><span class="sxs-lookup"><span data-stu-id="aedc8-137">yes</span></span>|<span data-ttu-id="aedc8-138">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-138">string</span></span>|<span data-ttu-id="aedc8-139">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="aedc8-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="aedc8-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="aedc8-141">ja</span><span class="sxs-lookup"><span data-stu-id="aedc8-141">yes</span></span>|<span data-ttu-id="aedc8-142">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-142">string</span></span>|<span data-ttu-id="aedc8-143">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="aedc8-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="aedc8-145">ja</span><span class="sxs-lookup"><span data-stu-id="aedc8-145">yes</span></span>|<span data-ttu-id="aedc8-146">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-146">string</span></span>|<span data-ttu-id="aedc8-147">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="aedc8-148">Svar</span><span class="sxs-lookup"><span data-stu-id="aedc8-148">Response</span></span>

| <span data-ttu-id="aedc8-149">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-149">Name</span></span>   | <span data-ttu-id="aedc8-150">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-150">Type</span></span>  | <span data-ttu-id="aedc8-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="aedc8-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="aedc8-152">200 OK</span></span>||<span data-ttu-id="aedc8-153">Det här är ett anpassat API som stöder borttagning av en modell från bibliotek med flera dokument.</span><span class="sxs-lookup"><span data-stu-id="aedc8-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="aedc8-154">Vid delvis lyckad åtgärd kan 200 OK fortfarande returneras och anroparen måste inspektera svarstexten för att förstå om modellen har tagits bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="aedc8-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="aedc8-155">Svarstext</span><span class="sxs-lookup"><span data-stu-id="aedc8-155">Response Body</span></span>
| <span data-ttu-id="aedc8-156">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-156">Name</span></span>   | <span data-ttu-id="aedc8-157">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-157">Type</span></span>  | <span data-ttu-id="aedc8-158">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="aedc8-159">TotalSuccccis</span><span class="sxs-lookup"><span data-stu-id="aedc8-159">TotalSuccesses</span></span>|<span data-ttu-id="aedc8-160">int</span><span class="sxs-lookup"><span data-stu-id="aedc8-160">int</span></span>|<span data-ttu-id="aedc8-161">Det totala antalet modeller som tas bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="aedc8-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="aedc8-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="aedc8-162">TotalFailures</span></span>|<span data-ttu-id="aedc8-163">int</span><span class="sxs-lookup"><span data-stu-id="aedc8-163">int</span></span>|<span data-ttu-id="aedc8-164">Det totala antalet modeller som inte kan tas bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="aedc8-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="aedc8-165">Information</span><span class="sxs-lookup"><span data-stu-id="aedc8-165">Details</span></span>|<span data-ttu-id="aedc8-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="aedc8-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="aedc8-167">Samlingen MachineLearningPublicationResult som var och en anger det detaljerade resultatet av att ta bort modellen från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="aedc8-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="aedc8-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="aedc8-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="aedc8-169">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-169">Name</span></span>   | <span data-ttu-id="aedc8-170">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-170">Type</span></span>  | <span data-ttu-id="aedc8-171">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="aedc8-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="aedc8-172">StatusCode</span></span>|<span data-ttu-id="aedc8-173">int</span><span class="sxs-lookup"><span data-stu-id="aedc8-173">int</span></span>|<span data-ttu-id="aedc8-174">HTTP-statuskoden.</span><span class="sxs-lookup"><span data-stu-id="aedc8-174">The HTTP status code.</span></span>|
|<span data-ttu-id="aedc8-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="aedc8-175">ErrorMessage</span></span>|<span data-ttu-id="aedc8-176">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-176">string</span></span>|<span data-ttu-id="aedc8-177">Felmeddelandet som anger vad som är fel när modellen tillämpas på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="aedc8-178">Publicering</span><span class="sxs-lookup"><span data-stu-id="aedc8-178">Publication</span></span>|<span data-ttu-id="aedc8-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="aedc8-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="aedc8-180">Den anger modellinformationen och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="aedc8-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="aedc8-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="aedc8-182">Namn</span><span class="sxs-lookup"><span data-stu-id="aedc8-182">Name</span></span> | <span data-ttu-id="aedc8-183">Typ</span><span class="sxs-lookup"><span data-stu-id="aedc8-183">Type</span></span> | <span data-ttu-id="aedc8-184">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aedc8-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="aedc8-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="aedc8-185">ModelUniqueId</span></span>|<span data-ttu-id="aedc8-186">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-186">string</span></span>|<span data-ttu-id="aedc8-187">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="aedc8-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="aedc8-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-188">TargetSiteUrl</span></span>|<span data-ttu-id="aedc8-189">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-189">string</span></span>|<span data-ttu-id="aedc8-190">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="aedc8-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="aedc8-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="aedc8-192">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-192">string</span></span>|<span data-ttu-id="aedc8-193">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="aedc8-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="aedc8-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="aedc8-195">sträng</span><span class="sxs-lookup"><span data-stu-id="aedc8-195">string</span></span>|<span data-ttu-id="aedc8-196">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="aedc8-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="aedc8-197">Exempel</span><span class="sxs-lookup"><span data-stu-id="aedc8-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="aedc8-198">Ta bort en modell från kontraktsdokumentbiblioteket i lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="aedc8-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="aedc8-199">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="aedc8-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="aedc8-200">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="aedc8-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="aedc8-201">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="aedc8-201">Sample response</span></span>

<span data-ttu-id="aedc8-202">I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tas bort på de angivna biblioteken.</span><span class="sxs-lookup"><span data-stu-id="aedc8-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="aedc8-203">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="aedc8-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="aedc8-204">Se även</span><span class="sxs-lookup"><span data-stu-id="aedc8-204">See also</span></span>

[<span data-ttu-id="aedc8-205">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="aedc8-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
