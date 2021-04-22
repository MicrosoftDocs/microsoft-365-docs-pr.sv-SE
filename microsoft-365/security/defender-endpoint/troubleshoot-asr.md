---
title: Felsöka problem med minskningsregler för attackytan
description: Resurser och exempelkod för att felsöka problem med minskningsregler för attackytan i Microsoft Defender för Slutpunkt.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9ff00c706b0fb336c178e227b1cb33eff9e9ebbc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935227"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="ab315-104">Felsöka minskningsregler för attackytor</span><span class="sxs-lookup"><span data-stu-id="ab315-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ab315-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ab315-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab315-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ab315-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab315-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab315-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab315-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="ab315-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab315-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="ab315-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="ab315-110">När du använder [minskningsregler för attackytan](attack-surface-reduction.md) kan du få problem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="ab315-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="ab315-111">En regel blockerar en fil, en process eller utför någon annan åtgärd som den inte ska utföra (falsk positiv inställning)</span><span class="sxs-lookup"><span data-stu-id="ab315-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="ab315-112">En regel fungerar inte enligt beskrivningen eller blockerar inte en fil eller process som den ska (falskt negativt)</span><span class="sxs-lookup"><span data-stu-id="ab315-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="ab315-113">Det finns fyra steg för att felsöka dessa problem:</span><span class="sxs-lookup"><span data-stu-id="ab315-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="ab315-114">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="ab315-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="ab315-115">Använda granskningsläge för att testa regeln</span><span class="sxs-lookup"><span data-stu-id="ab315-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="ab315-116">[Lägga till undantag för den angivna regeln](#add-exclusions-for-a-false-positive) (för falska positiva resultat)</span><span class="sxs-lookup"><span data-stu-id="ab315-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="ab315-117">Skicka supportloggar</span><span class="sxs-lookup"><span data-stu-id="ab315-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="ab315-118">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="ab315-118">Confirm prerequisites</span></span>

<span data-ttu-id="ab315-119">Minskning av attackytan fungerar bara på enheter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="ab315-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="ab315-120">Slutpunkter kör Windows 10 Enterprise, version 1709 (kallas även Fall Creators Update).</span><span class="sxs-lookup"><span data-stu-id="ab315-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="ab315-121">Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen.</span><span class="sxs-lookup"><span data-stu-id="ab315-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="ab315-122">[Om du använder någon annan antivirusapp inaktiveras microsoft Defender AV.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="ab315-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="ab315-123">[Realtidsskydd är](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ab315-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="ab315-124">Granskningsläget är inte aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ab315-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="ab315-125">Använd grupprincip för att ställa in regeln på **Inaktiverad** (värde: **0**) enligt beskrivningen i [Aktivera minskningsregler för attackytor.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="ab315-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="ab315-126">Om samtliga krav har uppfyllts går du vidare till nästa steg och testar regeln i granskningsläge.</span><span class="sxs-lookup"><span data-stu-id="ab315-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="ab315-127">Använda granskningsläge för att testa regeln</span><span class="sxs-lookup"><span data-stu-id="ab315-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="ab315-128">Du kan besöka webbplatsen med Windows Defender Test på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att minskningsregler för attackytor vanligtvis fungerar för förkonfigurerade scenarier och processer på en enhet, eller så kan du använda granskningsläge, vilket endast tillåter rapporteringsregler.</span><span class="sxs-lookup"><span data-stu-id="ab315-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="ab315-129">Följ de här [anvisningarna i Använd demoverktyget](evaluate-attack-surface-reduction.md) för att se hur minskningsregler för attackytor fungerar för att testa den specifika regel som du stöter på problem med.</span><span class="sxs-lookup"><span data-stu-id="ab315-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="ab315-130">Aktivera granskningsläge för den regel som du vill testa.</span><span class="sxs-lookup"><span data-stu-id="ab315-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="ab315-131">Använd grupprincip för att ställa in regeln på **Granskningsläge (värde:** **2**) enligt beskrivningen i [Aktivera minskningsregler för attackytan.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="ab315-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="ab315-132">Granskningsläget tillåter att regeln rapporterar filen eller processen, men den kan fortfarande köras.</span><span class="sxs-lookup"><span data-stu-id="ab315-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="ab315-133">Utföra den aktivitet som orsakar ett problem (öppna eller kör till exempel den fil eller process som ska blockeras men som tillåts).</span><span class="sxs-lookup"><span data-stu-id="ab315-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="ab315-134">[Granska händelseloggarna för att minska attackytan](attack-surface-reduction.md) för att se om regeln skulle ha blockerat filen eller processen om regeln hade angetts till **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="ab315-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="ab315-135">Om en regel inte blockerar en fil eller process som du förväntar dig bör den blockeras, kontrollerar du först om granskningsläge är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ab315-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="ab315-136">Granskningsläge kan ha aktiverats för testning av en annan funktion eller av ett automatiserat PowerShell-skript och kan ha inaktiverats när testerna har slutförts.</span><span class="sxs-lookup"><span data-stu-id="ab315-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="ab315-137">Om du har testat regeln med demoverktyget och med granskningsläge och minskningsregler för attackytor arbetar på förkonfigurerade scenarier, men regeln inte fungerar som förväntat, går du till något av följande avsnitt beroende på din situation:</span><span class="sxs-lookup"><span data-stu-id="ab315-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="ab315-138">Om minskningsregeln för attackytan blockerar något som den inte borde blockera (kallas även falsk positiv inställning) kan du först lägga till en exkluderingsregel för [attackytan.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="ab315-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="ab315-139">Om minskningsregeln för attackytan inte blockerar något som den ska blockera (kallas även falskt negativt) kan du fortsätta direkt till det sista steget, samla in diagnostikdata och skicka problemet [till oss.](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="ab315-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="ab315-140">Lägga till undantag för falska positiva resultat</span><span class="sxs-lookup"><span data-stu-id="ab315-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="ab315-141">Om minskningsregeln för attackytan blockerar något som den inte borde blockera (kallas även falsk positiv inställning) kan du lägga till undantag för att förhindra minskningsregler för attackytan från att utvärdera de undantagna filerna eller mapparna.</span><span class="sxs-lookup"><span data-stu-id="ab315-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="ab315-142">Mer information om hur du lägger till ett undantag finns [i Anpassa minskning av attackytan](customize-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="ab315-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="ab315-143">Du kan ange att enskilda filer och mappar ska undantas, men du kan inte ange enskilda regler.</span><span class="sxs-lookup"><span data-stu-id="ab315-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="ab315-144">Det innebär att filer eller mappar som är undantagna undantas från alla ASR-regler.</span><span class="sxs-lookup"><span data-stu-id="ab315-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="ab315-145">Rapportera ett falskt positivt eller falskt negativt värde</span><span class="sxs-lookup"><span data-stu-id="ab315-145">Report a false positive or false negative</span></span>

<span data-ttu-id="ab315-146">Använd det [webbaserade insändningsformuläret](https://www.microsoft.com/wdsi/filesubmission) i Windows Defender Security Intelligence om du vill rapportera ett falskt negativt eller falskt värde för nätverksskydd.</span><span class="sxs-lookup"><span data-stu-id="ab315-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="ab315-147">Med en Windows E5-prenumeration kan du också [skicka en länk till eventuell associerad avisering](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ab315-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="ab315-148">Samla in diagnostikdata för inskickade filer</span><span class="sxs-lookup"><span data-stu-id="ab315-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="ab315-149">När du rapporterar ett problem med minskningsregler för attackytan uppmanas du att samla in och skicka in diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem.</span><span class="sxs-lookup"><span data-stu-id="ab315-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="ab315-150">Öppna en upphöjd kommandotolk och ändra till Windows Defender-katalogen:</span><span class="sxs-lookup"><span data-stu-id="ab315-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="ab315-151">Kör det här kommandot för att generera diagnostikloggarna:</span><span class="sxs-lookup"><span data-stu-id="ab315-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="ab315-152">Som standard sparas de i `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="ab315-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="ab315-153">Bifoga filen i inskickat formulär.</span><span class="sxs-lookup"><span data-stu-id="ab315-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ab315-154">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ab315-154">Related articles</span></span>

- [<span data-ttu-id="ab315-155">Regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="ab315-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="ab315-156">Aktivera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="ab315-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="ab315-157">Utvärdera regler för minskning av attackytan</span><span class="sxs-lookup"><span data-stu-id="ab315-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
