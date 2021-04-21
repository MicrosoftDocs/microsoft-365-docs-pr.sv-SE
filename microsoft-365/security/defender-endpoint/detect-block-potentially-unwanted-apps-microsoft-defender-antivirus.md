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
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904016"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="80f53-104">Identifiera och blockera potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="80f53-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80f53-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="80f53-105">**Applies to:**</span></span>

- [<span data-ttu-id="80f53-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="80f53-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="80f53-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80f53-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="80f53-108">Potentiellt oönskade program (PUA) är en kategori med programvara som kan få datorn att köras långsamt, visa oväntade annonser eller som i värsta fall kan installera annan programvara som kan vara oväntad eller oönskad.</span><span class="sxs-lookup"><span data-stu-id="80f53-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="80f53-109">PUA betraktas inte som ett virus, skadlig kod eller någon annan typ av hot, men den kan utföra åtgärder på slutpunkter som negativt påverkar slutpunktens prestanda eller användning.</span><span class="sxs-lookup"><span data-stu-id="80f53-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="80f53-110">Termen *PUA kan* också referera till ett program som har ett dåligt rykte, enligt Microsoft Defender för Endpoint, på grund av vissa typer av oönskat beteende.</span><span class="sxs-lookup"><span data-stu-id="80f53-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="80f53-111">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="80f53-111">Here are some examples:</span></span>

- <span data-ttu-id="80f53-112">**Reklamprogramvara** som visar annonser eller kampanjer, inklusive programvara som infogar annonser på webbsidor.</span><span class="sxs-lookup"><span data-stu-id="80f53-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="80f53-113">**Sammanslagning av programvara** som ger möjlighet att installera annan programvara som inte har signerats digitalt av samma enhet.</span><span class="sxs-lookup"><span data-stu-id="80f53-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="80f53-114">Dessutom programvara som ger möjlighet att installera annan programvara som är berättigad som PUA.</span><span class="sxs-lookup"><span data-stu-id="80f53-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="80f53-115">**Programvara av** en programvara som aktivt försöker undvika identifiering av säkerhetsprodukter, bland annat programvara som beter sig på olika sätt i närvaro av säkerhetsprodukter.</span><span class="sxs-lookup"><span data-stu-id="80f53-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="80f53-116">Fler exempel och en diskussion om de villkor vi använder för att märka program för särskild uppmärksamhet från säkerhetsfunktioner finns i Hur Microsoft identifierar skadlig programvara och potentiellt [oönskade program.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="80f53-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="80f53-117">Potentiellt oönskade program kan öka risken för att nätverket smittas med faktisk skadlig programvara, göra att skadlig programvara blir svårare att identifiera eller slösa PÅ IT-resurser i att rensa dem.</span><span class="sxs-lookup"><span data-stu-id="80f53-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="80f53-118">PUA-skydd stöds i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="80f53-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="80f53-119">I Windows 10 (version 2004 och senare) blockerar Microsoft Defender Antivirus appar som betraktas som PUA för Enterprise-enheter (E5) som standard.</span><span class="sxs-lookup"><span data-stu-id="80f53-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="80f53-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80f53-120">Microsoft Edge</span></span>

<span data-ttu-id="80f53-121">Nya [Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)som är Chromium-baserad, blockerar potentiellt oönskade programnedladdningar och tillhörande resurs-URL:er.</span><span class="sxs-lookup"><span data-stu-id="80f53-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="80f53-122">Den här funktionen tillhandahålls via [Microsoft Defender SmartScreen.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="80f53-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="80f53-123">Aktivera PUA-skydd i Chromium-baserade Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="80f53-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="80f53-124">Även om potentiellt oönskat programskydd i Microsoft Edge (Chromium-baserad version 80.0.361.50) är inaktiverat som standard kan det enkelt aktiveras från webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="80f53-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="80f53-125">Välj ellipsen i Edge-webbläsaren och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="80f53-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="80f53-126">Välj **Sekretess, sökning och tjänster.**</span><span class="sxs-lookup"><span data-stu-id="80f53-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="80f53-127">Aktivera Blockera **potentiellt** oönskade appar **under Säkerhet.**</span><span class="sxs-lookup"><span data-stu-id="80f53-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="80f53-128">Om du kör Microsoft Edge (Chromium-baserad) kan du tryggt utforska funktionen för URL-blockering av PUA-skydd genom att testa den på en av våra [Microsoft Defender SmartScreen-demosidor.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="80f53-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="80f53-129">Blockera URL-adresser med Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="80f53-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="80f53-130">I Chromium-baserad Edge med PUA-skydd aktiverat skyddar Microsoft Defender SmartScreen dig från PUA-associerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="80f53-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="80f53-131">Säkerhetsadministratörer kan [konfigurera hur](/DeployEdge/configure-microsoft-edge) Microsoft Edge och Microsoft Defender SmartScreen samarbetar för att skydda grupper av användare från PUA-associerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="80f53-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="80f53-132">Det finns flera [grupprincipinställningar för](/DeployEdge/microsoft-edge-policies#smartscreen-settings) Microsoft Defender SmartScreen tillgängliga, bland annat en [för att blockera PUA.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)</span><span class="sxs-lookup"><span data-stu-id="80f53-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="80f53-133">Dessutom kan administratörer konfigurera [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) som en helhet, med grupprincipinställningar för att aktivera eller inaktivera Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="80f53-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="80f53-134">Även om Microsoft Defender för Endpoint har en egen blockeringslista baserat på en datauppsättning som hanteras av Microsoft kan du anpassa den här listan baserat på din egen information om hot.</span><span class="sxs-lookup"><span data-stu-id="80f53-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="80f53-135">Om du [skapar och hanterar indikatorer](manage-indicators.md) i Microsoft Defender för slutpunktsportalen respekterar Microsoft Defender SmartScreen de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="80f53-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="80f53-136">Microsoft Defender Antivirus- och PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="80f53-137">Skyddsfunktionen för potentiellt oönskade program (PUA) i Microsoft Defender Antivirus kan identifiera och blockera PUA på slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="80f53-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="80f53-138">Den här funktionen är tillgänglig i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="80f53-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="80f53-139">Microsoft Defender Antivirus blockerar identifierade PUA-filer och alla försök att ladda ned, flytta, köra eller installera dem.</span><span class="sxs-lookup"><span data-stu-id="80f53-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="80f53-140">Blockerade PUA-filer flyttas sedan till karantän.</span><span class="sxs-lookup"><span data-stu-id="80f53-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="80f53-141">När en PUA-fil identifieras på en slutpunkt skickar Microsoft Defender Antivirus ett meddelande till användaren[(om](configure-notifications-microsoft-defender-antivirus.md)inte meddelanden har inaktiverats) i samma format som andra identifieringar av hot.</span><span class="sxs-lookup"><span data-stu-id="80f53-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="80f53-142">Meddelandet föregås av för `PUA:` att ange dess innehåll.</span><span class="sxs-lookup"><span data-stu-id="80f53-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="80f53-143">Meddelandet visas i den vanliga [karantänlistan i Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="80f53-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="80f53-144">Konfigurera PUA-skydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="80f53-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="80f53-145">Du kan aktivera PUA-skydd [med Microsoft Intune-,](/mem/intune/protect/device-protect)Microsoft Endpoint Configuration [Manager-, Grupprincip-](/azure/active-directory-domain-services/manage-group-policy)eller via [PowerShell-cmdlets.](/powershell/module/defender/?preserve-view=true&view=win10-ps) [](/mem/configmgr/protect/deploy-use/endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="80f53-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="80f53-146">Du kan också använda PUA-skydd i granskningsläge för att identifiera potentiellt oönskade program utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="80f53-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="80f53-147">Identifieringarna fångas i Händelseloggen i Windows.</span><span class="sxs-lookup"><span data-stu-id="80f53-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="80f53-148">Besök demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) du vill bekräfta att funktionen fungerar och se hur den fungerar.</span><span class="sxs-lookup"><span data-stu-id="80f53-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="80f53-149">PUA-skydd i granskningsläge är användbart om ditt företag genomför en intern säkerhetskontroll av programvarans efterlevnad och du vill undvika falska positiva resultat.</span><span class="sxs-lookup"><span data-stu-id="80f53-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="80f53-150">Använda Intune för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="80f53-151">Mer information finns i Konfigurera inställningar för enhetsbegränsningar i [Microsoft Intune](/intune/device-restrictions-configure) och Microsoft Defender Antivirus för [Windows 10 i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="80f53-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="80f53-152">Konfigurera PUA-skydd med Konfigurationshanteraren</span><span class="sxs-lookup"><span data-stu-id="80f53-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="80f53-153">PUA-skydd är aktiverat som standard i Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="80f53-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="80f53-154">Mer [information om hur du konfigurerar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="80f53-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="80f53-155">Information om System Center 2012 Configuration Manager finns i Distribuera potentiellt oönskad programskyddsprincip för [slutpunktsskydd i Konfigurationshanteraren.](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)</span><span class="sxs-lookup"><span data-stu-id="80f53-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="80f53-156">PUA-händelser som blockerats av Microsoft Defender Antivirus rapporteras i Windows loggboken och inte i Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="80f53-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="80f53-157">Använda grupprincip för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="80f53-158">Ladda ned och [installera administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="80f53-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="80f53-159">Öppna konsolen Grupprinciphantering på datorn [för grupprinciphantering.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="80f53-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="80f53-160">Markera det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="80f53-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="80f53-161">I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="80f53-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="80f53-162">Expandera trädet till **Windows-komponenter**  >  **Microsoft Defender Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="80f53-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="80f53-163">Dubbelklicka på Konfigurera **identifiering för potentiellt oönskade program.**</span><span class="sxs-lookup"><span data-stu-id="80f53-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="80f53-164">Välj **Aktiverad för** att aktivera PUA-skydd.</span><span class="sxs-lookup"><span data-stu-id="80f53-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="80f53-165">Välj **Blockera** för att **blockera potentiellt** oönskade program i Alternativ eller välj **Granskningsläge** för att testa hur inställningen fungerar i din miljö.</span><span class="sxs-lookup"><span data-stu-id="80f53-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="80f53-166">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="80f53-166">Select **OK**.</span></span>

9. <span data-ttu-id="80f53-167">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="80f53-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="80f53-168">Använda PowerShell-cmdlets för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="80f53-169">Aktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="80f53-170">Om du anger värdet för den här cmdleten `Enabled` aktiverar du funktionen om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="80f53-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="80f53-171">Så här ställer du in PUA-skydd till granskningsläge</span><span class="sxs-lookup"><span data-stu-id="80f53-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="80f53-172">Inställningen `AuditMode` identifierar PUA:er utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="80f53-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="80f53-173">Inaktivera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-173">To disable PUA protection</span></span>

<span data-ttu-id="80f53-174">Vi rekommenderar att du behåller PUA-skydd aktiverat.</span><span class="sxs-lookup"><span data-stu-id="80f53-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="80f53-175">Du kan dock inaktivera det med hjälp av följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="80f53-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="80f53-176">Om du anger värdet för den här cmdleten `Disabled` inaktiveras funktionen om den är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="80f53-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="80f53-177">Mer information finns i Använda [PowerShell-cmdlets för att konfigurera och köra cmdlets för Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender.](/powershell/module/defender/index)</span><span class="sxs-lookup"><span data-stu-id="80f53-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="80f53-178">Visa PUA-händelser med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="80f53-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="80f53-179">PUA-händelser rapporteras i Windows loggboken, men inte i Microsoft Endpoint Manager eller i Intune.</span><span class="sxs-lookup"><span data-stu-id="80f53-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="80f53-180">Du kan också använda `Get-MpThreat` cmdleten för att visa hot som Microsoft Defender Antivirus hanterat.</span><span class="sxs-lookup"><span data-stu-id="80f53-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="80f53-181">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="80f53-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="80f53-182">Få e-postaviseringar om PUA-identifieringar</span><span class="sxs-lookup"><span data-stu-id="80f53-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="80f53-183">Du kan aktivera e-postaviseringar för att ta emot e-post om PUA-identifieringar.</span><span class="sxs-lookup"><span data-stu-id="80f53-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="80f53-184">Mer [information om hur du visar antivirushändelser](troubleshoot-microsoft-defender-antivirus.md) i Microsoft Defender finns i Felsöka händelse-IDn.</span><span class="sxs-lookup"><span data-stu-id="80f53-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="80f53-185">PUA-händelser registreras under händelse-ID **1160.**</span><span class="sxs-lookup"><span data-stu-id="80f53-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="80f53-186">Visa PUA-händelser med avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="80f53-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="80f53-187">Om du använder [Microsoft Defender för Slutpunkt kan du använda](microsoft-defender-endpoint.md)en avancerad fråga för att visa PUA-händelser.</span><span class="sxs-lookup"><span data-stu-id="80f53-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="80f53-188">Här är en exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="80f53-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="80f53-189">Mer information om avancerad sökning finns i [Proaktivt sök efter hot med avancerad sökning.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="80f53-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="80f53-190">Undanta filer från PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="80f53-191">Ibland är en fil felaktigt blockerad av PUA-skydd eller så krävs en funktion i en PUA för att slutföra en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="80f53-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="80f53-192">I sådana fall kan en fil läggas till i en undantagslista.</span><span class="sxs-lookup"><span data-stu-id="80f53-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="80f53-193">Mer information finns i [Konfigurera och validera undantag baserat på filtillägg och mappplats.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="80f53-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80f53-194">Se även</span><span class="sxs-lookup"><span data-stu-id="80f53-194">See also</span></span>

- [<span data-ttu-id="80f53-195">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="80f53-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="80f53-196">Konfigurera skydd för beteende, heuristisk och realtid</span><span class="sxs-lookup"><span data-stu-id="80f53-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)