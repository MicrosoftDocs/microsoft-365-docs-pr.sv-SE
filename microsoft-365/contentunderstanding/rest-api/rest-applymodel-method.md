---
title: Batch-tillämpa modell
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
description: Använd REST API för att tillämpa en dokumenttolkningsmodell på ett eller flera bibliotek.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286543"
---
# <a name="batch-apply-model"></a><span data-ttu-id="bef75-103">Batch-tillämpa modell</span><span class="sxs-lookup"><span data-stu-id="bef75-103">Batch Apply model</span></span>

<span data-ttu-id="bef75-104">Tillämpar (eller synkroniserar) en tränad dokumenttolkningsmodell på ett eller flera bibliotek (se [exempel](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="bef75-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="bef75-105">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="bef75-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="bef75-106">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="bef75-106">URI parameters</span></span>

<span data-ttu-id="bef75-107">Ingen</span><span class="sxs-lookup"><span data-stu-id="bef75-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="bef75-108">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="bef75-108">Request headers</span></span>

| <span data-ttu-id="bef75-109">Rubrik</span><span class="sxs-lookup"><span data-stu-id="bef75-109">Header</span></span> | <span data-ttu-id="bef75-110">Värde</span><span class="sxs-lookup"><span data-stu-id="bef75-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="bef75-111">Acceptera</span><span class="sxs-lookup"><span data-stu-id="bef75-111">Accept</span></span>|<span data-ttu-id="bef75-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="bef75-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="bef75-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="bef75-113">Content-Type</span></span>|<span data-ttu-id="bef75-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="bef75-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="bef75-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="bef75-115">x-requestdigest</span></span>|<span data-ttu-id="bef75-116">Den lämpliga sammanfattningen för aktuell webbplats.</span><span class="sxs-lookup"><span data-stu-id="bef75-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="bef75-117">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="bef75-117">Request body</span></span>

| <span data-ttu-id="bef75-118">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-118">Name</span></span> | <span data-ttu-id="bef75-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bef75-119">Required</span></span> | <span data-ttu-id="bef75-120">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-120">Type</span></span> | <span data-ttu-id="bef75-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="bef75-122">_metadata</span><span class="sxs-lookup"><span data-stu-id="bef75-122">__metadata</span></span>|<span data-ttu-id="bef75-123">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-123">yes</span></span>|<span data-ttu-id="bef75-124">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-124">string</span></span>|<span data-ttu-id="bef75-125">Ställ in objektmeta på SPO.</span><span class="sxs-lookup"><span data-stu-id="bef75-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="bef75-126">Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="bef75-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="bef75-127">Publikationer</span><span class="sxs-lookup"><span data-stu-id="bef75-127">Publications</span></span>|<span data-ttu-id="bef75-128">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-128">yes</span></span>|<span data-ttu-id="bef75-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="bef75-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="bef75-130">Samlingen MachineLearningPublicationEntityData som var och en anger modell- och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="bef75-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="bef75-131">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="bef75-132">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-132">Name</span></span> | <span data-ttu-id="bef75-133">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="bef75-133">Required</span></span> | <span data-ttu-id="bef75-134">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-134">Type</span></span> | <span data-ttu-id="bef75-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="bef75-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="bef75-136">ModelUniqueId</span></span>|<span data-ttu-id="bef75-137">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-137">yes</span></span>|<span data-ttu-id="bef75-138">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-138">string</span></span>|<span data-ttu-id="bef75-139">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="bef75-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="bef75-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-140">TargetSiteUrl</span></span>|<span data-ttu-id="bef75-141">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-141">yes</span></span>|<span data-ttu-id="bef75-142">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-142">string</span></span>|<span data-ttu-id="bef75-143">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bef75-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="bef75-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="bef75-145">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-145">yes</span></span>|<span data-ttu-id="bef75-146">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-146">string</span></span>|<span data-ttu-id="bef75-147">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="bef75-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="bef75-149">ja</span><span class="sxs-lookup"><span data-stu-id="bef75-149">yes</span></span>|<span data-ttu-id="bef75-150">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-150">string</span></span>|<span data-ttu-id="bef75-151">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="bef75-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="bef75-152">ViewOption</span></span>|<span data-ttu-id="bef75-153">nej</span><span class="sxs-lookup"><span data-stu-id="bef75-153">no</span></span>|<span data-ttu-id="bef75-154">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-154">string</span></span>|<span data-ttu-id="bef75-155">Anger om den nya modellvyn ska anges som biblioteksstandard.</span><span class="sxs-lookup"><span data-stu-id="bef75-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="bef75-156">Svar</span><span class="sxs-lookup"><span data-stu-id="bef75-156">Response</span></span>

| <span data-ttu-id="bef75-157">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-157">Name</span></span>   | <span data-ttu-id="bef75-158">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-158">Type</span></span>  | <span data-ttu-id="bef75-159">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="bef75-160">201 skapad</span><span class="sxs-lookup"><span data-stu-id="bef75-160">201 Created</span></span>||<span data-ttu-id="bef75-p102">Det här är ett anpassat API som stöder tillämpning av en modell för flera dokumentbibliotek. Om det skulle lyckas delvis kan 201 som skapats fortfarande returneras och anroparen måste inspektera svarstexten för att förstå om modellen har tillämpats på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="bef75-p102">This is a customized API to support applying a model to multi document libraries. In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="bef75-163">Svarstext</span><span class="sxs-lookup"><span data-stu-id="bef75-163">Response Body</span></span>

| <span data-ttu-id="bef75-164">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-164">Name</span></span>   | <span data-ttu-id="bef75-165">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-165">Type</span></span>  | <span data-ttu-id="bef75-166">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="bef75-167">TotalSuccccis</span><span class="sxs-lookup"><span data-stu-id="bef75-167">TotalSuccesses</span></span>|<span data-ttu-id="bef75-168">int</span><span class="sxs-lookup"><span data-stu-id="bef75-168">int</span></span>|<span data-ttu-id="bef75-169">Det totala antalet modeller som har tillämpats på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="bef75-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="bef75-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="bef75-170">TotalFailures</span></span>|<span data-ttu-id="bef75-171">int</span><span class="sxs-lookup"><span data-stu-id="bef75-171">int</span></span>|<span data-ttu-id="bef75-172">Det totala antalet modeller som inte kan tillämpas på ett dokumentbibliotek.</span><span class="sxs-lookup"><span data-stu-id="bef75-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="bef75-173">Information</span><span class="sxs-lookup"><span data-stu-id="bef75-173">Details</span></span>|<span data-ttu-id="bef75-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="bef75-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="bef75-175">Samlingen MachineLearningPublicationResult som var och en anger det detaljerade resultatet av att tillämpa modellen på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="bef75-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="bef75-176">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="bef75-177">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-177">Name</span></span>   | <span data-ttu-id="bef75-178">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-178">Type</span></span>  | <span data-ttu-id="bef75-179">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="bef75-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="bef75-180">StatusCode</span></span>|<span data-ttu-id="bef75-181">int</span><span class="sxs-lookup"><span data-stu-id="bef75-181">int</span></span>|<span data-ttu-id="bef75-182">HTTP-statuskoden.</span><span class="sxs-lookup"><span data-stu-id="bef75-182">The HTTP status code.</span></span>|
|<span data-ttu-id="bef75-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="bef75-183">ErrorMessage</span></span>|<span data-ttu-id="bef75-184">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-184">string</span></span>|<span data-ttu-id="bef75-185">Felmeddelandet som anger vad som är fel när modellen tillämpas på dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="bef75-186">Publicering</span><span class="sxs-lookup"><span data-stu-id="bef75-186">Publication</span></span>|<span data-ttu-id="bef75-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="bef75-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="bef75-188">Den anger modellinformationen och måldokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="bef75-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="bef75-189">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="bef75-190">Namn</span><span class="sxs-lookup"><span data-stu-id="bef75-190">Name</span></span> | <span data-ttu-id="bef75-191">Typ</span><span class="sxs-lookup"><span data-stu-id="bef75-191">Type</span></span> | <span data-ttu-id="bef75-192">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bef75-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="bef75-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="bef75-193">ModelUniqueId</span></span>|<span data-ttu-id="bef75-194">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-194">string</span></span>|<span data-ttu-id="bef75-195">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="bef75-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="bef75-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-196">TargetSiteUrl</span></span>|<span data-ttu-id="bef75-197">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-197">string</span></span>|<span data-ttu-id="bef75-198">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="bef75-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="bef75-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="bef75-200">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-200">string</span></span>|<span data-ttu-id="bef75-201">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="bef75-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="bef75-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="bef75-203">sträng</span><span class="sxs-lookup"><span data-stu-id="bef75-203">string</span></span>|<span data-ttu-id="bef75-204">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="bef75-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="bef75-205">Exempel</span><span class="sxs-lookup"><span data-stu-id="bef75-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="bef75-206">Tillämpa en modell på kontraktsdokumentbiblioteket i lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="bef75-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="bef75-207">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="bef75-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="bef75-208">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="bef75-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="bef75-209">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="bef75-209">Sample response</span></span>

<span data-ttu-id="bef75-210">I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tillämpas på de angivna biblioteken.</span><span class="sxs-lookup"><span data-stu-id="bef75-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="bef75-211">**Statuskod:** 201</span><span class="sxs-lookup"><span data-stu-id="bef75-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="bef75-212">Se även</span><span class="sxs-lookup"><span data-stu-id="bef75-212">See also</span></span>

[<span data-ttu-id="bef75-213">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="bef75-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
