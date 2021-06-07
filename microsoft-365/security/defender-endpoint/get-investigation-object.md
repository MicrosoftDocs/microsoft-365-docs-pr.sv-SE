---
title: Get Investigation object API
description: Använd detta API för att skapa anrop som är relaterade till att hämta undersökningsobjekt
keywords: apis, graph api, API som stöds, Investigation-objekt
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770139"
---
# <a name="get-investigation-api"></a><span data-ttu-id="1b2bd-104">Get Investigation API</span><span class="sxs-lookup"><span data-stu-id="1b2bd-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1b2bd-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1b2bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b2bd-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1b2bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b2bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b2bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1b2bd-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1b2bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1b2bd-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1b2bd-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b2bd-110">API description</span></span>
<span data-ttu-id="1b2bd-111">Hämtar specifik [undersökning genom](investigation.md) dess ID.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="1b2bd-112">ID kan vara undersöknings-ID eller undersökning som utlöser aviserings-ID.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="1b2bd-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="1b2bd-113">Limitations</span></span>
1. <span data-ttu-id="1b2bd-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1b2bd-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="1b2bd-115">Permissions</span></span>
<span data-ttu-id="1b2bd-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1b2bd-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1b2bd-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1b2bd-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="1b2bd-118">Permission type</span></span> |   <span data-ttu-id="1b2bd-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="1b2bd-119">Permission</span></span>  |   <span data-ttu-id="1b2bd-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="1b2bd-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1b2bd-121">Program</span><span class="sxs-lookup"><span data-stu-id="1b2bd-121">Application</span></span> |   <span data-ttu-id="1b2bd-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="1b2bd-122">Alert.Read.All</span></span> |    <span data-ttu-id="1b2bd-123">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="1b2bd-123">'Read all alerts'</span></span>
<span data-ttu-id="1b2bd-124">Program</span><span class="sxs-lookup"><span data-stu-id="1b2bd-124">Application</span></span> |   <span data-ttu-id="1b2bd-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="1b2bd-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="1b2bd-126">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="1b2bd-126">'Read and write all alerts'</span></span>
<span data-ttu-id="1b2bd-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1b2bd-127">Delegated (work or school account)</span></span> | <span data-ttu-id="1b2bd-128">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="1b2bd-128">Alert.Read</span></span> | <span data-ttu-id="1b2bd-129">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="1b2bd-129">'Read alerts'</span></span>
<span data-ttu-id="1b2bd-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="1b2bd-130">Delegated (work or school account)</span></span> | <span data-ttu-id="1b2bd-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="1b2bd-131">Alert.ReadWrite</span></span> | <span data-ttu-id="1b2bd-132">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="1b2bd-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="1b2bd-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="1b2bd-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1b2bd-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="1b2bd-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1b2bd-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="1b2bd-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="1b2bd-136">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="1b2bd-136">Request headers</span></span>

<span data-ttu-id="1b2bd-137">Namn</span><span class="sxs-lookup"><span data-stu-id="1b2bd-137">Name</span></span> | <span data-ttu-id="1b2bd-138">Typ</span><span class="sxs-lookup"><span data-stu-id="1b2bd-138">Type</span></span> | <span data-ttu-id="1b2bd-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1b2bd-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="1b2bd-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="1b2bd-140">Authorization</span></span> | <span data-ttu-id="1b2bd-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="1b2bd-141">String</span></span> | <span data-ttu-id="1b2bd-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1b2bd-142">Bearer {token}.</span></span> <span data-ttu-id="1b2bd-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="1b2bd-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1b2bd-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="1b2bd-144">Request body</span></span>
<span data-ttu-id="1b2bd-145">Tom</span><span class="sxs-lookup"><span data-stu-id="1b2bd-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1b2bd-146">Svar</span><span class="sxs-lookup"><span data-stu-id="1b2bd-146">Response</span></span>
<span data-ttu-id="1b2bd-147">Om det lyckas returnerar den här metoden 200, Ok svarskod med en [Undersökningar-entitet.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="1b2bd-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

