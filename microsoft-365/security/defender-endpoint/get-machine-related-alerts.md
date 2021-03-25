---
title: API för datorrelaterade aviseringar
description: Lär dig hur du använder API:t för att hämta maskinrelaterade aviseringar för att hämta alla aviseringar som rör en viss enhet i Microsoft Defender för Slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, enheter, relaterade, aviseringar
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 837643bf5793437380a6f33c0eeca55ccef2100b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199257"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="56ca0-104">API för datorrelaterade aviseringar</span><span class="sxs-lookup"><span data-stu-id="56ca0-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56ca0-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="56ca0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="56ca0-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="56ca0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="56ca0-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="56ca0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="56ca0-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="56ca0-108">API description</span></span>
<span data-ttu-id="56ca0-109">Hämtar alla aviseringar [som](alerts.md) är relaterade till en viss enhet.</span><span class="sxs-lookup"><span data-stu-id="56ca0-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="56ca0-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="56ca0-110">Limitations</span></span>
1. <span data-ttu-id="56ca0-111">Du kan fråga på enheter som senast uppdaterades enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="56ca0-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="56ca0-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="56ca0-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="56ca0-113">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="56ca0-113">Permission type</span></span> |   <span data-ttu-id="56ca0-114">Behörighet</span><span class="sxs-lookup"><span data-stu-id="56ca0-114">Permission</span></span>  |   <span data-ttu-id="56ca0-115">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="56ca0-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="56ca0-116">Program</span><span class="sxs-lookup"><span data-stu-id="56ca0-116">Application</span></span> |   <span data-ttu-id="56ca0-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="56ca0-117">Alert.Read.All</span></span> |    <span data-ttu-id="56ca0-118">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="56ca0-118">'Read all alerts'</span></span>
<span data-ttu-id="56ca0-119">Program</span><span class="sxs-lookup"><span data-stu-id="56ca0-119">Application</span></span> |   <span data-ttu-id="56ca0-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="56ca0-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="56ca0-121">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="56ca0-121">'Read and write all alerts'</span></span>
<span data-ttu-id="56ca0-122">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="56ca0-122">Delegated (work or school account)</span></span> | <span data-ttu-id="56ca0-123">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="56ca0-123">Alert.Read</span></span> | <span data-ttu-id="56ca0-124">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="56ca0-124">'Read alerts'</span></span>
<span data-ttu-id="56ca0-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="56ca0-125">Delegated (work or school account)</span></span> | <span data-ttu-id="56ca0-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="56ca0-126">Alert.ReadWrite</span></span> | <span data-ttu-id="56ca0-127">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="56ca0-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="56ca0-128">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="56ca0-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="56ca0-129">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="56ca0-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="56ca0-130">Användaren måste ha åtkomst till enheten baserat på enhetsgruppinställningar (mer information finns i [Skapa och](machine-groups.md) hantera enhetsgrupper)</span><span class="sxs-lookup"><span data-stu-id="56ca0-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="56ca0-131">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="56ca0-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="56ca0-132">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="56ca0-132">Request headers</span></span>

<span data-ttu-id="56ca0-133">Namn</span><span class="sxs-lookup"><span data-stu-id="56ca0-133">Name</span></span> | <span data-ttu-id="56ca0-134">Skriv</span><span class="sxs-lookup"><span data-stu-id="56ca0-134">Type</span></span> | <span data-ttu-id="56ca0-135">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="56ca0-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="56ca0-136">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="56ca0-136">Authorization</span></span> | <span data-ttu-id="56ca0-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="56ca0-137">String</span></span> | <span data-ttu-id="56ca0-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="56ca0-138">Bearer {token}.</span></span> <span data-ttu-id="56ca0-139">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="56ca0-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="56ca0-140">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="56ca0-140">Request body</span></span>
<span data-ttu-id="56ca0-141">Tom</span><span class="sxs-lookup"><span data-stu-id="56ca0-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="56ca0-142">Svar</span><span class="sxs-lookup"><span data-stu-id="56ca0-142">Response</span></span>
<span data-ttu-id="56ca0-143">Om det fungerar och det finns en enhet – 200 OK med en lista [över aviseringsenheter](alerts.md) i brödtexten.</span><span class="sxs-lookup"><span data-stu-id="56ca0-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="56ca0-144">Om enheten inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="56ca0-144">If device was not found - 404 Not Found.</span></span>
