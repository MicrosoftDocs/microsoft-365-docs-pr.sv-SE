---
title: Tilldela enhetsvärde – hantering av hot och sårbarhet
description: Lär dig hur du tilldelar ett lågt, normalt eller högt värde till en enhet så att du kan skilja mellan resursprioriteringar.
keywords: Microsoft Defender för Endpoint-enhetsvärdet, enhetsvärdet för hot och sårbarhetshanteringsenheter, enheter med höga värden, exponeringsresultat för enhetsvärden
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935203"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="6a5a1-104">Tilldela enhetsvärde – hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="6a5a1-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a5a1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6a5a1-105">**Applies to:**</span></span>

- [<span data-ttu-id="6a5a1-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a5a1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6a5a1-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="6a5a1-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6a5a1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a5a1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6a5a1-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6a5a1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6a5a1-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6a5a1-111">Genom att definiera en enhets värde kan du skilja på resursprioriteringar.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="6a5a1-112">Enhetsvärdet används för att införliva en enskild tillgångs riskdekans i beräkningen av exponeringsresultatet för hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="6a5a1-113">Enheter som tilldelas som "höga värden" får större vikt.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="6a5a1-114">Du kan också använda [API:t för enhetsvärde.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="6a5a1-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="6a5a1-115">Alternativ för enhetsvärde:</span><span class="sxs-lookup"><span data-stu-id="6a5a1-115">Device value options:</span></span>

- <span data-ttu-id="6a5a1-116">Låg</span><span class="sxs-lookup"><span data-stu-id="6a5a1-116">Low</span></span>
- <span data-ttu-id="6a5a1-117">Normal (standard)</span><span class="sxs-lookup"><span data-stu-id="6a5a1-117">Normal (Default)</span></span>
- <span data-ttu-id="6a5a1-118">Hög</span><span class="sxs-lookup"><span data-stu-id="6a5a1-118">High</span></span>

<span data-ttu-id="6a5a1-119">Exempel på enheter som bör tilldelas ett högt värde:</span><span class="sxs-lookup"><span data-stu-id="6a5a1-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="6a5a1-120">Domänkontrollanter, Active Directory</span><span class="sxs-lookup"><span data-stu-id="6a5a1-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="6a5a1-121">Internet-enheter</span><span class="sxs-lookup"><span data-stu-id="6a5a1-121">Internet facing devices</span></span>
- <span data-ttu-id="6a5a1-122">VIP-enheter</span><span class="sxs-lookup"><span data-stu-id="6a5a1-122">VIP devices</span></span>
- <span data-ttu-id="6a5a1-123">Enheter som fungerar som värd för interna/externa produktionstjänster</span><span class="sxs-lookup"><span data-stu-id="6a5a1-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="6a5a1-124">Välj enhetsvärde</span><span class="sxs-lookup"><span data-stu-id="6a5a1-124">Choose device value</span></span>

1. <span data-ttu-id="6a5a1-125">Gå till valfri enhetssida, den enklaste platsen är från enhetsinventeringen.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="6a5a1-126">Välj **Enhetsvärde** från tre punkter bredvid åtgärdsfältet högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Exempel på listrutan för enhetsvärde.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="6a5a1-128">En utfäll kan visas med enhetens aktuella värde och vad det innebär.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="6a5a1-129">Granska enhetens värde och välj det som passar bäst för din enhet.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="6a5a1-130">![Exempel på utfällvärde för enheten.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="6a5a1-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="6a5a1-131">Hur enhetsvärde påverkar exponeringsresultatet</span><span class="sxs-lookup"><span data-stu-id="6a5a1-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="6a5a1-132">Exponeringsresultatet är ett viktat medelvärde för alla enheter.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="6a5a1-133">Om du har enhetsgrupper kan du också filtrera poängen efter enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="6a5a1-134">Normal enheter har en vikt på 1</span><span class="sxs-lookup"><span data-stu-id="6a5a1-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="6a5a1-135">Enheter med låg värde har en vikt på 0,75</span><span class="sxs-lookup"><span data-stu-id="6a5a1-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="6a5a1-136">Enheter med höga värden har vikten NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="6a5a1-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="6a5a1-137">Om du har 100 enheter har varje enhet med höga värden 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="6a5a1-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a5a1-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6a5a1-138">Related topics</span></span>

- [<span data-ttu-id="6a5a1-139">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="6a5a1-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="6a5a1-140">Exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="6a5a1-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="6a5a1-141">API:er</span><span class="sxs-lookup"><span data-stu-id="6a5a1-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)