---
title: Åtgärdsåtgärder i Microsoft 365 Defender
description: Få en översikt över åtgärder som följer automatiska undersökningar i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c81f824a0faaca1c228aa650c003576cce210a67
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199213"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="a699f-104">Åtgärdsåtgärder i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a699f-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a699f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a699f-105">**Applies to:**</span></span>
- <span data-ttu-id="a699f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a699f-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="a699f-107">Reparationsåtgärder</span><span class="sxs-lookup"><span data-stu-id="a699f-107">Remediation actions</span></span>

<span data-ttu-id="a699f-108">Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="a699f-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="a699f-109">Vissa typer av åtgärdsåtgärder vidtas på enheter, även kallade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="a699f-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="a699f-110">Andra åtgärder vidtas på e-postinnehållet.</span><span class="sxs-lookup"><span data-stu-id="a699f-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="a699f-111">Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="a699f-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a699f-112">Om åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används.</span><span class="sxs-lookup"><span data-stu-id="a699f-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="a699f-113">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="a699f-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="a699f-114">Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a699f-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="a699f-115">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="a699f-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="a699f-116">Hot och åtgärdsåtgärder för e-& och samarbetsinnehåll</span><span class="sxs-lookup"><span data-stu-id="a699f-116">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="a699f-117">I följande tabell sammanfattas de åtgärder som stöds för närvarande i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="a699f-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="a699f-118">Åtgärdsåtgärder för enhet (slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="a699f-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="a699f-119">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="a699f-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="a699f-120">- Paket för insamling av undersökning</span><span class="sxs-lookup"><span data-stu-id="a699f-120">- Collect investigation package</span></span> <br/><span data-ttu-id="a699f-121">- Isolera enhet (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="a699f-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="a699f-122">- Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="a699f-122">- Offboard machine</span></span> <br/><span data-ttu-id="a699f-123">- Körning av släppkod</span><span class="sxs-lookup"><span data-stu-id="a699f-123">- Release code execution</span></span> <br/><span data-ttu-id="a699f-124">- Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="a699f-124">- Release from quarantine</span></span> <br/><span data-ttu-id="a699f-125">- Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="a699f-125">- Request sample</span></span> <br/><span data-ttu-id="a699f-126">– Begränsa körning av kod (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="a699f-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="a699f-127">- Kör antivirussökning</span><span class="sxs-lookup"><span data-stu-id="a699f-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="a699f-128">- Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="a699f-128">- Stop and quarantine</span></span>      |<span data-ttu-id="a699f-129">- Blockera URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="a699f-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="a699f-130">- Mjuk borttagning av e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="a699f-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="a699f-131">- Sätt e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="a699f-131">- Quarantine email</span></span><br/><span data-ttu-id="a699f-132">– sätt i karantän för en e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="a699f-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="a699f-133">- Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="a699f-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="a699f-134">Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="a699f-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="a699f-135">Åtgärdsåtgärder som följer automatiska undersökningar</span><span class="sxs-lookup"><span data-stu-id="a699f-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="a699f-136">När en automatiserad undersökning har slutförts nås en bedömning för alla bevis som ingår.</span><span class="sxs-lookup"><span data-stu-id="a699f-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="a699f-137">Beroende på omdömet identifieras åtgärdsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="a699f-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="a699f-138">I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="a699f-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="a699f-139">Det beror på hur [automatisk undersökning och svar har konfigurerats.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="a699f-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="a699f-140">I följande tabell visas möjliga bedömningar och resultat:</span><span class="sxs-lookup"><span data-stu-id="a699f-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="a699f-141">Bedömning</span><span class="sxs-lookup"><span data-stu-id="a699f-141">Verdict</span></span>    | <span data-ttu-id="a699f-142">Område</span><span class="sxs-lookup"><span data-stu-id="a699f-142">Area</span></span>    | <span data-ttu-id="a699f-143">Resultat</span><span class="sxs-lookup"><span data-stu-id="a699f-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="a699f-144">Skadlig</span><span class="sxs-lookup"><span data-stu-id="a699f-144">Malicious</span></span>    | <span data-ttu-id="a699f-145">Enheter (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="a699f-145">Devices (endpoints)</span></span>    | <span data-ttu-id="a699f-146">Åtgärdsåtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på **Fullständiga – åtgärda hot automatiskt)**</span><span class="sxs-lookup"><span data-stu-id="a699f-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="a699f-147">Skadlig</span><span class="sxs-lookup"><span data-stu-id="a699f-147">Malicious</span></span>    | <span data-ttu-id="a699f-148">E-postinnehåll (URL:er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="a699f-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="a699f-149">Rekommenderade åtgärdsåtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="a699f-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="a699f-150">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="a699f-150">Suspicious</span></span>    | <span data-ttu-id="a699f-151">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="a699f-151">Devices or email content</span></span> | <span data-ttu-id="a699f-152">Rekommenderade åtgärdsåtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="a699f-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="a699f-153">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="a699f-153">No threats found</span></span>    | <span data-ttu-id="a699f-154">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="a699f-154">Devices or email content</span></span>    | <span data-ttu-id="a699f-155">Inga åtgärder krävs</span><span class="sxs-lookup"><span data-stu-id="a699f-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="a699f-156">Åtgärder som vidtas manuellt</span><span class="sxs-lookup"><span data-stu-id="a699f-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="a699f-157">Förutom åtgärder som följer på automatiska undersökningar kan säkerhetsoperationsteamet vidta vissa åtgärder manuellt.</span><span class="sxs-lookup"><span data-stu-id="a699f-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="a699f-158">Detta omfattar följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="a699f-158">These include the following actions:</span></span>

- <span data-ttu-id="a699f-159">Manuell enhetsåtgärd, till exempel enhetsisolering eller karantänen för filer.</span><span class="sxs-lookup"><span data-stu-id="a699f-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="a699f-160">Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="a699f-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="a699f-161">[Avancerad sökåtgärd](../defender-endpoint/advanced-hunting-overview.md) på enheter eller e-post.</span><span class="sxs-lookup"><span data-stu-id="a699f-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="a699f-162">[Åtgärden](../office-365-security/threat-explorer.md) i Utforskaren för e-postinnehåll, t.ex. flytta e-post till skräppost, mjuk borttagning av e-post eller borttagning av e-post.</span><span class="sxs-lookup"><span data-stu-id="a699f-162">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="a699f-163">Manuell [svarsåtgärd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet.</span><span class="sxs-lookup"><span data-stu-id="a699f-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="a699f-164">Åtgärd för livesvar med Microsoft Defender för [slutpunkts-API:er,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)till exempel att isolera en enhet, köra en antivirussökning och hämta information om en fil.</span><span class="sxs-lookup"><span data-stu-id="a699f-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a699f-165">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="a699f-165">Next steps</span></span>

- [<span data-ttu-id="a699f-166">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="a699f-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="a699f-167">Visa och hantera åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="a699f-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="a699f-168">Hantera falska positiva/negativa i automatiska undersöknings- och svarsfunktioner</span><span class="sxs-lookup"><span data-stu-id="a699f-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
