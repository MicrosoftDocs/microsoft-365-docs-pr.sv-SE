---
title: Hämta CVE-KB map API
description: Lär dig hur du använder API:t Hämta CVE-KB-karta för att hämta en karta över CVE:er till KB- och CVE-information i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166893"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="00c86-104">Hämta CVE-KB map API</span><span class="sxs-lookup"><span data-stu-id="00c86-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="00c86-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="00c86-105">**Applies to:**</span></span>
- [<span data-ttu-id="00c86-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="00c86-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="00c86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00c86-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="00c86-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="00c86-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="00c86-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="00c86-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="00c86-110">Hämtar en karta över CVE-informationen till KB- och CVE-informationen.</span><span class="sxs-lookup"><span data-stu-id="00c86-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="00c86-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="00c86-111">Permissions</span></span>
<span data-ttu-id="00c86-112">Användaren behöver läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="00c86-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="00c86-113">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="00c86-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="00c86-114">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="00c86-114">Request headers</span></span>

<span data-ttu-id="00c86-115">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="00c86-115">Header</span></span> | <span data-ttu-id="00c86-116">Värde</span><span class="sxs-lookup"><span data-stu-id="00c86-116">Value</span></span> 
:---|:---
<span data-ttu-id="00c86-117">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="00c86-117">Authorization</span></span> | <span data-ttu-id="00c86-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="00c86-118">Bearer {token}.</span></span> <span data-ttu-id="00c86-119">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="00c86-119">**Required**.</span></span>
<span data-ttu-id="00c86-120">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="00c86-120">Content type</span></span> | <span data-ttu-id="00c86-121">application/json</span><span class="sxs-lookup"><span data-stu-id="00c86-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="00c86-122">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="00c86-122">Request body</span></span>
<span data-ttu-id="00c86-123">Tom</span><span class="sxs-lookup"><span data-stu-id="00c86-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="00c86-124">Svar</span><span class="sxs-lookup"><span data-stu-id="00c86-124">Response</span></span>
<span data-ttu-id="00c86-125">Om det lyckas och karta finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="00c86-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="00c86-126">Exempel</span><span class="sxs-lookup"><span data-stu-id="00c86-126">Example</span></span>

<span data-ttu-id="00c86-127">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="00c86-127">**Request**</span></span>

<span data-ttu-id="00c86-128">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="00c86-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="00c86-129">**Svar**</span><span class="sxs-lookup"><span data-stu-id="00c86-129">**Response**</span></span>

<span data-ttu-id="00c86-130">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="00c86-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
