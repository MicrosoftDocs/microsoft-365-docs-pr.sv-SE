---
title: Skapa modell
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
description: Använd REST API för att skapa en modell och dess associerade innehållstyp.
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177159"
---
# <a name="create-model"></a><span data-ttu-id="b668f-103">Skapa modell</span><span class="sxs-lookup"><span data-stu-id="b668f-103">Create model</span></span>

<span data-ttu-id="b668f-104">Skapar en modell och dess associerade innehållstyp.</span><span class="sxs-lookup"><span data-stu-id="b668f-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="b668f-105">Observera att det bara skapar modellen.</span><span class="sxs-lookup"><span data-stu-id="b668f-105">Note that this only creates the model.</span></span> <span data-ttu-id="b668f-106">Den kommer fortfarande att behöva tränas i innehållscentret (se [exempel](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="b668f-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="b668f-107">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b668f-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="b668f-108">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="b668f-108">URI Parameters</span></span>

<span data-ttu-id="b668f-109">Ingen</span><span class="sxs-lookup"><span data-stu-id="b668f-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="b668f-110">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="b668f-110">Request headers</span></span>

| <span data-ttu-id="b668f-111">Rubrik</span><span class="sxs-lookup"><span data-stu-id="b668f-111">Header</span></span> | <span data-ttu-id="b668f-112">Värde</span><span class="sxs-lookup"><span data-stu-id="b668f-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="b668f-113">Acceptera</span><span class="sxs-lookup"><span data-stu-id="b668f-113">Accept</span></span>|<span data-ttu-id="b668f-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="b668f-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="b668f-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b668f-115">Content-Type</span></span>|<span data-ttu-id="b668f-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="b668f-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="b668f-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="b668f-117">x-requestdigest</span></span>|<span data-ttu-id="b668f-118">Den lämpliga sammanfattningen för aktuell webbplats</span><span class="sxs-lookup"><span data-stu-id="b668f-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="b668f-119">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="b668f-119">Request body</span></span>

|<span data-ttu-id="b668f-120">Namn</span><span class="sxs-lookup"><span data-stu-id="b668f-120">Name</span></span>    |<span data-ttu-id="b668f-121">Typ</span><span class="sxs-lookup"><span data-stu-id="b668f-121">Type</span></span>   |<span data-ttu-id="b668f-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b668f-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="b668f-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="b668f-123">_metadata</span></span>|  |<span data-ttu-id="b668f-124">Ställ in objektmeta på SPO.</span><span class="sxs-lookup"><span data-stu-id="b668f-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="b668f-125">Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="b668f-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="b668f-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="b668f-126">ContentTypeGroup</span></span>|<span data-ttu-id="b668f-127">sträng</span><span class="sxs-lookup"><span data-stu-id="b668f-127">string</span></span>|<span data-ttu-id="b668f-128">Den associerade innehållstypgrupp som är kopplad till modellen.</span><span class="sxs-lookup"><span data-stu-id="b668f-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="b668f-129">Som standard för “Intelligenta dokumentinnehållstyper".</span><span class="sxs-lookup"><span data-stu-id="b668f-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="b668f-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="b668f-130">ContentTypeName</span></span>|<span data-ttu-id="b668f-131">sträng</span><span class="sxs-lookup"><span data-stu-id="b668f-131">string</span></span>|<span data-ttu-id="b668f-132">Namnet på den associerade innehållstypen.</span><span class="sxs-lookup"><span data-stu-id="b668f-132">The associated content type name.</span></span> <span data-ttu-id="b668f-133">Den skapade modellfilen kommer att ha samma namn.</span><span class="sxs-lookup"><span data-stu-id="b668f-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="b668f-134">Svar</span><span class="sxs-lookup"><span data-stu-id="b668f-134">Responses</span></span>

| <span data-ttu-id="b668f-135">Namn</span><span class="sxs-lookup"><span data-stu-id="b668f-135">Name</span></span>   | <span data-ttu-id="b668f-136">Typ</span><span class="sxs-lookup"><span data-stu-id="b668f-136">Type</span></span>  | <span data-ttu-id="b668f-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b668f-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="b668f-138">201 skapad</span><span class="sxs-lookup"><span data-stu-id="b668f-138">201 Created</span></span>| |<span data-ttu-id="b668f-139">Klart</span><span class="sxs-lookup"><span data-stu-id="b668f-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="b668f-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="b668f-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="b668f-141">Skapa en ny dokumenttolkningsmodell som heter "Contoso Contract"</span><span class="sxs-lookup"><span data-stu-id="b668f-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="b668f-142">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="b668f-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="b668f-143">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="b668f-143">Sample response</span></span>

<span data-ttu-id="b668f-144">**Statuskod:** 201</span><span class="sxs-lookup"><span data-stu-id="b668f-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="b668f-145">Se även</span><span class="sxs-lookup"><span data-stu-id="b668f-145">See also</span></span>

[<span data-ttu-id="b668f-146">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="b668f-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
