---
title: Reparations åtgärder efter automatiserade utredningar i Microsoft 365 Defender
description: Få en översikt över reparations åtgärder som följer automatiska utredningar i Microsoft 365 Defender
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
ms.openlocfilehash: 71cdf2d1b9a40e9cfbf487ca8596a0c2b09475d1
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847218"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-365-defender"></a><span data-ttu-id="c65ee-104">Reparations åtgärder efter automatiserade utredningar i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c65ee-104">Remediation actions following automated investigations in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c65ee-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c65ee-105">**Applies to:**</span></span>
- <span data-ttu-id="c65ee-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c65ee-106">Microsoft 365 Defender</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="c65ee-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="c65ee-107">Remediation actions</span></span>

<span data-ttu-id="c65ee-108">Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärds åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="c65ee-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="c65ee-109">Vissa typer av reparations åtgärder utförs på enheter, som även kallas slut punkter.</span><span class="sxs-lookup"><span data-stu-id="c65ee-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="c65ee-110">Andra reparations åtgärder vidtas på e-postinnehållet.</span><span class="sxs-lookup"><span data-stu-id="c65ee-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="c65ee-111">Automatiserade undersökningar slutfört efter att reparations åtgärder vidtogs, godkännts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="c65ee-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="c65ee-112">I följande tabell sammanfattas de reparations åtgärder som stöds i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="c65ee-112">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="c65ee-113">Reparations åtgärder för enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="c65ee-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="c65ee-114">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="c65ee-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="c65ee-115">-Samla in undersöknings paket</span><span class="sxs-lookup"><span data-stu-id="c65ee-115">- Collect investigation package</span></span> <br/><span data-ttu-id="c65ee-116">-Isolera enheter (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="c65ee-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="c65ee-117">-Ta bort dator</span><span class="sxs-lookup"><span data-stu-id="c65ee-117">- Offboard machine</span></span> <br/><span data-ttu-id="c65ee-118">-Lansering av kod</span><span class="sxs-lookup"><span data-stu-id="c65ee-118">- Release code execution</span></span> <br/><span data-ttu-id="c65ee-119">-Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="c65ee-119">- Release from quarantine</span></span> <br/><span data-ttu-id="c65ee-120">-Begäran-exempel</span><span class="sxs-lookup"><span data-stu-id="c65ee-120">- Request sample</span></span> <br/><span data-ttu-id="c65ee-121">-Begränsa kod körning (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="c65ee-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="c65ee-122">-Kör antivirus genomsökning</span><span class="sxs-lookup"><span data-stu-id="c65ee-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="c65ee-123">-Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="c65ee-123">- Stop and quarantine</span></span>      |<span data-ttu-id="c65ee-124">-Block-URL (tid för klick)</span><span class="sxs-lookup"><span data-stu-id="c65ee-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="c65ee-125">-Mjuka ta bort e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="c65ee-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="c65ee-126">-Karantän-e-postadress</span><span class="sxs-lookup"><span data-stu-id="c65ee-126">- Quarantine email</span></span><br/><span data-ttu-id="c65ee-127">-Quarantine a e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="c65ee-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="c65ee-128">-Inaktivera vidarebefordran av externa e-post</span><span class="sxs-lookup"><span data-stu-id="c65ee-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="c65ee-129">Reparations åtgärder som väntar på godkännande eller redan är avslutade kan visas i [Åtgärds centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="c65ee-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="c65ee-130">Reparations åtgärder utför automatiserade utredningar</span><span class="sxs-lookup"><span data-stu-id="c65ee-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="c65ee-131">När en automatiserad undersökning är klar är en Verdict nådd för varje del av beviset.</span><span class="sxs-lookup"><span data-stu-id="c65ee-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="c65ee-132">Beroende på Verdict identifieras åtgärds åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c65ee-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="c65ee-133">I vissa fall vidtas reparations åtgärder automatiskt. i andra fall väntar reparations åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="c65ee-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="c65ee-134">Det beror på hur [Automatisk undersökning och svar är konfigurerat](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="c65ee-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="c65ee-135">I följande tabell visas möjliga verdicts och resultat:</span><span class="sxs-lookup"><span data-stu-id="c65ee-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="c65ee-136">Verdict</span><span class="sxs-lookup"><span data-stu-id="c65ee-136">Verdict</span></span>    |<span data-ttu-id="c65ee-137">Under</span><span class="sxs-lookup"><span data-stu-id="c65ee-137">Area</span></span>    |<span data-ttu-id="c65ee-138">Resultat</span><span class="sxs-lookup"><span data-stu-id="c65ee-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="c65ee-139">Skadliga</span><span class="sxs-lookup"><span data-stu-id="c65ee-139">Malicious</span></span>    |<span data-ttu-id="c65ee-140">Enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="c65ee-140">Devices (endpoints)</span></span>    |<span data-ttu-id="c65ee-141">Reparations åtgärder vidtas automatiskt (förutsatt att organisationens [enhets grupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på att **automatiskt åtgärda hot** )</span><span class="sxs-lookup"><span data-stu-id="c65ee-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically** )</span></span>|
|<span data-ttu-id="c65ee-142">Skadliga</span><span class="sxs-lookup"><span data-stu-id="c65ee-142">Malicious</span></span>    |<span data-ttu-id="c65ee-143">E-postinnehåll (URL: er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="c65ee-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="c65ee-144">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="c65ee-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="c65ee-145">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="c65ee-145">Suspicious</span></span>    |<span data-ttu-id="c65ee-146">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="c65ee-146">Devices or email content</span></span> |<span data-ttu-id="c65ee-147">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="c65ee-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="c65ee-148">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="c65ee-148">No threats found</span></span>    |<span data-ttu-id="c65ee-149">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="c65ee-149">Devices or email content</span></span>    |<span data-ttu-id="c65ee-150">Inga reparations åtgärder behövs</span><span class="sxs-lookup"><span data-stu-id="c65ee-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="c65ee-151">Om reparations åtgärder vidtas automatiskt eller bara vid godkännande beror på vissa inställningar, till exempel organisationens enhets grup principer.</span><span class="sxs-lookup"><span data-stu-id="c65ee-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="c65ee-152">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="c65ee-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="c65ee-153">Konfigurera automatiserade undersökningar och svars funktioner i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c65ee-153">Configure automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="c65ee-154">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="c65ee-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="c65ee-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="c65ee-155">Next steps</span></span>

- [<span data-ttu-id="c65ee-156">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="c65ee-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="c65ee-157">Godkänna eller avvisa väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="c65ee-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="c65ee-158">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="c65ee-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
