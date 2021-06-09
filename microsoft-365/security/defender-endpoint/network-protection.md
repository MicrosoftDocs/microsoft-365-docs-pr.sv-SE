---
title: Använda nätverksskydd för att förhindra anslutningar till dåliga webbplatser
description: Skydda nätverket genom att hindra användare från att komma åt kända skadliga och misstänkta nätverksadresser
keywords: Nätverksskydd, sårbarheter, skadlig webbplats, ip, domän, domäner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844268"
---
# <a name="protect-your-network"></a><span data-ttu-id="fd6a0-104">Skydda ditt nätverk</span><span class="sxs-lookup"><span data-stu-id="fd6a0-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fd6a0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fd6a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="fd6a0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fd6a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fd6a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd6a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fd6a0-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fd6a0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fd6a0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="fd6a0-110">Nätverksskydd hjälper till att minska enheternas attackytor från Internetbaserade händelser.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="fd6a0-111">Det förhindrar anställda att använda något program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="fd6a0-112">Nätverksskydd utökar omfattningen av [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för att blockera all utgående HTTP-trafik som försöker ansluta till berykande källor med låg rykte (baserat på domän eller värdnamn).</span><span class="sxs-lookup"><span data-stu-id="fd6a0-112">Network protection expands the scope of [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="fd6a0-113">Nätverksskydd stöds i alla Windows, med början från Windows 10 version 1709.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="fd6a0-114">Nätverksskydd stöds ännu inte på andra operativsystem, men webbskydd stöds med den nya Microsoft Edge baserat på Chromium.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="fd6a0-115">Mer information finns i [Webbskydd](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fd6a0-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="fd6a0-116">Nätverksskydd utökar skyddet i [webbskyddet](web-protection-overview.md) till operativsystemets nivå.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="fd6a0-117">Det ger webbskyddsfunktioner i Microsoft Edge till andra webbläsare som stöds och program som inte är webbläsarbaserade.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="fd6a0-118">Dessutom tillhandahåller nätverksskydd synlighet och blockering av indikatorer på intrång (IOCs) när de används med identifiering och [svar av slutpunkter.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="fd6a0-119">Till exempel fungerar nätverksskydd med dina [anpassade indikatorer](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="fd6a0-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="fd6a0-120">Mer information om hur du aktiverar nätverksskydd finns [i Aktivera nätverksskydd.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="fd6a0-121">Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="fd6a0-122">Se testfältwebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur nätverksskyddet fungerar.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-122">See the Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="fd6a0-123">Nätverksskyddet fungerar bäst med [Microsoft Defender](microsoft-defender-endpoint.md)för Endpoint , som ger dig detaljerad rapportering om sårbarhetsskyddshändelser och -block som en del av scenarier [för aviseringsundersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="fd6a0-124">När nätverksskydd blockerar en anslutning visas ett meddelande från Åtgärdscenter.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="fd6a0-125">Ditt säkerhetsteam kan [anpassa meddelandet](customize-attack-surface-reduction.md#customize-the-notification) med organisationens information och kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="fd6a0-126">Dessutom kan regler för att minska attackytan aktiveras och anpassas så att de passar vissa tekniker att övervaka.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="fd6a0-127">Du kan också använda [granskningsläge](audit-windows-defender.md) för att utvärdera hur nätverksskydd skulle påverka organisationen om det var aktiverat.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd6a0-128">Krav</span><span class="sxs-lookup"><span data-stu-id="fd6a0-128">Requirements</span></span>

