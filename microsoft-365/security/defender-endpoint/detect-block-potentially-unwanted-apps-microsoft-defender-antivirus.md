---
title: Blockera potentiellt oönskade program med Microsoft Defender Antivirus
description: Aktivera den potentiellt oönskade antivirusfunktionen (PUA) för att blockera oönskad programvara som reklamprogram.
keywords: pua, aktivera, oönskad programvara, oönskade appar, reklamprogram, webbläsarverktygsfält, identifiera, blockera, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 20d4767f9813b741c55109d617f78302feaa0f7e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765029"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="a240e-104">Identifiera och blockera potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="a240e-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a240e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a240e-105">**Applies to:**</span></span>

- [<span data-ttu-id="a240e-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a240e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="a240e-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a240e-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="a240e-108">Potentiellt oönskade program (PUA) är en kategori av programvara som kan få datorn att köras långsamt, visa oväntade annonser eller i värsta fall installera annan programvara som kan vara oväntad eller oönskad.</span><span class="sxs-lookup"><span data-stu-id="a240e-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="a240e-109">Som standard i Windows 10 (version 2004 och senare) blockerar Microsoft Defender Antivirus appar som anses vara PUA-enheter för Enterprise-enheter (E5).</span><span class="sxs-lookup"><span data-stu-id="a240e-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="a240e-110">Potentiellt oönskade program (PUA) betraktas inte som virus, skadlig programvara eller andra typer av hot, men de kan utföra åtgärder på slutpunkter som negativt påverkar slutpunktens prestanda eller användning.</span><span class="sxs-lookup"><span data-stu-id="a240e-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="a240e-111">_PUA_ kan också hänvisa till ett program som har ett dåligt rykte, enligt Microsoft Defender för Endpoint, på grund av vissa typer av oönskat beteende.</span><span class="sxs-lookup"><span data-stu-id="a240e-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="a240e-112">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="a240e-112">Here are some examples:</span></span>

- <span data-ttu-id="a240e-113">**Reklamprogramvara** som visar annonser eller kampanjer, inklusive programvara som infogar annonser på webbsidor.</span><span class="sxs-lookup"><span data-stu-id="a240e-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="a240e-114">**Sammanslagning av programvara** som ger möjlighet att installera annan programvara som inte har signerats digitalt av samma enhet.</span><span class="sxs-lookup"><span data-stu-id="a240e-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="a240e-115">Dessutom programvara som kan installera annan programvara som kan anses vara PUA.</span><span class="sxs-lookup"><span data-stu-id="a240e-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="a240e-116">**Programvara av** en programvara som aktivt försöker undvika identifiering av säkerhetsprodukter, bland annat programvara som beter sig på olika sätt i närvaro av säkerhetsprodukter.</span><span class="sxs-lookup"><span data-stu-id="a240e-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="a240e-117">Fler exempel och en diskussion om de villkor vi använder för att märka program för särskild uppmärksamhet från säkerhetsfunktioner finns i Hur Microsoft identifierar skadlig programvara och potentiellt [oönskade program.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="a240e-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="a240e-118">Potentiellt oönskade program kan öka risken för att nätverket smittas med faktisk skadlig programvara, göra att skadlig programvara blir svårare att identifiera eller slösa PÅ IT-resurser i att rensa dem.</span><span class="sxs-lookup"><span data-stu-id="a240e-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="a240e-119">PUA-skydd stöds i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a240e-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="a240e-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a240e-120">Microsoft Edge</span></span>

<span data-ttu-id="a240e-121">Nya [Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)som är Chromium-baserad, blockerar potentiellt oönskade programnedladdningar och tillhörande resurs-URL:er.</span><span class="sxs-lookup"><span data-stu-id="a240e-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="a240e-122">Den här funktionen tillhandahålls via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="a240e-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="a240e-123">Aktivera PUA-skydd i Chromium-baserade Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a240e-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="a240e-124">Även om potentiellt oönskat programskydd i Microsoft Edge (Chromium-baserad version 80.0.361.50) är inaktiverat som standard kan det enkelt aktiveras från webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="a240e-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="a240e-125">Välj ellipsen och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a240e-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="a240e-126">Välj **Sekretess, sökning och tjänster.**</span><span class="sxs-lookup"><span data-stu-id="a240e-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="a240e-127">Aktivera Blockera **potentiellt** oönskade appar **under Säkerhet.**</span><span class="sxs-lookup"><span data-stu-id="a240e-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="a240e-128">Om du kör Microsoft Edge (Chromium-baserad) kan du tryggt utforska funktionen för URL-blockering av PUA-skydd genom att testa den på en av våra [Microsoft Defender SmartScreen-demosidor.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="a240e-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="a240e-129">Blockera URL-adresser med Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="a240e-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="a240e-130">I Chromium-baserad Edge med PUA-skydd aktiverat skyddar Microsoft Defender SmartScreen dig från PUA-associerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="a240e-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="a240e-131">Säkerhetsadministratörer kan [konfigurera hur](/DeployEdge/configure-microsoft-edge) Microsoft Edge och Microsoft Defender SmartScreen samarbetar för att skydda grupper av användare från PUA-associerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="a240e-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="a240e-132">Det finns flera [grupprincipinställningar för](/DeployEdge/microsoft-edge-policies#smartscreen-settings) Microsoft Defender SmartScreen tillgängliga, bland annat en [för att blockera PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="a240e-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="a240e-133">Dessutom kan administratörer konfigurera [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) som en helhet, med grupprincipinställningar för att aktivera eller inaktivera Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="a240e-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="a240e-134">Även om Microsoft Defender för Endpoint har en egen blockeringslista baserat på en datauppsättning som hanteras av Microsoft kan du anpassa den här listan baserat på din egen information om hot.</span><span class="sxs-lookup"><span data-stu-id="a240e-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="a240e-135">Om du [skapar och hanterar indikatorer](/microsoft-365/security/defender-endpoint/manage-indicators) i Microsoft Defender för slutpunktsportalen respekterar Microsoft Defender SmartScreen de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="a240e-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="a240e-136">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a240e-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a240e-137">Skyddsfunktionen för potentiellt oönskade program (PUA) i Microsoft Defender Antivirus kan identifiera och blockera PUA-program på slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="a240e-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="a240e-138">Den här funktionen är tillgänglig i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a240e-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="a240e-139">Microsoft Defender Antivirus blockerar identifierade PUA-filer och alla försök att ladda ned, flytta, köra eller installera dem.</span><span class="sxs-lookup"><span data-stu-id="a240e-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="a240e-140">Blockerade PUA-filer flyttas sedan till karantän.</span><span class="sxs-lookup"><span data-stu-id="a240e-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="a240e-141">När en PUA-fil identifieras på en slutpunkt skickar Microsoft Defender Antivirus ett meddelande till användaren[(om](configure-notifications-microsoft-defender-antivirus.md)inte meddelanden har inaktiverats) i samma format som andra identifieringar av hot.</span><span class="sxs-lookup"><span data-stu-id="a240e-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="a240e-142">Meddelandet föregås av för `PUA:` att ange dess innehåll.</span><span class="sxs-lookup"><span data-stu-id="a240e-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="a240e-143">Meddelandet visas i den vanliga [karantänlistan i Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a240e-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="a240e-144">Konfigurera PUA-skydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a240e-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a240e-145">Du kan aktivera PUA-skydd [med Microsoft Intune-,](/mem/intune/protect/device-protect)Microsoft Endpoint Configuration [Manager-, Grupprincip-](/azure/active-directory-domain-services/manage-group-policy)eller via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps) [](/mem/configmgr/protect/deploy-use/endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="a240e-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="a240e-146">Du kan också använda PUA-skydd i granskningsläge för att identifiera potentiellt oönskade program utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="a240e-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="a240e-147">Identifieringarna fångas i Händelseloggen i Windows.</span><span class="sxs-lookup"><span data-stu-id="a240e-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="a240e-148">Besök demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) du vill bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="a240e-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="a240e-149">PUA-skydd i granskningsläge är användbart om ditt företag genomför en intern säkerhetskontroll av programvarans efterlevnad och du vill undvika falska positiva resultat.</span><span class="sxs-lookup"><span data-stu-id="a240e-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="a240e-150">Använda Intune för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="a240e-151">Mer information finns i Konfigurera inställningar för enhetsbegränsningar i [Microsoft Intune](/intune/device-restrictions-configure) och Microsoft Defender Antivirus för [Windows 10 i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="a240e-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="a240e-152">Konfigurera PUA-skydd med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="a240e-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="a240e-153">PUA-skydd är aktiverat som standard i Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="a240e-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a240e-154">Mer [information om hur du konfigurerar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="a240e-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a240e-155">Information om System Center 2012 Configuration Manager finns i Distribuera potentiellt oönskad programskyddsprincip för [slutpunktsskydd i Konfigurationshanteraren.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)</span><span class="sxs-lookup"><span data-stu-id="a240e-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="a240e-156">PUA-händelser som blockerats av Microsoft Defender Antivirus rapporteras i Windows loggboken och inte i Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a240e-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="a240e-157">Använda grupprincip för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="a240e-158">Ladda ned och [installera administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="a240e-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="a240e-159">Öppna konsolen Grupprinciphantering på datorn [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="a240e-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="a240e-160">Markera det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="a240e-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="a240e-161">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="a240e-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="a240e-162">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="a240e-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="a240e-163">Dubbelklicka på Konfigurera **identifiering för potentiellt oönskade program.**</span><span class="sxs-lookup"><span data-stu-id="a240e-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="a240e-164">Välj **Aktiverad för** att aktivera PUA-skydd.</span><span class="sxs-lookup"><span data-stu-id="a240e-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="a240e-165">Välj **Blockera** för att **blockera potentiellt** oönskade program i Alternativ eller välj **Granskningsläge** för att testa hur inställningen fungerar i din miljö.</span><span class="sxs-lookup"><span data-stu-id="a240e-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="a240e-166">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="a240e-166">Select **OK**.</span></span>

9. <span data-ttu-id="a240e-167">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="a240e-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="a240e-168">Använda PowerShell-cmdlets för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="a240e-169">Aktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="a240e-170">Om du ställer in värdet för den här cmdleten `Enabled` till aktiverar du funktionen om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="a240e-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="a240e-171">Så här ställer du in PUA-skydd till granskningsläge</span><span class="sxs-lookup"><span data-stu-id="a240e-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="a240e-172">Inställningen `AuditMode` identifierar PUA:er utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="a240e-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="a240e-173">Inaktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-173">To disable PUA protection</span></span>

<span data-ttu-id="a240e-174">Vi rekommenderar att du behåller PUA-skydd aktiverat.</span><span class="sxs-lookup"><span data-stu-id="a240e-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="a240e-175">Du kan dock inaktivera det med hjälp av följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a240e-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="a240e-176">Om du anger värdet för den här cmdleten `Disabled` inaktiveras funktionen om den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="a240e-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="a240e-177">Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="a240e-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="a240e-178">Visa PUA-händelser</span><span class="sxs-lookup"><span data-stu-id="a240e-178">View PUA events</span></span>

<span data-ttu-id="a240e-179">PUA-händelser rapporteras i Windows loggboken, men inte i Microsoft Endpoint Manager eller i Intune.</span><span class="sxs-lookup"><span data-stu-id="a240e-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="a240e-180">Du kan också använda `Get-MpThreat` cmdleten för att visa hot som Microsoft Defender Antivirus hanterat.</span><span class="sxs-lookup"><span data-stu-id="a240e-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="a240e-181">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a240e-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="a240e-182">Du kan aktivera e-postaviseringar för att ta emot e-post om PUA-identifieringar.</span><span class="sxs-lookup"><span data-stu-id="a240e-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="a240e-183">Mer [information om hur du visar antivirushändelser](troubleshoot-microsoft-defender-antivirus.md) i Microsoft Defender finns i Felsöka händelse-IDn.</span><span class="sxs-lookup"><span data-stu-id="a240e-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="a240e-184">PUA-händelser registreras under händelse-ID **1160.**</span><span class="sxs-lookup"><span data-stu-id="a240e-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="a240e-185">Exklusive filer</span><span class="sxs-lookup"><span data-stu-id="a240e-185">Excluding files</span></span>

<span data-ttu-id="a240e-186">Ibland är en fil felaktigt blockerad av PUA-skydd eller så krävs en funktion i en PUA för att slutföra en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="a240e-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="a240e-187">I sådana fall kan en fil läggas till i en undantagslista.</span><span class="sxs-lookup"><span data-stu-id="a240e-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="a240e-188">Mer information finns i [Konfigurera och validera undantag baserat på filtillägg och mappplats.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a240e-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a240e-189">Se även</span><span class="sxs-lookup"><span data-stu-id="a240e-189">See also</span></span>

- [<span data-ttu-id="a240e-190">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="a240e-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a240e-191">Konfigurera behavioruellt, heuristiskt och realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="a240e-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)