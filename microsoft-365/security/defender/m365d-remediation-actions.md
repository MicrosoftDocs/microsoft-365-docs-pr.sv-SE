---
title: Åtgärdsåtgärder i Microsoft 365 Defender
description: Få en översikt över åtgärdsåtgärder som följer automatiska undersökningar i Microsoft 365 Defender
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, åtgärd
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f025f23242c28f698e6f67755cc59d21c4463914
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782951"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="153bf-104">Åtgärdsåtgärder i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="153bf-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="153bf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="153bf-105">**Applies to:**</span></span>
- <span data-ttu-id="153bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="153bf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="153bf-107">Under och efter en automatiserad undersökning i Microsoft 365 Defender identifieras åtgärder för skadliga eller misstänkta objekt.</span><span class="sxs-lookup"><span data-stu-id="153bf-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="153bf-108">Vissa typer av åtgärdsåtgärder vidtas på enheter, även kallade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="153bf-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="153bf-109">Andra åtgärder vidtas på e-postinnehållet.</span><span class="sxs-lookup"><span data-stu-id="153bf-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="153bf-110">Automatiserade undersökningar slutförs efter att åtgärder har vidtagits, godkänts eller avvisats.</span><span class="sxs-lookup"><span data-stu-id="153bf-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="153bf-111">Om åtgärder vidtas automatiskt eller bara på godkännande beror på vissa inställningar, till exempel hur automatiseringsnivåer används.</span><span class="sxs-lookup"><span data-stu-id="153bf-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="153bf-112">Mer information finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="153bf-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="153bf-113">Konfigurera automatisk undersökning och svarsfunktioner i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="153bf-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="153bf-114">Hur hot åtgärdas på enheter</span><span class="sxs-lookup"><span data-stu-id="153bf-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="153bf-115">Hot och åtgärdsåtgärder för e-& och samarbetsinnehåll</span><span class="sxs-lookup"><span data-stu-id="153bf-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="153bf-116">I följande tabell sammanfattas de åtgärdsåtgärder som stöds i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="153bf-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="153bf-117">Åtgärdsåtgärder för enhet (slutpunkt)</span><span class="sxs-lookup"><span data-stu-id="153bf-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="153bf-118">Åtgärder för e-postreparation</span><span class="sxs-lookup"><span data-stu-id="153bf-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="153bf-119">- Paket för insamling av undersökning</span><span class="sxs-lookup"><span data-stu-id="153bf-119">- Collect investigation package</span></span> <br/><span data-ttu-id="153bf-120">- Isolera enhet (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="153bf-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="153bf-121">- Offboard-dator</span><span class="sxs-lookup"><span data-stu-id="153bf-121">- Offboard machine</span></span> <br/><span data-ttu-id="153bf-122">- Körning av släppkod</span><span class="sxs-lookup"><span data-stu-id="153bf-122">- Release code execution</span></span> <br/><span data-ttu-id="153bf-123">- Släpp från karantän</span><span class="sxs-lookup"><span data-stu-id="153bf-123">- Release from quarantine</span></span> <br/><span data-ttu-id="153bf-124">- Exempel på förfrågan</span><span class="sxs-lookup"><span data-stu-id="153bf-124">- Request sample</span></span> <br/><span data-ttu-id="153bf-125">– Begränsa körning av kod (den här åtgärden kan ångras)</span><span class="sxs-lookup"><span data-stu-id="153bf-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="153bf-126">- Kör antivirussökning</span><span class="sxs-lookup"><span data-stu-id="153bf-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="153bf-127">- Stopp och karantän</span><span class="sxs-lookup"><span data-stu-id="153bf-127">- Stop and quarantine</span></span>      |<span data-ttu-id="153bf-128">- Blockera URL (tid för klickning)</span><span class="sxs-lookup"><span data-stu-id="153bf-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="153bf-129">- Mjuk borttagning av e-postmeddelanden eller kluster</span><span class="sxs-lookup"><span data-stu-id="153bf-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="153bf-130">- Sätt e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="153bf-130">- Quarantine email</span></span><br/><span data-ttu-id="153bf-131">– sätt i karantän för en e-postbilaga</span><span class="sxs-lookup"><span data-stu-id="153bf-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="153bf-132">- Inaktivera vidarebefordran av extern e-post</span><span class="sxs-lookup"><span data-stu-id="153bf-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="153bf-133">Åtgärdsåtgärder, oavsett om de väntar på godkännande eller redan har slutförts, kan visas i [Åtgärdscenter.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="153bf-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="153bf-134">Åtgärdsåtgärder som följer automatiska undersökningar</span><span class="sxs-lookup"><span data-stu-id="153bf-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="153bf-135">När en automatiserad undersökning har slutförts nås en bedömning för alla bevis som ingår.</span><span class="sxs-lookup"><span data-stu-id="153bf-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="153bf-136">Beroende på omdömet identifieras åtgärdsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="153bf-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="153bf-137">I vissa fall vidtas åtgärder automatiskt. i andra fall väntar åtgärder på godkännande.</span><span class="sxs-lookup"><span data-stu-id="153bf-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="153bf-138">Det beror på hur [automatisk undersökning och svar har konfigurerats.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="153bf-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="153bf-139">I följande tabell visas möjliga bedömningar och resultat:</span><span class="sxs-lookup"><span data-stu-id="153bf-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="153bf-140">Bedömning</span><span class="sxs-lookup"><span data-stu-id="153bf-140">Verdict</span></span>    | <span data-ttu-id="153bf-141">Enheter som påverkas</span><span class="sxs-lookup"><span data-stu-id="153bf-141">Affected entities</span></span>    | <span data-ttu-id="153bf-142">Resultat</span><span class="sxs-lookup"><span data-stu-id="153bf-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="153bf-143">Skadlig</span><span class="sxs-lookup"><span data-stu-id="153bf-143">Malicious</span></span>    | <span data-ttu-id="153bf-144">Enheter (slutpunkter)</span><span class="sxs-lookup"><span data-stu-id="153bf-144">Devices (endpoints)</span></span>    | <span data-ttu-id="153bf-145">Åtgärdsåtgärder vidtas automatiskt (under förutsättning att din organisations [enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på **Fullständiga – åtgärda hot automatiskt)**</span><span class="sxs-lookup"><span data-stu-id="153bf-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="153bf-146">Skadlig</span><span class="sxs-lookup"><span data-stu-id="153bf-146">Malicious</span></span>    | <span data-ttu-id="153bf-147">E-postinnehåll (URL:er eller bifogade filer)</span><span class="sxs-lookup"><span data-stu-id="153bf-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="153bf-148">Rekommenderade åtgärdsåtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="153bf-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="153bf-149">Misstänkt</span><span class="sxs-lookup"><span data-stu-id="153bf-149">Suspicious</span></span>    | <span data-ttu-id="153bf-150">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="153bf-150">Devices or email content</span></span> | <span data-ttu-id="153bf-151">Rekommenderade åtgärdsåtgärder väntar på godkännande</span><span class="sxs-lookup"><span data-stu-id="153bf-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="153bf-152">Inga hot hittades</span><span class="sxs-lookup"><span data-stu-id="153bf-152">No threats found</span></span>    | <span data-ttu-id="153bf-153">Enheter eller e-postinnehåll</span><span class="sxs-lookup"><span data-stu-id="153bf-153">Devices or email content</span></span>    | <span data-ttu-id="153bf-154">Inga åtgärder krävs</span><span class="sxs-lookup"><span data-stu-id="153bf-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="153bf-155">Åtgärder som vidtas manuellt</span><span class="sxs-lookup"><span data-stu-id="153bf-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="153bf-156">Förutom åtgärder som följer på automatiska undersökningar kan säkerhetsoperationsteamet vidta vissa åtgärder manuellt.</span><span class="sxs-lookup"><span data-stu-id="153bf-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="153bf-157">Det kan till exempel vara:</span><span class="sxs-lookup"><span data-stu-id="153bf-157">These include the following:</span></span>

- <span data-ttu-id="153bf-158">Manuell enhetsåtgärd, till exempel enhetsisolering eller karantänen för filer</span><span class="sxs-lookup"><span data-stu-id="153bf-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="153bf-159">Manuell e-poståtgärd, till exempel mjuk borttagning av e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="153bf-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="153bf-160">[Avancerad sökåtgärd](../defender-endpoint/advanced-hunting-overview.md) på enheter eller e-post</span><span class="sxs-lookup"><span data-stu-id="153bf-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="153bf-161">[Åtgärden](../office-365-security/threat-explorer.md) i Utforskaren för e-postinnehåll, t.ex. flytta e-post till skräppost, mjuk borttagning av e-post eller borttagning av e-post</span><span class="sxs-lookup"><span data-stu-id="153bf-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="153bf-162">Manuell [svarsåtgärd,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) till exempel ta bort en fil, stoppa en process och ta bort en schemalagd aktivitet</span><span class="sxs-lookup"><span data-stu-id="153bf-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="153bf-163">Åtgärd för livesvar med Microsoft Defender för [slutpunkts-API:er,](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)t.ex. isolera en enhet, köra en antivirussökning och hämta information om en fil</span><span class="sxs-lookup"><span data-stu-id="153bf-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="153bf-164">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="153bf-164">Next steps</span></span>

- [<span data-ttu-id="153bf-165">Besök åtgärden centret</span><span class="sxs-lookup"><span data-stu-id="153bf-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="153bf-166">Visa och hantera åtgärdsåtgärder</span><span class="sxs-lookup"><span data-stu-id="153bf-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="153bf-167">Adressera falska positiva tal eller falska negativa tal</span><span class="sxs-lookup"><span data-stu-id="153bf-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
