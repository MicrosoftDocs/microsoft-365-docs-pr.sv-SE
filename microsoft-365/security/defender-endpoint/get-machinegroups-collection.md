---
title: Hämta API för RBAC-maskingrupper
description: Lär dig hur du använder API:t för att hämta KB-samlings-API:t för att hämta en samling RBAC-enhetsgrupper i Microsoft Defender Advanced Threat Protection.
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
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167025"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="5cd39-104">Hämta API för KB-samling</span><span class="sxs-lookup"><span data-stu-id="5cd39-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5cd39-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5cd39-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="5cd39-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5cd39-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5cd39-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5cd39-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="5cd39-108">Hämtar en samling av RBAC-enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5cd39-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="5cd39-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5cd39-109">Permissions</span></span>
<span data-ttu-id="5cd39-110">Användaren behöver läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="5cd39-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="5cd39-111">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5cd39-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="5cd39-112">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="5cd39-112">Request headers</span></span>

<span data-ttu-id="5cd39-113">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="5cd39-113">Header</span></span> | <span data-ttu-id="5cd39-114">Value</span><span class="sxs-lookup"><span data-stu-id="5cd39-114">Value</span></span> 
:---|:---
<span data-ttu-id="5cd39-115">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5cd39-115">Authorization</span></span> | <span data-ttu-id="5cd39-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5cd39-116">Bearer {token}.</span></span> <span data-ttu-id="5cd39-117">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5cd39-117">**Required**.</span></span>
<span data-ttu-id="5cd39-118">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="5cd39-118">Content type</span></span> | <span data-ttu-id="5cd39-119">application/json</span><span class="sxs-lookup"><span data-stu-id="5cd39-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="5cd39-120">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="5cd39-120">Request body</span></span>
<span data-ttu-id="5cd39-121">Tom</span><span class="sxs-lookup"><span data-stu-id="5cd39-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5cd39-122">Svar</span><span class="sxs-lookup"><span data-stu-id="5cd39-122">Response</span></span>
<span data-ttu-id="5cd39-123">Om det lyckas – 200 OK.</span><span class="sxs-lookup"><span data-stu-id="5cd39-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="5cd39-124">Exempel</span><span class="sxs-lookup"><span data-stu-id="5cd39-124">Example</span></span>

<span data-ttu-id="5cd39-125">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="5cd39-125">**Request**</span></span>

<span data-ttu-id="5cd39-126">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="5cd39-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="5cd39-127">**Svar**</span><span class="sxs-lookup"><span data-stu-id="5cd39-127">**Response**</span></span>

<span data-ttu-id="5cd39-128">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="5cd39-128">Here is an example of the response.</span></span>
<span data-ttu-id="5cd39-129">Fält-ID innehåller enhetens **grupp-ID** och är lika med **fält rbacGroupId** i enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="5cd39-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="5cd39-130">Fält **som inte har** grupperats gäller endast för en grupp för alla enheter som inte har tilldelats någon grupp.</span><span class="sxs-lookup"><span data-stu-id="5cd39-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="5cd39-131">Den här gruppen har som vanligt namnet "Ej tilldelad grupp".</span><span class="sxs-lookup"><span data-stu-id="5cd39-131">This group as usual has name "UnassignedGroup".</span></span>

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
