---
title: Ta bort indikator-API.
description: Lär dig hur du använder indikator-API:t för att ta bort en indikator entitet med ID i Microsoft Defender för slutpunkt.
keywords: apis, public api, apis som stöds, delete, ti indikator, entitet, id
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
ms.technology: mde
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167109"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="b354a-104">Ta bort indikator-API</span><span class="sxs-lookup"><span data-stu-id="b354a-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b354a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b354a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b354a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b354a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b354a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b354a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b354a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b354a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b354a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b354a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b354a-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="b354a-110">API description</span></span>
<span data-ttu-id="b354a-111">Tar bort en [indikatortitet](ti-indicator.md) med hjälp av ID.</span><span class="sxs-lookup"><span data-stu-id="b354a-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="b354a-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="b354a-112">Limitations</span></span>
1. <span data-ttu-id="b354a-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="b354a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b354a-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b354a-114">Permissions</span></span>
<span data-ttu-id="b354a-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b354a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b354a-116">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b354a-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="b354a-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b354a-117">Permission type</span></span> |   <span data-ttu-id="b354a-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b354a-118">Permission</span></span>  |   <span data-ttu-id="b354a-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b354a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b354a-120">Program</span><span class="sxs-lookup"><span data-stu-id="b354a-120">Application</span></span> |   <span data-ttu-id="b354a-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b354a-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="b354a-122">"Läs och skriv TI-indikatorer"</span><span class="sxs-lookup"><span data-stu-id="b354a-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="b354a-123">Program</span><span class="sxs-lookup"><span data-stu-id="b354a-123">Application</span></span> |   <span data-ttu-id="b354a-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b354a-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="b354a-125">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="b354a-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="b354a-126">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b354a-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="b354a-127">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b354a-127">Request headers</span></span>

<span data-ttu-id="b354a-128">Namn</span><span class="sxs-lookup"><span data-stu-id="b354a-128">Name</span></span> | <span data-ttu-id="b354a-129">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="b354a-129">Type</span></span> | <span data-ttu-id="b354a-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b354a-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="b354a-131">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b354a-131">Authorization</span></span> | <span data-ttu-id="b354a-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="b354a-132">String</span></span> | <span data-ttu-id="b354a-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="b354a-133">Bearer {token}.</span></span> <span data-ttu-id="b354a-134">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="b354a-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="b354a-135">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b354a-135">Request body</span></span>
<span data-ttu-id="b354a-136">Tom</span><span class="sxs-lookup"><span data-stu-id="b354a-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b354a-137">Svar</span><span class="sxs-lookup"><span data-stu-id="b354a-137">Response</span></span>
<span data-ttu-id="b354a-138">Om indikator finns och tagits bort korrekt – 204 OK utan innehåll.</span><span class="sxs-lookup"><span data-stu-id="b354a-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="b354a-139">Om indikator med det angivna ID:t hittades inte – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="b354a-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="b354a-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="b354a-140">Example</span></span>

<span data-ttu-id="b354a-141">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b354a-141">**Request**</span></span>

<span data-ttu-id="b354a-142">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b354a-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
