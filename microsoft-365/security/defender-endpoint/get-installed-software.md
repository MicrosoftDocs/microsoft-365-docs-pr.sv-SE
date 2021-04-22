---
title: Skaffa installerad programvara
description: Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaruinventering, installerad programvara per enhet, api för & sårbarhetshantering, Microsoft Defender för Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: ebd689fd53dd804f857c6bec7a412c27988835d0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935119"
---
# <a name="get-installed-software"></a><span data-ttu-id="8f8d1-104">Skaffa installerad programvara</span><span class="sxs-lookup"><span data-stu-id="8f8d1-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f8d1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8f8d1-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f8d1-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8f8d1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f8d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f8d1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f8d1-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8f8d1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8f8d1-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8f8d1-110">Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="8f8d1-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="8f8d1-111">Permissions</span></span>
<span data-ttu-id="8f8d1-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8f8d1-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8f8d1-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8f8d1-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="8f8d1-114">Permission type</span></span> |   <span data-ttu-id="8f8d1-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="8f8d1-115">Permission</span></span>  |   <span data-ttu-id="8f8d1-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="8f8d1-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8f8d1-117">Program</span><span class="sxs-lookup"><span data-stu-id="8f8d1-117">Application</span></span> |<span data-ttu-id="8f8d1-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="8f8d1-118">Software.Read.All</span></span> |    <span data-ttu-id="8f8d1-119">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="8f8d1-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="8f8d1-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="8f8d1-120">Delegated (work or school account)</span></span> | <span data-ttu-id="8f8d1-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="8f8d1-121">Software.Read</span></span> |    <span data-ttu-id="8f8d1-122">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="8f8d1-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8f8d1-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8f8d1-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="8f8d1-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="8f8d1-124">Request headers</span></span>

<span data-ttu-id="8f8d1-125">Namn</span><span class="sxs-lookup"><span data-stu-id="8f8d1-125">Name</span></span> | <span data-ttu-id="8f8d1-126">Skriv</span><span class="sxs-lookup"><span data-stu-id="8f8d1-126">Type</span></span> | <span data-ttu-id="8f8d1-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8f8d1-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="8f8d1-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="8f8d1-128">Authorization</span></span> | <span data-ttu-id="8f8d1-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="8f8d1-129">String</span></span> | <span data-ttu-id="8f8d1-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-130">Bearer {token}.</span></span> <span data-ttu-id="8f8d1-131">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="8f8d1-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8f8d1-132">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="8f8d1-132">Request body</span></span>
<span data-ttu-id="8f8d1-133">Tom</span><span class="sxs-lookup"><span data-stu-id="8f8d1-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8f8d1-134">Svar</span><span class="sxs-lookup"><span data-stu-id="8f8d1-134">Response</span></span>
<span data-ttu-id="8f8d1-135">Om det lyckas returnerar den här metoden 200 OK med information om installerad programvara i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="8f8d1-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="8f8d1-136">Example</span></span>

<span data-ttu-id="8f8d1-137">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="8f8d1-137">**Request**</span></span>

<span data-ttu-id="8f8d1-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="8f8d1-139">**Svar**</span><span class="sxs-lookup"><span data-stu-id="8f8d1-139">**Response**</span></span>

<span data-ttu-id="8f8d1-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="8f8d1-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="8f8d1-141">Se även</span><span class="sxs-lookup"><span data-stu-id="8f8d1-141">See also</span></span>

- [<span data-ttu-id="8f8d1-142">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="8f8d1-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8f8d1-143">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="8f8d1-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
