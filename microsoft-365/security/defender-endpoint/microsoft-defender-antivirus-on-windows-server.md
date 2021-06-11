---
title: Microsoft Defender Antivirus på Windows Server
description: Lär dig hur du aktiverar och konfigurerar Microsoft Defender Antivirus på Windows Server 2016 och Windows Server 2019.
keywords: windows defender, server, s defender, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539281"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="da911-104">Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="da911-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da911-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="da911-105">**Applies to:**</span></span>

- [<span data-ttu-id="da911-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="da911-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="da911-107">Microsoft Defender Antivirus tillgänglig på följande versioner av Windows Server:</span><span class="sxs-lookup"><span data-stu-id="da911-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="da911-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="da911-108">Windows Server 2019</span></span>
- <span data-ttu-id="da911-109">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="da911-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="da911-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="da911-110">Windows Server 2016.</span></span> 

<span data-ttu-id="da911-111">I vissa fall kallas Microsoft Defender Antivirus kallas för *Endpoint Protection*; Protectionmotorn är dock densamma.</span><span class="sxs-lookup"><span data-stu-id="da911-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="da911-112">Även om funktionerna, konfigurationen och hanteringen till stor del är samma för Microsoft Defender Antivirus på [Windows 10](microsoft-defender-antivirus-in-windows-10.md)finns det några viktiga skillnader på Windows Server:</span><span class="sxs-lookup"><span data-stu-id="da911-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="da911-113">På Windows Server [tillämpas automatiska undantag](configure-server-exclusions-microsoft-defender-antivirus.md) baserat på din definierade serverroll.</span><span class="sxs-lookup"><span data-stu-id="da911-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="da911-114">På Windows Server och du kör en lösning som inte är ett Microsoft-antivirusprogram eller ett program mot skadlig programvara Microsoft Defender Antivirus inte antingen passivt läge eller inaktiverat läge automatiskt.</span><span class="sxs-lookup"><span data-stu-id="da911-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="da911-115">Du kan dock manuellt Microsoft Defender Antivirus passivt eller inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="da911-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="da911-116">Konfigurera Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="da911-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="da911-117">Processen för att konfigurera och köra Microsoft Defender Antivirus på en serverplattform omfattar flera steg:</span><span class="sxs-lookup"><span data-stu-id="da911-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="da911-118">[Aktivera gränssnittet.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="da911-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="da911-119">[Installera Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="da911-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="da911-120">[Kontrollera Microsoft Defender Antivirus är igång.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="da911-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="da911-121">[Uppdatera säkerhetsinformation för program mot skadlig programvara](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="da911-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="da911-122">(Vid behov) [Skicka exempel](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="da911-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="da911-123">(Vid behov) [Konfigurera automatiska undantag](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="da911-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="da911-124">(Endast om det behövs) [Ställ Microsoft Defender Antivirus till passivt läge](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="da911-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="da911-125">Aktivera användargränssnittet på Windows Server</span><span class="sxs-lookup"><span data-stu-id="da911-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="da911-126">Som standard är Microsoft Defender Antivirus installerad och fungerar på Windows Server.</span><span class="sxs-lookup"><span data-stu-id="da911-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="da911-127">Ibland installeras användargränssnittet som standard, men det behövs inte.</span><span class="sxs-lookup"><span data-stu-id="da911-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="da911-128">Du kan använda PowerShell, grupprinciper eller andra metoder för att hantera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="da911-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="da911-129">Om GUI:t inte är installerat på servern och du  vill installera det, antingen guiden Lägg till roller och funktioner eller PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="da911-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="da911-130">Aktivera GUI:t med guiden Lägg till roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="da911-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="da911-131">Se [Installera roller, rolltjänster och funktioner med hjälp](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)av guiden Lägg till roller och funktioner och använd guiden Lägg till roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="da911-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="da911-132">När du kommer till **steget Funktioner** i guiden går du **Windows Defender** under Funktioner och väljer alternativet GUI **för Windows Defender** gränssnitt.</span><span class="sxs-lookup"><span data-stu-id="da911-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="da911-133">I Windows Server 2016 ser guiden **Lägg till roller och funktioner** ut så här:</span><span class="sxs-lookup"><span data-stu-id="da911-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Guiden Lägg till roller och funktioner med guid för Windows Defender alternativ](images/server-add-gui.png)

   <span data-ttu-id="da911-135">I Windows Server 2019 påminner **guiden Lägg till roller och funktioner** om liknande.</span><span class="sxs-lookup"><span data-stu-id="da911-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="da911-136">Aktivera GUI:t med PowerShell</span><span class="sxs-lookup"><span data-stu-id="da911-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="da911-137">Följande PowerShell-cmdlet aktiverar gränssnittet:</span><span class="sxs-lookup"><span data-stu-id="da911-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="da911-138">Installera Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="da911-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="da911-139">Om du behöver installera eller installera Microsoft Defender Antivirus på Windows Server kan du göra det med hjälp av guiden Lägg till roller **och** funktioner eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da911-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="da911-140">Använd guiden Lägg till roller och funktioner för att installera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="da911-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="da911-141">Läs den [här artikeln](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)och använd guiden Lägg till roller **och funktioner.**</span><span class="sxs-lookup"><span data-stu-id="da911-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="da911-142">När du kommer till **steget Funktioner** i guiden väljer du Microsoft Defender Antivirus funktioner.</span><span class="sxs-lookup"><span data-stu-id="da911-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="da911-143">Välj även **guid för Windows Defender guidning.**</span><span class="sxs-lookup"><span data-stu-id="da911-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="da911-144">Använd PowerShell för att installera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="da911-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="da911-145">Om du vill använda PowerShell för Microsoft Defender Antivirus kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da911-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="da911-146">Händelsemeddelanden för den programskyddsmotor som ingår i Microsoft Defender Antivirus finns i [Microsoft Defender AV-händelser.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="da911-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="da911-147">Kontrollera Microsoft Defender Antivirus körs</span><span class="sxs-lookup"><span data-stu-id="da911-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="da911-148">När Microsoft Defender Antivirus har installerats är nästa steg att verifiera att den körs.</span><span class="sxs-lookup"><span data-stu-id="da911-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="da911-149">Kör följande PowerShell-cmdlet på din Windows Server-slutpunkt:</span><span class="sxs-lookup"><span data-stu-id="da911-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="da911-150">Kontrollera att brandväggsskyddet är aktiverat genom att köra följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da911-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="da911-151">Som ett alternativ till PowerShell kan du använda Kommandotolken för att verifiera Microsoft Defender Antivirus körs.</span><span class="sxs-lookup"><span data-stu-id="da911-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="da911-152">Det gör du genom att köra följande kommando från en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="da911-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="da911-153">Kommandot `sc query` returnerar information om Microsoft Defender Antivirus tjänst.</span><span class="sxs-lookup"><span data-stu-id="da911-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="da911-154">När Microsoft Defender Antivirus körs visas `STATE` värdet `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="da911-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="da911-155">Uppdatera säkerhetsinformation för program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="da911-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="da911-156">Om du vill ha uppdaterad säkerhetsinformation för program mot skadlig programvara måste Windows uppdatera tjänsten vara igång.</span><span class="sxs-lookup"><span data-stu-id="da911-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="da911-157">Om du använder en uppdateringshanteringstjänst, till exempel Windows Server Update Services (WSUS), ser du till att uppdateringar för Microsoft Defender Antivirus Säkerhetsinformation har godkänts för de datorer du hanterar.</span><span class="sxs-lookup"><span data-stu-id="da911-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="da911-158">Som standard laddar Windows inte ned och installerar uppdateringar automatiskt på Windows Server 2019 eller Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="da911-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="da911-159">Du kan ändra den här konfigurationen på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="da911-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="da911-160">Metod</span><span class="sxs-lookup"><span data-stu-id="da911-160">Method</span></span>  |<span data-ttu-id="da911-161">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="da911-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="da911-162">**Windows på** Kontrollpanelen</span><span class="sxs-lookup"><span data-stu-id="da911-162">**Windows Update** in Control Panel</span></span>     | <span data-ttu-id="da911-163">**Om du installerar uppdateringar** installeras alla uppdateringar automatiskt, även Windows Defender säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="da911-163">**Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="da911-164">**Ladda ned uppdateringar men låt mig välja** om de ska installeras så att Windows Defender kan ladda ned och installera säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="da911-164">**Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="da911-165">**Grupprincip**</span><span class="sxs-lookup"><span data-stu-id="da911-165">**Group Policy**</span></span>     | <span data-ttu-id="da911-166">Du kan konfigurera och hantera Windows-uppdatering med hjälp av inställningarna i Grupprincip på följande sökväg: **Administrativa mallar\Windows Components\Windows Update\Configure Automatic Updates**</span><span class="sxs-lookup"><span data-stu-id="da911-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="da911-167">Registernyckeln **AUOptions**</span><span class="sxs-lookup"><span data-stu-id="da911-167">The **AUOptions** registry key</span></span>     | <span data-ttu-id="da911-168">Med följande två värden kan Windows att automatiskt ladda ned och installera säkerhetsintelligensuppdateringar:</span><span class="sxs-lookup"><span data-stu-id="da911-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <p><span data-ttu-id="da911-169">**4**  -  **Installera uppdateringar automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="da911-169">**4** - **Install updates automatically**.</span></span> <span data-ttu-id="da911-170">Det här värdet leder till att alla uppdateringar installeras automatiskt, Windows Defender säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="da911-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="da911-171">**3**  -  **Ladda ned uppdateringar men låt mig välja om jag vill installera dem**.</span><span class="sxs-lookup"><span data-stu-id="da911-171">**3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="da911-172">Med det här Windows Defender du ladda ned och installera Säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="da911-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="da911-173">För att säkerställa att skyddet mot skadlig programvara bibehålls rekommenderar vi att du aktiverar följande tjänster:</span><span class="sxs-lookup"><span data-stu-id="da911-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="da911-174">Windows Felrapportering tjänst</span><span class="sxs-lookup"><span data-stu-id="da911-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="da911-175">Windows Uppdatera tjänst</span><span class="sxs-lookup"><span data-stu-id="da911-175">Windows Update service</span></span>

<span data-ttu-id="da911-176">I följande tabell visas tjänsterna för Microsoft Defender Antivirus och de beroende tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="da911-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="da911-177">Tjänstnamn</span><span class="sxs-lookup"><span data-stu-id="da911-177">Service Name</span></span>|<span data-ttu-id="da911-178">Filplats</span><span class="sxs-lookup"><span data-stu-id="da911-178">File Location</span></span>|<span data-ttu-id="da911-179">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="da911-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="da911-180">Windows Defender Tjänst (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="da911-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="da911-181">Det här är Microsoft Defender Antivirus tjänst som alltid måste köras.</span><span class="sxs-lookup"><span data-stu-id="da911-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="da911-182">Windows Felrapportering Tjänst (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="da911-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="da911-183">Den här tjänsten skickar felrapporter tillbaka till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="da911-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="da911-184">Windows Defender-brandväggen (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="da911-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="da911-185">Vi rekommenderar att Windows Defender-brandväggen tjänsten är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="da911-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="da911-186">Windows Uppdatering (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="da911-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="da911-187">Windows Uppdatering krävs för att få säkerhetsintelligensuppdateringar och uppdateringar av program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="da911-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="da911-188">Skicka exempel</span><span class="sxs-lookup"><span data-stu-id="da911-188">Submit samples</span></span>

<span data-ttu-id="da911-189">Exempel på inskickning gör att Microsoft kan samla in exempel på potentiellt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="da911-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="da911-190">För att ge fortsatt och uppdaterat skydd använder Microsoft forskare dessa exempel för att analysera misstänkta aktiviteter och skapa uppdaterade säkerhetsinformation mot skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="da911-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="da911-191">Vi samlar in körbara programfiler, till exempel .exe filer och .dll filer.</span><span class="sxs-lookup"><span data-stu-id="da911-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="da911-192">Vi samlar inte in filer som innehåller personuppgifter, t.ex. Microsoft Word dokument och PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="da911-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="da911-193">Skicka en fil</span><span class="sxs-lookup"><span data-stu-id="da911-193">Submit a file</span></span>

1. <span data-ttu-id="da911-194">Läs [inskickingsguiden.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="da911-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="da911-195">Besök [exempelportalen för inskicking](https://www.microsoft.com/wdsi/filesubmission)och skicka filen.</span><span class="sxs-lookup"><span data-stu-id="da911-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="da911-196">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="da911-196">Enable automatic sample submission</span></span>

<span data-ttu-id="da911-197">Om du vill aktivera automatisk exempelinskickning startar du en Windows PowerShell konsol som administratör och anger värdedata för **SubmitSamplesConsent** enligt någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="da911-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="da911-198">Inställning</span><span class="sxs-lookup"><span data-stu-id="da911-198">Setting</span></span>  |<span data-ttu-id="da911-199">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="da911-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="da911-200">**0**  -  **Fråga alltid**</span><span class="sxs-lookup"><span data-stu-id="da911-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="da911-201">I Microsoft Defender Antivirus uppmanas du att bekräfta överföringen av alla nödvändiga filer.</span><span class="sxs-lookup"><span data-stu-id="da911-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="da911-202">Det här är standardinställningen för Microsoft Defender Antivirus men rekommenderas inte för installationer på Windows Server 2016 eller 2019 utan guid.</span><span class="sxs-lookup"><span data-stu-id="da911-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="da911-203">**1**   -  **Skicka säkra exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="da911-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="da911-204">I Microsoft Defender Antivirus skickar alla filer som markerats som "säkra" och uppmanar dig att ange resten av filerna.</span><span class="sxs-lookup"><span data-stu-id="da911-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="da911-205">**2**  -  **Skicka aldrig**</span><span class="sxs-lookup"><span data-stu-id="da911-205">**2** - **Never send**</span></span>      |<span data-ttu-id="da911-206">Tjänsten Microsoft Defender Antivirus fråga och skickar inga filer.</span><span class="sxs-lookup"><span data-stu-id="da911-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="da911-207">**3**  -  **Skicka alla exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="da911-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="da911-208">Den Microsoft Defender Antivirus skickar alla filer utan att du uppmanas att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="da911-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="da911-209">Konfigurera automatiska undantag</span><span class="sxs-lookup"><span data-stu-id="da911-209">Configure automatic exclusions</span></span>

<span data-ttu-id="da911-210">För att säkerställa säkerhet och prestanda läggs vissa undantag till automatiskt baserat på de roller och funktioner som du installerar när du använder Microsoft Defender Antivirus på Windows Server 2016 eller 2019.</span><span class="sxs-lookup"><span data-stu-id="da911-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="da911-211">Se [Konfigurera undantag i Microsoft Defender Antivirus på Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="da911-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="da911-212">Behöver du ställa Microsoft Defender Antivirus till passivt läge?</span><span class="sxs-lookup"><span data-stu-id="da911-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="da911-213">Om du använder ett annat antivirusprogram än Microsoft som din primära antiviruslösning på Windows Server, måste du ställa Microsoft Defender Antivirus till passivt läge eller inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="da911-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="da911-214">I Windows Server, version 1803 eller senare, eller Windows Server 2019, kan du Microsoft Defender Antivirus passivt läge.</span><span class="sxs-lookup"><span data-stu-id="da911-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="da911-215">På Windows Server 2016 stöds Microsoft Defender Antivirus inte tillsammans med en produkt som inte är ett Microsoft-antivirusprogram eller en antimalware-produkt.</span><span class="sxs-lookup"><span data-stu-id="da911-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="da911-216">I sådana fall måste du Microsoft Defender Antivirus in i inaktivt läge.</span><span class="sxs-lookup"><span data-stu-id="da911-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="da911-217">Ställ Microsoft Defender Antivirus till passivt läge med hjälp av en registernyckel</span><span class="sxs-lookup"><span data-stu-id="da911-217">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="da911-218">Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus till passivt läge genom att ange följande registernyckel:</span><span class="sxs-lookup"><span data-stu-id="da911-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="da911-219">Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="da911-219">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="da911-220">Namn: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="da911-220">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="da911-221">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="da911-221">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="da911-222">Värde: `1`</span><span class="sxs-lookup"><span data-stu-id="da911-222">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="da911-223">Inaktivera Microsoft Defender Antivirus med hjälp av guiden Ta bort roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="da911-223">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="da911-224">Se [Installera eller avinstallera roller, rolltjänster eller funktioner och](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)använd guiden Ta bort roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="da911-224">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="da911-225">När du kommer till **steget Funktioner** i guiden avmarkerar du Windows Defender **Funktioner.**</span><span class="sxs-lookup"><span data-stu-id="da911-225">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="da911-226">Om du **rensar Windows Defender** för sig själv **under avsnittet Windows Defender-funktioner** uppmanas du att ta bort gränssnittsalternativet GUI **för Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="da911-226">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="da911-227">Microsoft Defender Antivirus körs fortfarande normalt utan användargränssnittet, men användargränssnittet kan inte aktiveras om du inaktiverar **Windows Defender** huvudfunktionen.</span><span class="sxs-lookup"><span data-stu-id="da911-227">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="da911-228">Stänga av Microsoft Defender Antivirus användargränssnittet med PowerShell</span><span class="sxs-lookup"><span data-stu-id="da911-228">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="da911-229">Om du vill inaktivera Microsoft Defender Antivirus GUI använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da911-229">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="da911-230">Använder du Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="da911-230">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="da911-231">Om du använder Windows Server 2016 och en antimalware/antivirusprodukt från tredje part som inte erbjuds eller utvecklas av Microsoft, måste du inaktivera/avinstallera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="da911-231">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="da911-232">Du kan inte avinstallera Windows-säkerhet-appen, men du kan inaktivera gränssnittet med hjälp av de här instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="da911-232">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="da911-233">Följande PowerShell-cmdlet avinstallerar Microsoft Defender Antivirus på Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="da911-233">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="da911-234">Om du Microsoft Defender Antivirus att Windows Server 2016 med hjälp av följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="da911-234">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="da911-235">Se även</span><span class="sxs-lookup"><span data-stu-id="da911-235">See also</span></span>

- [<span data-ttu-id="da911-236">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="da911-236">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="da911-237">Microsoft Defender Antivirus kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="da911-237">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
