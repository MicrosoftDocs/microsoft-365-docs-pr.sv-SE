---
title: Microsoft Defender Antivirus på Windows Server
description: Läs om hur du aktiverar och konfigurerar Microsoft Defender Antivirus i Windows Server 2016 och Windows Server 2019.
keywords: windows defender, server, s defender, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50e6f9b16dbc633e75e86acdc54ac43580107ae3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893383"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="41dd7-104">Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="41dd7-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41dd7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="41dd7-105">**Applies to:**</span></span>

- [<span data-ttu-id="41dd7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="41dd7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="41dd7-107">Microsoft Defender Antivirus är tillgängligt på följande versioner av Windows Server:</span><span class="sxs-lookup"><span data-stu-id="41dd7-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="41dd7-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="41dd7-108">Windows Server 2019</span></span>
- <span data-ttu-id="41dd7-109">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="41dd7-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="41dd7-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="41dd7-110">Windows Server 2016.</span></span> 

<span data-ttu-id="41dd7-111">I vissa fall kallas Microsoft Defender Antivirus för *Endpoint Protection*. Protectionmotorn är dock densamma.</span><span class="sxs-lookup"><span data-stu-id="41dd7-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="41dd7-112">Även om funktionerna, konfigurationen och hanteringen i stort sett är desamma för Microsoft Defender Antivirus i [Windows 10](microsoft-defender-antivirus-in-windows-10.md)finns det några viktiga skillnader på Windows Server:</span><span class="sxs-lookup"><span data-stu-id="41dd7-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="41dd7-113">I Windows Server [tillämpas automatiska undantag](configure-server-exclusions-microsoft-defender-antivirus.md) baserat på din definierade serverroll.</span><span class="sxs-lookup"><span data-stu-id="41dd7-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="41dd7-114">I Windows Server inaktiverar inte Microsoft Defender Antivirus sig själv automatiskt om du kör en annan antivirusprodukt.</span><span class="sxs-lookup"><span data-stu-id="41dd7-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="41dd7-115">En snabb överblick över processen</span><span class="sxs-lookup"><span data-stu-id="41dd7-115">The process at a glance</span></span>

<span data-ttu-id="41dd7-116">Det finns flera steg i processen för att konfigurera och köra Microsoft Defender Antivirus på en serverplattform:</span><span class="sxs-lookup"><span data-stu-id="41dd7-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="41dd7-117">[Aktivera gränssnittet.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="41dd7-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="41dd7-118">[Installera Microsoft Defender Antivirus.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="41dd7-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="41dd7-119">[Kontrollera att Microsoft Defender Antivirus körs](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="41dd7-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="41dd7-120">[Uppdatera säkerhetsinformation för program mot skadlig programvara](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="41dd7-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="41dd7-121">(Vid behov) [Skicka exempel](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="41dd7-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="41dd7-122">(Vid behov) [Konfigurera automatiska undantag](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="41dd7-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="41dd7-123">(Endast om det behövs) [Ställ in Microsoft Defender Antivirus på passivt läge](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="41dd7-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="41dd7-124">Aktivera användargränssnittet på Windows Server</span><span class="sxs-lookup"><span data-stu-id="41dd7-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="41dd7-125">Som standard installeras och fungerar Microsoft Defender Antivirus på Windows Server.</span><span class="sxs-lookup"><span data-stu-id="41dd7-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="41dd7-126">Användargränssnittet (GUI) installeras som standard på vissa SKU:er, men krävs inte eftersom du kan använda PowerShell eller andra metoder för att hantera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="41dd7-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="41dd7-127">Om GUI:t inte är installerat på servern kan  du lägga till det med hjälp av guiden Lägg till roller och funktioner eller med hjälp av PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="41dd7-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="41dd7-128">Aktivera GUI:t med guiden Lägg till roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="41dd7-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="41dd7-129">Se [Installera roller, rolltjänster och funktioner med hjälp](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)av guiden Lägg till roller och funktioner och använd guiden Lägg till roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="41dd7-130">När du kommer till **steget Funktioner** i guiden väljer du alternativet GUI för Windows Defender under Windows **Defender-funktioner.** </span><span class="sxs-lookup"><span data-stu-id="41dd7-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="41dd7-131">I Windows Server 2016 ser guiden **Lägg till roller och funktioner** ut så här:</span><span class="sxs-lookup"><span data-stu-id="41dd7-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Guiden Lägg till roller och funktioner med guid för Windows Defender-alternativet](images/server-add-gui.png)

   <span data-ttu-id="41dd7-133">I Windows Server 2019 påminner **guiden Lägg till roller och funktioner** om liknande.</span><span class="sxs-lookup"><span data-stu-id="41dd7-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="41dd7-134">Aktivera GUI:t med PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dd7-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="41dd7-135">Följande PowerShell-cmdlet aktiverar gränssnittet:</span><span class="sxs-lookup"><span data-stu-id="41dd7-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="41dd7-136">Installera Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="41dd7-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="41dd7-137">Du kan installera Microsoft Defender Antivirus med **hjälp av** guiden Lägg till roller och funktioner eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41dd7-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="41dd7-138">Använda guiden Lägg till roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="41dd7-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="41dd7-139">Läs den [här artikeln](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)och använd guiden Lägg till roller **och funktioner.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="41dd7-140">När du kommer till **steget Funktioner** i guiden väljer du alternativet Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="41dd7-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="41dd7-141">Välj även **alternativet GUI för Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="41dd7-142">Använda PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dd7-142">Use PowerShell</span></span>

<span data-ttu-id="41dd7-143">Om du vill använda PowerShell för att installera Microsoft Defender Antivirus kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41dd7-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="41dd7-144">Händelsemeddelanden för den antimalware-motor som ingår i Microsoft Defender Antivirus finns i [Microsoft Defender AV-händelser.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="41dd7-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="41dd7-145">Kontrollera att Microsoft Defender Antivirus körs</span><span class="sxs-lookup"><span data-stu-id="41dd7-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="41dd7-146">Kontrollera att Microsoft Defender Antivirus körs på servern genom att köra följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41dd7-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="41dd7-147">Kontrollera att brandväggsskyddet är aktiverat genom att köra följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41dd7-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="41dd7-148">Som ett alternativ till PowerShell kan du använda Kommandotolken för att verifiera att Microsoft Defender Antivirus körs.</span><span class="sxs-lookup"><span data-stu-id="41dd7-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="41dd7-149">Det gör du genom att köra följande kommando från en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="41dd7-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="41dd7-150">Kommandot `sc query` returnerar information om Microsoft Defender Antivirus-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="41dd7-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="41dd7-151">När Microsoft Defender Antivirus körs visas `STATE` `RUNNING` värdet.</span><span class="sxs-lookup"><span data-stu-id="41dd7-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="41dd7-152">Uppdatera säkerhetsinformation för program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="41dd7-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="41dd7-153">För att få uppdaterad säkerhetsinformation för program mot skadlig programvara måste du ha Windows Update-tjänsten igång.</span><span class="sxs-lookup"><span data-stu-id="41dd7-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="41dd7-154">Om du använder en uppdateringshanteringstjänst, t.ex. Windows Server Update Services (WSUS), ser du till att uppdateringar för Microsoft Defender Antivirus Security Intelligence är godkända för de datorer du hanterar.</span><span class="sxs-lookup"><span data-stu-id="41dd7-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="41dd7-155">Som standard laddar inte Windows Update ned och installerar uppdateringar automatiskt på Windows Server 2019 eller Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="41dd7-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="41dd7-156">Du kan ändra den här konfigurationen på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="41dd7-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="41dd7-157">Metod</span><span class="sxs-lookup"><span data-stu-id="41dd7-157">Method</span></span>  |<span data-ttu-id="41dd7-158">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="41dd7-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="41dd7-159">**Windows Update** på Kontrollpanelen</span><span class="sxs-lookup"><span data-stu-id="41dd7-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="41dd7-160">- **Om du installerar uppdateringar** installeras alla uppdateringar automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="41dd7-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="41dd7-161">- **Ladda ned uppdateringar men låt mig välja** om jag vill installera dem så att Windows Defender kan ladda ned och installera säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="41dd7-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="41dd7-162">**Grupprincip**</span><span class="sxs-lookup"><span data-stu-id="41dd7-162">**Group Policy**</span></span>     | <span data-ttu-id="41dd7-163">Du kan konfigurera och hantera Windows Update med hjälp av inställningarna i Grupprincip på följande sätt: **Administrativa mallar\Windows-komponenter\Windows Update\Konfigurera automatiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="41dd7-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="41dd7-164">Registernyckeln **AUOptions**</span><span class="sxs-lookup"><span data-stu-id="41dd7-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="41dd7-165">Med följande två värden kan Windows Update ladda ned och installera säkerhetsintelligensuppdateringar automatiskt:</span><span class="sxs-lookup"><span data-stu-id="41dd7-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="41dd7-166">- **4**  -  **Installera uppdateringar automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="41dd7-167">Det här värdet leder till att alla uppdateringar installeras automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="41dd7-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="41dd7-168">- **3**  -  **Ladda ned uppdateringar men låt mig välja om jag vill installera dem**.</span><span class="sxs-lookup"><span data-stu-id="41dd7-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="41dd7-169">Med det här värdet kan Windows Defender ladda ned och installera Säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="41dd7-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="41dd7-170">För att säkerställa att skyddet mot skadlig programvara bibehålls rekommenderar vi att du aktiverar följande tjänster:</span><span class="sxs-lookup"><span data-stu-id="41dd7-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="41dd7-171">Windows felrapporteringstjänst</span><span class="sxs-lookup"><span data-stu-id="41dd7-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="41dd7-172">Windows Update-tjänst</span><span class="sxs-lookup"><span data-stu-id="41dd7-172">Windows Update service</span></span>

<span data-ttu-id="41dd7-173">I följande tabell visas tjänsterna för Microsoft Defender Antivirus och de beroende tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="41dd7-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="41dd7-174">Tjänstnamn</span><span class="sxs-lookup"><span data-stu-id="41dd7-174">Service Name</span></span>|<span data-ttu-id="41dd7-175">Filplats</span><span class="sxs-lookup"><span data-stu-id="41dd7-175">File Location</span></span>|<span data-ttu-id="41dd7-176">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="41dd7-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="41dd7-177">Windows Defender-tjänsten (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="41dd7-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="41dd7-178">Det här är den huvudsakliga Microsoft Defender Antivirus-tjänsten som måste köras hela tiden.</span><span class="sxs-lookup"><span data-stu-id="41dd7-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="41dd7-179">Windows-felrapporteringstjänst (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="41dd7-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="41dd7-180">Den här tjänsten skickar felrapporter tillbaka till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41dd7-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="41dd7-181">Windows Defender-brandväggen (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="41dd7-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="41dd7-182">Vi rekommenderar att du lämnar windows Defender-brandväggstjänsten aktiverad.</span><span class="sxs-lookup"><span data-stu-id="41dd7-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="41dd7-183">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="41dd7-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="41dd7-184">Windows Update krävs för att få säkerhetsintelligensuppdateringar och uppdateringar av program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="41dd7-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="41dd7-185">Skicka exempel</span><span class="sxs-lookup"><span data-stu-id="41dd7-185">Submit samples</span></span>

<span data-ttu-id="41dd7-186">Exempel på inskickning gör att Microsoft kan samla in exempel på potentiellt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="41dd7-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="41dd7-187">För att ge fortsatt och uppdaterat skydd använder Microsoft forskare dessa exempel för att analysera misstänkta aktiviteter och skapa uppdaterade säkerhetsinformation mot skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="41dd7-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="41dd7-188">Vi samlar in körbara programfiler, till exempel EXE-filer och DLL-filer.</span><span class="sxs-lookup"><span data-stu-id="41dd7-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="41dd7-189">Vi samlar inte in filer som innehåller personuppgifter som Microsoft Word-dokument och PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="41dd7-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="41dd7-190">Skicka en fil</span><span class="sxs-lookup"><span data-stu-id="41dd7-190">Submit a file</span></span>

1. <span data-ttu-id="41dd7-191">Läs [inskickingsguiden.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="41dd7-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="41dd7-192">Besök [exempelportalen för inskicking](https://www.microsoft.com/wdsi/filesubmission)och skicka filen.</span><span class="sxs-lookup"><span data-stu-id="41dd7-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="41dd7-193">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="41dd7-193">Enable automatic sample submission</span></span>

<span data-ttu-id="41dd7-194">Om du vill aktivera automatisk exempelinskickning startar du en Windows PowerShell-konsol som administratör och anger värdedata för **SubmitSamplesConsent** enligt någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="41dd7-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="41dd7-195">Inställning</span><span class="sxs-lookup"><span data-stu-id="41dd7-195">Setting</span></span>  |<span data-ttu-id="41dd7-196">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="41dd7-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="41dd7-197">**0**  -  **Fråga alltid**</span><span class="sxs-lookup"><span data-stu-id="41dd7-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="41dd7-198">I antivirustjänsten Microsoft Defender uppmanas du att bekräfta inskickningen av alla nödvändiga filer.</span><span class="sxs-lookup"><span data-stu-id="41dd7-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="41dd7-199">Det här är standardinställningen för Microsoft Defender Antivirus, men rekommenderas inte för installationer på Windows Server 2016 eller 2019 utan guid.</span><span class="sxs-lookup"><span data-stu-id="41dd7-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="41dd7-200">**1**   -  **Skicka säkra exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="41dd7-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="41dd7-201">Antivirustjänsten Microsoft Defender skickar alla filer som markerats som "säkra" och frågar efter resten av filerna.</span><span class="sxs-lookup"><span data-stu-id="41dd7-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="41dd7-202">**2**  -  **Skicka aldrig**</span><span class="sxs-lookup"><span data-stu-id="41dd7-202">**2** - **Never send**</span></span>      |<span data-ttu-id="41dd7-203">Microsoft Defender Antivirus-tjänsten uppmanas inte och skickar inga filer.</span><span class="sxs-lookup"><span data-stu-id="41dd7-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="41dd7-204">**3**  -  **Skicka alla exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="41dd7-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="41dd7-205">Antivirustjänsten Microsoft Defender skickar alla filer utan en uppmaning om att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="41dd7-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="41dd7-206">Konfigurera automatiska undantag</span><span class="sxs-lookup"><span data-stu-id="41dd7-206">Configure automatic exclusions</span></span>

<span data-ttu-id="41dd7-207">För att säkerställa säkerhet och prestanda läggs vissa undantag till automatiskt utifrån de roller och funktioner som du installerar när du använder Microsoft Defender Antivirus på Windows Server 2016 eller 2019.</span><span class="sxs-lookup"><span data-stu-id="41dd7-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="41dd7-208">Se [Konfigurera undantag i Microsoft Defender Antivirus på Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="41dd7-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="41dd7-209">Behöver du ställa in Microsoft Defender Antivirus på passiv form?</span><span class="sxs-lookup"><span data-stu-id="41dd7-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="41dd7-210">Om du använder en produkt som inte är en Microsoft-antivirusprodukt som primär antiviruslösning, ställ in Microsoft Defender Antivirus på passivt läge.</span><span class="sxs-lookup"><span data-stu-id="41dd7-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="41dd7-211">Ställ in Microsoft Defender Antivirus på passivt läge med hjälp av en registernyckel</span><span class="sxs-lookup"><span data-stu-id="41dd7-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="41dd7-212">Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus på passiv form genom att ange följande registernyckel:</span><span class="sxs-lookup"><span data-stu-id="41dd7-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="41dd7-213">Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="41dd7-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="41dd7-214">Namn: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="41dd7-214">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="41dd7-215">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="41dd7-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="41dd7-216">Värde: `1`</span><span class="sxs-lookup"><span data-stu-id="41dd7-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="41dd7-217">Inaktivera Microsoft Defender Antivirus med hjälp av guiden Ta bort roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="41dd7-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="41dd7-218">Se [Installera eller avinstallera roller, rolltjänster eller funktioner och](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)använd guiden Ta bort roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="41dd7-219">När du kommer till **steget Funktioner** i guiden avmarkerar du alternativet **Windows Defender-funktioner.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="41dd7-220">Om du tar **bort Windows Defender** för sig själv under avsnittet Om Windows **Defender-funktioner** uppmanas du att ta bort gränssnittsalternativet GUI för **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="41dd7-221">Microsoft Defender Antivirus körs fortfarande normalt utan användargränssnittet, men användargränssnittet kan inte aktiveras om du inaktiverar **Windows Defender-huvudfunktionen.**</span><span class="sxs-lookup"><span data-stu-id="41dd7-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="41dd7-222">Inaktivera användargränssnittet i Microsoft Defender Antivirus med PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dd7-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="41dd7-223">Om du vill inaktivera Microsoft Defender Antivirus GUI använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="41dd7-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="41dd7-224">Använder du Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="41dd7-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="41dd7-225">Om du använder Windows Server 2016 och en antimalware/antivirusprodukt från tredje part som inte erbjuds eller utvecklas av Microsoft, måste du inaktivera/avinstallera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="41dd7-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="41dd7-226">Du kan inte avinstallera Windows-säkerhetsappen, men du kan inaktivera gränssnittet med hjälp av de här instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="41dd7-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="41dd7-227">Följande PowerShell-cmdlet avinstallerar Microsoft Defender Antivirus på Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="41dd7-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="41dd7-228">Se även</span><span class="sxs-lookup"><span data-stu-id="41dd7-228">See also</span></span>

- [<span data-ttu-id="41dd7-229">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="41dd7-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="41dd7-230">Kompatibilitet med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="41dd7-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
