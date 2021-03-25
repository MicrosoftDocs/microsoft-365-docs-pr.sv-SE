---
title: Få aviseringsinformation genom ID API
description: Lär dig hur du använder hämta aviseringsinformation genom ID API för att hämta en specifik avisering med dess ID i Microsoft Defender för slutpunkt.
keywords: apis, graph api, API som stöds, skaffa, avisering, information, id
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
ms.openlocfilehash: f9130b054ccea762e6c5cc4f2952bbfa82d24b83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200431"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="3dcf0-104">Få aviseringsinformation genom ID API</span><span class="sxs-lookup"><span data-stu-id="3dcf0-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3dcf0-105">**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="3dcf0-106">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3dcf0-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dcf0-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3dcf0-108">API-beskrivning</span><span class="sxs-lookup"><span data-stu-id="3dcf0-108">API description</span></span>
<span data-ttu-id="3dcf0-109">Hämtar en specifik [avisering](alerts.md) med hjälp av dess ID.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="3dcf0-110">Begränsningar</span><span class="sxs-lookup"><span data-stu-id="3dcf0-110">Limitations</span></span>
1. <span data-ttu-id="3dcf0-111">Du kan få aviseringar som senast uppdaterats enligt din konfigurerade lagringstid.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3dcf0-112">Prisbegränsningar för detta API är 100 samtal per minut och 1 500 samtal per timme.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3dcf0-113">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="3dcf0-113">Permissions</span></span>
<span data-ttu-id="3dcf0-114">En av följande behörigheter krävs för att anropa detta API.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3dcf0-115">Mer information, inklusive hur du väljer behörigheter, finns i Använda [Microsoft Defender för slutpunkts-API:er](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3dcf0-116">Behörighetstyp</span><span class="sxs-lookup"><span data-stu-id="3dcf0-116">Permission type</span></span> |   <span data-ttu-id="3dcf0-117">Behörighet</span><span class="sxs-lookup"><span data-stu-id="3dcf0-117">Permission</span></span>  |   <span data-ttu-id="3dcf0-118">Visningsnamn för behörighet</span><span class="sxs-lookup"><span data-stu-id="3dcf0-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3dcf0-119">Program</span><span class="sxs-lookup"><span data-stu-id="3dcf0-119">Application</span></span> |   <span data-ttu-id="3dcf0-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="3dcf0-120">Alert.Read.All</span></span> |    <span data-ttu-id="3dcf0-121">"Läs alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="3dcf0-121">'Read all alerts'</span></span>
<span data-ttu-id="3dcf0-122">Program</span><span class="sxs-lookup"><span data-stu-id="3dcf0-122">Application</span></span> |   <span data-ttu-id="3dcf0-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="3dcf0-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="3dcf0-124">"Läs och skriv alla aviseringar"</span><span class="sxs-lookup"><span data-stu-id="3dcf0-124">'Read and write all alerts'</span></span>
<span data-ttu-id="3dcf0-125">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-125">Delegated (work or school account)</span></span> | <span data-ttu-id="3dcf0-126">Avisering.Läsa</span><span class="sxs-lookup"><span data-stu-id="3dcf0-126">Alert.Read</span></span> | <span data-ttu-id="3dcf0-127">Läsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3dcf0-127">'Read alerts'</span></span>
<span data-ttu-id="3dcf0-128">Delegerat (arbets- eller skolkonto)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-128">Delegated (work or school account)</span></span> | <span data-ttu-id="3dcf0-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="3dcf0-129">Alert.ReadWrite</span></span> | <span data-ttu-id="3dcf0-130">"Aviseringar om läsning och skrivning"</span><span class="sxs-lookup"><span data-stu-id="3dcf0-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="3dcf0-131">När du skaffar en token med hjälp av användarautentiseringsuppgifter:</span><span class="sxs-lookup"><span data-stu-id="3dcf0-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3dcf0-132">Användaren måste ha minst följande rollbehörighet: 'Visa data' (mer information finns i [Skapa och](user-roles.md) hantera roller)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3dcf0-133">Användaren måste ha åtkomst till enheten som är kopplad till aviseringen, baserat på enhetsgruppinställningar (mer information finns i Skapa och hantera enhetsgrupper) [](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="3dcf0-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3dcf0-134">HTTP-begäran</span><span class="sxs-lookup"><span data-stu-id="3dcf0-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="3dcf0-135">Begäran om rubriker</span><span class="sxs-lookup"><span data-stu-id="3dcf0-135">Request headers</span></span>

<span data-ttu-id="3dcf0-136">Namn</span><span class="sxs-lookup"><span data-stu-id="3dcf0-136">Name</span></span> | <span data-ttu-id="3dcf0-137">Skriv</span><span class="sxs-lookup"><span data-stu-id="3dcf0-137">Type</span></span> | <span data-ttu-id="3dcf0-138">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3dcf0-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="3dcf0-139">Auktorisering</span><span class="sxs-lookup"><span data-stu-id="3dcf0-139">Authorization</span></span> | <span data-ttu-id="3dcf0-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="3dcf0-140">String</span></span> | <span data-ttu-id="3dcf0-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-141">Bearer {token}.</span></span> <span data-ttu-id="3dcf0-142">**Obligatoriskt.**</span><span class="sxs-lookup"><span data-stu-id="3dcf0-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3dcf0-143">Begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="3dcf0-143">Request body</span></span>
<span data-ttu-id="3dcf0-144">Tom</span><span class="sxs-lookup"><span data-stu-id="3dcf0-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3dcf0-145">Svar</span><span class="sxs-lookup"><span data-stu-id="3dcf0-145">Response</span></span>
<span data-ttu-id="3dcf0-146">Om det lyckas returnerar den här metoden 200 OK och [aviseringsentitet](alerts.md) i svarstexten.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="3dcf0-147">Om aviseringen med det angivna ID:t inte hittades – 404 Hittades inte.</span><span class="sxs-lookup"><span data-stu-id="3dcf0-147">If alert with the specified id was not found - 404 Not Found.</span></span>
