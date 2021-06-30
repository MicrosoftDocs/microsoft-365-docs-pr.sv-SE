---
title: Intune-baserad distribution för Microsoft Defender för Slutpunkt på Mac
description: Installera Microsoft Defender för slutpunkt på Mac med hjälp av Microsoft Intune.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7243e8f6fad225e6c4570184736e8d6588466d0a
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194967"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f4cfc-104">Intune-baserad distribution för Microsoft Defender för Slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="f4cfc-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4cfc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4cfc-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="f4cfc-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="f4cfc-107">I det här avsnittet beskrivs hur du distribuerar Microsoft Defender för slutpunkt på macOS via Intune.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="f4cfc-108">För en lyckad distribution måste du slutföra alla följande steg:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="f4cfc-109">Ladda ned onboarding-paketet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="f4cfc-110">Konfigurera klientenhet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="f4cfc-111">Godkänna systemtillägg</span><span class="sxs-lookup"><span data-stu-id="f4cfc-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="f4cfc-112">Skapa systemkonfigurationsprofiler</span><span class="sxs-lookup"><span data-stu-id="f4cfc-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="f4cfc-113">Publicera program</span><span class="sxs-lookup"><span data-stu-id="f4cfc-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="f4cfc-114">Krav och systemkrav</span><span class="sxs-lookup"><span data-stu-id="f4cfc-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="f4cfc-115">Innan du börjar kan du gå [till huvudsidan för Microsoft Defender](microsoft-defender-endpoint-mac.md) för Slutpunkt på macOS för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="f4cfc-116">Översikt</span><span class="sxs-lookup"><span data-stu-id="f4cfc-116">Overview</span></span>

