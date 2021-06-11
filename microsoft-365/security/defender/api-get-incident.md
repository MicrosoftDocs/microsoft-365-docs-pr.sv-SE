---
title: Hämta incident-API
description: Läs om hur du använder API:t Hämta incidenter för att få en enda incident i Microsoft 365 Defender.
keywords: apis, graph api, API som stöds, skaffa, fil, hash
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888458"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="78dc1-104">Hämta API för incidentinformation</span><span class="sxs-lookup"><span data-stu-id="78dc1-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="78dc1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="78dc1-105">**Applies to:**</span></span>
- [<span data-ttu-id="78dc1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78dc1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="78dc1-107">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="78dc1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="78dc1-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="78dc1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="78dc1-109">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="78dc1-109">API description</span></span>
<span data-ttu-id="78dc1-110">Hämtar ett specifikt incident med dess ID</span><span class="sxs-lookup"><span data-stu-id="78dc1-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="78dc1-111">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="78dc1-111">Limitations</span></span>
1. <span data-ttu-id="78dc1-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="78dc1-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="78dc1-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="78dc1-113">Permissions</span></span>
<span data-ttu-id="78dc1-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="78dc1-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="78dc1-115">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="78dc1-115">Permission type</span></span> |   <span data-ttu-id="78dc1-116">Behörighet</span><span class="sxs-lookup"><span data-stu-id="78dc1-116">Permission</span></span>  |   <span data-ttu-id="78dc1-117">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="78dc1-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="78dc1-118">Program</span><span class="sxs-lookup"><span data-stu-id="78dc1-118">Application</span></span> |   <span data-ttu-id="78dc1-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="78dc1-119">Incident.Read.All</span></span> | <span data-ttu-id="78dc1-120">"Läs alla incidenter"</span><span class="sxs-lookup"><span data-stu-id="78dc1-120">'Read all Incidents'</span></span>
<span data-ttu-id="78dc1-121">Program</span><span class="sxs-lookup"><span data-stu-id="78dc1-121">Application</span></span> |   <span data-ttu-id="78dc1-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="78dc1-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="78dc1-123">"Läsa och skriva alla incidenter"</span><span class="sxs-lookup"><span data-stu-id="78dc1-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="78dc1-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="78dc1-124">Delegated (work or school account)</span></span> | <span data-ttu-id="78dc1-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="78dc1-125">Incident.Read</span></span> | <span data-ttu-id="78dc1-126">"Läs incidenter"</span><span class="sxs-lookup"><span data-stu-id="78dc1-126">'Read Incidents'</span></span>
<span data-ttu-id="78dc1-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="78dc1-127">Delegated (work or school account)</span></span> | <span data-ttu-id="78dc1-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="78dc1-128">Incident.ReadWrite</span></span> | <span data-ttu-id="78dc1-129">"Läsa och skriva incidenter"</span><span class="sxs-lookup"><span data-stu-id="78dc1-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="78dc1-130">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="78dc1-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="78dc1-131">Användaren måste ha minst följande rollbehörighet: 'Visa data'</span><span class="sxs-lookup"><span data-stu-id="78dc1-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="78dc1-132">Svaret inkluderar endast incidenter som användaren exponeras för</span><span class="sxs-lookup"><span data-stu-id="78dc1-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="78dc1-133">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="78dc1-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="78dc1-134">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="78dc1-134">Request headers</span></span>

<span data-ttu-id="78dc1-135">Namn</span><span class="sxs-lookup"><span data-stu-id="78dc1-135">Name</span></span> | <span data-ttu-id="78dc1-136">Typ</span><span class="sxs-lookup"><span data-stu-id="78dc1-136">Type</span></span> | <span data-ttu-id="78dc1-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="78dc1-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="78dc1-138">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="78dc1-138">Authorization</span></span> | <span data-ttu-id="78dc1-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="78dc1-139">String</span></span> | <span data-ttu-id="78dc1-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="78dc1-140">Bearer {token}.</span></span> <span data-ttu-id="78dc1-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="78dc1-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="78dc1-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="78dc1-142">Request body</span></span>
<span data-ttu-id="78dc1-143">Tom</span><span class="sxs-lookup"><span data-stu-id="78dc1-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="78dc1-144">Svar</span><span class="sxs-lookup"><span data-stu-id="78dc1-144">Response</span></span>

<span data-ttu-id="78dc1-145">Om det lyckas returnerar den här metoden 200 OK och incidenten i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="78dc1-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="78dc1-146">Om incident med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="78dc1-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="78dc1-147">Exempel</span><span class="sxs-lookup"><span data-stu-id="78dc1-147">Example</span></span>

<span data-ttu-id="78dc1-148">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="78dc1-148">**Request**</span></span>

<span data-ttu-id="78dc1-149">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="78dc1-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
