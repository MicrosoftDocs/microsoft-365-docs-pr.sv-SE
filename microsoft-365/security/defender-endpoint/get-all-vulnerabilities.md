---
title: Få alla säkerhetsproblem
description: Hämtar en lista över alla säkerhetsproblem som påverkar organisationen
keywords: apis, graph api, API som stöds, hämta, sårbarhetsinformation, Microsoft Defender för Endpoint tvm api
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
ms.openlocfilehash: bfce003f586c5bfa32d65c834bb244ac13f6cf31
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935095"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="8cee8-104">Lista sårbarheter</span><span class="sxs-lookup"><span data-stu-id="8cee8-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8cee8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8cee8-105">**Applies to:**</span></span>
- [<span data-ttu-id="8cee8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8cee8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8cee8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8cee8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8cee8-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="8cee8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8cee8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="8cee8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8cee8-110">Hämtar en lista över alla säkerhetsproblem som påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="8cee8-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="8cee8-111">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="8cee8-111">Permissions</span></span>
<span data-ttu-id="8cee8-112">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="8cee8-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8cee8-113">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="8cee8-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="8cee8-114">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="8cee8-114">Permission type</span></span> |   <span data-ttu-id="8cee8-115">Behörighet</span><span class="sxs-lookup"><span data-stu-id="8cee8-115">Permission</span></span>  |   <span data-ttu-id="8cee8-116">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="8cee8-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8cee8-117">Program</span><span class="sxs-lookup"><span data-stu-id="8cee8-117">Application</span></span> |   <span data-ttu-id="8cee8-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8cee8-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="8cee8-119">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="8cee8-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8cee8-120">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="8cee8-120">Delegated (work or school account)</span></span> | <span data-ttu-id="8cee8-121">Sårbarhet.Läsa</span><span class="sxs-lookup"><span data-stu-id="8cee8-121">Vulnerability.Read</span></span> |   <span data-ttu-id="8cee8-122">"Läs sårbarhetsinformation för hot och sårbarhetshantering"</span><span class="sxs-lookup"><span data-stu-id="8cee8-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8cee8-123">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="8cee8-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="8cee8-124">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="8cee8-124">Request headers</span></span>

<span data-ttu-id="8cee8-125">Namn</span><span class="sxs-lookup"><span data-stu-id="8cee8-125">Name</span></span> | <span data-ttu-id="8cee8-126">Skriv</span><span class="sxs-lookup"><span data-stu-id="8cee8-126">Type</span></span> | <span data-ttu-id="8cee8-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8cee8-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="8cee8-128">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="8cee8-128">Authorization</span></span> | <span data-ttu-id="8cee8-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="8cee8-129">String</span></span> | <span data-ttu-id="8cee8-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8cee8-130">Bearer {token}.</span></span> <span data-ttu-id="8cee8-131">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="8cee8-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8cee8-132">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="8cee8-132">Request body</span></span>
<span data-ttu-id="8cee8-133">Tom</span><span class="sxs-lookup"><span data-stu-id="8cee8-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8cee8-134">Svar</span><span class="sxs-lookup"><span data-stu-id="8cee8-134">Response</span></span>
<span data-ttu-id="8cee8-135">Om det lyckas returnerar den här metoden 200 OK med en lista över säkerhetsproblem i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="8cee8-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="8cee8-136">Exempel</span><span class="sxs-lookup"><span data-stu-id="8cee8-136">Example</span></span>

<span data-ttu-id="8cee8-137">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="8cee8-137">**Request**</span></span>

<span data-ttu-id="8cee8-138">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="8cee8-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="8cee8-139">**Svar**</span><span class="sxs-lookup"><span data-stu-id="8cee8-139">**Response**</span></span>

<span data-ttu-id="8cee8-140">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="8cee8-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="8cee8-141">Se även</span><span class="sxs-lookup"><span data-stu-id="8cee8-141">See also</span></span>
- [<span data-ttu-id="8cee8-142">Riskbaserade hot & sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="8cee8-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8cee8-143">Svagheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="8cee8-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
