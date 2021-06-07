---
title: Skaffa installerad programvara
description: Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.
keywords: apis, graph api, api som stöds, skaffa, lista, fil, information, programvaruinventering, installerad programvara per enhet, hot & hantering av säkerhetsrisker api, Microsoft Defender för Endpoint tvm api
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 35cbeedc5d13f5eeb99718b4f98e2d8aabe1e965
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770163"
---
# <a name="get-installed-software"></a><span data-ttu-id="facd9-104">Skaffa installerad programvara</span><span class="sxs-lookup"><span data-stu-id="facd9-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="facd9-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="facd9-105">**Applies to:**</span></span>
- [<span data-ttu-id="facd9-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="facd9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="facd9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="facd9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="facd9-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="facd9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="facd9-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="facd9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="facd9-110">Hämtar en samling installerad programvara som är relaterad till ett visst enhets-ID.</span><span class="sxs-lookup"><span data-stu-id="facd9-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="facd9-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="facd9-111">Permissions</span></span>
<span data-ttu-id="facd9-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="facd9-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="facd9-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="facd9-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="facd9-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="facd9-114">Permission type</span></span> |   <span data-ttu-id="facd9-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="facd9-115">Permission</span></span>  |   <span data-ttu-id="facd9-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="facd9-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="facd9-117">Program</span><span class="sxs-lookup"><span data-stu-id="facd9-117">Application</span></span> |<span data-ttu-id="facd9-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="facd9-118">Software.Read.All</span></span> |    <span data-ttu-id="facd9-119">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="facd9-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="facd9-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="facd9-120">Delegated (work or school account)</span></span> | <span data-ttu-id="facd9-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="facd9-121">Software.Read</span></span> |    <span data-ttu-id="facd9-122">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="facd9-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="facd9-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="facd9-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="facd9-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="facd9-124">Request headers</span></span>

<span data-ttu-id="facd9-125">Namn</span><span class="sxs-lookup"><span data-stu-id="facd9-125">Name</span></span> | <span data-ttu-id="facd9-126">Typ</span><span class="sxs-lookup"><span data-stu-id="facd9-126">Type</span></span> | <span data-ttu-id="facd9-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="facd9-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="facd9-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="facd9-128">Authorization</span></span> | <span data-ttu-id="facd9-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="facd9-129">String</span></span> | <span data-ttu-id="facd9-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="facd9-130">Bearer {token}.</span></span> <span data-ttu-id="facd9-131">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="facd9-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="facd9-132">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="facd9-132">Request body</span></span>
<span data-ttu-id="facd9-133">Tom</span><span class="sxs-lookup"><span data-stu-id="facd9-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="facd9-134">Svar</span><span class="sxs-lookup"><span data-stu-id="facd9-134">Response</span></span>
<span data-ttu-id="facd9-135">Om det lyckas returnerar den här metoden 200 OK med information om installerad programvara i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="facd9-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="facd9-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="facd9-136">Example</span></span>

<span data-ttu-id="facd9-137">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="facd9-137">**Request**</span></span>

<span data-ttu-id="facd9-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="facd9-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="facd9-139">**Svar**</span><span class="sxs-lookup"><span data-stu-id="facd9-139">**Response**</span></span>

<span data-ttu-id="facd9-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="facd9-140">Here is an example of the response.</span></span>


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

## <a name="see-also"></a><span data-ttu-id="facd9-141">Se även</span><span class="sxs-lookup"><span data-stu-id="facd9-141">See also</span></span>

- [<span data-ttu-id="facd9-142">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="facd9-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="facd9-143">Hot & inventering av sårbarhetsprogramvara</span><span class="sxs-lookup"><span data-stu-id="facd9-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
