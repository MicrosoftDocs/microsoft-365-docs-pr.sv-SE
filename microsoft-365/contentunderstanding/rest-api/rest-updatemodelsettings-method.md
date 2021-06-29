---
title: UpdateModelSettings
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
description: Använd REST API för att uppdatera inställningar för tillgängliga modeller för dokumenttolkningsmodell i SharePoint Syntex.
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177171"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="8c33e-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="8c33e-103">UpdateModelSettings</span></span>

<span data-ttu-id="8c33e-104">Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en dokumenttolkningsmodell i SharePoint Syntex (se [exempel](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8c33e-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8c33e-105">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8c33e-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8c33e-106">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="8c33e-106">URI parameters</span></span>

|<span data-ttu-id="8c33e-107">Namn</span><span class="sxs-lookup"><span data-stu-id="8c33e-107">Name</span></span> |<span data-ttu-id="8c33e-108">In</span><span class="sxs-lookup"><span data-stu-id="8c33e-108">In</span></span> |<span data-ttu-id="8c33e-109">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="8c33e-109">Required</span></span>|<span data-ttu-id="8c33e-110">Typ</span><span class="sxs-lookup"><span data-stu-id="8c33e-110">Type</span></span>|<span data-ttu-id="8c33e-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c33e-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="8c33e-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="8c33e-112">modelFileName</span></span>|<span data-ttu-id="8c33e-113">fråga</span><span class="sxs-lookup"><span data-stu-id="8c33e-113">query</span></span>|<span data-ttu-id="8c33e-114">Sant</span><span class="sxs-lookup"><span data-stu-id="8c33e-114">True</span></span>|<span data-ttu-id="8c33e-115">sträng</span><span class="sxs-lookup"><span data-stu-id="8c33e-115">string</span></span>|<span data-ttu-id="8c33e-116">Namnet på Syntex-modellfilen.</span><span class="sxs-lookup"><span data-stu-id="8c33e-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="8c33e-117">Frågerubrik</span><span class="sxs-lookup"><span data-stu-id="8c33e-117">Request headers</span></span>

| <span data-ttu-id="8c33e-118">Rubrik</span><span class="sxs-lookup"><span data-stu-id="8c33e-118">Header</span></span> | <span data-ttu-id="8c33e-119">Värde</span><span class="sxs-lookup"><span data-stu-id="8c33e-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8c33e-120">Acceptera</span><span class="sxs-lookup"><span data-stu-id="8c33e-120">Accept</span></span>|<span data-ttu-id="8c33e-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8c33e-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8c33e-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8c33e-122">Content-Type</span></span>|<span data-ttu-id="8c33e-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8c33e-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8c33e-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8c33e-124">x-requestdigest</span></span>|<span data-ttu-id="8c33e-125">Lämplig sammanfattning för den aktuella webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8c33e-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="8c33e-126">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="8c33e-126">Request body</span></span>

|<span data-ttu-id="8c33e-127">Namn</span><span class="sxs-lookup"><span data-stu-id="8c33e-127">Name</span></span>    |<span data-ttu-id="8c33e-128">Typ</span><span class="sxs-lookup"><span data-stu-id="8c33e-128">Type</span></span>   |<span data-ttu-id="8c33e-129">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c33e-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="8c33e-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="8c33e-130">ModelSettings</span></span>|<span data-ttu-id="8c33e-131">sträng</span><span class="sxs-lookup"><span data-stu-id="8c33e-131">string</span></span>|<span data-ttu-id="8c33e-132">JSON för modellinställningar.</span><span class="sxs-lookup"><span data-stu-id="8c33e-132">JSON of model settings.</span></span>|
|<span data-ttu-id="8c33e-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c33e-133">Description</span></span>|<span data-ttu-id="8c33e-134">sträng</span><span class="sxs-lookup"><span data-stu-id="8c33e-134">string</span></span>|<span data-ttu-id="8c33e-135">Modellbeskrivningen. </span><span class="sxs-lookup"><span data-stu-id="8c33e-135">The model description.</span></span>|
|<span data-ttu-id="8c33e-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="8c33e-136">RetentionLabel</span></span>| |<span data-ttu-id="8c33e-137">Information om den associerade etiketten (etikett-ID och namn).</span><span class="sxs-lookup"><span data-stu-id="8c33e-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="8c33e-138">Svar</span><span class="sxs-lookup"><span data-stu-id="8c33e-138">Responses</span></span>

| <span data-ttu-id="8c33e-139">Namn</span><span class="sxs-lookup"><span data-stu-id="8c33e-139">Name</span></span>   | <span data-ttu-id="8c33e-140">Typ</span><span class="sxs-lookup"><span data-stu-id="8c33e-140">Type</span></span>  | <span data-ttu-id="8c33e-141">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8c33e-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8c33e-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="8c33e-142">200 OK</span></span>| |<span data-ttu-id="8c33e-143">Klart</span><span class="sxs-lookup"><span data-stu-id="8c33e-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="8c33e-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="8c33e-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="8c33e-145">Uppdatera modellinställningar för Contoso Contract</span><span class="sxs-lookup"><span data-stu-id="8c33e-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="8c33e-146">I det här exemplet uppdateras modellbeskrivningen och kvarhållningsetiketten "Standard Hold".</span><span class="sxs-lookup"><span data-stu-id="8c33e-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="8c33e-147">ID:t för kvarhållningstaggen är `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="8c33e-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8c33e-148">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="8c33e-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="8c33e-149">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="8c33e-149">Sample response</span></span>

<span data-ttu-id="8c33e-150">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="8c33e-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="8c33e-151">Se även</span><span class="sxs-lookup"><span data-stu-id="8c33e-151">See also</span></span>

[<span data-ttu-id="8c33e-152">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="8c33e-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
