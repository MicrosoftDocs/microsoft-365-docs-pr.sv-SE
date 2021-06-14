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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904277"
---
# <a name="batchdelete"></a><span data-ttu-id="d9016-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="d9016-103">BatchDelete</span></span>

<span data-ttu-id="d9016-104">Tar bort en tillämpad dokumenttolkningsmodell från ett eller flera bibliotek.</span><span class="sxs-lookup"><span data-stu-id="d9016-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="d9016-105">Observera att en modell måste tas bort från alla bibliotek innan den ska kunna tas bort (se [exempel](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="d9016-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="d9016-106">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="d9016-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="d9016-107">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="d9016-107">URI parameters</span></span>

<span data-ttu-id="d9016-108">Ingen</span><span class="sxs-lookup"><span data-stu-id="d9016-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="d9016-109">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="d9016-109">Request headers</span></span>

| <span data-ttu-id="d9016-110">Rubrik</span><span class="sxs-lookup"><span data-stu-id="d9016-110">Header</span></span> | <span data-ttu-id="d9016-111">Värde</span><span class="sxs-lookup"><span data-stu-id="d9016-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="d9016-112">Acceptera</span><span class="sxs-lookup"><span data-stu-id="d9016-112">Accept</span></span>|<span data-ttu-id="d9016-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="d9016-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="d9016-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d9016-114">Content-Type</span></span>|<span data-ttu-id="d9016-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="d9016-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="d9016-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="d9016-116">x-requestdigest</span></span>|<span data-ttu-id="d9016-117">Den lämpliga sammanfattningen för aktuell webbplats.</span><span class="sxs-lookup"><span data-stu-id="d9016-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="d9016-118">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="d9016-118">Request body</span></span>

| <span data-ttu-id="d9016-119">Namn</span><span class="sxs-lookup"><span data-stu-id="d9016-119">Name</span></span> | <span data-ttu-id="d9016-120">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="d9016-120">Required</span></span> | <span data-ttu-id="d9016-121">Typ</span><span class="sxs-lookup"><span data-stu-id="d9016-121">Type</span></span> | <span data-ttu-id="d9016-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d9016-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="d9016-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="d9016-123">ModelUniqueId</span></span>|<span data-ttu-id="d9016-124">ja</span><span class="sxs-lookup"><span data-stu-id="d9016-124">yes</span></span>|<span data-ttu-id="d9016-125">sträng</span><span class="sxs-lookup"><span data-stu-id="d9016-125">string</span></span>|<span data-ttu-id="d9016-126">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="d9016-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="d9016-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="d9016-127">TargetSiteUrl</span></span>|<span data-ttu-id="d9016-128">ja</span><span class="sxs-lookup"><span data-stu-id="d9016-128">yes</span></span>|<span data-ttu-id="d9016-129">sträng</span><span class="sxs-lookup"><span data-stu-id="d9016-129">string</span></span>|<span data-ttu-id="d9016-130">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d9016-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="d9016-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d9016-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="d9016-132">ja</span><span class="sxs-lookup"><span data-stu-id="d9016-132">yes</span></span>|<span data-ttu-id="d9016-133">sträng</span><span class="sxs-lookup"><span data-stu-id="d9016-133">string</span></span>|<span data-ttu-id="d9016-134">Serverns relativa webbadress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="d9016-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="d9016-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="d9016-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="d9016-136">ja</span><span class="sxs-lookup"><span data-stu-id="d9016-136">yes</span></span>|<span data-ttu-id="d9016-137">sträng</span><span class="sxs-lookup"><span data-stu-id="d9016-137">string</span></span>|<span data-ttu-id="d9016-138">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="d9016-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="d9016-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="d9016-139">ViewOption</span></span>|<span data-ttu-id="d9016-140">ingen</span><span class="sxs-lookup"><span data-stu-id="d9016-140">no</span></span>|<span data-ttu-id="d9016-141">sträng</span><span class="sxs-lookup"><span data-stu-id="d9016-141">string</span></span>|<span data-ttu-id="d9016-142">Anger om den nya modellvyn ska anges som biblioteksstandard.</span><span class="sxs-lookup"><span data-stu-id="d9016-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="d9016-143">Svar</span><span class="sxs-lookup"><span data-stu-id="d9016-143">Response</span></span>

| <span data-ttu-id="d9016-144">Namn</span><span class="sxs-lookup"><span data-stu-id="d9016-144">Name</span></span>   | <span data-ttu-id="d9016-145">Typ</span><span class="sxs-lookup"><span data-stu-id="d9016-145">Type</span></span>  | <span data-ttu-id="d9016-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="d9016-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="d9016-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="d9016-147">200 OK</span></span>| |<span data-ttu-id="d9016-148">Klart</span><span class="sxs-lookup"><span data-stu-id="d9016-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="d9016-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="d9016-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="d9016-150">Ta bort en modell från kontraktsdokumentbiblioteket i lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="d9016-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="d9016-151">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="d9016-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="d9016-152">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="d9016-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="d9016-153">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="d9016-153">Sample response</span></span>

<span data-ttu-id="d9016-154">I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tillämpas på de angivna biblioteken.</span><span class="sxs-lookup"><span data-stu-id="d9016-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="d9016-155">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="d9016-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d9016-156">Se även</span><span class="sxs-lookup"><span data-stu-id="d9016-156">See also</span></span>

[<span data-ttu-id="d9016-157">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="d9016-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
