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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 1541e1d6e177416d77d768cef04d2524e6907ab5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289925"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="4cfe2-104">Ta bort indikator-API</span><span class="sxs-lookup"><span data-stu-id="4cfe2-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cfe2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="4cfe2-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cfe2-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4cfe2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cfe2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cfe2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4cfe2-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="4cfe2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4cfe2-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4cfe2-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="4cfe2-110">API description</span></span>

<span data-ttu-id="4cfe2-111">Tar bort en [indikatortitet](ti-indicator.md) med hjälp av ID.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="4cfe2-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="4cfe2-112">Limitations</span></span>

<span data-ttu-id="4cfe2-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="4cfe2-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="4cfe2-114">Permissions</span></span>

<span data-ttu-id="4cfe2-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4cfe2-116">Mer information, inklusive hur du väljer behörigheter, finns i [Komma igång](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4cfe2-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="4cfe2-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="4cfe2-117">Permission type</span></span> | <span data-ttu-id="4cfe2-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="4cfe2-118">Permission</span></span> | <span data-ttu-id="4cfe2-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="4cfe2-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4cfe2-120">Program</span><span class="sxs-lookup"><span data-stu-id="4cfe2-120">Application</span></span> | <span data-ttu-id="4cfe2-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4cfe2-121">Ti.ReadWrite</span></span> | <span data-ttu-id="4cfe2-122">"Läs och skriv TI-indikatorer"</span><span class="sxs-lookup"><span data-stu-id="4cfe2-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="4cfe2-123">Program</span><span class="sxs-lookup"><span data-stu-id="4cfe2-123">Application</span></span> | <span data-ttu-id="4cfe2-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4cfe2-124">Ti.ReadWrite.All</span></span> | <span data-ttu-id="4cfe2-125">Indikatorer för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="4cfe2-125">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="4cfe2-126">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="4cfe2-126">HTTP request</span></span>

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="4cfe2-127">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="4cfe2-127">Request headers</span></span>

<span data-ttu-id="4cfe2-128">Namn</span><span class="sxs-lookup"><span data-stu-id="4cfe2-128">Name</span></span> | <span data-ttu-id="4cfe2-129">Typ</span><span class="sxs-lookup"><span data-stu-id="4cfe2-129">Type</span></span> | <span data-ttu-id="4cfe2-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="4cfe2-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="4cfe2-131">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="4cfe2-131">Authorization</span></span> | <span data-ttu-id="4cfe2-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="4cfe2-132">String</span></span> | <span data-ttu-id="4cfe2-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-133">Bearer {token}.</span></span> <span data-ttu-id="4cfe2-134">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="4cfe2-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4cfe2-135">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="4cfe2-135">Request body</span></span>

<span data-ttu-id="4cfe2-136">Tom</span><span class="sxs-lookup"><span data-stu-id="4cfe2-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4cfe2-137">Svar</span><span class="sxs-lookup"><span data-stu-id="4cfe2-137">Response</span></span>

<span data-ttu-id="4cfe2-138">Om indikator finns och tagits bort korrekt – 204 OK utan innehåll.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>

<span data-ttu-id="4cfe2-139">Om indikator med det angivna ID:t hittades inte – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4cfe2-140">Exempel</span><span class="sxs-lookup"><span data-stu-id="4cfe2-140">Example</span></span>

### <a name="request"></a><span data-ttu-id="4cfe2-141">Begäran</span><span class="sxs-lookup"><span data-stu-id="4cfe2-141">Request</span></span>

<span data-ttu-id="4cfe2-142">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="4cfe2-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
