---
title: Reparations åtgärder efter automatiserade utredningar av skydd mot Microsoft Threat
description: Få en översikt över reparations åtgärder som följer automatiska utredningar av Microsoft Threat Protection
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5106ef34f11cb43d74fa993fcdb820d6a5dce86f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429485"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="2d4ae-104">Reparations åtgärder efter automatiserade utredningar av skydd mot Microsoft Threat</span><span class="sxs-lookup"><span data-stu-id="2d4ae-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2d4ae-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2d4ae-105">**Applies to:**</span></span>
- <span data-ttu-id="2d4ae-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2d4ae-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="2d4ae-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="2d4ae-107">Remediation actions</span></span>

<span data-ttu-id="2d4ae-108">Under och efter en automatisk undersökning av Microsoft Threat Protection identifieras åtgärds åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="2d4ae-109">Vissa typer av reparations åtgärder utförs på enheter, som även kallas slut punkter.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="2d4ae-110">Andra reparations åtgärder vidtas på e-postinnehållet.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="2d4ae-111">Automatiserade undersökningar slutfört efter att reparations åtgärder vidtogs, godkännts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="2d4ae-112">I följande tabell sammanfattas de reparations åtgärder som stöds för närvarande i Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="2d4ae-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="2d4ae-113">Reparations åtgärder för enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="2d4ae-114">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="2d4ae-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="2d4ae-115">-Samla in undersöknings paket</span><span class="sxs-lookup"><span data-stu-id="2d4ae-115">- Collect investigation package</span></span> <br/><span data-ttu-id="2d4ae-116">-Isolera enheter (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="2d4ae-117">-Ta bort dator</span><span class="sxs-lookup"><span data-stu-id="2d4ae-117">- Offboard machine</span></span> <br/><span data-ttu-id="2d4ae-118">-Lansering av kod</span><span class="sxs-lookup"><span data-stu-id="2d4ae-118">- Release code execution</span></span> <br/><span data-ttu-id="2d4ae-119">-Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="2d4ae-119">- Release from quarantine</span></span> <br/><span data-ttu-id="2d4ae-120">-Begäran-exempel</span><span class="sxs-lookup"><span data-stu-id="2d4ae-120">- Request sample</span></span> <br/><span data-ttu-id="2d4ae-121">-Begränsa kod körning (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="2d4ae-122">-Kör antivirus genomsökning</span><span class="sxs-lookup"><span data-stu-id="2d4ae-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="2d4ae-123">-Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="2d4ae-123">- Stop and quarantine</span></span>      |<span data-ttu-id="2d4ae-124">-Block-URL (tid för klick)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="2d4ae-125">-Mjuka ta bort e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="2d4ae-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="2d4ae-126">-Karantän-e-postadress</span><span class="sxs-lookup"><span data-stu-id="2d4ae-126">- Quarantine email</span></span><br/><span data-ttu-id="2d4ae-127">-Quarantine a e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="2d4ae-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="2d4ae-128">-Inaktivera vidarebefordran av externa e-post</span><span class="sxs-lookup"><span data-stu-id="2d4ae-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="2d4ae-129">Reparations åtgärder som väntar på godkännande eller redan är avslutade kan visas i [Åtgärds centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="2d4ae-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="2d4ae-130">Reparations åtgärder utför automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="2d4ae-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="2d4ae-131">När en automatiserad undersökning är klar är en Verdict nådd för varje del av beviset.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="2d4ae-132">Beroende på Verdict identifieras åtgärds åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="2d4ae-133">I vissa fall vidtas reparations åtgärder automatiskt. i andra fall väntar reparations åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="2d4ae-134">Det beror på hur [Automatisk undersökning och svar är konfigurerat](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="2d4ae-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="2d4ae-135">I följande tabell visas möjliga verdicts och resultat:</span><span class="sxs-lookup"><span data-stu-id="2d4ae-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="2d4ae-136">Verdict</span><span class="sxs-lookup"><span data-stu-id="2d4ae-136">Verdict</span></span>    |<span data-ttu-id="2d4ae-137">Under</span><span class="sxs-lookup"><span data-stu-id="2d4ae-137">Area</span></span>    |<span data-ttu-id="2d4ae-138">Resultat</span><span class="sxs-lookup"><span data-stu-id="2d4ae-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="2d4ae-139">Skadliga</span><span class="sxs-lookup"><span data-stu-id="2d4ae-139">Malicious</span></span>    |<span data-ttu-id="2d4ae-140">Enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-140">Devices (endpoints)</span></span>    |<span data-ttu-id="2d4ae-141">Reparations åtgärder vidtas automatiskt (förutsatt att organisationens [enhets grupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på att **automatiskt åtgärda hot**)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="2d4ae-142">Skadliga</span><span class="sxs-lookup"><span data-stu-id="2d4ae-142">Malicious</span></span>    |<span data-ttu-id="2d4ae-143">E-postinnehåll (URL: er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="2d4ae-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="2d4ae-144">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="2d4ae-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="2d4ae-145">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="2d4ae-145">Suspicious</span></span>    |<span data-ttu-id="2d4ae-146">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="2d4ae-146">Devices or email content</span></span> |<span data-ttu-id="2d4ae-147">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="2d4ae-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="2d4ae-148">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="2d4ae-148">No threats found</span></span>    |<span data-ttu-id="2d4ae-149">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="2d4ae-149">Devices or email content</span></span>    |<span data-ttu-id="2d4ae-150">Inga reparations åtgärder behövs</span><span class="sxs-lookup"><span data-stu-id="2d4ae-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="2d4ae-151">Om reparations åtgärder vidtas automatiskt eller bara vid godkännande beror på vissa inställningar, till exempel organisationens enhets grup principer.</span><span class="sxs-lookup"><span data-stu-id="2d4ae-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="2d4ae-152">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="2d4ae-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="2d4ae-153">Konfigurera automatisk granskning och svars funktioner i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2d4ae-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="2d4ae-154">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="2d4ae-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="2d4ae-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2d4ae-155">Next steps</span></span>

- [<span data-ttu-id="2d4ae-156">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="2d4ae-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="2d4ae-157">Godkänna eller avvisa väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="2d4ae-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="2d4ae-158">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="2d4ae-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
