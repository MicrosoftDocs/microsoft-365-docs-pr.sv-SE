---
title: Få aviseringar om filernas information
description: Hämta alla filer som är relaterade till en viss avisering med Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, få aviseringsinformation, aviseringsinformation, relaterade filer
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
ms.technology: mde
ms.openlocfilehash: 31cbbaee9a97c061b61cc9f7ecc71bb759aea081
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166990"
---
# <a name="get-alert-related-files-information-api"></a><span data-ttu-id="e22e2-104">API:t för att få aviseringsrelaterad filinformation</span><span class="sxs-lookup"><span data-stu-id="e22e2-104">Get alert related files information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e22e2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e22e2-105">**Applies to:**</span></span>
- [<span data-ttu-id="e22e2-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e22e2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e22e2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e22e2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
 
> <span data-ttu-id="e22e2-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e22e2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e22e2-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e22e2-109">Sign up for free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e22e2-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="e22e2-110">API description</span></span>
<span data-ttu-id="e22e2-111">Hämtar alla filer som är relaterade till en viss avisering.</span><span class="sxs-lookup"><span data-stu-id="e22e2-111">Retrieves all files related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="e22e2-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="e22e2-112">Limitations</span></span>
1. <span data-ttu-id="e22e2-113">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="e22e2-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="e22e2-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="e22e2-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="e22e2-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="e22e2-115">Permissions</span></span>
<span data-ttu-id="e22e2-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="e22e2-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e22e2-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e22e2-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e22e2-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="e22e2-118">Permission type</span></span> | <span data-ttu-id="e22e2-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="e22e2-119">Permission</span></span> | <span data-ttu-id="e22e2-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="e22e2-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e22e2-121">Program</span><span class="sxs-lookup"><span data-stu-id="e22e2-121">Application</span></span> | <span data-ttu-id="e22e2-122">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e22e2-122">File.Read.All</span></span> | <span data-ttu-id="e22e2-123">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="e22e2-123">'Read file profiles'</span></span>
<span data-ttu-id="e22e2-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="e22e2-124">Delegated (work or school account)</span></span> | <span data-ttu-id="e22e2-125">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="e22e2-125">File.Read.All</span></span> | <span data-ttu-id="e22e2-126">"Läsa filprofiler"</span><span class="sxs-lookup"><span data-stu-id="e22e2-126">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="e22e2-127">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="e22e2-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e22e2-128">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="e22e2-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e22e2-129">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e22e2-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e22e2-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="e22e2-130">HTTP request</span></span>
```
GET /api/alerts/{id}/files
```

## <a name="request-headers"></a><span data-ttu-id="e22e2-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="e22e2-131">Request headers</span></span>

<span data-ttu-id="e22e2-132">Namn</span><span class="sxs-lookup"><span data-stu-id="e22e2-132">Name</span></span> | <span data-ttu-id="e22e2-133">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="e22e2-133">Type</span></span> | <span data-ttu-id="e22e2-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e22e2-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="e22e2-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="e22e2-135">Authorization</span></span> | <span data-ttu-id="e22e2-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="e22e2-136">String</span></span> | <span data-ttu-id="e22e2-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e22e2-137">Bearer {token}.</span></span> <span data-ttu-id="e22e2-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="e22e2-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e22e2-139">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="e22e2-139">Request body</span></span>
<span data-ttu-id="e22e2-140">Tom</span><span class="sxs-lookup"><span data-stu-id="e22e2-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e22e2-141">Svar</span><span class="sxs-lookup"><span data-stu-id="e22e2-141">Response</span></span>
<span data-ttu-id="e22e2-142">Om det lyckas och avisering och filer finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="e22e2-142">If successful and alert and files exist - 200 OK.</span></span> <span data-ttu-id="e22e2-143">Om aviseringen inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="e22e2-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="e22e2-144">Exempel</span><span class="sxs-lookup"><span data-stu-id="e22e2-144">Example</span></span>

<span data-ttu-id="e22e2-145">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="e22e2-145">**Request**</span></span>

<span data-ttu-id="e22e2-146">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="e22e2-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/files
```

<span data-ttu-id="e22e2-147">**Svar**</span><span class="sxs-lookup"><span data-stu-id="e22e2-147">**Response**</span></span>

<span data-ttu-id="e22e2-148">Här är ett exempel på svaret.</span><span class="sxs-lookup"><span data-stu-id="e22e2-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files",
    "value": [
        {
            "sha1": "f2a00fd2f2de1be0214b8529f1e9f67096c1aa70",
            "sha256": "dcd71ef5fff4362a9f64cf3f96f14f2b11d6f428f3badbedcb9ff3361e7079aa",
            "md5": "8d5b7cc9a832e21d22503057e1fec8e9",
            "globalPrevalence": 29,
            "globalFirstObserved": "2019-03-23T23:54:06.0135204Z",
            "globalLastObserved": "2019-04-23T00:43:20.0489831Z",
            "size": 113984,
            "fileType": null,
            "isPeFile": true,
            "filePublisher": "Microsoft Corporation",
            "fileProductName": "Microsoft� Windows� Operating System",
            "signer": "Microsoft Corporation",
            "issuer": "Microsoft Code Signing PCA",
            "signerHash": "9dc17888b5cfad98b3cb35c1994e96227f061675",
            "isValidCertificate": true,
            "determinationType": "Unknown",
            "determinationValue": null
        }
        ...
    ]
}
```
