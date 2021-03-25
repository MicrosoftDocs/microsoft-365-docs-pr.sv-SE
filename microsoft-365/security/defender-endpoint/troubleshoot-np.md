---
title: Felsöka problem med nätverksskydd
description: Resurser och exempelkod för att felsöka problem med nätverksskydd i Microsoft Defender för slutpunkt.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 34bebddcf052a643529f1d2b8a8a869a0ffe4a91
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183831"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="a2ded-104">Felsöka nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="a2ded-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a2ded-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a2ded-105">**Applies to:**</span></span>
- [<span data-ttu-id="a2ded-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2ded-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a2ded-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2ded-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a2ded-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a2ded-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a2ded-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a2ded-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="a2ded-110">När du använder [nätverksskydd](network-protection.md) kan det uppstå problem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a2ded-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="a2ded-111">Nätverksskydd blockerar en webbplats som är säker (falsk positiv åtkomst)</span><span class="sxs-lookup"><span data-stu-id="a2ded-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="a2ded-112">Nätverksskydd blockerar inte misstänkta eller kända skadliga webbplatser (falskt negativt)</span><span class="sxs-lookup"><span data-stu-id="a2ded-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="a2ded-113">Det finns fyra steg för att felsöka dessa problem:</span><span class="sxs-lookup"><span data-stu-id="a2ded-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="a2ded-114">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="a2ded-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="a2ded-115">Använda granskningsläge för att testa regeln</span><span class="sxs-lookup"><span data-stu-id="a2ded-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="a2ded-116">Lägga till undantag för den angivna regeln (för falska positiva resultat)</span><span class="sxs-lookup"><span data-stu-id="a2ded-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="a2ded-117">Skicka supportloggar</span><span class="sxs-lookup"><span data-stu-id="a2ded-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="a2ded-118">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="a2ded-118">Confirm prerequisites</span></span>

<span data-ttu-id="a2ded-119">Nätverksskydd fungerar bara på enheter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="a2ded-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="a2ded-120">Slutpunkter kör Windows 10 Pro eller Enterprise, version 1709 eller senare.</span><span class="sxs-lookup"><span data-stu-id="a2ded-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="a2ded-121">Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen.</span><span class="sxs-lookup"><span data-stu-id="a2ded-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="a2ded-122">[Se vad som händer när du använder en antiviruslösning som inte är en Microsoft-lösning.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="a2ded-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="a2ded-123">[Realtidsskydd är](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a2ded-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="a2ded-124">[Moln levererat skydd är](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a2ded-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="a2ded-125">Granskningsläge är inte aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a2ded-125">Audit mode is not enabled.</span></span> <span data-ttu-id="a2ded-126">Använd [grupprincip för](enable-network-protection.md#group-policy) att ange att regeln ska **inaktiveras** (värde: **0**).</span><span class="sxs-lookup"><span data-stu-id="a2ded-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="a2ded-127">Använda granskningsläge</span><span class="sxs-lookup"><span data-stu-id="a2ded-127">Use audit mode</span></span>

<span data-ttu-id="a2ded-128">Du kan aktivera nätverksskydd i granskningsläge och sedan besöka en webbplats som vi har skapat för att nedgradera funktionen.</span><span class="sxs-lookup"><span data-stu-id="a2ded-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="a2ded-129">Alla webbplatsanslutningar tillåts av nätverksskydd, men en händelse loggas för att ange vilken anslutning som skulle ha blockerats om nätverksskyddet var aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a2ded-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="a2ded-130">Ange nätverksskydd som **Granskningsläge**.</span><span class="sxs-lookup"><span data-stu-id="a2ded-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="a2ded-131">Utför den anslutningsaktivitet som orsakar ett problem (försök till exempel gå till webbplatsen eller anslut till den IP-adress du vill eller inte vill blockera).</span><span class="sxs-lookup"><span data-stu-id="a2ded-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="a2ded-132">[Granska händelseloggarna för nätverksskydd](network-protection.md#review-network-protection-events-in-windows-event-viewer) för att se om funktionen skulle ha blockerat anslutningen om den hade angetts till **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="a2ded-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="a2ded-133">Om nätverksskyddet inte blockerar en anslutning som du förväntar dig bör den blockeras, aktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="a2ded-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="a2ded-134">Rapportera ett falskt positivt eller falskt negativt värde</span><span class="sxs-lookup"><span data-stu-id="a2ded-134">Report a false positive or false negative</span></span>

<span data-ttu-id="a2ded-135">Om du har testat funktionen med demowebbplatsen och med granskningsläge och nätverksskydd arbetar med förkonfigurerade scenarier, men inte fungerar som förväntat för en viss anslutning, kan du använda det webbaserade insändningsformuläret i [Windows Defender Säkerhetsinformation](https://www.microsoft.com/wdsi/filesubmission) för att rapportera ett falskt negativt eller falskt positivt resultat för nätverksskydd.</span><span class="sxs-lookup"><span data-stu-id="a2ded-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="a2ded-136">Med en E5-prenumeration kan du också [skicka en länk till eventuell associerad avisering](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="a2ded-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="a2ded-137">Se [Adress: falska positiva/negativa i Microsoft Defender för Slutpunkt](defender-endpoint-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="a2ded-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="a2ded-138">Undanta webbplatsen från nätverkets skyddsområde</span><span class="sxs-lookup"><span data-stu-id="a2ded-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="a2ded-139">Om du vill tillåta att webbplatsen blockeras (falsk positiv inställning) lägger du till dess URL-adress i [listan med betrodda platser.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="a2ded-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="a2ded-140">Webbresurser från den här listan kringgår kontrollen av nätverksskydd.</span><span class="sxs-lookup"><span data-stu-id="a2ded-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="a2ded-141">Samla in diagnostikdata för inskickade filer</span><span class="sxs-lookup"><span data-stu-id="a2ded-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="a2ded-142">När du rapporterar ett problem med nätverksskydd uppmanas du att samla in och skicka diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem.</span><span class="sxs-lookup"><span data-stu-id="a2ded-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="a2ded-143">Öppna en upphöjd kommandotolk och ändra till Windows Defender-katalogen:</span><span class="sxs-lookup"><span data-stu-id="a2ded-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="a2ded-144">Kör det här kommandot för att generera diagnostikloggarna:</span><span class="sxs-lookup"><span data-stu-id="a2ded-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="a2ded-145">Som standard sparas de i C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span><span class="sxs-lookup"><span data-stu-id="a2ded-145">By default, they are saved to C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span></span> <span data-ttu-id="a2ded-146">Bifoga filen i inskickat formulär.</span><span class="sxs-lookup"><span data-stu-id="a2ded-146">Attach the file to the submission form.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a2ded-147">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a2ded-147">Related topics</span></span>

- [<span data-ttu-id="a2ded-148">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="a2ded-148">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="a2ded-149">Utvärdera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="a2ded-149">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="a2ded-150">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="a2ded-150">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="a2ded-151">Adressera falska positiva/negativa tal i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="a2ded-151">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
