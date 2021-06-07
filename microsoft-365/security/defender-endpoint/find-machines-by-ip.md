---
title: Hitta enheter genom internt IP API
description: Hitta enheter som visas med den begärda interna IP-adressen inom intervallet 15 minuter före och efter en viss tidsstämpel
keywords: apis, graph api, api som stöds, skaffa, enhet, IP, hitta, hitta enhet, via ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769443"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="054fb-104">Hitta enheter genom internt IP API</span><span class="sxs-lookup"><span data-stu-id="054fb-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="054fb-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="054fb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="054fb-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="054fb-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="054fb-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="054fb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="054fb-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="054fb-108">API description</span></span>
<span data-ttu-id="054fb-109">Hitta [datorer](machine.md) som visas med den begärda interna IP-adressen inom intervallet 15 minuter före och efter en viss tidsstämpel.</span><span class="sxs-lookup"><span data-stu-id="054fb-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="054fb-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="054fb-110">Limitations</span></span>
1. <span data-ttu-id="054fb-111">Tidsstämpeln måste vara inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="054fb-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="054fb-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="054fb-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="054fb-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="054fb-113">Permissions</span></span>
<span data-ttu-id="054fb-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="054fb-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="054fb-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="054fb-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="054fb-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="054fb-116">Permission type</span></span> |   <span data-ttu-id="054fb-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="054fb-117">Permission</span></span>  |   <span data-ttu-id="054fb-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="054fb-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="054fb-119">Program</span><span class="sxs-lookup"><span data-stu-id="054fb-119">Application</span></span> |   <span data-ttu-id="054fb-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="054fb-120">Machine.Read.All</span></span> |  <span data-ttu-id="054fb-121">"Läs alla maskinprofiler"</span><span class="sxs-lookup"><span data-stu-id="054fb-121">'Read all machine profiles'</span></span>
<span data-ttu-id="054fb-122">Program</span><span class="sxs-lookup"><span data-stu-id="054fb-122">Application</span></span> |   <span data-ttu-id="054fb-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="054fb-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="054fb-124">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="054fb-124">'Read and write all machine information'</span></span>
<span data-ttu-id="054fb-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="054fb-125">Delegated (work or school account)</span></span> | <span data-ttu-id="054fb-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="054fb-126">Machine.Read</span></span> | <span data-ttu-id="054fb-127">"Läs maskininformation"</span><span class="sxs-lookup"><span data-stu-id="054fb-127">'Read machine information'</span></span>
<span data-ttu-id="054fb-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="054fb-128">Delegated (work or school account)</span></span> | <span data-ttu-id="054fb-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="054fb-129">Machine.ReadWrite</span></span> | <span data-ttu-id="054fb-130">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="054fb-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="054fb-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="054fb-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="054fb-132">Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="054fb-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="054fb-133">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="054fb-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="054fb-134">Svar omfattar endast enheter som användaren har åtkomst till baserat på enhetsgruppinställningar (mer information finns i Skapa och [hantera](machine-groups.md) enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="054fb-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="054fb-135">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="054fb-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="054fb-136">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="054fb-136">Request headers</span></span>

<span data-ttu-id="054fb-137">Namn</span><span class="sxs-lookup"><span data-stu-id="054fb-137">Name</span></span> | <span data-ttu-id="054fb-138">Typ</span><span class="sxs-lookup"><span data-stu-id="054fb-138">Type</span></span> | <span data-ttu-id="054fb-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="054fb-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="054fb-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="054fb-140">Authorization</span></span> | <span data-ttu-id="054fb-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="054fb-141">String</span></span> | <span data-ttu-id="054fb-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="054fb-142">Bearer {token}.</span></span> <span data-ttu-id="054fb-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="054fb-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="054fb-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="054fb-144">Request body</span></span>
<span data-ttu-id="054fb-145">Tom</span><span class="sxs-lookup"><span data-stu-id="054fb-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="054fb-146">Svar</span><span class="sxs-lookup"><span data-stu-id="054fb-146">Response</span></span>
<span data-ttu-id="054fb-147">Om det lyckas – 200 OK med en lista över maskinerna i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="054fb-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="054fb-148">Om tidsstämpeln inte är inom de senaste 30 dagarna – 400 Bad Request.</span><span class="sxs-lookup"><span data-stu-id="054fb-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="054fb-149">Exempel</span><span class="sxs-lookup"><span data-stu-id="054fb-149">Example</span></span>

<span data-ttu-id="054fb-150">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="054fb-150">**Request**</span></span>

<span data-ttu-id="054fb-151">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="054fb-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
