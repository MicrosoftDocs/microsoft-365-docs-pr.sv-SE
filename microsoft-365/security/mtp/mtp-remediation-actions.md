---
title: Åtgärdsåtgärder i Microsoft 365 Defender
description: Få en översikt över åtgärder som följer på automatiserade undersökningar i Microsoft 365 Defender
keywords: automatiserad, undersökning, varning, utlösare, åtgärd, åtgärd
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932856"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="155de-104">Åtgärdsåtgärder i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="155de-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="155de-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="155de-105">**Applies to:**</span></span>
- <span data-ttu-id="155de-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="155de-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="155de-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="155de-107">Remediation actions</span></span>

<span data-ttu-id="155de-108">Under och efter en automatisk undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="155de-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="155de-109">Vissa typer av åtgärder vidtas på enheter, även kallade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="155de-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="155de-110">Andra åtgärder vidtas på e-postinnehåll.</span><span class="sxs-lookup"><span data-stu-id="155de-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="155de-111">Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="155de-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="155de-112">Huruvida åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används.</span><span class="sxs-lookup"><span data-stu-id="155de-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="155de-113">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="155de-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="155de-114">Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="155de-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="155de-115">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="155de-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="155de-116">Hot och åtgärder för e-post och & samarbetsinnehåll</span><span class="sxs-lookup"><span data-stu-id="155de-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="155de-117">I följande tabell sammanfattas de åtgärder som stöds för närvarande i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="155de-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="155de-118">Åtgärdsåtgärder för enhet (slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="155de-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="155de-119">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="155de-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="155de-120">- Samla in undersökningspaket</span><span class="sxs-lookup"><span data-stu-id="155de-120">- Collect investigation package</span></span> <br/><span data-ttu-id="155de-121">- Isolera enhet (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="155de-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="155de-122">- Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="155de-122">- Offboard machine</span></span> <br/><span data-ttu-id="155de-123">- Släppa kodkörning</span><span class="sxs-lookup"><span data-stu-id="155de-123">- Release code execution</span></span> <br/><span data-ttu-id="155de-124">- Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="155de-124">- Release from quarantine</span></span> <br/><span data-ttu-id="155de-125">- Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="155de-125">- Request sample</span></span> <br/><span data-ttu-id="155de-126">– Begränsa körning av kod (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="155de-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="155de-127">- Kör antivirussökning</span><span class="sxs-lookup"><span data-stu-id="155de-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="155de-128">- Stoppa och sätta i karantän</span><span class="sxs-lookup"><span data-stu-id="155de-128">- Stop and quarantine</span></span>      |<span data-ttu-id="155de-129">- Blockera URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="155de-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="155de-130">- Mjuk borttagning av e-postmeddelanden och kluster</span><span class="sxs-lookup"><span data-stu-id="155de-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="155de-131">- Sätt e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="155de-131">- Quarantine email</span></span><br/><span data-ttu-id="155de-132">- Sätt en e-postbilaga i karantän</span><span class="sxs-lookup"><span data-stu-id="155de-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="155de-133">- Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="155de-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="155de-134">Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)</span><span class="sxs-lookup"><span data-stu-id="155de-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="155de-135">Åtgärdsåtgärder som följer på automatiska undersökningar</span><span class="sxs-lookup"><span data-stu-id="155de-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="155de-136">När en automatiserad undersökning slutförs, nås en bedömning för alla bevis som ingår.</span><span class="sxs-lookup"><span data-stu-id="155de-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="155de-137">Beroende på vilket beslut det gäller identifieras åtgärdsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="155de-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="155de-138">I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="155de-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="155de-139">Det beror på hur [automatisk undersökning och svar har konfigurerats.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="155de-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="155de-140">I följande tabell visas möjliga utfall:</span><span class="sxs-lookup"><span data-stu-id="155de-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="155de-141">Bedömning</span><span class="sxs-lookup"><span data-stu-id="155de-141">Verdict</span></span>    | <span data-ttu-id="155de-142">Område</span><span class="sxs-lookup"><span data-stu-id="155de-142">Area</span></span>    | <span data-ttu-id="155de-143">Resultat</span><span class="sxs-lookup"><span data-stu-id="155de-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="155de-144">Skadlig</span><span class="sxs-lookup"><span data-stu-id="155de-144">Malicious</span></span>    | <span data-ttu-id="155de-145">Enheter (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="155de-145">Devices (endpoints)</span></span>    | <span data-ttu-id="155de-146">Åtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på Fullständiga – åtgärda **hot automatiskt)**</span><span class="sxs-lookup"><span data-stu-id="155de-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="155de-147">Skadlig</span><span class="sxs-lookup"><span data-stu-id="155de-147">Malicious</span></span>    | <span data-ttu-id="155de-148">E-postinnehåll (URL:er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="155de-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="155de-149">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="155de-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="155de-150">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="155de-150">Suspicious</span></span>    | <span data-ttu-id="155de-151">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="155de-151">Devices or email content</span></span> | <span data-ttu-id="155de-152">Rekommenderade åtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="155de-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="155de-153">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="155de-153">No threats found</span></span>    | <span data-ttu-id="155de-154">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="155de-154">Devices or email content</span></span>    | <span data-ttu-id="155de-155">Inga åtgärder krävs</span><span class="sxs-lookup"><span data-stu-id="155de-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="155de-156">Åtgärder som vidtas manuellt</span><span class="sxs-lookup"><span data-stu-id="155de-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="155de-157">Förutom åtgärder som följer på automatiserade undersökningar kan säkerhetsteamet även vidta vissa åtgärder manuellt.</span><span class="sxs-lookup"><span data-stu-id="155de-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="155de-158">Det kan till exempel vara följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="155de-158">These include the following actions:</span></span>

- <span data-ttu-id="155de-159">Manuell enhetsåtgärd, till exempel enhetsisolering eller karantän för filer.</span><span class="sxs-lookup"><span data-stu-id="155de-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="155de-160">Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="155de-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="155de-161">[Avancerad sökåtgärd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) på enheter eller e-post.</span><span class="sxs-lookup"><span data-stu-id="155de-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="155de-162">[Åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) i Utforskaren för e-postinnehåll, till exempel flytta e-post till skräppost, mjuk borttagning av e-post eller hård borttagning av e-post.</span><span class="sxs-lookup"><span data-stu-id="155de-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="155de-163">Manuell [svarsåtgärd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel att ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.</span><span class="sxs-lookup"><span data-stu-id="155de-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="155de-164">Åtgärd för livesvar med [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)för slutpunkts-API:er, till exempel att isolera en enhet, köra en antivirussökning och hämta information om en fil.</span><span class="sxs-lookup"><span data-stu-id="155de-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="155de-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="155de-165">Next steps</span></span>

- [<span data-ttu-id="155de-166">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="155de-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="155de-167">Godkänna eller avvisa väntande åtgärder</span><span class="sxs-lookup"><span data-stu-id="155de-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="155de-168">Hantera falska positiva/negativa tal i automatisk undersökning och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="155de-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