<span data-ttu-id="f4cfc-117">I följande tabell sammanfattas de steg du måste vidta för att distribuera och hantera Microsoft Defender för Slutpunkt på Mac-datorer, via Intune.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="f4cfc-118">Mer detaljerade anvisningar finns nedan.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="f4cfc-119">Steg</span><span class="sxs-lookup"><span data-stu-id="f4cfc-119">Step</span></span> | <span data-ttu-id="f4cfc-120">Exempelfilnamn</span><span class="sxs-lookup"><span data-stu-id="f4cfc-120">Sample file names</span></span> | <span data-ttu-id="f4cfc-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="f4cfc-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="f4cfc-122">Ladda ned onboarding-paketet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="f4cfc-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="f4cfc-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="f4cfc-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="f4cfc-125">Godkänna systemtillägg för Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4cfc-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="f4cfc-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="f4cfc-127">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="f4cfc-127">N/A</span></span> |
| [<span data-ttu-id="f4cfc-128">Godkänna Kernel-tillägg för Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4cfc-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="f4cfc-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="f4cfc-130">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="f4cfc-130">N/A</span></span> |
| [<span data-ttu-id="f4cfc-131">Bevilja fullständig diskåtkomst till Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4cfc-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="f4cfc-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="f4cfc-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="f4cfc-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="f4cfc-134">Princip för nätverkstillägg</span><span class="sxs-lookup"><span data-stu-id="f4cfc-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="f4cfc-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="f4cfc-136">Uppgift saknas</span><span class="sxs-lookup"><span data-stu-id="f4cfc-136">N/A</span></span> |
| [<span data-ttu-id="f4cfc-137">Konfigurera Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="f4cfc-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="f4cfc-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="f4cfc-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="f4cfc-140">Konfigurationsinställningar för Microsoft Defender för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f4cfc-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="f4cfc-141">**Obs!** Om du planerar att köra en tredjeparts-AV för macOS ställer du in `passiveMode` på `true` .</span><span class="sxs-lookup"><span data-stu-id="f4cfc-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="f4cfc-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="f4cfc-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="f4cfc-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="f4cfc-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="f4cfc-144">Konfigurera Microsoft Defender för Endpoint- och MS AutoUpdate-meddelanden (MAU)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="f4cfc-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="f4cfc-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="f4cfc-146">com.microsoft.autoupdate2 eller com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="f4cfc-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="f4cfc-147">Ladda ned onboarding-paketet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-147">Download the onboarding package</span></span>

<span data-ttu-id="f4cfc-148">Ladda ned onboarding-paketen från Microsoft Defender Säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="f4cfc-149">I Microsoft Defender Säkerhetscenter du till Inställningar  >  **onboarding av**  >  **enhetshantering.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="f4cfc-150">Ställ in operativsystemet på **macOS** och distributionsmetoden till **Hantering av mobila enheter /Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Skärmbild av onboarding-inställningar](images/atp-mac-install.png)

3. <span data-ttu-id="f4cfc-152">Välj **Hämta introduktionspaket**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="f4cfc-153">Spara den _WindowsDefenderATPOnboardingPackage.zip_ filen i samma katalog.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="f4cfc-154">Extrahera innehållet i .zip filen:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-154">Extract the contents of the .zip file:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="f4cfc-155">Skapa systemkonfigurationsprofiler</span><span class="sxs-lookup"><span data-stu-id="f4cfc-155">Create System Configuration profiles</span></span>

<span data-ttu-id="f4cfc-156">Nästa steg är att skapa systemkonfigurationsprofiler som Microsoft Defender för Endpoint behöver.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="f4cfc-157">Öppna [konfigurationsprofiler Microsoft Endpoint Manager Enheter](https://endpoint.microsoft.com/) **i administrationscentret** för  >  **enheter.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="f4cfc-158">Blob för onboarding</span><span class="sxs-lookup"><span data-stu-id="f4cfc-158">Onboarding blob</span></span>

<span data-ttu-id="f4cfc-159">Den här profilen innehåller licensinformation för Microsoft Defender för Endpoint, utan att den rapporterar att den inte är licensierad.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="f4cfc-160">Välj **Skapa profil** under **Konfigurationsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="f4cfc-161">Välj **Plattform** = **macOS**, **Profiltyp** = **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="f4cfc-162">**Mallnamn** = **Anpassad**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="f4cfc-163">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-164">![Skapa anpassad konfigurationsprofil](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="f4cfc-165">Välj ett namn för profilen, t.ex. "Defender eller Endpoint onboarding för macOS".</span><span class="sxs-lookup"><span data-stu-id="f4cfc-165">Choose a name for the profile, e.g., "Defender or Endpoint onboarding for macOS".</span></span> <span data-ttu-id="f4cfc-166">Klicka **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-167">![Anpassad konfigurationsprofil – namn](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="f4cfc-168">Välj ett namn för konfigurationsprofilens namn, t.ex. "Defender för slutpunkts onboarding för macOS".</span><span class="sxs-lookup"><span data-stu-id="f4cfc-168">Choose a name for the configuration profile name, e.g., "Defender for Endpoint onboarding for macOS".</span></span>
1. <span data-ttu-id="f4cfc-169">Välj intune/WindowsDefenderATPOnboarding.xml som du extraherade från onboarding-paketet ovan som konfigurationsprofilfil.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-170">![Importera en konfiguration från en fil för anpassad konfigurationsprofil](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="f4cfc-171">Klicka **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-171">Click **Next**.</span></span>
1. <span data-ttu-id="f4cfc-172">Tilldela enheter på fliken **Uppgift.** Klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-173">![Anpassad konfigurationsprofil – tilldelning](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="f4cfc-174">Granska och **skapa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-174">Review and **Create**.</span></span>
1. <span data-ttu-id="f4cfc-175">Öppna   >  **konfigurationsprofiler för** enheter – du kan se din skapade profil där.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-176">![Profil för anpassad konfiguration – klar](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="f4cfc-177">Godkänna systemtillägg</span><span class="sxs-lookup"><span data-stu-id="f4cfc-177">Approve System Extensions</span></span>

<span data-ttu-id="f4cfc-178">Den här profilen krävs för macOS 10.15 (Catalina) eller nyare.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="f4cfc-179">Den ignoreras i äldre macOS.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="f4cfc-180">Välj **Skapa profil** under **Konfigurationsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="f4cfc-181">Välj **Plattform** = **macOS**, **Profiltyp** = **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="f4cfc-182">**Mallnamn** = **Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="f4cfc-183">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-183">Click **Create**.</span></span>
1. <span data-ttu-id="f4cfc-184">Ge den **här nya** profilen ett namn på fliken Grunder.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="f4cfc-185">På fliken **Konfigurationsinställningar** expanderar **du Systemtillägg** och lägger till följande poster i avsnittet **Tillåtna systemtillägg:**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="f4cfc-186">Paketidentifierare</span><span class="sxs-lookup"><span data-stu-id="f4cfc-186">Bundle identifier</span></span>         | <span data-ttu-id="f4cfc-187">Teamidentifierare</span><span class="sxs-lookup"><span data-stu-id="f4cfc-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="f4cfc-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="f4cfc-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="f4cfc-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f4cfc-189">UBF8T346G9</span></span>
    <span data-ttu-id="f4cfc-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="f4cfc-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="f4cfc-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="f4cfc-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-192">![Inställningar för systemtillägg](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="f4cfc-193">På fliken **Uppgifter tilldelar** du den här profilen till **Alla användare & Alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="f4cfc-194">Granska och skapa den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="f4cfc-195">Kernel-tillägg</span><span class="sxs-lookup"><span data-stu-id="f4cfc-195">Kernel Extensions</span></span>

<span data-ttu-id="f4cfc-196">Den här profilen krävs för macOS 10.15 (Catalina) eller äldre.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="f4cfc-197">Det ignoreras på nyare macOS.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="f4cfc-198">Apple Silicon-enheter (M1) stöder inte KEXT.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="f4cfc-199">Installationen av en konfigurationsprofil som består av KEXT-principer misslyckas på dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="f4cfc-200">Välj **Skapa profil** under **Konfigurationsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="f4cfc-201">Välj **Plattform** = **macOS**, **Profiltyp** = **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="f4cfc-202">**Mallnamn** = **Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="f4cfc-203">Klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-203">Click **Create**.</span></span>
1. <span data-ttu-id="f4cfc-204">Ge den **här nya** profilen ett namn på fliken Grunder.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="f4cfc-205">Expandera **Kernel-tillägg** på **fliken Konfigurationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="f4cfc-206">Ange **teamidentifierare** **till UBF8T346G9** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-207">![Inställningar för Kernel-tillägg](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="f4cfc-208">På fliken **Uppgifter tilldelar** du den här profilen till **Alla användare & Alla enheter.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="f4cfc-209">Granska och skapa den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="f4cfc-210">Fullständig diskåtkomst</span><span class="sxs-lookup"><span data-stu-id="f4cfc-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="f4cfc-211">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="f4cfc-212">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="f4cfc-213">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="f4cfc-214">Den här konfigurationsprofilen beviljar Fullständig diskåtkomst till Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f4cfc-215">Om du tidigare har konfigurerat Microsoft Defender för Slutpunkt via Intune rekommenderar vi att du uppdaterar distributionen med den här konfigurationsprofilen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="f4cfc-216">Ladda [**ned fulldisk.mobileconfig från**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) vår [GitHub-lagringsplats.](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="f4cfc-217">Följ instruktionerna för [blob för onboarding](#onboarding-blob) ovan, med "Defender för slutpunkt fullständig diskåtkomst" som profilnamn och nedladdad **fulldisk.mobileconfig** som konfigurationsprofilnamn.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="f4cfc-218">Nätverksfilter</span><span class="sxs-lookup"><span data-stu-id="f4cfc-218">Network Filter</span></span>

<span data-ttu-id="f4cfc-219">Som en del av funktionerna Slutpunktsidentifiering och svar inspekterar Microsoft Defender för slutpunkt på macOS sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter portalen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="f4cfc-220">Med följande princip kan nätverkstillägget utföra de här funktionerna.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="f4cfc-221">Ladda [**ned netfilter.mobileconfig från**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) vår [GitHub-lagringsplats](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="f4cfc-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="f4cfc-222">Följ instruktionerna för [blob för onboarding](#onboarding-blob) ovan, med "Defender för slutpunktsnätverksfilter" som profilnamn och nedladdat **netfilter.mobileconfig** som konfigurationsprofilnamn.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="f4cfc-223">Meddelanden</span><span class="sxs-lookup"><span data-stu-id="f4cfc-223">Notifications</span></span>

<span data-ttu-id="f4cfc-224">Den här profilen används för att tillåta Microsoft Defender för Slutpunkt på macOS och Microsoft Auto Update för att visa meddelanden i användargränssnittet i macOS 10.15 (Catalina) eller nyare.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="f4cfc-225">Ladda [**ned notif.mobileconfig från**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) vår [GitHub-lagringsplats](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="f4cfc-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="f4cfc-226">Följ instruktionerna för [blob för onboarding](#onboarding-blob) ovan, med "Defender for Endpoint Notifications" som profilnamn och nedladdat **notif.mobileconfig** som konfigurationsprofilnamn.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "Defender for Endpoint Notifications" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="f4cfc-227">Visa status</span><span class="sxs-lookup"><span data-stu-id="f4cfc-227">View Status</span></span>

<span data-ttu-id="f4cfc-228">När Intune-ändringarna har spridits till de registrerade enheterna kan du se dem under **Övervaka**  >  **enhetsstatus:**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f4cfc-229">![Vy över enhetsstatus i bildskärm](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="f4cfc-230">Publicera program</span><span class="sxs-lookup"><span data-stu-id="f4cfc-230">Publish application</span></span>

<span data-ttu-id="f4cfc-231">I det här steget kan du distribuera Microsoft Defender för Endpoint till registrerade datorer.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="f4cfc-232">Öppna [Microsoft Endpoint Manager i](https://endpoint.microsoft.com/) **administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-233">![Redo att skapa program](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="f4cfc-234">Välj Efter plattform > macOS-> Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="f4cfc-235">Välj **Apptyp** = **macOS och** klicka på **Välj.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-236">![Ange programtyp](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="f4cfc-237">Behåll standardvärdena och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-238">![Programegenskaper](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="f4cfc-239">Lägg till uppgifter och klicka på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="f4cfc-241">Granska och **skapa**.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-241">Review and **Create**.</span></span>
1. <span data-ttu-id="f4cfc-242">Du kan besöka **Appar**  >  **Efter plattform**  >  **macOS** för att se det i listan över alla program.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-243">![Listan Program](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="f4cfc-244">(Detaljerad information finns på [Intune-sidan för Defender-distribution](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="f4cfc-245">Du måste skapa alla nödvändiga konfigurationsprofiler och skicka dem till alla datorer, enligt ovan.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="f4cfc-246">Konfigurera klientenhet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-246">Client device setup</span></span>

<span data-ttu-id="f4cfc-247">Du behöver ingen särskild etablering för en Mac-enhet utöver en Företagsportal [standardinstallation.](/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="f4cfc-248">Bekräfta enhetshantering.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-249">![Bekräfta skärmbilden på enhetshantering](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="f4cfc-250">Välj **Öppna systeminställningar**, leta **reda på Hanteringsprofil** i listan och välj **Godkänn...**. Din hanteringsprofil visades som **verifierad:**</span><span class="sxs-lookup"><span data-stu-id="f4cfc-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Skärmbild av hanteringsprofilen](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="f4cfc-252">Välj **Fortsätt** och slutför registreringen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="f4cfc-253">Nu kan du registrera fler enheter.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-253">You may now enroll more devices.</span></span> <span data-ttu-id="f4cfc-254">Du kan också registrera dem senare, när du har slutfört konfiguration av systemkonfiguration och programpaket.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="f4cfc-255">Öppna Hantera enheter alla enheter  >  **i**  >  Intune.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="f4cfc-256">Här kan du se din enhet bland dem som listas:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f4cfc-257">![Skärmbild av Lägg till enheter](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="f4cfc-258">Verifiera status för klientenhet</span><span class="sxs-lookup"><span data-stu-id="f4cfc-258">Verify client device state</span></span>

1. <span data-ttu-id="f4cfc-259">När konfigurationsprofilerna har distribuerats till dina enheter öppnar du **Systeminställningar**  >  **på** din Mac-enhet.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-260">![Skärmbild av Systeminställningar](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![Skärmbild av systeminställningar](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="f4cfc-262">Kontrollera att följande konfigurationsprofiler finns och är installerade.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="f4cfc-263">**Hanteringsprofilen** ska vara Intune-systemprofilen.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="f4cfc-264">_Wdav-config_ _och wdav-kext_ är systemkonfigurationsprofiler som lagts till i Intune:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![Skärmbild av profiler](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="f4cfc-266">Du bör även se ikonen Microsoft Defender för Slutpunkt i det övre högra hörnet:</span><span class="sxs-lookup"><span data-stu-id="f4cfc-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4cfc-267">![Skärmbild av Microsoft Defender för slutpunktsikonen i statusfältet](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f4cfc-268">Felsökning</span><span class="sxs-lookup"><span data-stu-id="f4cfc-268">Troubleshooting</span></span>

<span data-ttu-id="f4cfc-269">Problem: Ingen licens hittades.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-269">Issue: No license found.</span></span>

<span data-ttu-id="f4cfc-270">Lösning: Följ stegen ovan för att skapa en enhetsprofil med hjälp av WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="f4cfc-271">Loggningsinstallationsproblem</span><span class="sxs-lookup"><span data-stu-id="f4cfc-271">Logging installation issues</span></span>

<span data-ttu-id="f4cfc-272">Mer information om hur du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Problem [med loggningsinstallation.](mac-resources.md#logging-installation-issues)</span><span class="sxs-lookup"><span data-stu-id="f4cfc-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="f4cfc-273">Avinstallation</span><span class="sxs-lookup"><span data-stu-id="f4cfc-273">Uninstallation</span></span>

<span data-ttu-id="f4cfc-274">Mer [information om hur](mac-resources.md#uninstalling) du tar bort Microsoft Defender för Slutpunkt på macOS från klientenheter finns i Avinstallera.</span><span class="sxs-lookup"><span data-stu-id="f4cfc-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
