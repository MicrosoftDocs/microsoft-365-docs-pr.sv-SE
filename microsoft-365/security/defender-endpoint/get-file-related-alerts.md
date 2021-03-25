---
title: API för filrelaterade aviseringar
description: Lär dig hur du använder API:t Hämta filrelaterade aviseringar för att få en samling aviseringar relaterade till en viss filhash i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, fil, hash
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
ms.openlocfilehash: 4c981f4a94b32bed924af92b48924e78cc8e0882
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167133"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="31c67-104">API för filrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="31c67-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31c67-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="31c67-105">**Applies to:**</span></span>
- [<span data-ttu-id="31c67-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="31c67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="31c67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31c67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="31c67-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="31c67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31c67-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="31c67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="31c67-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="31c67-110">API description</span></span>
<span data-ttu-id="31c67-111">Hämtar en samling aviseringar som är relaterade till en viss filhash.</span><span class="sxs-lookup"><span data-stu-id="31c67-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="31c67-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="31c67-112">Limitations</span></span>
1. <span data-ttu-id="31c67-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="31c67-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="31c67-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="31c67-114">Permissions</span></span>
<span data-ttu-id="31c67-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="31c67-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31c67-116">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="31c67-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="31c67-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="31c67-117">Permission type</span></span> |   <span data-ttu-id="31c67-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="31c67-118">Permission</span></span>  |   <span data-ttu-id="31c67-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="31c67-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31c67-120">Program</span><span class="sxs-lookup"><span data-stu-id="31c67-120">Application</span></span> |   <span data-ttu-id="31c67-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="31c67-121">Alert.Read.All</span></span> |    <span data-ttu-id="31c67-122">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="31c67-122">'Read all alerts'</span></span>
<span data-ttu-id="31c67-123">Program</span><span class="sxs-lookup"><span data-stu-id="31c67-123">Application</span></span> |   <span data-ttu-id="31c67-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="31c67-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="31c67-125">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="31c67-125">'Read and write all alerts'</span></span>
<span data-ttu-id="31c67-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="31c67-126">Delegated (work or school account)</span></span> | <span data-ttu-id="31c67-127">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="31c67-127">Alert.Read</span></span> | <span data-ttu-id="31c67-128">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="31c67-128">'Read alerts'</span></span>
<span data-ttu-id="31c67-129">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="31c67-129">Delegated (work or school account)</span></span> | <span data-ttu-id="31c67-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="31c67-130">Alert.ReadWrite</span></span> | <span data-ttu-id="31c67-131">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="31c67-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="31c67-132">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="31c67-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="31c67-133">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="31c67-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="31c67-134">Svaret inkluderar endast aviseringar, som associeras med enheter, som användaren har [](machine-groups.md) åtkomst till, baserat på enhetsgruppsinställningar (mer information finns i Skapa och hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="31c67-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="31c67-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="31c67-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="31c67-136">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="31c67-136">Request headers</span></span>

<span data-ttu-id="31c67-137">Namn</span><span class="sxs-lookup"><span data-stu-id="31c67-137">Name</span></span> | <span data-ttu-id="31c67-138">Type (Typ)</span><span class="sxs-lookup"><span data-stu-id="31c67-138">Type</span></span> | <span data-ttu-id="31c67-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="31c67-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="31c67-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="31c67-140">Authorization</span></span> | <span data-ttu-id="31c67-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="31c67-141">String</span></span> | <span data-ttu-id="31c67-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="31c67-142">Bearer {token}.</span></span> <span data-ttu-id="31c67-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="31c67-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="31c67-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="31c67-144">Request body</span></span>
<span data-ttu-id="31c67-145">Tom</span><span class="sxs-lookup"><span data-stu-id="31c67-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31c67-146">Svar</span><span class="sxs-lookup"><span data-stu-id="31c67-146">Response</span></span>
<span data-ttu-id="31c67-147">Om filen lyckas och det finns en fil – 200 OK med en lista [över aviseringsenheter](alerts.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="31c67-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="31c67-148">Om filen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="31c67-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="31c67-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="31c67-149">Example</span></span>

<span data-ttu-id="31c67-150">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="31c67-150">**Request**</span></span>

<span data-ttu-id="31c67-151">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="31c67-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```