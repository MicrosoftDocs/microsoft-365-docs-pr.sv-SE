---
title: API för starta undersökning
description: Använd detta API för att påbörja undersökning på en enhet.
keywords: apis, graph api, api som stöds, undersökning
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
ms.openlocfilehash: 4bdbfbb20f3abb9829b2c8be83b9eaa6ec92cde7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187331"
---
# <a name="start-investigation-api"></a><span data-ttu-id="fba2a-104">API för starta undersökning</span><span class="sxs-lookup"><span data-stu-id="fba2a-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fba2a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fba2a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fba2a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fba2a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fba2a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fba2a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fba2a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fba2a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fba2a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fba2a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="fba2a-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="fba2a-110">API description</span></span>
<span data-ttu-id="fba2a-111">Starta automatisk undersökning på en enhet.</span><span class="sxs-lookup"><span data-stu-id="fba2a-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="fba2a-112">Mer information [finns i Översikt över](automated-investigations.md) automatiserade undersökningar.</span><span class="sxs-lookup"><span data-stu-id="fba2a-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="fba2a-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="fba2a-113">Limitations</span></span>
1. <span data-ttu-id="fba2a-114">Prisbegränsningar för detta API är 50 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="fba2a-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="fba2a-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="fba2a-115">Permissions</span></span>
<span data-ttu-id="fba2a-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="fba2a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fba2a-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="fba2a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="fba2a-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="fba2a-118">Permission type</span></span> |   <span data-ttu-id="fba2a-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="fba2a-119">Permission</span></span>  |   <span data-ttu-id="fba2a-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="fba2a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fba2a-121">Program</span><span class="sxs-lookup"><span data-stu-id="fba2a-121">Application</span></span> |   <span data-ttu-id="fba2a-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fba2a-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="fba2a-123">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="fba2a-123">'Read and write all alerts'</span></span>
<span data-ttu-id="fba2a-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="fba2a-124">Delegated (work or school account)</span></span> | <span data-ttu-id="fba2a-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="fba2a-125">Alert.ReadWrite</span></span> | <span data-ttu-id="fba2a-126">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="fba2a-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="fba2a-127">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="fba2a-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="fba2a-128">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="fba2a-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="fba2a-129">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="fba2a-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="fba2a-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="fba2a-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="fba2a-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="fba2a-131">Request headers</span></span>

<span data-ttu-id="fba2a-132">Namn</span><span class="sxs-lookup"><span data-stu-id="fba2a-132">Name</span></span> | <span data-ttu-id="fba2a-133">Skriv</span><span class="sxs-lookup"><span data-stu-id="fba2a-133">Type</span></span> | <span data-ttu-id="fba2a-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fba2a-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="fba2a-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="fba2a-135">Authorization</span></span> | <span data-ttu-id="fba2a-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="fba2a-136">String</span></span> | <span data-ttu-id="fba2a-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="fba2a-137">Bearer {token}.</span></span> <span data-ttu-id="fba2a-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="fba2a-138">**Required**.</span></span>
<span data-ttu-id="fba2a-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="fba2a-139">Content-Type</span></span> | <span data-ttu-id="fba2a-140">sträng</span><span class="sxs-lookup"><span data-stu-id="fba2a-140">string</span></span> | <span data-ttu-id="fba2a-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="fba2a-141">application/json.</span></span> <span data-ttu-id="fba2a-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="fba2a-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="fba2a-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="fba2a-143">Request body</span></span>
<span data-ttu-id="fba2a-144">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="fba2a-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="fba2a-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="fba2a-145">Parameter</span></span> | <span data-ttu-id="fba2a-146">Skriv</span><span class="sxs-lookup"><span data-stu-id="fba2a-146">Type</span></span>    | <span data-ttu-id="fba2a-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fba2a-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="fba2a-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="fba2a-148">Comment</span></span> |   <span data-ttu-id="fba2a-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="fba2a-149">String</span></span> |    <span data-ttu-id="fba2a-150">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="fba2a-150">Comment to associate with the action.</span></span> <span data-ttu-id="fba2a-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="fba2a-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="fba2a-152">Svar</span><span class="sxs-lookup"><span data-stu-id="fba2a-152">Response</span></span>
<span data-ttu-id="fba2a-153">Om det lyckas returnerar den här metoden 201 – Skapad svarskod och [undersökning](investigation.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="fba2a-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="fba2a-154">Exempel</span><span class="sxs-lookup"><span data-stu-id="fba2a-154">Example</span></span>

<span data-ttu-id="fba2a-155">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="fba2a-155">**Request**</span></span>

<span data-ttu-id="fba2a-156">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="fba2a-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
