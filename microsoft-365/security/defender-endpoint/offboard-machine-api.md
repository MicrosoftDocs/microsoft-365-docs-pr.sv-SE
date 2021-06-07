---
title: Api för Offboard-dator
description: Lär dig hur du använder ett API för att ta bort en enhet från Microsoft Defender för Endpoint.
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
ms.openlocfilehash: e2b1114cd091c9cd42aa8e4525416f9d73358a65
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771999"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="5d960-104">Api för Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="5d960-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d960-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5d960-105">**Applies to:**</span></span>
- [<span data-ttu-id="5d960-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5d960-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5d960-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d960-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5d960-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5d960-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5d960-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5d960-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5d960-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="5d960-110">API description</span></span>
<span data-ttu-id="5d960-111">Offboard-enhet från Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="5d960-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="5d960-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="5d960-112">Limitations</span></span>
 - <span data-ttu-id="5d960-113">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="5d960-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="5d960-114">Detta API stöds i Windows 10, version 1703 och senare, eller i Windows Server 2019 och senare.</span><span class="sxs-lookup"><span data-stu-id="5d960-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="5d960-115">Detta API stöds inte på MacOS- eller Linux-enheter.</span><span class="sxs-lookup"><span data-stu-id="5d960-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="5d960-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="5d960-116">Permissions</span></span>
<span data-ttu-id="5d960-117">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="5d960-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5d960-118">Mer information, inklusive hur du väljer behörigheter, finns i [Använda Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5d960-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5d960-119">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="5d960-119">Permission type</span></span> |   <span data-ttu-id="5d960-120">Behörighet</span><span class="sxs-lookup"><span data-stu-id="5d960-120">Permission</span></span>  |   <span data-ttu-id="5d960-121">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="5d960-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5d960-122">Program</span><span class="sxs-lookup"><span data-stu-id="5d960-122">Application</span></span> |   <span data-ttu-id="5d960-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="5d960-123">Machine.Offboard</span></span> |  <span data-ttu-id="5d960-124">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="5d960-124">'Offboard machine'</span></span>
<span data-ttu-id="5d960-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="5d960-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="5d960-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="5d960-126">Machine.Offboard</span></span> |  <span data-ttu-id="5d960-127">'Offboard machine'</span><span class="sxs-lookup"><span data-stu-id="5d960-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="5d960-128">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="5d960-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5d960-129">Användaren måste ha AD-roll som global administratör</span><span class="sxs-lookup"><span data-stu-id="5d960-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="5d960-130">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="5d960-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5d960-131">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="5d960-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="5d960-132">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="5d960-132">Request headers</span></span>

<span data-ttu-id="5d960-133">Namn</span><span class="sxs-lookup"><span data-stu-id="5d960-133">Name</span></span> | <span data-ttu-id="5d960-134">Typ</span><span class="sxs-lookup"><span data-stu-id="5d960-134">Type</span></span> | <span data-ttu-id="5d960-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5d960-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="5d960-136">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="5d960-136">Authorization</span></span> | <span data-ttu-id="5d960-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="5d960-137">String</span></span> | <span data-ttu-id="5d960-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5d960-138">Bearer {token}.</span></span> <span data-ttu-id="5d960-139">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5d960-139">**Required**.</span></span>
<span data-ttu-id="5d960-140">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="5d960-140">Content-Type</span></span> | <span data-ttu-id="5d960-141">sträng</span><span class="sxs-lookup"><span data-stu-id="5d960-141">string</span></span> | <span data-ttu-id="5d960-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="5d960-142">application/json.</span></span> <span data-ttu-id="5d960-143">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5d960-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5d960-144">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="5d960-144">Request body</span></span>
<span data-ttu-id="5d960-145">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="5d960-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5d960-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d960-146">Parameter</span></span> | <span data-ttu-id="5d960-147">Typ</span><span class="sxs-lookup"><span data-stu-id="5d960-147">Type</span></span>    | <span data-ttu-id="5d960-148">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="5d960-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="5d960-149">Kommentar</span><span class="sxs-lookup"><span data-stu-id="5d960-149">Comment</span></span> |   <span data-ttu-id="5d960-150">Sträng</span><span class="sxs-lookup"><span data-stu-id="5d960-150">String</span></span> |    <span data-ttu-id="5d960-151">Kommentar som ska associeras med åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5d960-151">Comment to associate with the action.</span></span> <span data-ttu-id="5d960-152">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="5d960-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="5d960-153">Svar</span><span class="sxs-lookup"><span data-stu-id="5d960-153">Response</span></span>
<span data-ttu-id="5d960-154">Om det lyckas returnerar den här metoden 201 – Skapad svarskod [och Maskinåtgärd](machineaction.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="5d960-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="5d960-155">Exempel</span><span class="sxs-lookup"><span data-stu-id="5d960-155">Example</span></span>

<span data-ttu-id="5d960-156">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="5d960-156">**Request**</span></span>

<span data-ttu-id="5d960-157">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="5d960-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
