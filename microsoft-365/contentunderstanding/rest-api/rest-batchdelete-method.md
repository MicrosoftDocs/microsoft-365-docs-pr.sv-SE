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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287459"
---
# <a name="batchdelete"></a><span data-ttu-id="e6594-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="e6594-103">BatchDelete</span></span>

<span data-ttu-id="e6594-104">Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="e6594-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="e6594-105">Observera att en modell måste tas bort från alla bibliotek innan den ska kunna tas bort (se [exempel](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="e6594-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="e6594-106">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="e6594-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="e6594-107">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="e6594-107">URI parameters</span></span>

<span data-ttu-id="e6594-108">Ingen</span><span class="sxs-lookup"><span data-stu-id="e6594-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="e6594-109">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="e6594-109">Request headers</span></span>

| <span data-ttu-id="e6594-110">Rubrik</span><span class="sxs-lookup"><span data-stu-id="e6594-110">Header</span></span> | <span data-ttu-id="e6594-111">Värde</span><span class="sxs-lookup"><span data-stu-id="e6594-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="e6594-112">Acceptera</span><span class="sxs-lookup"><span data-stu-id="e6594-112">Accept</span></span>|<span data-ttu-id="e6594-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="e6594-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="e6594-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e6594-114">Content-Type</span></span>|<span data-ttu-id="e6594-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="e6594-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="e6594-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="e6594-116">x-requestdigest</span></span>|<span data-ttu-id="e6594-117">Den lämpliga sammanfattningen för aktuell webbplats.</span><span class="sxs-lookup"><span data-stu-id="e6594-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="e6594-118">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="e6594-118">Request body</span></span>

| <span data-ttu-id="e6594-119">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-119">Name</span></span> | <span data-ttu-id="e6594-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="e6594-120">Required</span></span> | <span data-ttu-id="e6594-121">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-121">Type</span></span> | <span data-ttu-id="e6594-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="e6594-123">Publikationer</span><span class="sxs-lookup"><span data-stu-id="e6594-123">Publications</span></span>|<span data-ttu-id="e6594-124">ja</span><span class="sxs-lookup"><span data-stu-id="e6594-124">yes</span></span>|<span data-ttu-id="e6594-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="e6594-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="e6594-126">Samlingen MachineLearningPublicationEntityData som var och en anger modell- och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="e6594-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="e6594-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="e6594-128">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-128">Name</span></span> | <span data-ttu-id="e6594-129">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="e6594-129">Required</span></span> | <span data-ttu-id="e6594-130">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-130">Type</span></span> | <span data-ttu-id="e6594-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="e6594-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="e6594-132">ModelUniqueId</span></span>|<span data-ttu-id="e6594-133">ja</span><span class="sxs-lookup"><span data-stu-id="e6594-133">yes</span></span>|<span data-ttu-id="e6594-134">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-134">string</span></span>|<span data-ttu-id="e6594-135">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="e6594-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="e6594-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-136">TargetSiteUrl</span></span>|<span data-ttu-id="e6594-137">ja</span><span class="sxs-lookup"><span data-stu-id="e6594-137">yes</span></span>|<span data-ttu-id="e6594-138">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-138">string</span></span>|<span data-ttu-id="e6594-139">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e6594-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="e6594-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="e6594-141">ja</span><span class="sxs-lookup"><span data-stu-id="e6594-141">yes</span></span>|<span data-ttu-id="e6594-142">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-142">string</span></span>|<span data-ttu-id="e6594-143">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="e6594-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="e6594-145">ja</span><span class="sxs-lookup"><span data-stu-id="e6594-145">yes</span></span>|<span data-ttu-id="e6594-146">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-146">string</span></span>|<span data-ttu-id="e6594-147">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="e6594-148">Svar</span><span class="sxs-lookup"><span data-stu-id="e6594-148">Response</span></span>

| <span data-ttu-id="e6594-149">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-149">Name</span></span>   | <span data-ttu-id="e6594-150">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-150">Type</span></span>  | <span data-ttu-id="e6594-151">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e6594-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="e6594-152">200 OK</span></span>||<span data-ttu-id="e6594-p102">Det här är ett anpassat API som stöder borttagning av en modell från bibliotek med flera dokument. Vid delvis lyckad åtgärd kan 200 OK fortfarande returneras och anroparen måste inspektera svarstexten för att förstå om modellen har tagits bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="e6594-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="e6594-155">Svarstext</span><span class="sxs-lookup"><span data-stu-id="e6594-155">Response Body</span></span>

