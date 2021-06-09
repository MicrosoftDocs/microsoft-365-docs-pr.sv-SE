---
title: Hämta API för filrelaterade datorer
description: Lär dig hur du använder API:t för filrelaterade datorer för att få en samling datorer som är relaterade till en filhash i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, enheter, hash
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
ms.openlocfilehash: 211a29bcd9265ae20c4f3e1817fcaaf562260d39
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770283"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="aa62d-104">Hämta API för filrelaterade datorer</span><span class="sxs-lookup"><span data-stu-id="aa62d-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa62d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="aa62d-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa62d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa62d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa62d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa62d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa62d-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="aa62d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa62d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="aa62d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="aa62d-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="aa62d-110">API description</span></span>
<span data-ttu-id="aa62d-111">Hämtar en samling datorer som [är relaterade](machine.md) till en viss filhash.</span><span class="sxs-lookup"><span data-stu-id="aa62d-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="aa62d-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="aa62d-112">Limitations</span></span>
1. <span data-ttu-id="aa62d-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="aa62d-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="aa62d-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="aa62d-114">Permissions</span></span>
<span data-ttu-id="aa62d-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="aa62d-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aa62d-116">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aa62d-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="aa62d-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="aa62d-117">Permission type</span></span> |   <span data-ttu-id="aa62d-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="aa62d-118">Permission</span></span>  |   <span data-ttu-id="aa62d-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="aa62d-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aa62d-120">Program</span><span class="sxs-lookup"><span data-stu-id="aa62d-120">Application</span></span> |   <span data-ttu-id="aa62d-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="aa62d-121">Machine.Read.All</span></span> |  <span data-ttu-id="aa62d-122">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="aa62d-122">'Read all machine profiles'</span></span>
<span data-ttu-id="aa62d-123">Program</span><span class="sxs-lookup"><span data-stu-id="aa62d-123">Application</span></span> |   <span data-ttu-id="aa62d-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="aa62d-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="aa62d-125">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="aa62d-125">'Read and write all machine information'</span></span>
<span data-ttu-id="aa62d-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="aa62d-126">Delegated (work or school account)</span></span> | <span data-ttu-id="aa62d-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="aa62d-127">Machine.Read</span></span> | <span data-ttu-id="aa62d-128">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="aa62d-128">'Read machine information'</span></span>
<span data-ttu-id="aa62d-129">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="aa62d-129">Delegated (work or school account)</span></span> | <span data-ttu-id="aa62d-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="aa62d-130">Machine.ReadWrite</span></span> | <span data-ttu-id="aa62d-131">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="aa62d-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="aa62d-132">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="aa62d-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="aa62d-133">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="aa62d-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="aa62d-134">Svaret omfattar endast enheter, som användaren har åtkomst till, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="aa62d-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="aa62d-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="aa62d-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="aa62d-136">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="aa62d-136">Request headers</span></span>

<span data-ttu-id="aa62d-137">Namn</span><span class="sxs-lookup"><span data-stu-id="aa62d-137">Name</span></span> | <span data-ttu-id="aa62d-138">Typ</span><span class="sxs-lookup"><span data-stu-id="aa62d-138">Type</span></span> | <span data-ttu-id="aa62d-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aa62d-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="aa62d-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="aa62d-140">Authorization</span></span> | <span data-ttu-id="aa62d-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="aa62d-141">String</span></span> | <span data-ttu-id="aa62d-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aa62d-142">Bearer {token}.</span></span> <span data-ttu-id="aa62d-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="aa62d-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="aa62d-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="aa62d-144">Request body</span></span>
<span data-ttu-id="aa62d-145">Tom</span><span class="sxs-lookup"><span data-stu-id="aa62d-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aa62d-146">Svar</span><span class="sxs-lookup"><span data-stu-id="aa62d-146">Response</span></span>
<span data-ttu-id="aa62d-147">Om filen lyckas och det finns en fil – 200 OK med en [lista över datorenheter](machine.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="aa62d-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="aa62d-148">Om filen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="aa62d-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="aa62d-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="aa62d-149">Example</span></span>

<span data-ttu-id="aa62d-150">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="aa62d-150">**Request**</span></span>

<span data-ttu-id="aa62d-151">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="aa62d-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
