---
title: Tilldela enhetsvärde – hantering av hot och sårbarhet
description: Lär dig hur du tilldelar ett lågt, normalt eller högt värde till en enhet så att du kan skilja mellan resursprioriteringar.
keywords: Microsoft Defender för endpoint device value, threat and vulnerability management device value, high value devices, device value exposure score
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
ms.openlocfilehash: 1f5d90190418f84795bdd899ea0e48ac25831a96
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689395"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="eec79-104">Tilldela enhetsvärde – hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="eec79-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eec79-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="eec79-105">**Applies to:**</span></span>

- [<span data-ttu-id="eec79-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="eec79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="eec79-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="eec79-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="eec79-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eec79-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eec79-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="eec79-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eec79-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="eec79-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="eec79-111">Genom att definiera en enhets värde kan du skilja på resursprioriteringar.</span><span class="sxs-lookup"><span data-stu-id="eec79-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="eec79-112">Enhetsvärdet används för att införliva en enskild tillgångs riskdekans i beräkningen av exponeringsresultatet för hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="eec79-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="eec79-113">Enheter som tilldelas som "höga värden" får större vikt.</span><span class="sxs-lookup"><span data-stu-id="eec79-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="eec79-114">Du kan också använda [API:t för enhetsvärde.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="eec79-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="eec79-115">Alternativ för enhetsvärde:</span><span class="sxs-lookup"><span data-stu-id="eec79-115">Device value options:</span></span>

- <span data-ttu-id="eec79-116">Låg</span><span class="sxs-lookup"><span data-stu-id="eec79-116">Low</span></span>
- <span data-ttu-id="eec79-117">Normal (standard)</span><span class="sxs-lookup"><span data-stu-id="eec79-117">Normal (Default)</span></span>
- <span data-ttu-id="eec79-118">Högsta</span><span class="sxs-lookup"><span data-stu-id="eec79-118">High</span></span>

<span data-ttu-id="eec79-119">Exempel på enheter som bör tilldelas ett högt värde:</span><span class="sxs-lookup"><span data-stu-id="eec79-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="eec79-120">Domänkontrollanter, Active Directory</span><span class="sxs-lookup"><span data-stu-id="eec79-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="eec79-121">Internet-enheter</span><span class="sxs-lookup"><span data-stu-id="eec79-121">Internet facing devices</span></span>
- <span data-ttu-id="eec79-122">VIP-enheter</span><span class="sxs-lookup"><span data-stu-id="eec79-122">VIP devices</span></span>
- <span data-ttu-id="eec79-123">Enheter som fungerar som värd för interna/externa produktionstjänster</span><span class="sxs-lookup"><span data-stu-id="eec79-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="eec79-124">Välj enhetsvärde</span><span class="sxs-lookup"><span data-stu-id="eec79-124">Choose device value</span></span>

1. <span data-ttu-id="eec79-125">Gå till valfri enhetssida, den enklaste platsen är från enhetsinventeringen.</span><span class="sxs-lookup"><span data-stu-id="eec79-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="eec79-126">Välj **Enhetsvärde** från tre punkter bredvid åtgärdsfältet högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="eec79-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Exempel på listrutan för enhetsvärde.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="eec79-128">En utfäll kan visas med enhetens aktuella värde och vad det innebär.</span><span class="sxs-lookup"><span data-stu-id="eec79-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="eec79-129">Granska enhetens värde och välj det som passar bäst för din enhet.</span><span class="sxs-lookup"><span data-stu-id="eec79-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="eec79-130">![Exempel på utfällvärde för enheten.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="eec79-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="eec79-131">Hur enhetsvärde påverkar exponeringsresultatet</span><span class="sxs-lookup"><span data-stu-id="eec79-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="eec79-132">Exponeringsresultatet är ett viktat medelvärde för alla enheter.</span><span class="sxs-lookup"><span data-stu-id="eec79-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="eec79-133">Om du har enhetsgrupper kan du också filtrera poängen efter enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="eec79-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="eec79-134">Normal enheter har en vikt på 1</span><span class="sxs-lookup"><span data-stu-id="eec79-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="eec79-135">Enheter med låg värde har en vikt på 0,75</span><span class="sxs-lookup"><span data-stu-id="eec79-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="eec79-136">Enheter med höga värden har vikten NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="eec79-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="eec79-137">Om du har 100 enheter har varje enhet med höga värden 10 (100/10)</span><span class="sxs-lookup"><span data-stu-id="eec79-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="eec79-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="eec79-138">Related topics</span></span>

- [<span data-ttu-id="eec79-139">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="eec79-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="eec79-140">Exponeringsresultat</span><span class="sxs-lookup"><span data-stu-id="eec79-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="eec79-141">API:er</span><span class="sxs-lookup"><span data-stu-id="eec79-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)