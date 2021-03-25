---
title: Skaffa API för användarrelaterade aviseringar
description: Hämta en samling aviseringar som är relaterade till ett visst användar-ID med Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, användare, relaterade, aviseringar
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
ms.openlocfilehash: cff4530cfa4ecd6b0d918a9112e7be3c0f30209c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166795"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="abaf7-104">Skaffa API för användarrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="abaf7-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="abaf7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="abaf7-105">**Applies to:**</span></span>
- [<span data-ttu-id="abaf7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="abaf7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="abaf7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="abaf7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="abaf7-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="abaf7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="abaf7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="abaf7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="abaf7-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="abaf7-110">API description</span></span>
<span data-ttu-id="abaf7-111">Hämtar en samling aviseringar som är relaterade till ett visst användar-ID.</span><span class="sxs-lookup"><span data-stu-id="abaf7-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="abaf7-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="abaf7-112">Limitations</span></span>
1. <span data-ttu-id="abaf7-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="abaf7-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="abaf7-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="abaf7-114">Permissions</span></span>
<span data-ttu-id="abaf7-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="abaf7-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="abaf7-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="abaf7-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="abaf7-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="abaf7-117">Permission type</span></span> |   <span data-ttu-id="abaf7-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="abaf7-118">Permission</span></span>  |   <span data-ttu-id="abaf7-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="abaf7-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="abaf7-120">Program</span><span class="sxs-lookup"><span data-stu-id="abaf7-120">Application</span></span> |   <span data-ttu-id="abaf7-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="abaf7-121">Alert.Read.All</span></span> |    <span data-ttu-id="abaf7-122">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="abaf7-122">'Read all alerts'</span></span>
<span data-ttu-id="abaf7-123">Program</span><span class="sxs-lookup"><span data-stu-id="abaf7-123">Application</span></span> |   <span data-ttu-id="abaf7-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="abaf7-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="abaf7-125">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="abaf7-125">'Read and write all alerts'</span></span>
<span data-ttu-id="abaf7-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="abaf7-126">Delegated (work or school account)</span></span> | <span data-ttu-id="abaf7-127">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="abaf7-127">Alert.Read</span></span> | <span data-ttu-id="abaf7-128">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="abaf7-128">'Read alerts'</span></span>
<span data-ttu-id="abaf7-129">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="abaf7-129">Delegated (work or school account)</span></span> | <span data-ttu-id="abaf7-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="abaf7-130">Alert.ReadWrite</span></span> | <span data-ttu-id="abaf7-131">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="abaf7-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="abaf7-132">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="abaf7-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="abaf7-133">Användaren måste ha minst följande rollbehörighet: "Visa data".</span><span class="sxs-lookup"><span data-stu-id="abaf7-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="abaf7-134">Mer information finns i Skapa [och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="abaf7-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="abaf7-135">Svaret inkluderar endast aviseringar, som associeras med enheter, som användaren har [](machine-groups.md) åtkomst till, baserat på enhetsgruppsinställningar (mer information finns i Skapa och hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="abaf7-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="abaf7-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="abaf7-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="abaf7-137">**ID:t är inte det fullständiga UPN, utan bara användarnamnet. (Om du till exempel vill hämta user1@contoso.com använda /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="abaf7-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="abaf7-138">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="abaf7-138">Request headers</span></span>

<span data-ttu-id="abaf7-139">Namn</span><span class="sxs-lookup"><span data-stu-id="abaf7-139">Name</span></span> | <span data-ttu-id="abaf7-140">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="abaf7-140">Type</span></span> | <span data-ttu-id="abaf7-141">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="abaf7-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="abaf7-142">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="abaf7-142">Authorization</span></span> | <span data-ttu-id="abaf7-143">Sträng</span><span class="sxs-lookup"><span data-stu-id="abaf7-143">String</span></span> | <span data-ttu-id="abaf7-144">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="abaf7-144">Bearer {token}.</span></span> <span data-ttu-id="abaf7-145">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="abaf7-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="abaf7-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="abaf7-146">Request body</span></span>
<span data-ttu-id="abaf7-147">Tom</span><span class="sxs-lookup"><span data-stu-id="abaf7-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="abaf7-148">Svar</span><span class="sxs-lookup"><span data-stu-id="abaf7-148">Response</span></span>
<span data-ttu-id="abaf7-149">Om det lyckas och användaren finns - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="abaf7-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="abaf7-150">Om användaren inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="abaf7-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="abaf7-151">Exempel</span><span class="sxs-lookup"><span data-stu-id="abaf7-151">Example</span></span>

<span data-ttu-id="abaf7-152">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="abaf7-152">**Request**</span></span>

<span data-ttu-id="abaf7-153">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="abaf7-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```