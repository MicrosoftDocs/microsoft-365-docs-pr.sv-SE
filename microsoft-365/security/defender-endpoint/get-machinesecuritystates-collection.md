---
title: Get machines security states collection API
description: Hämta en samling säkerhetsstater för enheter med Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, enhet, säkerhet, status
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200371"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="a98e3-104">Get Machines security states collection API</span><span class="sxs-lookup"><span data-stu-id="a98e3-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a98e3-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a98e3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a98e3-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a98e3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a98e3-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a98e3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a98e3-108">Hämtar en samling säkerhets tillstånd för enheter.</span><span class="sxs-lookup"><span data-stu-id="a98e3-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="a98e3-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a98e3-109">Permissions</span></span>
<span data-ttu-id="a98e3-110">Användaren behöver läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="a98e3-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="a98e3-111">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="a98e3-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="a98e3-112">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="a98e3-112">Request headers</span></span>

<span data-ttu-id="a98e3-113">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="a98e3-113">Header</span></span> | <span data-ttu-id="a98e3-114">Värde</span><span class="sxs-lookup"><span data-stu-id="a98e3-114">Value</span></span> 
:---|:---
<span data-ttu-id="a98e3-115">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="a98e3-115">Authorization</span></span> | <span data-ttu-id="a98e3-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a98e3-116">Bearer {token}.</span></span> <span data-ttu-id="a98e3-117">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a98e3-117">**Required**.</span></span>
<span data-ttu-id="a98e3-118">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="a98e3-118">Content type</span></span> | <span data-ttu-id="a98e3-119">application/json</span><span class="sxs-lookup"><span data-stu-id="a98e3-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="a98e3-120">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="a98e3-120">Request body</span></span>
<span data-ttu-id="a98e3-121">Tom</span><span class="sxs-lookup"><span data-stu-id="a98e3-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a98e3-122">Svar</span><span class="sxs-lookup"><span data-stu-id="a98e3-122">Response</span></span>
<span data-ttu-id="a98e3-123">Om det lyckas – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="a98e3-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="a98e3-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="a98e3-124">Example</span></span>

<span data-ttu-id="a98e3-125">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="a98e3-125">**Request**</span></span>

<span data-ttu-id="a98e3-126">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="a98e3-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="a98e3-127">**Svar**</span><span class="sxs-lookup"><span data-stu-id="a98e3-127">**Response**</span></span>

<span data-ttu-id="a98e3-128">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="a98e3-128">Here is an example of the response.</span></span>
<span data-ttu-id="a98e3-129">*Fält-ID* innehåller enhets-ID och är lika med *fält-ID*\* i enhetsinformation.</span><span class="sxs-lookup"><span data-stu-id="a98e3-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
