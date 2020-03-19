---
title: Reparationsåtgärder efter automatiserade undersökningar i Microsoft Threat Protection
description: Få en översikt över åtgärder för reparation som följer automatiserade undersökningar i Microsoft Threat Protection
keywords: automatiserad, utredning, alert, utlösa, åtgärder, sanering
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42808677"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="5eabf-104">Reparationsåtgärder efter automatiserade undersökningar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5eabf-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="5eabf-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="5eabf-105">**Applies to:**</span></span>
- <span data-ttu-id="5eabf-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="5eabf-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="5eabf-107">Åtgärder för reparation</span><span class="sxs-lookup"><span data-stu-id="5eabf-107">Remediation actions</span></span>

<span data-ttu-id="5eabf-108">Under och efter en automatisk undersökning i Microsoft Threat Protection identifieras reparationsåtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="5eabf-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="5eabf-109">Vissa typer av åtgärder för reparation vidtas på enheter, även kallade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="5eabf-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="5eabf-110">Andra åtgärder för reparation vidtas på e-postinnehåll.</span><span class="sxs-lookup"><span data-stu-id="5eabf-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="5eabf-111">Automatiserade undersökningar slutförs efter att reparationsåtgärder har vidtagits, godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="5eabf-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="5eabf-112">I följande tabell sammanfattas åtgärder för reparation som för närvarande stöds i Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="5eabf-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="5eabf-113">Åtgärdsåtgärder för enhet (slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="5eabf-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="5eabf-114">Åtgärder för reparation av e-post</span><span class="sxs-lookup"><span data-stu-id="5eabf-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="5eabf-115">Karantänfil</span><span class="sxs-lookup"><span data-stu-id="5eabf-115">Quarantine file</span></span><br/><span data-ttu-id="5eabf-116">Ta bort registernyckel</span><span class="sxs-lookup"><span data-stu-id="5eabf-116">Remove registry key</span></span><br/><span data-ttu-id="5eabf-117">Döda process</span><span class="sxs-lookup"><span data-stu-id="5eabf-117">Kill process</span></span> <br/><span data-ttu-id="5eabf-118">Stoppa tjänsten</span><span class="sxs-lookup"><span data-stu-id="5eabf-118">Stop service</span></span> <br/><span data-ttu-id="5eabf-119">Inaktivera drivrutin</span><span class="sxs-lookup"><span data-stu-id="5eabf-119">Disable driver</span></span> <br/><span data-ttu-id="5eabf-120">Ta bort schemalagd aktivitet</span><span class="sxs-lookup"><span data-stu-id="5eabf-120">Remove scheduled task</span></span>      |<span data-ttu-id="5eabf-121">E-postmeddelanden eller kluster för mjuk borttagning</span><span class="sxs-lookup"><span data-stu-id="5eabf-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="5eabf-122">Blockera URL (tid för klick)</span><span class="sxs-lookup"><span data-stu-id="5eabf-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="5eabf-123">Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="5eabf-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="5eabf-124">Reparationsåtgärder, oavsett om de väntar på godkännande eller redan är slutförda, kan visas i [Åtgärdscenter](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="5eabf-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="5eabf-125">Domar och resultat efter automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="5eabf-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="5eabf-126">När en automatiserad undersökning är klar, en dom nås för varje del av bevis inblandade, och saneringsåtgärder identifieras.</span><span class="sxs-lookup"><span data-stu-id="5eabf-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="5eabf-127">I vissa fall vidtas åtgärder för att åtgärda dem automatiskt. I andra fall väntar saneringsåtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="5eabf-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="5eabf-128">I följande tabell listas möjliga domar och resultat:</span><span class="sxs-lookup"><span data-stu-id="5eabf-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="5eabf-129">Dom</span><span class="sxs-lookup"><span data-stu-id="5eabf-129">Verdict</span></span>    |<span data-ttu-id="5eabf-130">Området</span><span class="sxs-lookup"><span data-stu-id="5eabf-130">Area</span></span>   |<span data-ttu-id="5eabf-131">Resultat</span><span class="sxs-lookup"><span data-stu-id="5eabf-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="5eabf-132">Skadlig</span><span class="sxs-lookup"><span data-stu-id="5eabf-132">Malicious</span></span>  |<span data-ttu-id="5eabf-133">Enheter (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="5eabf-133">Devices (endpoints)</span></span>    |<span data-ttu-id="5eabf-134">Reparationsåtgärder vidtas automatiskt</span><span class="sxs-lookup"><span data-stu-id="5eabf-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="5eabf-135">Skadlig</span><span class="sxs-lookup"><span data-stu-id="5eabf-135">Malicious</span></span>  |<span data-ttu-id="5eabf-136">E-postinnehåll (webbadresser eller bilagor)</span><span class="sxs-lookup"><span data-stu-id="5eabf-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="5eabf-137">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="5eabf-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="5eabf-138">Misstänkta</span><span class="sxs-lookup"><span data-stu-id="5eabf-138">Suspicious</span></span> |<span data-ttu-id="5eabf-139">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="5eabf-139">Devices or email content</span></span> |<span data-ttu-id="5eabf-140">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="5eabf-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="5eabf-141">Ren</span><span class="sxs-lookup"><span data-stu-id="5eabf-141">Clean</span></span>  |<span data-ttu-id="5eabf-142">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="5eabf-142">Devices or email content</span></span>   |<span data-ttu-id="5eabf-143">Inga saneringsåtgärder behövs</span><span class="sxs-lookup"><span data-stu-id="5eabf-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="5eabf-144">Granska en väntande åtgärd i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="5eabf-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="5eabf-145">Om du tror att något har missats eller felaktigt upptäckts av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta!</span><span class="sxs-lookup"><span data-stu-id="5eabf-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="5eabf-146">[Rapportera falska positiva identifieringar/negativ](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="5eabf-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="5eabf-147">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="5eabf-147">Next steps</span></span>

- [<span data-ttu-id="5eabf-148">Godkänna eller avvisa åtgärder</span><span class="sxs-lookup"><span data-stu-id="5eabf-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="5eabf-149">Läs mer om Åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="5eabf-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
