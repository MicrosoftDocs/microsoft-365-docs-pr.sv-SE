---
title: Manuell distribution av Microsoft Defender ATP för macOS
description: Installera Microsoft Defender ATP för macOS manuellt från kommandoraden.
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187451"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="fbb36-104">Manuell distribution av Microsoft Defender för Slutpunkt för macOS</span><span class="sxs-lookup"><span data-stu-id="fbb36-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fbb36-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fbb36-105">**Applies to:**</span></span>
- [<span data-ttu-id="fbb36-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fbb36-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fbb36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbb36-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fbb36-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="fbb36-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fbb36-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="fbb36-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="fbb36-110">I det här avsnittet beskrivs hur du distribuerar Microsoft Defender för slutpunkt för macOS manuellt.</span><span class="sxs-lookup"><span data-stu-id="fbb36-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="fbb36-111">För en lyckad distribution måste du slutföra alla följande steg:</span><span class="sxs-lookup"><span data-stu-id="fbb36-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="fbb36-112">Ladda ned installation- och onboarding-paket</span><span class="sxs-lookup"><span data-stu-id="fbb36-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="fbb36-113">Programinstallation (macOS 10.15 och äldre versioner)</span><span class="sxs-lookup"><span data-stu-id="fbb36-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="fbb36-114">Programinstallation (macOS 11 och senare versioner)</span><span class="sxs-lookup"><span data-stu-id="fbb36-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="fbb36-115">Klientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fbb36-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="fbb36-116">Krav och systemkrav</span><span class="sxs-lookup"><span data-stu-id="fbb36-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="fbb36-117">Innan du börjar kan du gå [till huvudsidan för Microsoft Defender](microsoft-defender-endpoint-mac.md) för Slutpunkt för macOS för att få en beskrivning av förutsättningarna och systemkraven för den aktuella programvaruversionen.</span><span class="sxs-lookup"><span data-stu-id="fbb36-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="fbb36-118">Ladda ned installation- och onboarding-paket</span><span class="sxs-lookup"><span data-stu-id="fbb36-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="fbb36-119">Ladda ned installation- och onboarding-paketen från Microsoft Defender Säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="fbb36-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="fbb36-120">I Microsoft Defender Säkerhetscenter går du till **Inställningar > Enhetshantering > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="fbb36-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="fbb36-121">I avsnitt 1 på sidan anger du operativsystem till **macOS** och distributionsmetod till **Lokalt skript.**</span><span class="sxs-lookup"><span data-stu-id="fbb36-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="fbb36-122">I avsnitt 2 på sidan väljer du Ladda **ned installationspaketet**.</span><span class="sxs-lookup"><span data-stu-id="fbb36-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="fbb36-123">Spara den som wdav.pkg i en lokal katalog.</span><span class="sxs-lookup"><span data-stu-id="fbb36-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="fbb36-124">Välj Hämta introduktionspaket i avsnitt 2 **på sidan.**</span><span class="sxs-lookup"><span data-stu-id="fbb36-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="fbb36-125">Spara den WindowsDefenderATPOnboardingPackage.zip filen i samma katalog.</span><span class="sxs-lookup"><span data-stu-id="fbb36-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Skärmbild av Microsoft Defender Säkerhetscenter](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="fbb36-127">Kontrollera att du har de två filerna i kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="fbb36-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="fbb36-128">Programinstallation (macOS 10.15 och äldre versioner)</span><span class="sxs-lookup"><span data-stu-id="fbb36-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="fbb36-129">Du måste ha administratörsbehörighet på enheten för att slutföra den här processen.</span><span class="sxs-lookup"><span data-stu-id="fbb36-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="fbb36-130">Navigera till den nedladdade wdav.pkg i Finder och öppna den.</span><span class="sxs-lookup"><span data-stu-id="fbb36-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Skärmbild av appinstallation1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="fbb36-132">Välj **Fortsätt**, godkänn licensvillkoren och ange lösenordet när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="fbb36-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Skärmbild av appinstallation2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="fbb36-134">Du uppmanas att tillåta att en drivrutin från Microsoft installeras (antingen "Systemtillägg blockerat" eller "Installationen är spärrad" eller båda.</span><span class="sxs-lookup"><span data-stu-id="fbb36-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="fbb36-135">Drivrutinen måste tillåtas att installeras.</span><span class="sxs-lookup"><span data-stu-id="fbb36-135">The driver must be allowed to be installed.</span></span>

   ![Skärmbild av appinstallation3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="fbb36-137">Välj **Öppna säkerhetsinställningar** eller **Öppna systeminställningar > säkerhetsinställningar & sekretess.**</span><span class="sxs-lookup"><span data-stu-id="fbb36-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="fbb36-138">Välj **Tillåt:**</span><span class="sxs-lookup"><span data-stu-id="fbb36-138">Select **Allow**:</span></span>

    ![Skärmbild av fönstret Säkerhet och sekretess](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="fbb36-140">Installationen utförs.</span><span class="sxs-lookup"><span data-stu-id="fbb36-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="fbb36-141">Om du inte väljer **Tillåt** fortsätter installationen efter 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="fbb36-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="fbb36-142">Microsoft Defender för Slutpunkt läses in, men vissa funktioner, till exempel realtidsskydd, inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="fbb36-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="fbb36-143">Mer information [om hur du löser](mac-support-kext.md) det finns i Felsöka problem med kerneltillägg.</span><span class="sxs-lookup"><span data-stu-id="fbb36-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="fbb36-144">macOS kan begära att starta om enheten vid den första installationen av Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="fbb36-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fbb36-145">Realtidsskydd är inte tillgängligt förrän enheten startas om.</span><span class="sxs-lookup"><span data-stu-id="fbb36-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="fbb36-146">Programinstallation (macOS 11 och senare versioner)</span><span class="sxs-lookup"><span data-stu-id="fbb36-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="fbb36-147">Du måste ha administratörsbehörighet på enheten för att slutföra den här processen.</span><span class="sxs-lookup"><span data-stu-id="fbb36-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="fbb36-148">Navigera till den nedladdade wdav.pkg i Finder och öppna den.</span><span class="sxs-lookup"><span data-stu-id="fbb36-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Skärmbild av appinstallation4](images/big-sur-install-1.png)

2. <span data-ttu-id="fbb36-150">Välj **Fortsätt**, godkänn licensvillkoren och ange lösenordet när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="fbb36-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="fbb36-151">I slutet av installationsprocessen godkänner du de systemtillägg som används av produkten.</span><span class="sxs-lookup"><span data-stu-id="fbb36-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="fbb36-152">Välj **Öppna säkerhetsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="fbb36-152">Select **Open Security Preferences**.</span></span>

    ![Godkännande av systemtillägg](images/big-sur-install-2.png)

4. <span data-ttu-id="fbb36-154">I fönstret **Säkerhet & sekretess** väljer du **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="fbb36-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Säkerhetsinställningar för systemtillägg1](images/big-sur-install-3.png)

5. <span data-ttu-id="fbb36-156">Upprepa steg 3 & 4 för alla systemtillägg som distribueras med Microsoft Defender för Slutpunkt för Mac.</span><span class="sxs-lookup"><span data-stu-id="fbb36-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="fbb36-157">Som en del av funktionerna Identifiering av slutpunkt och svar inspekterar Microsoft Defender för Slutpunkt för Mac sockettrafik och rapporterar den här informationen till Microsoft Defender Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="fbb36-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="fbb36-158">När du uppmanas att ge Microsoft Defender behörighet att filtrera nätverkstrafik väljer du **Tillåt**.</span><span class="sxs-lookup"><span data-stu-id="fbb36-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Säkerhetsinställningar för systemtillägg2](images/big-sur-install-4.png)

7. <span data-ttu-id="fbb36-160">Öppna **Systeminställningar för**& sekretess och gå till fliken Sekretess. Ge fullständig diskåtkomstbehörighet till Microsoft Defender ATP och  >   Microsoft Defender  **ATP Endpoint Security Extension.**  </span><span class="sxs-lookup"><span data-stu-id="fbb36-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Fullständig diskåtkomst](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="fbb36-162">Klientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fbb36-162">Client configuration</span></span>

1. <span data-ttu-id="fbb36-163">Kopiera wdav.pkg och MicrosoftDefenderATPOnboardingMacOs.py till enheten där du distribuerar Microsoft Defender för Endpoint för macOS.</span><span class="sxs-lookup"><span data-stu-id="fbb36-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="fbb36-164">Klientenheten är inte kopplad till orgId.</span><span class="sxs-lookup"><span data-stu-id="fbb36-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="fbb36-165">Observera att *orgId-attributet* är tomt.</span><span class="sxs-lookup"><span data-stu-id="fbb36-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="fbb36-166">Kör Python-skriptet för att installera konfigurationsfilen:</span><span class="sxs-lookup"><span data-stu-id="fbb36-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="fbb36-167">Kontrollera att enheten nu är kopplad till din organisation och rapporterar ett *giltigt orgId:*</span><span class="sxs-lookup"><span data-stu-id="fbb36-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="fbb36-168">Efter installationen visas Microsoft Defender-ikonen i statusfältet i macOS i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="fbb36-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![Microsoft Defender-ikon i skärmbild i statusfältet](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="fbb36-170">Så här tillåter du fullständig diskåtkomst</span><span class="sxs-lookup"><span data-stu-id="fbb36-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="fbb36-171">macOS 10.15 (Catalina) innehåller nya förbättringar av säkerhet och sekretess.</span><span class="sxs-lookup"><span data-stu-id="fbb36-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="fbb36-172">Från och med den här versionen kan program som standard inte komma åt vissa platser på disken (till exempel Dokument, Nedladdningar, Skrivbord osv.) utan uttryckligt medgivande.</span><span class="sxs-lookup"><span data-stu-id="fbb36-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="fbb36-173">Om inget sådant medgivande getts kan Inte Microsoft Defender för Endpoint skydda din enhet fullt ut.</span><span class="sxs-lookup"><span data-stu-id="fbb36-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="fbb36-174">Om du vill ge medgivande öppnar du Systeminställningar – > säkerhet & sekretess – > sekretess – > fullständig diskåtkomst.</span><span class="sxs-lookup"><span data-stu-id="fbb36-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="fbb36-175">Klicka på låsikonen om du vill göra ändringar (längst ned i dialogrutan).</span><span class="sxs-lookup"><span data-stu-id="fbb36-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="fbb36-176">Välj Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="fbb36-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="fbb36-177">Loggningsinstallationsproblem</span><span class="sxs-lookup"><span data-stu-id="fbb36-177">Logging installation issues</span></span>

<span data-ttu-id="fbb36-178">Mer [information om hur](mac-resources.md#logging-installation-issues) du hittar den automatiskt genererade loggen som skapas av installationsprogrammet när ett fel uppstår finns i Problem med loggningsinstallationen.</span><span class="sxs-lookup"><span data-stu-id="fbb36-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="fbb36-179">Avinstallation</span><span class="sxs-lookup"><span data-stu-id="fbb36-179">Uninstallation</span></span>

<span data-ttu-id="fbb36-180">Mer [information om hur](mac-resources.md#uninstalling) du tar bort Microsoft Defender för Endpoint för macOS från klientenheter finns i Avinstallera.</span><span class="sxs-lookup"><span data-stu-id="fbb36-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
