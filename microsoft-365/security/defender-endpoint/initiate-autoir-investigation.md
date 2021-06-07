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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770895"
---
# <a name="start-investigation-api"></a><span data-ttu-id="089e7-104">API för starta undersökning</span><span class="sxs-lookup"><span data-stu-id="089e7-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="089e7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="089e7-105">**Applies to:**</span></span>
- [<span data-ttu-id="089e7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="089e7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="089e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="089e7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="089e7-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="089e7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="089e7-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="089e7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="089e7-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="089e7-110">API description</span></span>
<span data-ttu-id="089e7-111">Starta automatisk undersökning på en enhet.</span><span class="sxs-lookup"><span data-stu-id="089e7-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="089e7-112">Mer information [finns i Översikt över](automated-investigations.md) automatiserade undersökningar.</span><span class="sxs-lookup"><span data-stu-id="089e7-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="089e7-113">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="089e7-113">Limitations</span></span>
1. <span data-ttu-id="089e7-114">Prisbegränsningar för detta API är 50 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="089e7-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="089e7-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="089e7-115">Permissions</span></span>
<span data-ttu-id="089e7-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="089e7-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="089e7-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="089e7-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="089e7-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="089e7-118">Permission type</span></span> |   <span data-ttu-id="089e7-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="089e7-119">Permission</span></span>  |   <span data-ttu-id="089e7-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="089e7-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="089e7-121">Program</span><span class="sxs-lookup"><span data-stu-id="089e7-121">Application</span></span> |   <span data-ttu-id="089e7-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="089e7-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="089e7-123">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="089e7-123">'Read and write all alerts'</span></span>
<span data-ttu-id="089e7-124">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="089e7-124">Delegated (work or school account)</span></span> | <span data-ttu-id="089e7-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="089e7-125">Alert.ReadWrite</span></span> | <span data-ttu-id="089e7-126">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="089e7-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="089e7-127">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="089e7-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="089e7-128">Användaren måste ha minst följande rollbehörighet: 'Aktiva åtgärdsåtgärder'. [](user-roles.md) (Mer information finns i Skapa och hantera roller)</span><span class="sxs-lookup"><span data-stu-id="089e7-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="089e7-129">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="089e7-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="089e7-130">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="089e7-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="089e7-131">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="089e7-131">Request headers</span></span>

<span data-ttu-id="089e7-132">Namn</span><span class="sxs-lookup"><span data-stu-id="089e7-132">Name</span></span> | <span data-ttu-id="089e7-133">Typ</span><span class="sxs-lookup"><span data-stu-id="089e7-133">Type</span></span> | <span data-ttu-id="089e7-134">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="089e7-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="089e7-135">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="089e7-135">Authorization</span></span> | <span data-ttu-id="089e7-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="089e7-136">String</span></span> | <span data-ttu-id="089e7-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="089e7-137">Bearer {token}.</span></span> <span data-ttu-id="089e7-138">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="089e7-138">**Required**.</span></span>
<span data-ttu-id="089e7-139">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="089e7-139">Content-Type</span></span> | <span data-ttu-id="089e7-140">sträng</span><span class="sxs-lookup"><span data-stu-id="089e7-140">string</span></span> | <span data-ttu-id="089e7-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="089e7-141">application/json.</span></span> <span data-ttu-id="089e7-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="089e7-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="089e7-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="089e7-143">Request body</span></span>
<span data-ttu-id="089e7-144">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="089e7-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="089e7-145">Parameter</span><span class="sxs-lookup"><span data-stu-id="089e7-145">Parameter</span></span> | <span data-ttu-id="089e7-146">Typ</span><span class="sxs-lookup"><span data-stu-id="089e7-146">Type</span></span>    | <span data-ttu-id="089e7-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="089e7-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="089e7-148">Kommentar</span><span class="sxs-lookup"><span data-stu-id="089e7-148">Comment</span></span> |   <span data-ttu-id="089e7-149">Sträng</span><span class="sxs-lookup"><span data-stu-id="089e7-149">String</span></span> |    <span data-ttu-id="089e7-150">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="089e7-150">Comment to associate with the action.</span></span> <span data-ttu-id="089e7-151">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="089e7-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="089e7-152">Svar</span><span class="sxs-lookup"><span data-stu-id="089e7-152">Response</span></span>
<span data-ttu-id="089e7-153">Om det lyckas returnerar den här metoden 201 – Skapad svarskod och [undersökning](investigation.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="089e7-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="089e7-154">Exempel</span><span class="sxs-lookup"><span data-stu-id="089e7-154">Example</span></span>

<span data-ttu-id="089e7-155">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="089e7-155">**Request**</span></span>

<span data-ttu-id="089e7-156">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="089e7-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
