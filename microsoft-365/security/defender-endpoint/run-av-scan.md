---
title: Kör API för antivirusskanning
description: Använd detta API för att skapa anrop som är relaterade till att köra en antivirussökning på en enhet.
keywords: apis, graph api, API som stöds, ta bort enheten från isolation
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
ms.openlocfilehash: d0db45daa786c1a44272e4d02153af3fe658e781
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200215"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="01101-104">Kör API för antivirusskanning</span><span class="sxs-lookup"><span data-stu-id="01101-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01101-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="01101-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="01101-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="01101-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01101-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="01101-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="01101-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="01101-108">API description</span></span>
<span data-ttu-id="01101-109">Starta en sökning i Microsoft Defender Antivirus på en enhet.</span><span class="sxs-lookup"><span data-stu-id="01101-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="01101-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="01101-110">Limitations</span></span>
1. <span data-ttu-id="01101-111">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="01101-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="01101-112">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="01101-112">Permissions</span></span>
<span data-ttu-id="01101-113">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="01101-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="01101-114">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="01101-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="01101-115">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="01101-115">Permission type</span></span> |   <span data-ttu-id="01101-116">Behörighet</span><span class="sxs-lookup"><span data-stu-id="01101-116">Permission</span></span>  |   <span data-ttu-id="01101-117">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="01101-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="01101-118">Program</span><span class="sxs-lookup"><span data-stu-id="01101-118">Application</span></span> |   <span data-ttu-id="01101-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="01101-119">Machine.Scan</span></span> |  <span data-ttu-id="01101-120">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="01101-120">'Scan machine'</span></span>
<span data-ttu-id="01101-121">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="01101-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="01101-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="01101-122">Machine.Scan</span></span> |  <span data-ttu-id="01101-123">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="01101-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="01101-124">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="01101-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="01101-125">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="01101-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="01101-126">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="01101-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="01101-127">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="01101-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="01101-128">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="01101-128">Request headers</span></span>

<span data-ttu-id="01101-129">Namn</span><span class="sxs-lookup"><span data-stu-id="01101-129">Name</span></span> | <span data-ttu-id="01101-130">Skriv</span><span class="sxs-lookup"><span data-stu-id="01101-130">Type</span></span> | <span data-ttu-id="01101-131">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="01101-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="01101-132">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="01101-132">Authorization</span></span> | <span data-ttu-id="01101-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="01101-133">String</span></span> | <span data-ttu-id="01101-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="01101-134">Bearer {token}.</span></span> <span data-ttu-id="01101-135">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="01101-135">**Required**.</span></span>
<span data-ttu-id="01101-136">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="01101-136">Content-Type</span></span> | <span data-ttu-id="01101-137">sträng</span><span class="sxs-lookup"><span data-stu-id="01101-137">string</span></span> | <span data-ttu-id="01101-138">application/json</span><span class="sxs-lookup"><span data-stu-id="01101-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="01101-139">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="01101-139">Request body</span></span>
<span data-ttu-id="01101-140">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="01101-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="01101-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="01101-141">Parameter</span></span> | <span data-ttu-id="01101-142">Skriv</span><span class="sxs-lookup"><span data-stu-id="01101-142">Type</span></span>    | <span data-ttu-id="01101-143">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="01101-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="01101-144">Kommentar</span><span class="sxs-lookup"><span data-stu-id="01101-144">Comment</span></span> |   <span data-ttu-id="01101-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="01101-145">String</span></span> | <span data-ttu-id="01101-146">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="01101-146">Comment to associate with the action.</span></span> <span data-ttu-id="01101-147">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="01101-147">**Required**.</span></span>
<span data-ttu-id="01101-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="01101-148">ScanType</span></span>|   <span data-ttu-id="01101-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="01101-149">String</span></span>  | <span data-ttu-id="01101-150">Definierar typen av sökning.</span><span class="sxs-lookup"><span data-stu-id="01101-150">Defines the type of the Scan.</span></span> <span data-ttu-id="01101-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="01101-151">**Required**.</span></span>

<span data-ttu-id="01101-152">**ScanType** styr vilken typ av genomsökning som ska utföras och kan vara något av följande:</span><span class="sxs-lookup"><span data-stu-id="01101-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="01101-153">**Snabb** – genomför snabbsökning på enheten</span><span class="sxs-lookup"><span data-stu-id="01101-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="01101-154">**Fullständig** – Utför fullständig sökning på enheten</span><span class="sxs-lookup"><span data-stu-id="01101-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="01101-155">Svar</span><span class="sxs-lookup"><span data-stu-id="01101-155">Response</span></span>
<span data-ttu-id="01101-156">Om det lyckas returnerar den här metoden 201, Skapad svarskod och _MachineAction-objekt_ i svarets brödtext.</span><span class="sxs-lookup"><span data-stu-id="01101-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="01101-157">Exempel</span><span class="sxs-lookup"><span data-stu-id="01101-157">Example</span></span>

<span data-ttu-id="01101-158">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="01101-158">**Request**</span></span>

<span data-ttu-id="01101-159">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="01101-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

