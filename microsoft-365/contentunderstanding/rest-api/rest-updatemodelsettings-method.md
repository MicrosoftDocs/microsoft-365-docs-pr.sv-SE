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
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904307"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="0e236-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="0e236-103">UpdateModelSettings</span></span>

<span data-ttu-id="0e236-104">Uppdaterar tillgängliga modellers inställningar (tillhörande bevarandeetikett och modellbeskrivning) för en dokumenttolkningsmodell i SharePoint Syntex (se [exempel](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="0e236-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="0e236-105">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="0e236-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="0e236-106">URI-parametrar</span><span class="sxs-lookup"><span data-stu-id="0e236-106">URI parameters</span></span>

<span data-ttu-id="0e236-107">Ingen</span><span class="sxs-lookup"><span data-stu-id="0e236-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="0e236-108">Frågerubrik</span><span class="sxs-lookup"><span data-stu-id="0e236-108">Request headers</span></span>

| <span data-ttu-id="0e236-109">Rubrik</span><span class="sxs-lookup"><span data-stu-id="0e236-109">Header</span></span> | <span data-ttu-id="0e236-110">Värde</span><span class="sxs-lookup"><span data-stu-id="0e236-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="0e236-111">Acceptera</span><span class="sxs-lookup"><span data-stu-id="0e236-111">Accept</span></span>|<span data-ttu-id="0e236-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="0e236-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="0e236-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="0e236-113">Content-Type</span></span>|<span data-ttu-id="0e236-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="0e236-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="0e236-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="0e236-115">x-requestdigest</span></span>|<span data-ttu-id="0e236-116">Lämplig sammanfattning för den aktuella webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0e236-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="0e236-117">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="0e236-117">Request body</span></span>

|<span data-ttu-id="0e236-118">Namn</span><span class="sxs-lookup"><span data-stu-id="0e236-118">Name</span></span>    |<span data-ttu-id="0e236-119">Typ</span><span class="sxs-lookup"><span data-stu-id="0e236-119">Type</span></span>   |<span data-ttu-id="0e236-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e236-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="0e236-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="0e236-121">ModelSettings</span></span>|<span data-ttu-id="0e236-122">sträng</span><span class="sxs-lookup"><span data-stu-id="0e236-122">string</span></span>|<span data-ttu-id="0e236-123">JSON för modellinställningar.</span><span class="sxs-lookup"><span data-stu-id="0e236-123">JSON of model settings.</span></span>|
|<span data-ttu-id="0e236-124">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e236-124">Description</span></span>|<span data-ttu-id="0e236-125">sträng</span><span class="sxs-lookup"><span data-stu-id="0e236-125">string</span></span>|<span data-ttu-id="0e236-126">Modellbeskrivningen. </span><span class="sxs-lookup"><span data-stu-id="0e236-126">The model description.</span></span>|
|<span data-ttu-id="0e236-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="0e236-127">RetentionLabel</span></span>| |<span data-ttu-id="0e236-128">Information om den associerade etiketten (etikett-ID och namn).</span><span class="sxs-lookup"><span data-stu-id="0e236-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="0e236-129">Svar</span><span class="sxs-lookup"><span data-stu-id="0e236-129">Responses</span></span>

| <span data-ttu-id="0e236-130">Namn</span><span class="sxs-lookup"><span data-stu-id="0e236-130">Name</span></span>   | <span data-ttu-id="0e236-131">Typ</span><span class="sxs-lookup"><span data-stu-id="0e236-131">Type</span></span>  | <span data-ttu-id="0e236-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0e236-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="0e236-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="0e236-133">200 OK</span></span>| |<span data-ttu-id="0e236-134">Klart</span><span class="sxs-lookup"><span data-stu-id="0e236-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="0e236-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="0e236-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="0e236-136">Uppdatera modellinställningar för Contoso Contract</span><span class="sxs-lookup"><span data-stu-id="0e236-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="0e236-137">I det här exemplet uppdateras modellbeskrivningen och kvarhållningsetiketten "Standard Hold".</span><span class="sxs-lookup"><span data-stu-id="0e236-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="0e236-138">ID:t för kvarhållningstaggen är `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="0e236-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="0e236-139">Exempelbegäran</span><span class="sxs-lookup"><span data-stu-id="0e236-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="0e236-140">Exempelsvar</span><span class="sxs-lookup"><span data-stu-id="0e236-140">Sample response</span></span>

<span data-ttu-id="0e236-141">**Statuskod:** 200</span><span class="sxs-lookup"><span data-stu-id="0e236-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="0e236-142">Se även</span><span class="sxs-lookup"><span data-stu-id="0e236-142">See also</span></span>

[<span data-ttu-id="0e236-143">REST API för dokumenttolkningsmodell i Syntex</span><span class="sxs-lookup"><span data-stu-id="0e236-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
