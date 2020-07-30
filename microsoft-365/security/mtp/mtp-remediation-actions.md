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
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502943"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="29f84-104">Reparationsåtgärder efter automatiserade undersökningar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="29f84-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="29f84-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="29f84-105">**Applies to:**</span></span>
- <span data-ttu-id="29f84-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="29f84-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="29f84-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="29f84-107">Remediation actions</span></span>

<span data-ttu-id="29f84-108">Under och efter en automatisk undersökning i Microsoft Threat Protection identifieras reparationsåtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="29f84-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="29f84-109">Vissa typer av reparationsåtgärder vidtas på enheter, även kallade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="29f84-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="29f84-110">Andra åtgärder för reparation vidtas på e-postinnehåll.</span><span class="sxs-lookup"><span data-stu-id="29f84-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="29f84-111">Automatiserade undersökningar slutförs efter att reparationsåtgärder har vidtagits, godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="29f84-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="29f84-112">I följande tabell sammanfattas åtgärder för reparation som för närvarande stöds i Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="29f84-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="29f84-113">Åtgärdsåtgärder för enhet (slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="29f84-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="29f84-114">Åtgärder för reparation av e-post</span><span class="sxs-lookup"><span data-stu-id="29f84-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="29f84-115">- Samla in utredningspaket</span><span class="sxs-lookup"><span data-stu-id="29f84-115">- Collect investigation package</span></span> <br/><span data-ttu-id="29f84-116">- Isolera enheten (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="29f84-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="29f84-117">- Offboard maskin</span><span class="sxs-lookup"><span data-stu-id="29f84-117">- Offboard machine</span></span> <br/><span data-ttu-id="29f84-118">- Utförande av utgivningskod</span><span class="sxs-lookup"><span data-stu-id="29f84-118">- Release code execution</span></span> <br/><span data-ttu-id="29f84-119">- Frisläppande från karantän</span><span class="sxs-lookup"><span data-stu-id="29f84-119">- Release from quarantine</span></span> <br/><span data-ttu-id="29f84-120">- Ta prov på begäran</span><span class="sxs-lookup"><span data-stu-id="29f84-120">- Request sample</span></span> <br/><span data-ttu-id="29f84-121">- Begränsa körning av kod (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="29f84-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="29f84-122">- Kör antivirus scan</span><span class="sxs-lookup"><span data-stu-id="29f84-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="29f84-123">- Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="29f84-123">- Stop and quarantine</span></span>      |<span data-ttu-id="29f84-124">- Blockera URL (tid-för-klick)</span><span class="sxs-lookup"><span data-stu-id="29f84-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="29f84-125">- Mjuk ta bort e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="29f84-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="29f84-126">- Karantän e-post</span><span class="sxs-lookup"><span data-stu-id="29f84-126">- Quarantine email</span></span><br/><span data-ttu-id="29f84-127">- Karantän en e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="29f84-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="29f84-128">- Stäng av vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="29f84-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="29f84-129">Reparationsåtgärder, oavsett om de väntar på godkännande eller redan är slutförda, kan visas i [Åtgärdscenter](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="29f84-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="29f84-130">Saneringsåtgärder följer på automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="29f84-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="29f84-131">När en automatiserad undersökning är klar, en dom nås för varje del av bevis inblandade, och sanering åtgärder identifieras.</span><span class="sxs-lookup"><span data-stu-id="29f84-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="29f84-132">I vissa fall vidtas åtgärder för att åtgärda dem automatiskt. I andra fall väntar saneringsåtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="29f84-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="29f84-133">I följande tabell listas möjliga domar och resultat:</span><span class="sxs-lookup"><span data-stu-id="29f84-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="29f84-134">Dom</span><span class="sxs-lookup"><span data-stu-id="29f84-134">Verdict</span></span>    |<span data-ttu-id="29f84-135">Området</span><span class="sxs-lookup"><span data-stu-id="29f84-135">Area</span></span>    |<span data-ttu-id="29f84-136">Resultat</span><span class="sxs-lookup"><span data-stu-id="29f84-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="29f84-137">Skadlig</span><span class="sxs-lookup"><span data-stu-id="29f84-137">Malicious</span></span>    |<span data-ttu-id="29f84-138">Enheter (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="29f84-138">Devices (endpoints)</span></span>    |<span data-ttu-id="29f84-139">Reparationsåtgärder vidtas automatiskt</span><span class="sxs-lookup"><span data-stu-id="29f84-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="29f84-140">Skadlig</span><span class="sxs-lookup"><span data-stu-id="29f84-140">Malicious</span></span>    |<span data-ttu-id="29f84-141">E-postinnehåll (webbadresser eller bilagor)</span><span class="sxs-lookup"><span data-stu-id="29f84-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="29f84-142">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="29f84-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="29f84-143">Misstänkta</span><span class="sxs-lookup"><span data-stu-id="29f84-143">Suspicious</span></span>    |<span data-ttu-id="29f84-144">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="29f84-144">Devices or email content</span></span> |<span data-ttu-id="29f84-145">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="29f84-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="29f84-146">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="29f84-146">No threats found</span></span>    |<span data-ttu-id="29f84-147">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="29f84-147">Devices or email content</span></span>    |<span data-ttu-id="29f84-148">Inga saneringsåtgärder behövs</span><span class="sxs-lookup"><span data-stu-id="29f84-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="29f84-149">Granska en väntande åtgärd i åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="29f84-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="29f84-150">Om du tror att något missades eller felaktigt upptäcktes av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta!</span><span class="sxs-lookup"><span data-stu-id="29f84-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="29f84-151">[Rapportera falska positiva identifieringar/negativ](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="29f84-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="29f84-152">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="29f84-152">Next steps</span></span>

- [<span data-ttu-id="29f84-153">Godkänna eller avvisa åtgärder</span><span class="sxs-lookup"><span data-stu-id="29f84-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="29f84-154">Läs mer om Åtgärdscentret</span><span class="sxs-lookup"><span data-stu-id="29f84-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
