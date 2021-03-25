---
title: Skaffa API för domänrelaterade aviseringar
description: Lär dig hur du använder API:t för att hämta domänrelaterade aviseringar för att hämta aviseringar relaterade till en viss domänadress i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, domän, relaterade, aviseringar
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166869"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="b0e36-104">Skaffa API för domänrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="b0e36-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0e36-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b0e36-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0e36-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0e36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0e36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0e36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0e36-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b0e36-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b0e36-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b0e36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="b0e36-110">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="b0e36-110">API description</span></span>
<span data-ttu-id="b0e36-111">Hämtar en samling aviseringar [som är](alerts.md) relaterade till en viss domänadress.</span><span class="sxs-lookup"><span data-stu-id="b0e36-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="b0e36-112">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="b0e36-112">Limitations</span></span>
1. <span data-ttu-id="b0e36-113">Du kan fråga efter aviseringar som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="b0e36-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="b0e36-114">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="b0e36-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b0e36-115">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="b0e36-115">Permissions</span></span>
<span data-ttu-id="b0e36-116">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="b0e36-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b0e36-117">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b0e36-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b0e36-118">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="b0e36-118">Permission type</span></span> |   <span data-ttu-id="b0e36-119">Behörighet</span><span class="sxs-lookup"><span data-stu-id="b0e36-119">Permission</span></span>  |   <span data-ttu-id="b0e36-120">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="b0e36-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b0e36-121">Program</span><span class="sxs-lookup"><span data-stu-id="b0e36-121">Application</span></span> |   <span data-ttu-id="b0e36-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="b0e36-122">Alert.Read.All</span></span> |    <span data-ttu-id="b0e36-123">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="b0e36-123">'Read all alerts'</span></span>
<span data-ttu-id="b0e36-124">Program</span><span class="sxs-lookup"><span data-stu-id="b0e36-124">Application</span></span> |   <span data-ttu-id="b0e36-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b0e36-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="b0e36-126">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="b0e36-126">'Read and write all alerts'</span></span>
<span data-ttu-id="b0e36-127">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b0e36-127">Delegated (work or school account)</span></span> | <span data-ttu-id="b0e36-128">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="b0e36-128">Alert.Read</span></span> | <span data-ttu-id="b0e36-129">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="b0e36-129">'Read alerts'</span></span>
<span data-ttu-id="b0e36-130">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="b0e36-130">Delegated (work or school account)</span></span> | <span data-ttu-id="b0e36-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b0e36-131">Alert.ReadWrite</span></span> | <span data-ttu-id="b0e36-132">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="b0e36-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="b0e36-133">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="b0e36-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="b0e36-134">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="b0e36-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b0e36-135">Svaret inkluderar endast aviseringar, som associeras med enheter, som användaren har [](machine-groups.md) åtkomst till, baserat på enhetsgruppsinställningar (mer information finns i Skapa och hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="b0e36-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b0e36-136">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="b0e36-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="b0e36-137">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="b0e36-137">Request headers</span></span>

| <span data-ttu-id="b0e36-138">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="b0e36-138">Header</span></span>        | <span data-ttu-id="b0e36-139">Value</span><span class="sxs-lookup"><span data-stu-id="b0e36-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="b0e36-140">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="b0e36-140">Authorization</span></span> | <span data-ttu-id="b0e36-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="b0e36-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="b0e36-142">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="b0e36-142">Request body</span></span>
<span data-ttu-id="b0e36-143">Tom</span><span class="sxs-lookup"><span data-stu-id="b0e36-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b0e36-144">Svar</span><span class="sxs-lookup"><span data-stu-id="b0e36-144">Response</span></span>
<span data-ttu-id="b0e36-145">Om det lyckas och domänen finns – 200 OK med lista över [aviseringsenheter.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="b0e36-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="b0e36-146">Om domänen inte finns – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="b0e36-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="b0e36-147">Exempel</span><span class="sxs-lookup"><span data-stu-id="b0e36-147">Example</span></span>

<span data-ttu-id="b0e36-148">**Begäran**</span><span class="sxs-lookup"><span data-stu-id="b0e36-148">**Request**</span></span>

<span data-ttu-id="b0e36-149">Här är ett exempel på begäran.</span><span class="sxs-lookup"><span data-stu-id="b0e36-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
