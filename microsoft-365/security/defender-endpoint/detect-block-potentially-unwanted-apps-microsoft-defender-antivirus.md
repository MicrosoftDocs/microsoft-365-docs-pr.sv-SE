---
title: Blockera potentiellt oönskade program med Microsoft Defender Antivirus
description: Aktivera antivirusfunktionen för potentiellt oönskade program (PUA) för att blockera oönskad programvara som adware.
keywords: pua, aktivera, oönskad programvara, oönskade appar, adware, webbläsarverktygsfält, identifiera, blockera, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275246"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="24480-104">Identifiera och blockera potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="24480-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24480-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="24480-105">**Applies to:**</span></span>

- [<span data-ttu-id="24480-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="24480-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="24480-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="24480-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="24480-108">PUA (Potentially unwanted applications) är en kategori av program som kan göra att datorn körs långsamt, visa oväntade annonser eller, i värsta fall, installera andra program som kan vara oväntade eller oönskade.</span><span class="sxs-lookup"><span data-stu-id="24480-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="24480-109">PUA anses inte vara ett virus, skadlig programvara eller någon annan typ av hot, men den kan utföra åtgärder på slutpunkter som negativt påverkar slutpunktens prestanda eller användning.</span><span class="sxs-lookup"><span data-stu-id="24480-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="24480-110">Termen *PUA* kan också referera till ett program med dålig rykte, enligt Microsoft Defender för Endpoint, på grund av vissa typer av oönskat beteende.</span><span class="sxs-lookup"><span data-stu-id="24480-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="24480-111">Här är några exempel:</span><span class="sxs-lookup"><span data-stu-id="24480-111">Here are some examples:</span></span>

- <span data-ttu-id="24480-112">**Reklamprogram** som visar annonser eller kampanjer, inklusive programvara som infogar annonser till webbsidor.</span><span class="sxs-lookup"><span data-stu-id="24480-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="24480-113">**Sammanslagning av programvara** som ger möjlighet att installera annan programvara som inte har signerats digitalt av samma entitet.</span><span class="sxs-lookup"><span data-stu-id="24480-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="24480-114">Dessutom programvara som erbjuder installation av annan programvara som räknas som PUA.</span><span class="sxs-lookup"><span data-stu-id="24480-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="24480-115">**Undvikande programvara** som aktivt försöker undvika identifiering av säkerhetsprodukter, inklusive programvara som beter sig annorlunda i närvaro av säkerhetsprodukter.</span><span class="sxs-lookup"><span data-stu-id="24480-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="24480-116">Fler exempel och en diskussion om de kriterier vi använder för att märka program för särskild uppmärksamhet från säkerhetsfunktioner finns i [Hur Microsoft identifierar skadlig programvara och potentiellt oönskade program](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="24480-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="24480-117">Potentiellt oönskade program kan öka risken att nätverket smittas med skadlig programvara, göra det svårare att identifiera skadlig programvara eller slösa IT-resurser på att städa upp dem.</span><span class="sxs-lookup"><span data-stu-id="24480-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="24480-118">PUA-skydd stöds i Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="24480-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="24480-119">I Windows 10 (version 2004 och senare) blockerar Microsoft Defender Antivirus appar som anses vara PUA för företagsenheter (E5) som standard.</span><span class="sxs-lookup"><span data-stu-id="24480-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="24480-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="24480-120">Microsoft Edge</span></span>

<span data-ttu-id="24480-121">Den [nya Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), som är Chromium-baserad, blockerar potentiellt oönskade programnedladdningar och associerade resurs-URL:er.</span><span class="sxs-lookup"><span data-stu-id="24480-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="24480-122">Den här funktionen tillhandahålls via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="24480-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="24480-123">Aktivera PUA-skydd i Chromium-baserad Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="24480-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="24480-124">Även om skydd mot potentiellt oönskat program i Microsoft Edge (Chromium-baserat, version 80.0.361.50) är inaktiverat som standard kan det enkelt aktiveras från webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="24480-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="24480-125">Välj ellipsen i din Edge-webbläsaren och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="24480-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="24480-126">Välj **sekretess, sökning och tjänster**.</span><span class="sxs-lookup"><span data-stu-id="24480-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="24480-127">Under avsnittet **Säkerhet** aktiverar du **Blockera potentiellt oönskade program**.</span><span class="sxs-lookup"><span data-stu-id="24480-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="24480-128">Om du kör Microsoft Edge (Chromium-baserat) kan du utforska URL-blockeringsfunktionen i PUA-skydd genom att testa den på någon av våra [Microsoft Defender SmartScreen-demosidor](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="24480-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="24480-129">Blockera URL-adresser med Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="24480-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="24480-130">I den Chromium-baserade Edge-webbläsaren med PUA-skydd aktiverat skyddar Microsoft Defender SmartScreen dig från PUA-associerade URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="24480-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="24480-131">Säkerhetsadministratörer kan [konfigurera](/DeployEdge/configure-microsoft-edge) hur Microsoft Edge och Microsoft Defender SmartScreen fungerar tillsammans för att skydda användargrupper från PUA-associerade URL:er.</span><span class="sxs-lookup"><span data-stu-id="24480-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="24480-132">Det finns flera [grupprincipinställningar](/DeployEdge/microsoft-edge-policies#smartscreen-settings) som är uttryckligen tillgängliga för Microsoft Defender SmartScreen, inklusive en [för att blockera PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="24480-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="24480-133">Dessutom kan administratörer [konfigurera Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) som helhet, och med hjälp av grupprincipinställningar, aktivera eller inaktivera Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="24480-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="24480-134">Även om Microsoft Defender för Endpoint har en egen blockeringslista baserat på en datauppsättning som hanteras av Microsoft kan du anpassa listan baserat på egen information om hot.</span><span class="sxs-lookup"><span data-stu-id="24480-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="24480-135">Om du [skapar och hanterar indikatorer](manage-indicators.md) i Microsoft Defender för Endpoint-portalen respekterar Microsoft Defender SmartScreen de nya inställningarna.</span><span class="sxs-lookup"><span data-stu-id="24480-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="24480-136">Microsoft Defender Antivirus och PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="24480-137">Skyddsfunktionen för de potentiellt oönskade programmen i Microsoft Defender Antivirus kan identifiera och blockera PUA på slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="24480-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="24480-138">Den här funktionen finns för Windows 10, Windows Server 2019 och Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="24480-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="24480-139">Microsoft Defender Antivirus blockerar identifierade PUA-filer och alla försök att hämta, flytta, köra eller installera dem.</span><span class="sxs-lookup"><span data-stu-id="24480-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="24480-140">Blockerade PUA-filer flyttas sedan till karantän.</span><span class="sxs-lookup"><span data-stu-id="24480-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="24480-141">När en PUA-fil identifieras på en slutpunkt skickar Microsoft Defender Antivirus ett meddelande till användaren ([om inte aviseringar har inaktiverats](configure-notifications-microsoft-defender-antivirus.md)) i samma format som andra hotidentifieringar.</span><span class="sxs-lookup"><span data-stu-id="24480-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="24480-142">Meddelandet föregås av `PUA:` för att ange innehållet.</span><span class="sxs-lookup"><span data-stu-id="24480-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="24480-143">Meddelandet visas i den vanliga [-karantänlistan i Windows säkerhet-appen](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="24480-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="24480-144">Konfigurera PUA-skydd i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="24480-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="24480-145">Du kan aktivera PUA-skydd med [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Grupprincip](/azure/active-directory-domain-services/manage-group-policy) eller via [PowerShell-cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="24480-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="24480-146">Du kan också använda PUA-skydd i granskningsläge för att identifiera potentiellt oönskade program utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="24480-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="24480-147">Identifieringarna fångas i Windows-händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="24480-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="24480-148">Besök demowebbplatsen Microsoft Defender för Endpoint på [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) för att bekräfta att funktionen fungerar och se den i aktion.</span><span class="sxs-lookup"><span data-stu-id="24480-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="24480-149">PUA-skydd i granskningsläge är användbart om företaget utför en intern efterlevnadskontroll av programvarusäkerhet och du vill undvika falska positiva fel.</span><span class="sxs-lookup"><span data-stu-id="24480-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="24480-150">Använda Intune för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="24480-151">För mer information läs [Konfigurera inställningar för enhetsbegränsning i Microsoft Intune](/intune/device-restrictions-configure) och [Inställningar för enhetsbegränsning för Microsoft Defender i Windows 10 i Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="24480-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="24480-152">Använda konfigurationshanteraren för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="24480-153">PUA-skydd är aktiverat som standard i Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="24480-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="24480-154">För information om hur du konfigurerar Microsoft Endpoint Manager (Current Branch) läs [Hur du skapar och distribuerar principer för skadlig programvara: Schemalagda genomsökningsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings).</span><span class="sxs-lookup"><span data-stu-id="24480-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="24480-155">Information om konfigurationshanteraren för System Center 2012 finns i [Hur du distribuerar skyddsprincip för potentiellt oönskad program för Endpoint i Konfigurationshanteraren](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="24480-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="24480-156">PUA-händelser som blockerats av Microsoft Defender Antivirus rapporteras i Windows Loggboken och inte i Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="24480-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="24480-157">Använda Grupprincip för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="24480-158">Hämta och installera [administrativa mallar (.admx) för Windows 10, oktober 2020 uppdatering (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="24480-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="24480-159">Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="24480-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="24480-160">Markera grupprincipobjektet du vill konfigurera och välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="24480-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="24480-161">I **Redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="24480-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="24480-162">Expandera trädstrukturen till **Windows-komponenter** > **Microsoft Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="24480-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="24480-163">Dubbelklicka på **Konfigurera identifiering för potentiellt oönskade program**.</span><span class="sxs-lookup"><span data-stu-id="24480-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="24480-164">Välj **Aktivera** för att aktivera PUA-skydd.</span><span class="sxs-lookup"><span data-stu-id="24480-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="24480-165">I **Alternativ** väljer du **Blockera** för att blockera potentiellt oönskade program eller välj **Granskningsläge** för att testa hur inställningen fungerar i din miljö.</span><span class="sxs-lookup"><span data-stu-id="24480-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="24480-166">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="24480-166">Select **OK**.</span></span>

9. <span data-ttu-id="24480-167">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="24480-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="24480-168">Använda PowerShell-cmdlets för att konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="24480-169">Så här aktiverar PUA-skydd.</span><span class="sxs-lookup"><span data-stu-id="24480-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="24480-170">Att ställa in värdet för denna cmdlet till `Enabled` aktiverar funktionen om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="24480-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="24480-171">Så här ställer du in PUA-skydd till granskningsläge</span><span class="sxs-lookup"><span data-stu-id="24480-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="24480-172">Inställningen av `AuditMode` identifierar PUA-program utan att blockera dem.</span><span class="sxs-lookup"><span data-stu-id="24480-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="24480-173">Så här inaktiverar du PUA-skydd.</span><span class="sxs-lookup"><span data-stu-id="24480-173">To disable PUA protection</span></span>

<span data-ttu-id="24480-174">Vi rekommenderar att du behåller PUA-skyddet aktiverat.</span><span class="sxs-lookup"><span data-stu-id="24480-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="24480-175">Du kan dock inaktivera den med hjälp av följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="24480-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="24480-176">Att ställa in värdet för denna cmdlet till `Disabled` aktiverar funktionen om den har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="24480-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="24480-177">Mer information finns i [Hur du använder PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="24480-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="24480-178">Visa PUA-händelser med hjälp av PowerShell</span><span class="sxs-lookup"><span data-stu-id="24480-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="24480-179">PUA-händelser rapporteras i Windows Loggboken, men inte i Microsoft Endpoint Manager eller i Intune.</span><span class="sxs-lookup"><span data-stu-id="24480-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="24480-180">Du kan också använda nämnda `Get-MpThreat` cmdlet för att visa hot som Microsoft Defender Antivirus hanterade.</span><span class="sxs-lookup"><span data-stu-id="24480-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="24480-181">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="24480-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="24480-182">Få e-postaviseringar om PUA-identifieringar</span><span class="sxs-lookup"><span data-stu-id="24480-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="24480-183">Du kan aktivera e-postaviseringar för att få e-post om PUA-identifieringar.</span><span class="sxs-lookup"><span data-stu-id="24480-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="24480-184">Gå till [Felsökningshändelse-ID:er](troubleshoot-microsoft-defender-antivirus.md) för mer information om hur du visar händelser för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="24480-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="24480-185">PUA-händelser registreras under händelse-ID **1160**.</span><span class="sxs-lookup"><span data-stu-id="24480-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="24480-186">Visa PUA-händelser med hjälp av avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="24480-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="24480-187">Om du använder [Microsoft Defender för Endpoint](microsoft-defender-endpoint.md)kan du använda en avancerad sökfråga för att visa PUA-händelser.</span><span class="sxs-lookup"><span data-stu-id="24480-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="24480-188">Här är en exempelfråga:</span><span class="sxs-lookup"><span data-stu-id="24480-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="24480-189">Mer information om Avancerad jakt finns i [Hur du proaktivt jagar efter hot med Avancerad jakt](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="24480-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="24480-190">Exkludera filer från PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="24480-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="24480-191">Ibland blockeras en fil felaktigt av PUA-skydd eller så krävs en funktion i en PUA för att slutföra en aktivitet.</span><span class="sxs-lookup"><span data-stu-id="24480-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="24480-192">I sådana fall kan en fil läggas till i en undantagslista.</span><span class="sxs-lookup"><span data-stu-id="24480-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="24480-193">Mer information finns i [Konfigurera och validera undantag baserat på filtillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="24480-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="24480-194">Se även</span><span class="sxs-lookup"><span data-stu-id="24480-194">See also</span></span>

- [<span data-ttu-id="24480-195">Nästa generations skydd</span><span class="sxs-lookup"><span data-stu-id="24480-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="24480-196">Konfigurera heuristiskt, beteende- och realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="24480-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)