| <span data-ttu-id="e6594-156">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-156">Name</span></span>   | <span data-ttu-id="e6594-157">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-157">Type</span></span>  | <span data-ttu-id="e6594-158">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e6594-159">TotalSuccccis</span><span class="sxs-lookup"><span data-stu-id="e6594-159">TotalSuccesses</span></span>|<span data-ttu-id="e6594-160">int</span><span class="sxs-lookup"><span data-stu-id="e6594-160">int</span></span>|<span data-ttu-id="e6594-161">Det totala antalet modeller som tas bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="e6594-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="e6594-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="e6594-162">TotalFailures</span></span>|<span data-ttu-id="e6594-163">int</span><span class="sxs-lookup"><span data-stu-id="e6594-163">int</span></span>|<span data-ttu-id="e6594-164">Det totala antalet modeller som inte kan tas bort från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="e6594-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="e6594-165">Information</span><span class="sxs-lookup"><span data-stu-id="e6594-165">Details</span></span>|<span data-ttu-id="e6594-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="e6594-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="e6594-167">Samlingen MachineLearningPublicationResult som var och en anger det detaljerade resultatet av att ta bort modellen från ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="e6594-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="e6594-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="e6594-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="e6594-169">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-169">Name</span></span>   | <span data-ttu-id="e6594-170">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-170">Type</span></span>  | <span data-ttu-id="e6594-171">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e6594-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="e6594-172">StatusCode</span></span>|<span data-ttu-id="e6594-173">int</span><span class="sxs-lookup"><span data-stu-id="e6594-173">int</span></span>|<span data-ttu-id="e6594-174">HTTP-statuskoden.</span><span class="sxs-lookup"><span data-stu-id="e6594-174">The HTTP status code.</span></span>|
|<span data-ttu-id="e6594-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="e6594-175">ErrorMessage</span></span>|<span data-ttu-id="e6594-176">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-176">string</span></span>|<span data-ttu-id="e6594-177">Felmeddelandet som anger vad som är fel när modellen tillämpas på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="e6594-178">Publicering</span><span class="sxs-lookup"><span data-stu-id="e6594-178">Publication</span></span>|<span data-ttu-id="e6594-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="e6594-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="e6594-180">Den anger modellinformationen och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="e6594-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="e6594-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="e6594-182">Namn</span><span class="sxs-lookup"><span data-stu-id="e6594-182">Name</span></span> | <span data-ttu-id="e6594-183">Typ</span><span class="sxs-lookup"><span data-stu-id="e6594-183">Type</span></span> | <span data-ttu-id="e6594-184">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e6594-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="e6594-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="e6594-185">ModelUniqueId</span></span>|<span data-ttu-id="e6594-186">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-186">string</span></span>|<span data-ttu-id="e6594-187">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="e6594-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="e6594-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-188">TargetSiteUrl</span></span>|<span data-ttu-id="e6594-189">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-189">string</span></span>|<span data-ttu-id="e6594-190">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="e6594-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="e6594-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="e6594-192">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-192">string</span></span>|<span data-ttu-id="e6594-193">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="e6594-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e6594-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="e6594-195">sträng</span><span class="sxs-lookup"><span data-stu-id="e6594-195">string</span></span>|<span data-ttu-id="e6594-196">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="e6594-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="e6594-197">Exempel</span><span class="sxs-lookup"><span data-stu-id="e6594-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="e6594-198">Ta bort en modell från kontraktsdokumentbiblioteket i lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="e6594-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="e6594-199">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="e6594-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="e6594-200">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="e6594-200">Sample request</span></span>

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

#### <a name="sample-response"></a><span data-ttu-id="e6594-201">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="e6594-201">Sample response</span></span>

<span data-ttu-id="e6594-202">I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tas bort på de angivna biblioteken.</span><span class="sxs-lookup"><span data-stu-id="e6594-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="e6594-203">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="e6594-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e6594-204">Se även</span><span class="sxs-lookup"><span data-stu-id="e6594-204">See also</span></span>

[<span data-ttu-id="e6594-205">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="e6594-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
