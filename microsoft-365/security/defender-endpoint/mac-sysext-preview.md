---
title: Microsoft Defender ATP för Mac – systemtillägg (förhandsversion)
description: Den här artikeln innehåller instruktioner för hur du provar systemtilläggsfunktionen i Microsoft Defender ATP för Mac. Den här funktionen är för närvarande i offentlig förhandsversion.
keywords: microsoft, defender, atp, mac, kernel, system, tillägg, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 8b644e27c5a36d2175ab18ae92424e7c70f39d0f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070266"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a><span data-ttu-id="1eef2-105">Microsoft Defender för slutpunkt för Mac – systemtillägg offentlig förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="1eef2-105">Microsoft Defender for Endpoint for Mac - system extensions public preview)</span></span>

<span data-ttu-id="1eef2-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1eef2-106">**Applies to:**</span></span>
- [<span data-ttu-id="1eef2-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1eef2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1eef2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1eef2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1eef2-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1eef2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1eef2-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1eef2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="1eef2-111">I linje med macOS-utveckling förbereder vi en Defender för slutpunkt för Mac-uppdatering som utnyttjar systemtillägg istället för kernel-tillägg.</span><span class="sxs-lookup"><span data-stu-id="1eef2-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint for Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="1eef2-112">Den här uppdateringen gäller endast för macOS Catalina (10.15.4) och senare versioner av macOS.</span><span class="sxs-lookup"><span data-stu-id="1eef2-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="1eef2-113">Den här funktionen är för närvarande i offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="1eef2-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="1eef2-114">I den här artikeln beskrivs hur du aktiverar den här funktionen på din enhet.</span><span class="sxs-lookup"><span data-stu-id="1eef2-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="1eef2-115">Du kan prova den här funktionen lokalt på din egen enhet eller konfigurera den via ett hanteringsverktyg.</span><span class="sxs-lookup"><span data-stu-id="1eef2-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="1eef2-116">De här instruktionerna förutsätter att du redan har Defender för Endpoint igång på enheten.</span><span class="sxs-lookup"><span data-stu-id="1eef2-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="1eef2-117">Mer information finns på den [här sidan.](microsoft-defender-endpoint-mac.md)</span><span class="sxs-lookup"><span data-stu-id="1eef2-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="1eef2-118">Kända problem</span><span class="sxs-lookup"><span data-stu-id="1eef2-118">Known issues</span></span>

- <span data-ttu-id="1eef2-119">Vi har fått rapporter om att nätverkstillägget stör Apple SSO Kerberos-tillägget.</span><span class="sxs-lookup"><span data-stu-id="1eef2-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="1eef2-120">I den aktuella versionen av produkten installeras fortfarande ett kernel-tillägg.</span><span class="sxs-lookup"><span data-stu-id="1eef2-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="1eef2-121">Kernel-tillägg används endast som en reservmekanism och kommer att tas bort innan den här funktionen når offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="1eef2-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="1eef2-122">Vi arbetar fortfarande med en produktversion som distribuerar och fungerar korrekt på macOS 11 Big Sur.</span><span class="sxs-lookup"><span data-stu-id="1eef2-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="1eef2-123">Distributionsförutsättningarna</span><span class="sxs-lookup"><span data-stu-id="1eef2-123">Deployment prerequisites</span></span>

- <span data-ttu-id="1eef2-124">Lägsta macOS-operativsystemsversion: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="1eef2-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="1eef2-125">Lägsta produktversion: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="1eef2-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="1eef2-126">Enheten måste vara i **uppdateringskanalen för Insider – snabbt.**</span><span class="sxs-lookup"><span data-stu-id="1eef2-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="1eef2-127">Du kan kontrollera uppdateringskanalen med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1eef2-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="1eef2-128">Om enheten inte redan finns i uppdateringskanalen för Insider – snabbt kör du följande kommando från terminalen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="1eef2-129">Kanaluppdateringen börjar gälla nästa gång produkten startar (när nästa produktuppdatering installeras eller när enheten startas om).</span><span class="sxs-lookup"><span data-stu-id="1eef2-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="1eef2-130">Om du är i en hanterad miljö (JAMF eller Intune) kan du även konfigurera uppdateringskanalen via fjärrstyrd anslutning.</span><span class="sxs-lookup"><span data-stu-id="1eef2-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="1eef2-131">Mer information finns i [Distribuera uppdateringar för Microsoft Defender ATP för Mac: Ange kanalnamnet](mac-updates.md#set-the-channel-name).</span><span class="sxs-lookup"><span data-stu-id="1eef2-131">For more information, see [Deploy updates for Microsoft Defender ATP for Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="1eef2-132">Distributionssteg</span><span class="sxs-lookup"><span data-stu-id="1eef2-132">Deployment steps</span></span>

<span data-ttu-id="1eef2-133">Följ distributionsanvisningarna som motsvarar din miljö och den metod du föredrar för att prova den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="1eef2-134">Manuell distribution</span><span class="sxs-lookup"><span data-stu-id="1eef2-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="1eef2-135">Godkänna systemtilläggen och aktivera nätverkstillägget</span><span class="sxs-lookup"><span data-stu-id="1eef2-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="1eef2-136">När alla distributionsförutsättningarna är uppfyllda startar du om enheten för att starta godkännande- och aktiveringsprocessen för systemtillägg.</span><span class="sxs-lookup"><span data-stu-id="1eef2-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="1eef2-137">Du ser en serie systemuppslag om att godkänna Defender för slutpunktssystemtillägg.</span><span class="sxs-lookup"><span data-stu-id="1eef2-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="1eef2-138">Du måste godkänna **alla** uppmaningar i serien eftersom macOS kräver ett uttryckligt godkännande för varje tillägg som Defender för Endpoint för Mac installerar på enheten.</span><span class="sxs-lookup"><span data-stu-id="1eef2-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint for Mac installs on the device.</span></span>
   
   <span data-ttu-id="1eef2-139">För varje godkännande väljer du **Öppna säkerhetsinställningar** och sedan Tillåt **för** att tillåta att systemtillägget körs.</span><span class="sxs-lookup"><span data-stu-id="1eef2-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1eef2-140">Du måste stänga och öppna säkerhetsinställningarna **i**  >  **Systeminställningar & sekretessfönstret** mellan efterföljande godkännanden.</span><span class="sxs-lookup"><span data-stu-id="1eef2-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="1eef2-141">Annars visas inte nästa godkännande i macOS.</span><span class="sxs-lookup"><span data-stu-id="1eef2-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1eef2-142">Det finns en timeout på en minut innan produkten hamnar i kernel-tillägg igen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="1eef2-143">Det säkerställer att enheten är skyddad.</span><span class="sxs-lookup"><span data-stu-id="1eef2-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="1eef2-144">Om det tar mer än en minut startar du om datorn genom att starta om enheten eller använda den för att `sudo killall -9 wdavdaemon` starta godkännandeflödet igen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![Popup-fönster för godkännande av systemtillägg](images/mac-system-extension-approval.png)

   ![Godkännandefönster för systemtillägg](images/mac-system-extension-pref.png)

1. <span data-ttu-id="1eef2-147">När systemtilläggen har godkänts uppmanar macOS dig att godkänna att nätverkstrafiken filtreras.</span><span class="sxs-lookup"><span data-stu-id="1eef2-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="1eef2-148">Klicka **på Tillåt.**</span><span class="sxs-lookup"><span data-stu-id="1eef2-148">Click **Allow**.</span></span>

   ![Popup-meddelande om godkännande av nätverkstillägg](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="1eef2-150">Bevilja fullständig diskåtkomst till slutpunktssäkerhetssystemtillägget</span><span class="sxs-lookup"><span data-stu-id="1eef2-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="1eef2-151">Öppna fliken **Systeminställningar**  >  **för & Sekretess**  >  **och** ge **fullständig diskåtkomst** till **Microsoft Defender Endpoint Security Extension.**</span><span class="sxs-lookup"><span data-stu-id="1eef2-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Fullständig diskåtkomst för Slutpunktssäkerhetssystemtillägg](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="1eef2-153">Starta om enheten</span><span class="sxs-lookup"><span data-stu-id="1eef2-153">Reboot your device</span></span>

<span data-ttu-id="1eef2-154">För att ändringarna ska gå ut måste du starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="1eef2-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="1eef2-155">Kontrollera att systemtilläggen körs</span><span class="sxs-lookup"><span data-stu-id="1eef2-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="1eef2-156">Kör följande kommando från terminalen:</span><span class="sxs-lookup"><span data-stu-id="1eef2-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="1eef2-157">`endpoint_security_extension`Terminalutdata anger att produkten använder systemtilläggsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="1eef2-158">Hanterad distribution</span><span class="sxs-lookup"><span data-stu-id="1eef2-158">Managed deployment</span></span>

<span data-ttu-id="1eef2-159">Se Nya [konfigurationsprofiler för macOS Catalina](mac-sysext-policies.md#jamf) och nyare versioner av macOS: JAMF för de nya konfigurationsprofiler som du måste distribuera för den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="1eef2-160">Förutom de profilerna ska du konfigurera målenheterna så att de finns i uppdateringskanalen För Insider – snabbt, enligt beskrivningen [i Distributionsförutsättningarna.](#deployment-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="1eef2-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="1eef2-161">Kör följande kommando på en enhet där alla krav uppfylls och de nya konfigurationsprofilerna har distribuerats:</span><span class="sxs-lookup"><span data-stu-id="1eef2-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="1eef2-162">Om det här `endpoint_security_extension` kommandot skrivs ut används systemtilläggsfunktionen i produkten.</span><span class="sxs-lookup"><span data-stu-id="1eef2-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="1eef2-163">Validera grundläggande scenarier</span><span class="sxs-lookup"><span data-stu-id="1eef2-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="1eef2-164">Test European Institute for Computer Antivirus Research (EICAR).</span><span class="sxs-lookup"><span data-stu-id="1eef2-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="1eef2-165">Kör följande kommando från ett terminalfönster:</span><span class="sxs-lookup"><span data-stu-id="1eef2-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="1eef2-166">Kontrollera att EICAR-filen har satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="1eef2-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="1eef2-167">Du kan kontrollera filens status på sidan Säkerhetshistorik i användargränssnittet eller från en kommandorad med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="1eef2-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="1eef2-168">Testa scenariot Slutpunktsidentifiering och svar (EDR) -PROJEKT.</span><span class="sxs-lookup"><span data-stu-id="1eef2-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="1eef2-169">Kör följande kommando från ett terminalfönster:</span><span class="sxs-lookup"><span data-stu-id="1eef2-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="1eef2-170">Verifiera att två aviseringar visas i portalen på datorsidan för EICAR- och EDR-SJÄLV-scenarier.</span><span class="sxs-lookup"><span data-stu-id="1eef2-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="1eef2-171">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="1eef2-171">Frequently asked questions</span></span>

- <span data-ttu-id="1eef2-172">F: Varför ser jag fortfarande `kernel_extension` när jag `mdatp health --field real_time_protection_subsystem` kör?</span><span class="sxs-lookup"><span data-stu-id="1eef2-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="1eef2-173">S: Gå tillbaka till [avsnittet Distributionsförutsättningarna](#deployment-prerequisites) och kontrollera att alla krav uppfylls.</span><span class="sxs-lookup"><span data-stu-id="1eef2-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="1eef2-174">Om alla krav uppfylls startar du om enheten och kontrollerar igen.</span><span class="sxs-lookup"><span data-stu-id="1eef2-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="1eef2-175">F: När stöds macOS 11 Big Sur?</span><span class="sxs-lookup"><span data-stu-id="1eef2-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="1eef2-176">S: Vi arbetar aktivt med att lägga till support för macOS 11.</span><span class="sxs-lookup"><span data-stu-id="1eef2-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="1eef2-177">Vi publicerar mer information [på sidan Vad är nytt.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="1eef2-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>