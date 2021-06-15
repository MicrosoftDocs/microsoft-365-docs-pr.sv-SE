---
title: Hämta modell- och biblioteksinformation
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
description: Använd REST API för att få information om en modell och biblioteket där den har tillämpats.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904298"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="633fb-103">Hämta modell- och biblioteksinformation</span><span class="sxs-lookup"><span data-stu-id="633fb-103">Get model and library information</span></span>

<span data-ttu-id="633fb-104">Hämtar information om en modell och biblioteket där den har tillämpats (se [exempel](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="633fb-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="633fb-105">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="633fb-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="633fb-106">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="633fb-106">URI parameters</span></span>

| <span data-ttu-id="633fb-107">Namn</span><span class="sxs-lookup"><span data-stu-id="633fb-107">Name</span></span> | <span data-ttu-id="633fb-108">In</span><span class="sxs-lookup"><span data-stu-id="633fb-108">In</span></span> | <span data-ttu-id="633fb-109">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="633fb-109">Required</span></span> | <span data-ttu-id="633fb-110">Typ</span><span class="sxs-lookup"><span data-stu-id="633fb-110">Type</span></span> | <span data-ttu-id="633fb-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="633fb-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="633fb-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="633fb-112">ModelUniqueId</span></span>|<span data-ttu-id="633fb-113">fråga</span><span class="sxs-lookup"><span data-stu-id="633fb-113">query</span></span>|<span data-ttu-id="633fb-114">Sant</span><span class="sxs-lookup"><span data-stu-id="633fb-114">True</span></span>|<span data-ttu-id="633fb-115">GUID</span><span class="sxs-lookup"><span data-stu-id="633fb-115">GUID</span></span>|<span data-ttu-id="633fb-116">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="633fb-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="633fb-117">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="633fb-117">Request headers</span></span>

| <span data-ttu-id="633fb-118">Rubrik</span><span class="sxs-lookup"><span data-stu-id="633fb-118">Header</span></span> | <span data-ttu-id="633fb-119">Värde</span><span class="sxs-lookup"><span data-stu-id="633fb-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="633fb-120">Acceptera</span><span class="sxs-lookup"><span data-stu-id="633fb-120">Accept</span></span>|<span data-ttu-id="633fb-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="633fb-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="633fb-122">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="633fb-122">Request body</span></span>

| <span data-ttu-id="633fb-123">Namn</span><span class="sxs-lookup"><span data-stu-id="633fb-123">Name</span></span> | <span data-ttu-id="633fb-124">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="633fb-124">Required</span></span> | <span data-ttu-id="633fb-125">Typ</span><span class="sxs-lookup"><span data-stu-id="633fb-125">Type</span></span> | <span data-ttu-id="633fb-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="633fb-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="633fb-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="633fb-127">ModelUniqueId</span></span>|<span data-ttu-id="633fb-128">ja</span><span class="sxs-lookup"><span data-stu-id="633fb-128">yes</span></span>|<span data-ttu-id="633fb-129">sträng</span><span class="sxs-lookup"><span data-stu-id="633fb-129">string</span></span>|<span data-ttu-id="633fb-130">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="633fb-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="633fb-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="633fb-131">TargetSiteUrl</span></span>|<span data-ttu-id="633fb-132">ja</span><span class="sxs-lookup"><span data-stu-id="633fb-132">yes</span></span>|<span data-ttu-id="633fb-133">sträng</span><span class="sxs-lookup"><span data-stu-id="633fb-133">string</span></span>|<span data-ttu-id="633fb-134">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="633fb-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="633fb-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="633fb-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="633fb-136">ja</span><span class="sxs-lookup"><span data-stu-id="633fb-136">yes</span></span>|<span data-ttu-id="633fb-137">sträng</span><span class="sxs-lookup"><span data-stu-id="633fb-137">string</span></span>|<span data-ttu-id="633fb-138">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="633fb-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="633fb-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="633fb-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="633fb-140">ja</span><span class="sxs-lookup"><span data-stu-id="633fb-140">yes</span></span>|<span data-ttu-id="633fb-141">sträng</span><span class="sxs-lookup"><span data-stu-id="633fb-141">string</span></span>|<span data-ttu-id="633fb-142">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="633fb-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="633fb-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="633fb-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="633fb-144">ja</span><span class="sxs-lookup"><span data-stu-id="633fb-144">yes</span></span>|<span data-ttu-id="633fb-145">int</span><span class="sxs-lookup"><span data-stu-id="633fb-145">int</span></span>|<span data-ttu-id="633fb-146">Flaggan som anger om målbiblioteket har tagits bort eller inte.</span><span class="sxs-lookup"><span data-stu-id="633fb-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="633fb-147">Svar</span><span class="sxs-lookup"><span data-stu-id="633fb-147">Response</span></span>

| <span data-ttu-id="633fb-148">Namn</span><span class="sxs-lookup"><span data-stu-id="633fb-148">Name</span></span>   | <span data-ttu-id="633fb-149">Typ</span><span class="sxs-lookup"><span data-stu-id="633fb-149">Type</span></span>  | <span data-ttu-id="633fb-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="633fb-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="633fb-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="633fb-151">200 OK</span></span>| |<span data-ttu-id="633fb-152">Klart</span><span class="sxs-lookup"><span data-stu-id="633fb-152">Success</span></span>|
|<span data-ttu-id="633fb-153">201 skapad</span><span class="sxs-lookup"><span data-stu-id="633fb-153">201 Created</span></span>| |<span data-ttu-id="633fb-154">Observera att eftersom detta API stöder att tillämpa modell på flera bibliotek, kan en 201 returneras även om det inte går att tillämpa modellen på ett av biblioteken.</span><span class="sxs-lookup"><span data-stu-id="633fb-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="633fb-155">Kontrollera svarbrödtexten för att förstå om modellen har tillämpats på alla angivna bibliotek.</span><span class="sxs-lookup"><span data-stu-id="633fb-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="633fb-156">Gå till [Frågebrödtext](rest-getmodelandlibraryinfo.md#request-body) för mer information.</span><span class="sxs-lookup"><span data-stu-id="633fb-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="633fb-157">Exempel</span><span class="sxs-lookup"><span data-stu-id="633fb-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="633fb-158">Få information om kontraktsmodellen och det främsta dokumentbiblioteket på lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="633fb-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="633fb-159">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="633fb-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="633fb-160">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="633fb-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="633fb-161">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="633fb-161">Sample response</span></span>

<span data-ttu-id="633fb-162">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="633fb-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="633fb-163">Se även</span><span class="sxs-lookup"><span data-stu-id="633fb-163">See also</span></span>

[<span data-ttu-id="633fb-164">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="633fb-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)