---
title: API för insamling av undersökningspaket
description: Använd detta API för att skapa anrop som är relaterade till insamling av ett undersökningspaket från en enhet.
keywords: apis, graph api, api som stöds, paket för insamling av undersökning
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
ms.openlocfilehash: 4cf60ea73ea907be9c10b2dd9562a0ea60127f2d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289901"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="5dbac-104">API för insamling av undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="5dbac-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5dbac-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5dbac-105">**Applies to:**</span></span>
- [<span data-ttu-id="5dbac-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5dbac-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5dbac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5dbac-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="5dbac-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5dbac-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5dbac-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5dbac-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5dbac-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="5dbac-110">API description</span></span>

<span data-ttu-id="5dbac-111">Samla in undersökningspaket från en enhet.</span><span class="sxs-lookup"><span data-stu-id="5dbac-111">Collect investigation package from a device.</span></span>

## <a name="limitations"></a><span data-ttu-id="5dbac-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="5dbac-112">Limitations</span></span>

1. <span data-ttu-id="5dbac-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="5dbac-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="5dbac-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5dbac-114">Permissions</span></span>

<span data-ttu-id="5dbac-115">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="5dbac-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5dbac-116">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5dbac-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5dbac-117">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="5dbac-117">Permission type</span></span> | <span data-ttu-id="5dbac-118">Behörighet</span><span class="sxs-lookup"><span data-stu-id="5dbac-118">Permission</span></span> | <span data-ttu-id="5dbac-119">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="5dbac-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5dbac-120">Program</span><span class="sxs-lookup"><span data-stu-id="5dbac-120">Application</span></span> | <span data-ttu-id="5dbac-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5dbac-121">Machine.CollectForensics</span></span> | <span data-ttu-id="5dbac-122">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="5dbac-122">'Collect forensics'</span></span>
<span data-ttu-id="5dbac-123">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5dbac-123">Delegated (work or school account)</span></span> | <span data-ttu-id="5dbac-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="5dbac-124">Machine.CollectForensics</span></span> | <span data-ttu-id="5dbac-125">"Samla in en forensiska"</span><span class="sxs-lookup"><span data-stu-id="5dbac-125">'Collect forensics'</span></span>

> [!NOTE]
> <span data-ttu-id="5dbac-126">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="5dbac-126">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="5dbac-127">Användaren måste ha minst följande rollbehörighet: "Undersökning av aviseringar" (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="5dbac-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="5dbac-128">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="5dbac-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5dbac-129">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5dbac-129">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="5dbac-130">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="5dbac-130">Request headers</span></span>

<span data-ttu-id="5dbac-131">Namn</span><span class="sxs-lookup"><span data-stu-id="5dbac-131">Name</span></span> | <span data-ttu-id="5dbac-132">Typ</span><span class="sxs-lookup"><span data-stu-id="5dbac-132">Type</span></span> | <span data-ttu-id="5dbac-133">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5dbac-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="5dbac-134">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5dbac-134">Authorization</span></span> | <span data-ttu-id="5dbac-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="5dbac-135">String</span></span> | <span data-ttu-id="5dbac-136">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5dbac-136">Bearer {token}.</span></span> <span data-ttu-id="5dbac-137">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5dbac-137">**Required**.</span></span>
<span data-ttu-id="5dbac-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5dbac-138">Content-Type</span></span> | <span data-ttu-id="5dbac-139">sträng</span><span class="sxs-lookup"><span data-stu-id="5dbac-139">string</span></span> | <span data-ttu-id="5dbac-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="5dbac-140">application/json.</span></span> <span data-ttu-id="5dbac-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5dbac-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5dbac-142">Frågebrödtext</span><span class="sxs-lookup"><span data-stu-id="5dbac-142">Request body</span></span>

<span data-ttu-id="5dbac-143">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="5dbac-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5dbac-144">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dbac-144">Parameter</span></span> | <span data-ttu-id="5dbac-145">Typ</span><span class="sxs-lookup"><span data-stu-id="5dbac-145">Type</span></span> | <span data-ttu-id="5dbac-146">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5dbac-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="5dbac-147">Kommentar</span><span class="sxs-lookup"><span data-stu-id="5dbac-147">Comment</span></span> | <span data-ttu-id="5dbac-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="5dbac-148">String</span></span> | <span data-ttu-id="5dbac-149">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5dbac-149">Comment to associate with the action.</span></span> <span data-ttu-id="5dbac-150">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5dbac-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="5dbac-151">Svar</span><span class="sxs-lookup"><span data-stu-id="5dbac-151">Response</span></span>

<span data-ttu-id="5dbac-152">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="5dbac-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="5dbac-153">Exempel</span><span class="sxs-lookup"><span data-stu-id="5dbac-153">Example</span></span>

### <a name="request"></a><span data-ttu-id="5dbac-154">Begäran</span><span class="sxs-lookup"><span data-stu-id="5dbac-154">Request</span></span>

<span data-ttu-id="5dbac-155">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="5dbac-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