<span data-ttu-id="fd6a0-129">Nätverksskydd kräver Windows 10 Pro företag och Microsoft Defender Antivirus i realtidsskydd.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="fd6a0-130">Windows version</span><span class="sxs-lookup"><span data-stu-id="fd6a0-130">Windows version</span></span> | <span data-ttu-id="fd6a0-131">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="fd6a0-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="fd6a0-132">Windows 10 version 1709 eller senare</span><span class="sxs-lookup"><span data-stu-id="fd6a0-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="fd6a0-133">Windows Server 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="fd6a0-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="fd6a0-134">[Microsoft Defender Antivirus realtidsskydd och](configure-real-time-protection-microsoft-defender-antivirus.md) moln [levererat skydd måste](enable-cloud-protection-microsoft-defender-antivirus.md) vara aktiverat</span><span class="sxs-lookup"><span data-stu-id="fd6a0-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="fd6a0-135">När du har aktiverat tjänsterna kan du behöva konfigurera nätverket eller brandväggen så att anslutningarna mellan tjänsterna och dina enheter tillåts (kallas även slutpunkter).</span><span class="sxs-lookup"><span data-stu-id="fd6a0-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="fd6a0-136">Granska nätverksskyddshändelser i Microsoft Defender för Endpoint Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="fd6a0-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="fd6a0-137">Microsoft Defender för Endpoint tillhandahåller detaljerad rapportering om händelser och block som en del av dess scenarier [för aviseringsundersökning.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="fd6a0-138">Du kan fråga Microsoft Defender efter slutpunktsdata med hjälp av [avancerad sökning.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="fd6a0-139">Om du använder granskningsläge [kan du](audit-windows-defender.md)använda avancerad sökning för att se hur inställningarna för nätverksskydd skulle påverka din miljö om de var aktiverade.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="fd6a0-140">Här är en exempelfråga</span><span class="sxs-lookup"><span data-stu-id="fd6a0-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="fd6a0-141">Granska nätverksskyddshändelser i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="fd6a0-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="fd6a0-142">Du kan granska Windows om du vill se händelser som skapas när nätverksskydd blockerar (eller granskar) åtkomst till en skadlig IP eller domän:</span><span class="sxs-lookup"><span data-stu-id="fd6a0-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="fd6a0-143">[Kopiera XML-filen direkt.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="fd6a0-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="fd6a0-144">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-144">Select **OK**.</span></span>

<span data-ttu-id="fd6a0-145">Den här proceduren skapar en anpassad vy som filtrerar för att bara visa följande händelser relaterade till nätverksskydd:</span><span class="sxs-lookup"><span data-stu-id="fd6a0-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="fd6a0-146">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="fd6a0-146">Event ID</span></span> | <span data-ttu-id="fd6a0-147">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fd6a0-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="fd6a0-148">5007</span><span class="sxs-lookup"><span data-stu-id="fd6a0-148">5007</span></span> | <span data-ttu-id="fd6a0-149">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="fd6a0-149">Event when settings are changed</span></span> |
| <span data-ttu-id="fd6a0-150">1125</span><span class="sxs-lookup"><span data-stu-id="fd6a0-150">1125</span></span> | <span data-ttu-id="fd6a0-151">Händelse när nätverksskydd aktiveras i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="fd6a0-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="fd6a0-152">1126</span><span class="sxs-lookup"><span data-stu-id="fd6a0-152">1126</span></span> | <span data-ttu-id="fd6a0-153">Händelse när nätverksskyddet utbrandar i blockläge</span><span class="sxs-lookup"><span data-stu-id="fd6a0-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="fd6a0-154">Att tänka på Windows virtuella skrivbordet som Windows 10 Enterprise flersession</span><span class="sxs-lookup"><span data-stu-id="fd6a0-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="fd6a0-155">Tänk på Windows 10 Enterprise funktioner för flera användare:</span><span class="sxs-lookup"><span data-stu-id="fd6a0-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="fd6a0-156">Nätverksskydd är en funktion för hela enheten och kan inte riktas till specifika användarsessioner.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="fd6a0-157">Principer för filtrering av webbinnehåll är också enhetsomfattande.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="fd6a0-158">Om du behöver skilja mellan användargrupper kan du skapa separata Windows för virtuella skrivbord som värd för pooler och tilldelningar.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="fd6a0-159">Testa nätverksskydd i granskningsläge för att bedöma dess beteende innan det lanseras.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="fd6a0-160">Överväg att ändra distributionen om du har ett stort antal användare eller ett stort antal sessioner för flera användare.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="fd6a0-161">Alternativt alternativ för nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fd6a0-161">Alternative option for network protection</span></span>

<span data-ttu-id="fd6a0-162">För Windows 10 Enterprise flersession 1909 och uppåt, och används i Windows Virtual Desktop i Azure, kan nätverksskydd för Microsoft Edge aktiveras med följande metod:</span><span class="sxs-lookup"><span data-stu-id="fd6a0-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="fd6a0-163">Använd [Aktivera nätverksskydd och](enable-network-protection.md) följ instruktionerna för att tillämpa principen.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="fd6a0-164">Utför följande PowerShell-kommando: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="fd6a0-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="fd6a0-165">Felsökning av nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fd6a0-165">Network protection troubleshooting</span></span>

<span data-ttu-id="fd6a0-166">På grund av miljön där Network Protection körs kanske Microsoft inte kan identifiera proxyinställningar för operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="fd6a0-167">I vissa fall kan inte nätverksskyddsklienter nå molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="fd6a0-168">För att lösa anslutningsproblem bör kunder med E5-licenser konfigurera någon av följande Defender-registernycklar:</span><span class="sxs-lookup"><span data-stu-id="fd6a0-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="fd6a0-169">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="fd6a0-169">Related articles</span></span>

- <span data-ttu-id="fd6a0-170">[Utvärdera |](evaluate-network-protection.md) Utför ett snabbt scenario som visar hur funktionen fungerar och vilka händelser som normalt skulle skapas.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="fd6a0-171">[Aktivera nätverksskydd](enable-network-protection.md) | Använd grupprinciper, PowerShell och MDM-CSP:er för att aktivera och hantera nätverksskydd i nätverket.</span><span class="sxs-lookup"><span data-stu-id="fd6a0-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
