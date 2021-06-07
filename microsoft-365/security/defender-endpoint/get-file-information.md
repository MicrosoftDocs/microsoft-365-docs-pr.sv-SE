---
title: Hämta API för filinformation
description: Lär dig hur du använder API:t för filinformation för att hämta en fil av Sha1, Sha256 eller MD5-identifierare i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, api som stöds, hämta, fil, information, sha1, sha256, md5
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7877fb2d9b616b487d23befd0f0af35ce2c0753
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770302"
---
# <a name="get-file-information-api"></a><span data-ttu-id="2bd86-104">Hämta API för filinformation</span><span class="sxs-lookup"><span data-stu-id="2bd86-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bd86-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2bd86-105">**Applies to:**</span></span>
- [<span data-ttu-id="2bd86-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2bd86-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2bd86-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2bd86-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2bd86-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="2bd86-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2bd86-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="2bd86-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2bd86-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bd86-110">API description</span></span>
<span data-ttu-id="2bd86-111">Hämtar en fil [med](files.md) identifierare Sha1 eller Sha256</span><span class="sxs-lookup"><span data-stu-id="2bd86-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="2bd86-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="2bd86-112">Limitations</span></span>
1. <span data-ttu-id="2bd86-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="2bd86-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2bd86-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="2bd86-114">Permissions</span></span>
<span data-ttu-id="2bd86-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="2bd86-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2bd86-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2bd86-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2bd86-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="2bd86-117">Permission type</span></span> |   <span data-ttu-id="2bd86-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="2bd86-118">Permission</span></span>  |   <span data-ttu-id="2bd86-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="2bd86-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2bd86-120">Program</span><span class="sxs-lookup"><span data-stu-id="2bd86-120">Application</span></span> |   <span data-ttu-id="2bd86-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bd86-121">File.Read.All</span></span> | <span data-ttu-id="2bd86-122">"Läs alla filprofiler"</span><span class="sxs-lookup"><span data-stu-id="2bd86-122">'Read all file profiles'</span></span>
<span data-ttu-id="2bd86-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="2bd86-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2bd86-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="2bd86-124">File.Read.All</span></span> |    <span data-ttu-id="2bd86-125">"Läs alla filprofiler"</span><span class="sxs-lookup"><span data-stu-id="2bd86-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="2bd86-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="2bd86-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2bd86-127">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="2bd86-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2bd86-128">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="2bd86-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="2bd86-129">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="2bd86-129">Request headers</span></span>

<span data-ttu-id="2bd86-130">Namn</span><span class="sxs-lookup"><span data-stu-id="2bd86-130">Name</span></span> | <span data-ttu-id="2bd86-131">Typ</span><span class="sxs-lookup"><span data-stu-id="2bd86-131">Type</span></span> | <span data-ttu-id="2bd86-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="2bd86-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="2bd86-133">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="2bd86-133">Authorization</span></span> | <span data-ttu-id="2bd86-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="2bd86-134">String</span></span> | <span data-ttu-id="2bd86-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="2bd86-135">Bearer {token}.</span></span> <span data-ttu-id="2bd86-136">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="2bd86-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="2bd86-137">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="2bd86-137">Request body</span></span>
<span data-ttu-id="2bd86-138">Tom</span><span class="sxs-lookup"><span data-stu-id="2bd86-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2bd86-139">Svar</span><span class="sxs-lookup"><span data-stu-id="2bd86-139">Response</span></span>
<span data-ttu-id="2bd86-140">Om det lyckas och filen finns – 200 OK med [fil entiteten](files.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="2bd86-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="2bd86-141">Om filen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="2bd86-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2bd86-142">Exempel</span><span class="sxs-lookup"><span data-stu-id="2bd86-142">Example</span></span>

<span data-ttu-id="2bd86-143">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="2bd86-143">**Request**</span></span>

<span data-ttu-id="2bd86-144">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="2bd86-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="2bd86-145">**Svar**</span><span class="sxs-lookup"><span data-stu-id="2bd86-145">**Response**</span></span>

<span data-ttu-id="2bd86-146">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="2bd86-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
