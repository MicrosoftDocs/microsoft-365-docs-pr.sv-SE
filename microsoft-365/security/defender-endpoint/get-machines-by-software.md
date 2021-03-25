---
title: Lista enheter efter programvara
description: Hämta en lista över enheter som har den här programvaran installerad.
keywords: apis, graph api, API som stöds, skaffa, lista enheter, lista över enheter, lista enheter efter programvara, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200395"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="b484e-104">Lista enheter efter programvara</span><span class="sxs-lookup"><span data-stu-id="b484e-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b484e-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b484e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b484e-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b484e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b484e-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b484e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b484e-108">Hämta en lista över enhetsreferenser som har den här programvaran installerad.</span><span class="sxs-lookup"><span data-stu-id="b484e-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="b484e-109">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b484e-109">Permissions</span></span>
<span data-ttu-id="b484e-110">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b484e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b484e-111">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="b484e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b484e-112">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b484e-112">Permission type</span></span> |   <span data-ttu-id="b484e-113">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b484e-113">Permission</span></span>  |   <span data-ttu-id="b484e-114">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b484e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b484e-115">Program</span><span class="sxs-lookup"><span data-stu-id="b484e-115">Application</span></span> | <span data-ttu-id="b484e-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b484e-116">Software.Read.All</span></span> | <span data-ttu-id="b484e-117">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="b484e-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b484e-118">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b484e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b484e-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b484e-119">Software.Read</span></span> | <span data-ttu-id="b484e-120">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="b484e-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b484e-121">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b484e-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="b484e-122">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b484e-122">Request headers</span></span>

| <span data-ttu-id="b484e-123">Namn</span><span class="sxs-lookup"><span data-stu-id="b484e-123">Name</span></span>        | <span data-ttu-id="b484e-124">Skriv</span><span class="sxs-lookup"><span data-stu-id="b484e-124">Type</span></span> | <span data-ttu-id="b484e-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b484e-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="b484e-126">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b484e-126">Authorization</span></span> | <span data-ttu-id="b484e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="b484e-127">String</span></span> | <span data-ttu-id="b484e-128">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="b484e-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b484e-129">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b484e-129">Request body</span></span>
<span data-ttu-id="b484e-130">Tom</span><span class="sxs-lookup"><span data-stu-id="b484e-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b484e-131">Svar</span><span class="sxs-lookup"><span data-stu-id="b484e-131">Response</span></span>
<span data-ttu-id="b484e-132">Om det lyckas returnerar den här metoden 200 OK och en lista över enheter med programvaran installerad i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="b484e-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="b484e-133">Exempel</span><span class="sxs-lookup"><span data-stu-id="b484e-133">Example</span></span>

<span data-ttu-id="b484e-134">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b484e-134">**Request**</span></span>

<span data-ttu-id="b484e-135">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b484e-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="b484e-136">**Svar**</span><span class="sxs-lookup"><span data-stu-id="b484e-136">**Response**</span></span>

<span data-ttu-id="b484e-137">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="b484e-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b484e-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="b484e-138">Related topics</span></span>
- [<span data-ttu-id="b484e-139">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="b484e-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b484e-140">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="b484e-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
