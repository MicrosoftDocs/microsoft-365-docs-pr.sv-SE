---
title: Felsöka problem med nätverksskydd
description: Resurser och exempelkod för att felsöka problem med nätverksskydd i Microsoft Defender för slutpunkt.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844064"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="6a486-104">Felsöka nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="6a486-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6a486-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6a486-105">**Applies to:**</span></span>
- [<span data-ttu-id="6a486-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6a486-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6a486-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a486-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="6a486-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6a486-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6a486-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6a486-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="6a486-110">När du använder [nätverksskydd](network-protection.md) kan det uppstå problem, till exempel:</span><span class="sxs-lookup"><span data-stu-id="6a486-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="6a486-111">Nätverksskydd blockerar en webbplats som är säker (falsk positiv åtkomst)</span><span class="sxs-lookup"><span data-stu-id="6a486-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="6a486-112">Nätverksskydd blockerar inte misstänkta eller kända skadliga webbplatser (falskt negativt)</span><span class="sxs-lookup"><span data-stu-id="6a486-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="6a486-113">Det finns fyra steg för att felsöka dessa problem:</span><span class="sxs-lookup"><span data-stu-id="6a486-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="6a486-114">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="6a486-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="6a486-115">Använda granskningsläge för att testa regeln</span><span class="sxs-lookup"><span data-stu-id="6a486-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="6a486-116">Lägga till undantag för den angivna regeln (för falska positiva resultat)</span><span class="sxs-lookup"><span data-stu-id="6a486-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="6a486-117">Skicka supportloggar</span><span class="sxs-lookup"><span data-stu-id="6a486-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="6a486-118">Bekräfta förutsättningarna</span><span class="sxs-lookup"><span data-stu-id="6a486-118">Confirm prerequisites</span></span>

<span data-ttu-id="6a486-119">Nätverksskydd fungerar bara på enheter med följande villkor:</span><span class="sxs-lookup"><span data-stu-id="6a486-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="6a486-120">Slutpunkter körs med Windows 10 Pro Enterprise- eller Enterprise-version, version 1709 eller senare.</span><span class="sxs-lookup"><span data-stu-id="6a486-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="6a486-121">Slutpunkter använder Microsoft Defender Antivirus som den enda antivirusskyddsappen.</span><span class="sxs-lookup"><span data-stu-id="6a486-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="6a486-122">[Se vad som händer när du använder en antiviruslösning som inte är en Microsoft-lösning.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="6a486-122">[See what happens when you are using a non-Microsoft antivirus solution](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="6a486-123">[Realtidsskydd är](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a486-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="6a486-124">[Moln levererat skydd är](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a486-124">[Cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="6a486-125">Granskningsläge är inte aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a486-125">Audit mode is not enabled.</span></span> <span data-ttu-id="6a486-126">Använd [grupprincip för](enable-network-protection.md#group-policy) att ange att regeln ska **inaktiveras** (värde: **0**).</span><span class="sxs-lookup"><span data-stu-id="6a486-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="6a486-127">Använda granskningsläge</span><span class="sxs-lookup"><span data-stu-id="6a486-127">Use audit mode</span></span>

<span data-ttu-id="6a486-128">Du kan aktivera nätverksskydd i granskningsläge och sedan besöka en webbplats som vi har skapat för att nedgradera funktionen.</span><span class="sxs-lookup"><span data-stu-id="6a486-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="6a486-129">Alla webbplatsanslutningar tillåts av nätverksskydd, men en händelse loggas för att ange vilken anslutning som skulle ha blockerats om nätverksskyddet var aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6a486-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="6a486-130">Ange nätverksskydd som **Granskningsläge**.</span><span class="sxs-lookup"><span data-stu-id="6a486-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="6a486-131">Utför den anslutningsaktivitet som orsakar ett problem (försök till exempel gå till webbplatsen eller anslut till den IP-adress du vill eller inte vill blockera).</span><span class="sxs-lookup"><span data-stu-id="6a486-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="6a486-132">[Granska händelseloggarna för nätverksskydd](network-protection.md#review-network-protection-events-in-windows-event-viewer) för att se om funktionen skulle ha blockerat anslutningen om den hade angetts till **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="6a486-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="6a486-133">Om nätverksskyddet inte blockerar en anslutning som du förväntar dig bör den blockeras, aktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="6a486-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="6a486-134">Rapportera ett falskt positivt eller falskt negativt värde</span><span class="sxs-lookup"><span data-stu-id="6a486-134">Report a false positive or false negative</span></span>

<span data-ttu-id="6a486-135">Om du har testat funktionen med demowebbplatsen och med granskningsläge och nätverksskydd arbetar med förkonfigurerade scenarier, men inte fungerar som förväntat för en viss anslutning, kan du använda det webbaserade insändningsformuläret för [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) om du vill rapportera ett falskt negativt eller falskt positivt resultat för nätverksskydd.</span><span class="sxs-lookup"><span data-stu-id="6a486-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="6a486-136">Med en E5-prenumeration kan du också [skicka en länk till eventuell associerad avisering](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="6a486-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="6a486-137">Se [Adress: falska positiva/negativa i Microsoft Defender för Slutpunkt](defender-endpoint-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="6a486-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="6a486-138">Undanta webbplatsen från nätverkets skyddsområde</span><span class="sxs-lookup"><span data-stu-id="6a486-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="6a486-139">Om du vill tillåta att webbplatsen blockeras (falsk positiv inställning) lägger du till dess URL-adress i [listan med betrodda platser.](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/)</span><span class="sxs-lookup"><span data-stu-id="6a486-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="6a486-140">Webbresurser från den här listan kringgår kontrollen av nätverksskydd.</span><span class="sxs-lookup"><span data-stu-id="6a486-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="6a486-141">Samla in diagnostikdata för inskickade filer</span><span class="sxs-lookup"><span data-stu-id="6a486-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="6a486-142">När du rapporterar ett problem med nätverksskydd uppmanas du att samla in och skicka diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem.</span><span class="sxs-lookup"><span data-stu-id="6a486-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="6a486-143">Öppna en upphöjd kommandotolk och ändra i Windows Defender katalog:</span><span class="sxs-lookup"><span data-stu-id="6a486-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="6a486-144">Kör det här kommandot för att generera diagnostikloggarna:</span><span class="sxs-lookup"><span data-stu-id="6a486-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="6a486-145">Bifoga filen i inskickat formulär.</span><span class="sxs-lookup"><span data-stu-id="6a486-145">Attach the file to the submission form.</span></span> <span data-ttu-id="6a486-146">Som standard sparas diagnostikloggar på `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="6a486-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="6a486-147">Lösa anslutningsproblem med nätverksskydd (för E5-kunder)</span><span class="sxs-lookup"><span data-stu-id="6a486-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="6a486-148">På grund av miljön där nätverksskyddet körs kan Microsoft inte se dina proxyinställningar för operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="6a486-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="6a486-149">I vissa fall kan inte nätverksskyddsklienter nå molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="6a486-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="6a486-150">Lös anslutningsproblem med nätverksskydd genom att konfigurera en av följande registernycklar så att nätverksskyddet blir medvetna om proxykonfigurationen:</span><span class="sxs-lookup"><span data-stu-id="6a486-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="6a486-151">---ELLER---</span><span class="sxs-lookup"><span data-stu-id="6a486-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="6a486-152">Du kan konfigurera registernyckeln med hjälp av PowerShell, Microsoft Endpoint Manager eller grupprincip.</span><span class="sxs-lookup"><span data-stu-id="6a486-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="6a486-153">Här är några resurser som kan vara till hjälp:</span><span class="sxs-lookup"><span data-stu-id="6a486-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="6a486-154">Arbeta med registernycklar</span><span class="sxs-lookup"><span data-stu-id="6a486-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="6a486-155">Konfigurera anpassade klientinställningar för Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="6a486-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="6a486-156">Använda grupprincipinställningar för att hantera Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="6a486-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="6a486-157">Se även</span><span class="sxs-lookup"><span data-stu-id="6a486-157">See also</span></span>

- [<span data-ttu-id="6a486-158">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="6a486-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="6a486-159">Utvärdera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="6a486-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="6a486-160">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="6a486-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="6a486-161">Adressera falska positiva/negativa tal i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="6a486-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
