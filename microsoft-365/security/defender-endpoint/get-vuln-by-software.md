---
title: Lista sårbarhet efter programvara
description: Hämta en lista över säkerhetsproblem i den installerade programvaran.
keywords: apis, graph api, API som stöds, skaffa, sårbarhetslista, Microsoft Defender för Endpoint tvm api
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769923"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="a30e4-104">Lista sårbarhet efter programvara</span><span class="sxs-lookup"><span data-stu-id="a30e4-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a30e4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a30e4-105">**Applies to:**</span></span>
- [<span data-ttu-id="a30e4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a30e4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a30e4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a30e4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a30e4-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a30e4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a30e4-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a30e4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="a30e4-110">Hämta en lista över säkerhetsproblem i den installerade programvaran.</span><span class="sxs-lookup"><span data-stu-id="a30e4-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="a30e4-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a30e4-111">Permissions</span></span>
<span data-ttu-id="a30e4-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="a30e4-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a30e4-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="a30e4-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="a30e4-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="a30e4-114">Permission type</span></span> |   <span data-ttu-id="a30e4-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a30e4-115">Permission</span></span>  |   <span data-ttu-id="a30e4-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="a30e4-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a30e4-117">Program</span><span class="sxs-lookup"><span data-stu-id="a30e4-117">Application</span></span> | <span data-ttu-id="a30e4-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="a30e4-118">Software.Read.All</span></span> | <span data-ttu-id="a30e4-119">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="a30e4-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="a30e4-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a30e4-120">Delegated (work or school account)</span></span> | <span data-ttu-id="a30e4-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="a30e4-121">Software.Read</span></span> | <span data-ttu-id="a30e4-122">"Läs information om hot och sårbarhetshanteringsprogramvara"</span><span class="sxs-lookup"><span data-stu-id="a30e4-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="a30e4-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="a30e4-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="a30e4-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="a30e4-124">Request headers</span></span>

| <span data-ttu-id="a30e4-125">Namn</span><span class="sxs-lookup"><span data-stu-id="a30e4-125">Name</span></span>        | <span data-ttu-id="a30e4-126">Typ</span><span class="sxs-lookup"><span data-stu-id="a30e4-126">Type</span></span> | <span data-ttu-id="a30e4-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a30e4-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="a30e4-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="a30e4-128">Authorization</span></span> | <span data-ttu-id="a30e4-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="a30e4-129">String</span></span> | <span data-ttu-id="a30e4-130">Bearer {token}. **Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a30e4-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="a30e4-131">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="a30e4-131">Request body</span></span>
<span data-ttu-id="a30e4-132">Tom</span><span class="sxs-lookup"><span data-stu-id="a30e4-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a30e4-133">Svar</span><span class="sxs-lookup"><span data-stu-id="a30e4-133">Response</span></span>
<span data-ttu-id="a30e4-134">Om det lyckas returnerar den här metoden 200 OK med en lista över säkerhetsproblem som exponeras av den angivna programvaran.</span><span class="sxs-lookup"><span data-stu-id="a30e4-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="a30e4-135">Exempel</span><span class="sxs-lookup"><span data-stu-id="a30e4-135">Example</span></span>

<span data-ttu-id="a30e4-136">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="a30e4-136">**Request**</span></span>

<span data-ttu-id="a30e4-137">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="a30e4-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="a30e4-138">**Svar**</span><span class="sxs-lookup"><span data-stu-id="a30e4-138">**Response**</span></span>

<span data-ttu-id="a30e4-139">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="a30e4-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
                "publicExploit": false,
                "exploitVerified": false,
                "exploitInKit": false,
                "exploitTypes": [],
                "exploitUris": []
            }
            ...
        ]
}
```

