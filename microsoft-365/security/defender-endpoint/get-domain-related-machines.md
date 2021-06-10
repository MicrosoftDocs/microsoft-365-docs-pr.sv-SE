---
title: Skaffa API för domänrelaterade datorer
description: Lär dig hur du använder API för domänrelaterade datorer för att få datorer som kommunicerar till eller från en domän i Microsoft Defender för Endpoint.
keywords: apis, graph api, API som stöds, skaffa, domän, relaterade, enheter
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772239"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="a5175-104">Skaffa API för domänrelaterade datorer</span><span class="sxs-lookup"><span data-stu-id="a5175-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a5175-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5175-105">**Applies to:**</span></span>
- [<span data-ttu-id="a5175-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5175-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5175-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5175-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5175-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a5175-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a5175-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a5175-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="a5175-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5175-110">API description</span></span>
<span data-ttu-id="a5175-111">Hämtar en samling datorer [som](machine.md) har kommunicerat till eller från en viss domänadress.</span><span class="sxs-lookup"><span data-stu-id="a5175-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="a5175-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="a5175-112">Limitations</span></span>
1. <span data-ttu-id="a5175-113">Du kan fråga på enheter som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="a5175-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="a5175-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="a5175-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="a5175-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="a5175-115">Permissions</span></span>
<span data-ttu-id="a5175-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="a5175-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a5175-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a5175-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a5175-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="a5175-118">Permission type</span></span> |   <span data-ttu-id="a5175-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a5175-119">Permission</span></span>  |   <span data-ttu-id="a5175-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="a5175-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a5175-121">Program</span><span class="sxs-lookup"><span data-stu-id="a5175-121">Application</span></span> |   <span data-ttu-id="a5175-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="a5175-122">Machine.Read.All</span></span> |  <span data-ttu-id="a5175-123">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="a5175-123">'Read all machine profiles'</span></span>
<span data-ttu-id="a5175-124">Program</span><span class="sxs-lookup"><span data-stu-id="a5175-124">Application</span></span> |   <span data-ttu-id="a5175-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="a5175-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="a5175-126">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="a5175-126">'Read and write all machine information'</span></span>
<span data-ttu-id="a5175-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a5175-127">Delegated (work or school account)</span></span> | <span data-ttu-id="a5175-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="a5175-128">Machine.Read</span></span> | <span data-ttu-id="a5175-129">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="a5175-129">'Read machine information'</span></span>
<span data-ttu-id="a5175-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="a5175-130">Delegated (work or school account)</span></span> | <span data-ttu-id="a5175-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="a5175-131">Machine.ReadWrite</span></span> | <span data-ttu-id="a5175-132">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="a5175-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="a5175-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="a5175-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a5175-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="a5175-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="a5175-135">Svaret omfattar endast enheter som användaren kan komma åt, baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="a5175-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a5175-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="a5175-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="a5175-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="a5175-137">Request headers</span></span>

<span data-ttu-id="a5175-138">Namn</span><span class="sxs-lookup"><span data-stu-id="a5175-138">Name</span></span> | <span data-ttu-id="a5175-139">Typ</span><span class="sxs-lookup"><span data-stu-id="a5175-139">Type</span></span> | <span data-ttu-id="a5175-140">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5175-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="a5175-141">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="a5175-141">Authorization</span></span> | <span data-ttu-id="a5175-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5175-142">String</span></span> | <span data-ttu-id="a5175-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a5175-143">Bearer {token}.</span></span> <span data-ttu-id="a5175-144">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="a5175-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a5175-145">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="a5175-145">Request body</span></span>
<span data-ttu-id="a5175-146">Tom</span><span class="sxs-lookup"><span data-stu-id="a5175-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a5175-147">Svar</span><span class="sxs-lookup"><span data-stu-id="a5175-147">Response</span></span>
<span data-ttu-id="a5175-148">Om det lyckas och det finns en domän – 200 OK med en lista över [datorenheter.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="a5175-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="a5175-149">Om domänen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="a5175-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a5175-150">Exempel</span><span class="sxs-lookup"><span data-stu-id="a5175-150">Example</span></span>

<span data-ttu-id="a5175-151">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="a5175-151">**Request**</span></span>

<span data-ttu-id="a5175-152">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="a5175-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
