---
title: Ange enhetsvärde-API
description: Lär dig hur du anger värdet på en enhet med hjälp av Microsoft Defender för Endpoint API.
keywords: apis, graph api, API som stöds, taggar, maskintaggar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 33692ddf62153c0a6aa8f84568d69803af113bc6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185569"
---
# <a name="set-device-value-api"></a><span data-ttu-id="3af85-104">Ange enhetsvärde-API</span><span class="sxs-lookup"><span data-stu-id="3af85-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3af85-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3af85-105">**Applies to:**</span></span>
- [<span data-ttu-id="3af85-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3af85-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3af85-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3af85-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3af85-108">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3af85-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="3af85-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3af85-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3af85-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3af85-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3af85-111">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="3af85-111">API description</span></span>

<span data-ttu-id="3af85-112">Ange enhetsvärdet för en viss [dator.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="3af85-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="3af85-113">Mer information [finns i Tilldela](tvm-assign-device-value.md) enhetsvärden.</span><span class="sxs-lookup"><span data-stu-id="3af85-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="3af85-114">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="3af85-114">Limitations</span></span>

1. <span data-ttu-id="3af85-115">Du kan publicera på enheter som senast sågs enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="3af85-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="3af85-116">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="3af85-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3af85-117">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3af85-117">Permissions</span></span>

<span data-ttu-id="3af85-118">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="3af85-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3af85-119">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3af85-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3af85-120">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3af85-120">Permission type</span></span> |    <span data-ttu-id="3af85-121">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3af85-121">Permission</span></span>    |    <span data-ttu-id="3af85-122">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3af85-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3af85-123">Program</span><span class="sxs-lookup"><span data-stu-id="3af85-123">Application</span></span> |    <span data-ttu-id="3af85-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3af85-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="3af85-125">"Läsa och skriva all maskininformation"</span><span class="sxs-lookup"><span data-stu-id="3af85-125">'Read and write all machine information'</span></span>
<span data-ttu-id="3af85-126">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3af85-126">Delegated (work or school account)</span></span> | <span data-ttu-id="3af85-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3af85-127">Machine.ReadWrite</span></span> | <span data-ttu-id="3af85-128">Maskininformation för läsning och skrivning</span><span class="sxs-lookup"><span data-stu-id="3af85-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="3af85-129">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="3af85-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="3af85-130">Användaren måste ha minst följande rollbehörighet: "Hantera säkerhetsinställning".</span><span class="sxs-lookup"><span data-stu-id="3af85-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="3af85-131">Mer information finns i [Skapa och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="3af85-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3af85-132">Användaren måste ha åtkomst till datorn baserat på datorns gruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera datorgrupper)</span><span class="sxs-lookup"><span data-stu-id="3af85-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3af85-133">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3af85-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="3af85-134">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="3af85-134">Request headers</span></span>

<span data-ttu-id="3af85-135">Namn</span><span class="sxs-lookup"><span data-stu-id="3af85-135">Name</span></span> | <span data-ttu-id="3af85-136">Skriv</span><span class="sxs-lookup"><span data-stu-id="3af85-136">Type</span></span> | <span data-ttu-id="3af85-137">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3af85-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="3af85-138">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3af85-138">Authorization</span></span> | <span data-ttu-id="3af85-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="3af85-139">String</span></span> | <span data-ttu-id="3af85-140">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3af85-140">Bearer {token}.</span></span> <span data-ttu-id="3af85-141">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3af85-141">**Required**.</span></span>
<span data-ttu-id="3af85-142">Innehållstyp</span><span class="sxs-lookup"><span data-stu-id="3af85-142">Content-Type</span></span> | <span data-ttu-id="3af85-143">sträng</span><span class="sxs-lookup"><span data-stu-id="3af85-143">string</span></span> | <span data-ttu-id="3af85-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="3af85-144">application/json.</span></span> <span data-ttu-id="3af85-145">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3af85-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="3af85-146">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="3af85-146">Request body</span></span>

<span data-ttu-id="3af85-147">Ange följande parametrar för ett JSON-objekt i begärans brödtext:</span><span class="sxs-lookup"><span data-stu-id="3af85-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="3af85-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="3af85-148">Parameter</span></span> |    <span data-ttu-id="3af85-149">Skriv</span><span class="sxs-lookup"><span data-stu-id="3af85-149">Type</span></span>    | <span data-ttu-id="3af85-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3af85-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="3af85-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="3af85-151">DeviceValue</span></span> |    <span data-ttu-id="3af85-152">Uppräkning</span><span class="sxs-lookup"><span data-stu-id="3af85-152">Enum</span></span> |    <span data-ttu-id="3af85-153">Enhetsvärde.</span><span class="sxs-lookup"><span data-stu-id="3af85-153">Device value.</span></span> <span data-ttu-id="3af85-154">Tillåtna värden är: "Normal", "Låg" och "Hög".</span><span class="sxs-lookup"><span data-stu-id="3af85-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="3af85-155">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3af85-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="3af85-156">Svar</span><span class="sxs-lookup"><span data-stu-id="3af85-156">Response</span></span>

<span data-ttu-id="3af85-157">Om svaret lyckas returnerar den här metoden 200 – OK-svarskod och den uppdaterade datorn i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="3af85-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="3af85-158">Exempel</span><span class="sxs-lookup"><span data-stu-id="3af85-158">Example</span></span>

<span data-ttu-id="3af85-159">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="3af85-159">**Request**</span></span>

<span data-ttu-id="3af85-160">Här är ett exempel på en begäran som lägger till en maskintagg.</span><span class="sxs-lookup"><span data-stu-id="3af85-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
