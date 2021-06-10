---
title: Hämta API för KB-samling
description: Hämta en samling kunskapsbaser (kB) och KB-information med Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167181"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="2b135-104">Hämta API för KB-samling</span><span class="sxs-lookup"><span data-stu-id="2b135-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b135-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2b135-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b135-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2b135-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b135-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b135-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2b135-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2b135-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2b135-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2b135-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="2b135-110">Hämtar en samling kb- och KB-information.</span><span class="sxs-lookup"><span data-stu-id="2b135-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="2b135-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2b135-111">Permissions</span></span>
<span data-ttu-id="2b135-112">Användaren behöver läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="2b135-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="2b135-113">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2b135-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="2b135-114">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2b135-114">Request headers</span></span>

<span data-ttu-id="2b135-115">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="2b135-115">Header</span></span> | <span data-ttu-id="2b135-116">Värde</span><span class="sxs-lookup"><span data-stu-id="2b135-116">Value</span></span> 
:---|:---
<span data-ttu-id="2b135-117">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2b135-117">Authorization</span></span> | <span data-ttu-id="2b135-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2b135-118">Bearer {token}.</span></span> <span data-ttu-id="2b135-119">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2b135-119">**Required**.</span></span>
<span data-ttu-id="2b135-120">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="2b135-120">Content type</span></span> | <span data-ttu-id="2b135-121">application/json</span><span class="sxs-lookup"><span data-stu-id="2b135-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="2b135-122">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2b135-122">Request body</span></span>
<span data-ttu-id="2b135-123">Tom</span><span class="sxs-lookup"><span data-stu-id="2b135-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2b135-124">Svar</span><span class="sxs-lookup"><span data-stu-id="2b135-124">Response</span></span>
<span data-ttu-id="2b135-125">Om det lyckas – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="2b135-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="2b135-126">Exempel</span><span class="sxs-lookup"><span data-stu-id="2b135-126">Example</span></span>

<span data-ttu-id="2b135-127">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2b135-127">**Request**</span></span>

<span data-ttu-id="2b135-128">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2b135-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="2b135-129">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2b135-129">**Response**</span></span>

<span data-ttu-id="2b135-130">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2b135-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
