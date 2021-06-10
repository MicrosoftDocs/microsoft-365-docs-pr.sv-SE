---
title: Hämta API för RBAC-maskingrupper
description: Lär dig hur du använder API:t för att hämta KB-samlings-API:t för att hämta en samling RBAC-enhetsgrupper i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, get, RBAC, grupp
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
ms.date: 10/07/2018
ms.openlocfilehash: 18566025d79f02281c1d2c1509dd98f1e57879c2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932781"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="075c7-104">Hämta API för KB-samling</span><span class="sxs-lookup"><span data-stu-id="075c7-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="075c7-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="075c7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="075c7-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="075c7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="075c7-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="075c7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="075c7-108">Hämtar en samling av RBAC-enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="075c7-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="075c7-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="075c7-109">Permissions</span></span>
<span data-ttu-id="075c7-110">Användaren behöver läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="075c7-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="075c7-111">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="075c7-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="075c7-112">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="075c7-112">Request headers</span></span>

<span data-ttu-id="075c7-113">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="075c7-113">Header</span></span> | <span data-ttu-id="075c7-114">Värde</span><span class="sxs-lookup"><span data-stu-id="075c7-114">Value</span></span> 
:---|:---
<span data-ttu-id="075c7-115">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="075c7-115">Authorization</span></span> | <span data-ttu-id="075c7-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="075c7-116">Bearer {token}.</span></span> <span data-ttu-id="075c7-117">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="075c7-117">**Required**.</span></span>
<span data-ttu-id="075c7-118">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="075c7-118">Content type</span></span> | <span data-ttu-id="075c7-119">application/json</span><span class="sxs-lookup"><span data-stu-id="075c7-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="075c7-120">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="075c7-120">Request body</span></span>
<span data-ttu-id="075c7-121">Tom</span><span class="sxs-lookup"><span data-stu-id="075c7-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="075c7-122">Svar</span><span class="sxs-lookup"><span data-stu-id="075c7-122">Response</span></span>
<span data-ttu-id="075c7-123">Om det lyckas – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="075c7-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="075c7-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="075c7-124">Example</span></span>

<span data-ttu-id="075c7-125">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="075c7-125">**Request**</span></span>

<span data-ttu-id="075c7-126">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="075c7-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="075c7-127">**Svar**</span><span class="sxs-lookup"><span data-stu-id="075c7-127">**Response**</span></span>

<span data-ttu-id="075c7-128">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="075c7-128">Here is an example of the response.</span></span>
<span data-ttu-id="075c7-129">Fält-ID innehåller enhetens **grupp-ID** och är lika med **fält rbacGroupId** i enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="075c7-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="075c7-130">Fält **som inte har** grupperats gäller endast för en grupp för alla enheter som inte har tilldelats någon grupp.</span><span class="sxs-lookup"><span data-stu-id="075c7-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="075c7-131">Den här gruppen har som vanligt namnet "Ej tilldelad grupp".</span><span class="sxs-lookup"><span data-stu-id="075c7-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
