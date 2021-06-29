---
title: Skapa klassificeringsbegäran
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
description: Använd REST API för att skapa en begäran om att klassificera en eller flera filer med hjälp av en tränad dokumenttolkningsmodell.
ms.openlocfilehash: 3a796bcdb38a9a6930b51f7d585febb69082732e
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177087"
---
# <a name="create-classification-request"></a><span data-ttu-id="ec390-103">Skapa klassificeringsbegäran</span><span class="sxs-lookup"><span data-stu-id="ec390-103">Create classification request</span></span>

<span data-ttu-id="ec390-104">Skapar en begäran om att klassificera en eller flera filer med hjälp av den använda den tillämpade dokumenttolkningsmodellen (se [exempel](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="ec390-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="ec390-105">SharePoint Onlines (och SharePoint 2016 och senare lokalt) REST-tjänst har stöd för att kombinera flera begäranden.</span><span class="sxs-lookup"><span data-stu-id="ec390-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="ec390-106">Begäranden kombineras till ett enda anrop till tjänsten med hjälp av frågealternativet OData $batch.</span><span class="sxs-lookup"><span data-stu-id="ec390-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="ec390-107">Den här metoden kan användas köa arbetsobjekt för klassificering för hundratals dokument samtidigt.</span><span class="sxs-lookup"><span data-stu-id="ec390-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="ec390-108">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="ec390-108">HTTP request</span></span>

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="ec390-109">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="ec390-109">URI Parameters</span></span>

<span data-ttu-id="ec390-110">Ingen</span><span class="sxs-lookup"><span data-stu-id="ec390-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="ec390-111">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="ec390-111">Request headers</span></span>

| <span data-ttu-id="ec390-112">Rubrik</span><span class="sxs-lookup"><span data-stu-id="ec390-112">Header</span></span> | <span data-ttu-id="ec390-113">Värde</span><span class="sxs-lookup"><span data-stu-id="ec390-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="ec390-114">Acceptera</span><span class="sxs-lookup"><span data-stu-id="ec390-114">Accept</span></span>|<span data-ttu-id="ec390-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="ec390-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="ec390-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ec390-116">Content-Type</span></span>|<span data-ttu-id="ec390-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="ec390-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="ec390-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="ec390-118">x-requestdigest</span></span>|<span data-ttu-id="ec390-119">Den lämpliga sammanfattningen för aktuell webbplats</span><span class="sxs-lookup"><span data-stu-id="ec390-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="ec390-120">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="ec390-120">Request body</span></span>

|<span data-ttu-id="ec390-121">Namn</span><span class="sxs-lookup"><span data-stu-id="ec390-121">Name</span></span>    |<span data-ttu-id="ec390-122">Typ</span><span class="sxs-lookup"><span data-stu-id="ec390-122">Type</span></span>   |<span data-ttu-id="ec390-123">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ec390-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="ec390-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="ec390-124">_metadata</span></span>|<span data-ttu-id="ec390-125">sträng</span><span class="sxs-lookup"><span data-stu-id="ec390-125">string</span></span> |<span data-ttu-id="ec390-126">Ställ in objektmeta på SPO.</span><span class="sxs-lookup"><span data-stu-id="ec390-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="ec390-127">Använd alltid värdet: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="ec390-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="ec390-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="ec390-128">TargetSiteId</span></span>|<span data-ttu-id="ec390-129">guid</span><span class="sxs-lookup"><span data-stu-id="ec390-129">guid</span></span>|<span data-ttu-id="ec390-130">ID för webbplatsen där filen som ska klassificera finns.</span><span class="sxs-lookup"><span data-stu-id="ec390-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="ec390-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="ec390-131">TargetWebId</span></span>|<span data-ttu-id="ec390-132">guid</span><span class="sxs-lookup"><span data-stu-id="ec390-132">guid</span></span>|<span data-ttu-id="ec390-133">ID på webben där filen som ska klassificera finns.</span><span class="sxs-lookup"><span data-stu-id="ec390-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="ec390-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="ec390-134">TargetUniqueId</span></span>|<span data-ttu-id="ec390-135">guid</span><span class="sxs-lookup"><span data-stu-id="ec390-135">guid</span></span>|<span data-ttu-id="ec390-136">ID för filen som ska klassificeras.</span><span class="sxs-lookup"><span data-stu-id="ec390-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="ec390-137">Svar</span><span class="sxs-lookup"><span data-stu-id="ec390-137">Responses</span></span>

| <span data-ttu-id="ec390-138">Namn</span><span class="sxs-lookup"><span data-stu-id="ec390-138">Name</span></span>   | <span data-ttu-id="ec390-139">Typ</span><span class="sxs-lookup"><span data-stu-id="ec390-139">Type</span></span>  | <span data-ttu-id="ec390-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="ec390-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="ec390-141">201 skapad</span><span class="sxs-lookup"><span data-stu-id="ec390-141">201 Created</span></span>| |<span data-ttu-id="ec390-142">Klart</span><span class="sxs-lookup"><span data-stu-id="ec390-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="ec390-143">Exempel</span><span class="sxs-lookup"><span data-stu-id="ec390-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="ec390-144">Köa en begäran om att klassificera en fil med id "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="ec390-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="ec390-145">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="ec390-145">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="ec390-146">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="ec390-146">Sample response</span></span>

<span data-ttu-id="ec390-147">**Statuskod:** 201</span><span class="sxs-lookup"><span data-stu-id="ec390-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="ec390-148">Se även</span><span class="sxs-lookup"><span data-stu-id="ec390-148">See also</span></span>

[<span data-ttu-id="ec390-149">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="ec390-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
