---
title: Reparations åtgärder i Microsoft 365 Defender
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683301"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="2e376-104">Reparations åtgärder i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e376-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2e376-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2e376-105">**Applies to:**</span></span>
- <span data-ttu-id="2e376-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e376-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="2e376-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="2e376-107">Remediation actions</span></span>

<span data-ttu-id="2e376-108">Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärds åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="2e376-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="2e376-109">Vissa typer av reparations åtgärder utförs på enheter, som även kallas slut punkter.</span><span class="sxs-lookup"><span data-stu-id="2e376-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="2e376-110">Andra reparations åtgärder vidtas på e-postinnehållet.</span><span class="sxs-lookup"><span data-stu-id="2e376-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="2e376-111">Automatiserade undersökningar slutfört efter att reparations åtgärder vidtogs, godkännts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="2e376-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e376-112">Om reparations åtgärder vidtas automatiskt eller bara vid godkännandet beror på vissa inställningar, till exempel hur automatiserings nivåer fungerar.</span><span class="sxs-lookup"><span data-stu-id="2e376-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="2e376-113">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="2e376-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="2e376-114">Konfigurera den automatiska undersöknings-och svars funktionerna i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e376-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="2e376-115">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="2e376-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="2e376-116">Hot och reparations åtgärder på e-post & samarbets innehåll</span><span class="sxs-lookup"><span data-stu-id="2e376-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="2e376-117">I följande tabell sammanfattas de reparations åtgärder som stöds i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="2e376-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="2e376-118">Reparations åtgärder för enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="2e376-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="2e376-119">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="2e376-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="2e376-120">-Samla in undersöknings paket</span><span class="sxs-lookup"><span data-stu-id="2e376-120">- Collect investigation package</span></span> <br/><span data-ttu-id="2e376-121">-Isolera enheter (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="2e376-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="2e376-122">-Ta bort dator</span><span class="sxs-lookup"><span data-stu-id="2e376-122">- Offboard machine</span></span> <br/><span data-ttu-id="2e376-123">-Lansering av kod</span><span class="sxs-lookup"><span data-stu-id="2e376-123">- Release code execution</span></span> <br/><span data-ttu-id="2e376-124">-Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="2e376-124">- Release from quarantine</span></span> <br/><span data-ttu-id="2e376-125">-Begäran-exempel</span><span class="sxs-lookup"><span data-stu-id="2e376-125">- Request sample</span></span> <br/><span data-ttu-id="2e376-126">-Begränsa kod körning (denna åtgärd kan ångras)</span><span class="sxs-lookup"><span data-stu-id="2e376-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="2e376-127">-Kör antivirus genomsökning</span><span class="sxs-lookup"><span data-stu-id="2e376-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="2e376-128">-Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="2e376-128">- Stop and quarantine</span></span>      |<span data-ttu-id="2e376-129">-Block-URL (tid för klick)</span><span class="sxs-lookup"><span data-stu-id="2e376-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="2e376-130">-Mjuka ta bort e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="2e376-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="2e376-131">-Karantän-e-postadress</span><span class="sxs-lookup"><span data-stu-id="2e376-131">- Quarantine email</span></span><br/><span data-ttu-id="2e376-132">-Quarantine a e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="2e376-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="2e376-133">-Inaktivera vidarebefordran av externa e-post</span><span class="sxs-lookup"><span data-stu-id="2e376-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="2e376-134">Reparations åtgärder som väntar på godkännande eller redan är avslutade kan visas i [Åtgärds centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="2e376-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="2e376-135">Reparations åtgärder som följer automatiska utredningar</span><span class="sxs-lookup"><span data-stu-id="2e376-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="2e376-136">När en automatiserad undersökning är klar är en Verdict nådd för varje del av beviset.</span><span class="sxs-lookup"><span data-stu-id="2e376-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="2e376-137">Beroende på Verdict identifieras åtgärds åtgärder.</span><span class="sxs-lookup"><span data-stu-id="2e376-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="2e376-138">I vissa fall vidtas reparations åtgärder automatiskt. i andra fall väntar reparations åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="2e376-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="2e376-139">Det beror på hur [Automatisk undersökning och svar är konfigurerat](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="2e376-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="2e376-140">I följande tabell visas möjliga verdicts och resultat:</span><span class="sxs-lookup"><span data-stu-id="2e376-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="2e376-141">Verdict</span><span class="sxs-lookup"><span data-stu-id="2e376-141">Verdict</span></span>    | <span data-ttu-id="2e376-142">Under</span><span class="sxs-lookup"><span data-stu-id="2e376-142">Area</span></span>    | <span data-ttu-id="2e376-143">Resultat</span><span class="sxs-lookup"><span data-stu-id="2e376-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="2e376-144">Skadliga</span><span class="sxs-lookup"><span data-stu-id="2e376-144">Malicious</span></span>    | <span data-ttu-id="2e376-145">Enheter (slut punkter)</span><span class="sxs-lookup"><span data-stu-id="2e376-145">Devices (endpoints)</span></span>    | <span data-ttu-id="2e376-146">Reparations åtgärder vidtas automatiskt (förutsatt att organisationens [enhets grupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på att **automatiskt åtgärda hot**)</span><span class="sxs-lookup"><span data-stu-id="2e376-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="2e376-147">Skadliga</span><span class="sxs-lookup"><span data-stu-id="2e376-147">Malicious</span></span>    | <span data-ttu-id="2e376-148">E-postinnehåll (URL: er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="2e376-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="2e376-149">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="2e376-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="2e376-150">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="2e376-150">Suspicious</span></span>    | <span data-ttu-id="2e376-151">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="2e376-151">Devices or email content</span></span> | <span data-ttu-id="2e376-152">Rekommenderade reparations åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="2e376-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="2e376-153">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="2e376-153">No threats found</span></span>    | <span data-ttu-id="2e376-154">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="2e376-154">Devices or email content</span></span>    | <span data-ttu-id="2e376-155">Inga reparations åtgärder behövs</span><span class="sxs-lookup"><span data-stu-id="2e376-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="2e376-156">Reparations åtgärder som vidtas manuellt</span><span class="sxs-lookup"><span data-stu-id="2e376-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="2e376-157">Förutom reparations åtgärder som följer automatiska utredningar kan dina säkerhets åtgärder vidta vissa reparations åtgärder manuellt.</span><span class="sxs-lookup"><span data-stu-id="2e376-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="2e376-158">Bland annat följande:</span><span class="sxs-lookup"><span data-stu-id="2e376-158">These include the following actions:</span></span>

- <span data-ttu-id="2e376-159">Manuell enhets åtgärd, till exempel enhets isolering eller fil karantän.</span><span class="sxs-lookup"><span data-stu-id="2e376-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="2e376-160">Manuell e-poståtgärd, till exempel borttagning av e-postmeddelanden utan meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2e376-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="2e376-161">[Avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) åtgärd på enheter eller e-post.</span><span class="sxs-lookup"><span data-stu-id="2e376-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="2e376-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) -åtgärd för e-postinnehåll, till exempel att flytta e-post till skräp post, mjukt ta bort e-post eller ta bort meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2e376-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="2e376-163">Manuell [direkt svars](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) åtgärd, till exempel ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.</span><span class="sxs-lookup"><span data-stu-id="2e376-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="2e376-164">Live Response-åtgärd med [Microsoft Defender för slut punkts-API: er](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), till exempel att isolera en enhet, köra en Antivirus sökning och få information om en fil.</span><span class="sxs-lookup"><span data-stu-id="2e376-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="2e376-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2e376-165">Next steps</span></span>

- [<span data-ttu-id="2e376-166">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="2e376-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="2e376-167">Godkänna eller avvisa väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="2e376-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="2e376-168">Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner</span><span class="sxs-lookup"><span data-stu-id="2e376-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
