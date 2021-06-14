---
title: Tillämpa en modell
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904357"
---
# <a name="apply-model"></a><span data-ttu-id="356f7-103">Tillämpa en modell</span><span class="sxs-lookup"><span data-stu-id="356f7-103">Apply model</span></span>

<span data-ttu-id="356f7-104">Tillämpar (eller synkroniserar) en tränad dokumenttolkningsmodell på ett eller flera bibliotek (se [exempel](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="356f7-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="356f7-105">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="356f7-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="356f7-106">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="356f7-106">URI parameters</span></span>

<span data-ttu-id="356f7-107">Ingen</span><span class="sxs-lookup"><span data-stu-id="356f7-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="356f7-108">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="356f7-108">Request headers</span></span>

| <span data-ttu-id="356f7-109">Rubrik</span><span class="sxs-lookup"><span data-stu-id="356f7-109">Header</span></span> | <span data-ttu-id="356f7-110">Värde</span><span class="sxs-lookup"><span data-stu-id="356f7-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="356f7-111">Acceptera</span><span class="sxs-lookup"><span data-stu-id="356f7-111">Accept</span></span>|<span data-ttu-id="356f7-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="356f7-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="356f7-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="356f7-113">Content-Type</span></span>|<span data-ttu-id="356f7-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="356f7-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="356f7-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="356f7-115">x-requestdigest</span></span>|<span data-ttu-id="356f7-116">Den lämpliga sammanfattningen för aktuell webbplats.</span><span class="sxs-lookup"><span data-stu-id="356f7-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="356f7-117">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="356f7-117">Request body</span></span>

| <span data-ttu-id="356f7-118">Namn</span><span class="sxs-lookup"><span data-stu-id="356f7-118">Name</span></span> | <span data-ttu-id="356f7-119">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="356f7-119">Required</span></span> | <span data-ttu-id="356f7-120">Typ</span><span class="sxs-lookup"><span data-stu-id="356f7-120">Type</span></span> | <span data-ttu-id="356f7-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="356f7-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="356f7-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="356f7-122">ModelUniqueId</span></span>|<span data-ttu-id="356f7-123">ja</span><span class="sxs-lookup"><span data-stu-id="356f7-123">yes</span></span>|<span data-ttu-id="356f7-124">sträng</span><span class="sxs-lookup"><span data-stu-id="356f7-124">string</span></span>|<span data-ttu-id="356f7-125">Modellfilens unika ID.</span><span class="sxs-lookup"><span data-stu-id="356f7-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="356f7-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="356f7-126">TargetSiteUrl</span></span>|<span data-ttu-id="356f7-127">ja</span><span class="sxs-lookup"><span data-stu-id="356f7-127">yes</span></span>|<span data-ttu-id="356f7-128">sträng</span><span class="sxs-lookup"><span data-stu-id="356f7-128">string</span></span>|<span data-ttu-id="356f7-129">Den fullständiga URL-adressen till målbibliotekswebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="356f7-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="356f7-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="356f7-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="356f7-131">ja</span><span class="sxs-lookup"><span data-stu-id="356f7-131">yes</span></span>|<span data-ttu-id="356f7-132">sträng</span><span class="sxs-lookup"><span data-stu-id="356f7-132">string</span></span>|<span data-ttu-id="356f7-133">Serverns relativa URL-adress för webben för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="356f7-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="356f7-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="356f7-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="356f7-135">ja</span><span class="sxs-lookup"><span data-stu-id="356f7-135">yes</span></span>|<span data-ttu-id="356f7-136">sträng</span><span class="sxs-lookup"><span data-stu-id="356f7-136">string</span></span>|<span data-ttu-id="356f7-137">Serverns relativa URL-adress för målbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="356f7-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="356f7-138">ViewOption</span><span class="sxs-lookup"><span data-stu-id="356f7-138">ViewOption</span></span>|<span data-ttu-id="356f7-139">nej</span><span class="sxs-lookup"><span data-stu-id="356f7-139">no</span></span>|<span data-ttu-id="356f7-140">sträng</span><span class="sxs-lookup"><span data-stu-id="356f7-140">string</span></span>|<span data-ttu-id="356f7-141">Anger om den nya modellvyn ska anges som biblioteksstandard.</span><span class="sxs-lookup"><span data-stu-id="356f7-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="356f7-142">Svar</span><span class="sxs-lookup"><span data-stu-id="356f7-142">Response</span></span>

| <span data-ttu-id="356f7-143">Namn</span><span class="sxs-lookup"><span data-stu-id="356f7-143">Name</span></span>   | <span data-ttu-id="356f7-144">Typ</span><span class="sxs-lookup"><span data-stu-id="356f7-144">Type</span></span>  | <span data-ttu-id="356f7-145">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="356f7-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="356f7-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="356f7-146">200 OK</span></span>| |<span data-ttu-id="356f7-147">Klart</span><span class="sxs-lookup"><span data-stu-id="356f7-147">Success</span></span>|
|<span data-ttu-id="356f7-148">201 skapad</span><span class="sxs-lookup"><span data-stu-id="356f7-148">201 Created</span></span>| |<span data-ttu-id="356f7-149">Observera att eftersom detta API stöder att tillämpa modell för flera bibliotek kan 201 returneras även om det inte går att tillämpa modellen på ett av biblioteken.</span><span class="sxs-lookup"><span data-stu-id="356f7-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="356f7-150">Kontrollera svarbrödtexten för att förstå om modellen har tillämpats på alla angivna bibliotek.</span><span class="sxs-lookup"><span data-stu-id="356f7-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="356f7-151">Gå till [Frågebrödtext](rest-applymodel-method.md#request-body) för mer information.</span><span class="sxs-lookup"><span data-stu-id="356f7-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="356f7-152">Exempel</span><span class="sxs-lookup"><span data-stu-id="356f7-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="356f7-153">Tillämpa en modell på kontraktsdokumentbiblioteket i lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="356f7-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="356f7-154">I det här exemplet är ID:t för dokumenttolkningsmodellen i Contoso Contract `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="356f7-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="356f7-155">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="356f7-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="356f7-156">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="356f7-156">Sample response</span></span>

<span data-ttu-id="356f7-157">I svaret refererar TotalFailures och TotalSuccesses till antalet misslyckanden och framgångar för modellen som tillämpas på de angivna biblioteken.</span><span class="sxs-lookup"><span data-stu-id="356f7-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="356f7-158">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="356f7-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="356f7-159">Se även</span><span class="sxs-lookup"><span data-stu-id="356f7-159">See also</span></span>

[<span data-ttu-id="356f7-160">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="356f7-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
