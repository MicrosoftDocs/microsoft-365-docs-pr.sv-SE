---
title: Microsoft Defender Antivirus på Windows Server
description: Läs om hur du aktiverar och konfigurerar Microsoft Defender Antivirus i Windows Server 2016 och Windows Server 2019.
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
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269498"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="0977a-104">Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="0977a-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0977a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0977a-105">**Applies to:**</span></span>

- [<span data-ttu-id="0977a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0977a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0977a-107">Microsoft Defender Antivirus är tillgängligt på följande versioner av Windows Server:</span><span class="sxs-lookup"><span data-stu-id="0977a-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="0977a-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="0977a-108">Windows Server 2019</span></span>
- <span data-ttu-id="0977a-109">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="0977a-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="0977a-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="0977a-110">Windows Server 2016.</span></span> 

<span data-ttu-id="0977a-111">I vissa fall kallas Microsoft Defender Antivirus för *Endpoint Protection*. Protectionmotorn är dock densamma.</span><span class="sxs-lookup"><span data-stu-id="0977a-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="0977a-112">Även om funktionerna, konfigurationen och hanteringen i stort sett är desamma för Microsoft Defender Antivirus i [Windows 10](microsoft-defender-antivirus-in-windows-10.md)finns det några viktiga skillnader på Windows Server:</span><span class="sxs-lookup"><span data-stu-id="0977a-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="0977a-113">I Windows Server [tillämpas automatiska undantag](configure-server-exclusions-microsoft-defender-antivirus.md) baserat på den definierade serverrollen.</span><span class="sxs-lookup"><span data-stu-id="0977a-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="0977a-114">Om du kör en lösning som inte är en Microsoft-antivirus-/antimalwarelösning på Windows Server förs inte Microsoft Defender Antivirus automatiskt in i antingen passivt läge eller inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="0977a-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="0977a-115">Du kan dock ställa in Microsoft Defender Antivirus på passivt eller inaktiverat läge manuellt.</span><span class="sxs-lookup"><span data-stu-id="0977a-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="0977a-116">Konfigurera Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="0977a-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="0977a-117">Det finns flera steg i processen för att konfigurera och köra Microsoft Defender Antivirus på en serverplattform:</span><span class="sxs-lookup"><span data-stu-id="0977a-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="0977a-118">[Aktivera gränssnittet.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="0977a-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="0977a-119">[Installera Microsoft Defender Antivirus.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="0977a-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="0977a-120">[Kontrollera att Microsoft Defender Antivirus körs](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="0977a-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="0977a-121">[Uppdatera säkerhetsinformation för program mot skadlig programvara](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="0977a-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="0977a-122">(Vid behov) [Skicka exempel](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="0977a-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="0977a-123">(Vid behov) [Konfigurera automatiska undantag](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="0977a-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="0977a-124">(Endast om det behövs) [Ställ in Microsoft Defender Antivirus på passivt läge](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="0977a-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="0977a-125">Aktivera användargränssnittet på Windows Server</span><span class="sxs-lookup"><span data-stu-id="0977a-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="0977a-126">Som standard installeras och fungerar Microsoft Defender Antivirus på Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0977a-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="0977a-127">Ibland installeras användargränssnittet som standard, men det behövs inte.</span><span class="sxs-lookup"><span data-stu-id="0977a-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="0977a-128">Du kan använda PowerShell, grupprinciper eller andra metoder för att hantera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0977a-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="0977a-129">Om GUI:t inte är installerat på servern och du  vill installera det, antingen guiden Lägg till roller och funktioner eller PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0977a-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="0977a-130">Aktivera GUI:t med guiden Lägg till roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="0977a-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="0977a-131">Se [Installera roller, rolltjänster och funktioner med hjälp](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)av guiden Lägg till roller och funktioner och använd guiden Lägg till roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="0977a-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="0977a-132">När du kommer till **steget Funktioner** i guiden väljer du alternativet GUI för Windows Defender under Windows **Defender-funktioner.** </span><span class="sxs-lookup"><span data-stu-id="0977a-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="0977a-133">I Windows Server 2016 ser guiden **Lägg till roller och funktioner** ut så här:</span><span class="sxs-lookup"><span data-stu-id="0977a-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Guiden Lägg till roller och funktioner med guid för Windows Defender-alternativet](images/server-add-gui.png)

   <span data-ttu-id="0977a-135">I Windows Server 2019 påminner **guiden Lägg till roller och funktioner** om liknande.</span><span class="sxs-lookup"><span data-stu-id="0977a-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="0977a-136">Aktivera GUI:t med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0977a-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="0977a-137">Följande PowerShell-cmdlet aktiverar gränssnittet:</span><span class="sxs-lookup"><span data-stu-id="0977a-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="0977a-138">Installera Microsoft Defender Antivirus på Windows Server</span><span class="sxs-lookup"><span data-stu-id="0977a-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="0977a-139">Om du behöver installera eller installera om Microsoft Defender Antivirus på Windows Server kan du göra det med hjälp av guiden Lägg till **roller** och funktioner eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0977a-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="0977a-140">Använd guiden Lägg till roller och funktioner för att installera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0977a-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="0977a-141">Läs den [här artikeln](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)och använd guiden Lägg till roller **och funktioner.**</span><span class="sxs-lookup"><span data-stu-id="0977a-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="0977a-142">När du kommer till **steget Funktioner** i guiden väljer du alternativet Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0977a-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="0977a-143">Välj även **alternativet GUI för Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="0977a-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="0977a-144">Använda PowerShell för att installera Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0977a-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="0977a-145">Om du vill använda PowerShell för att installera Microsoft Defender Antivirus kör du följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0977a-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="0977a-146">Händelsemeddelanden för den antimalware-motor som ingår i Microsoft Defender Antivirus finns i [Microsoft Defender AV-händelser.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0977a-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="0977a-147">Kontrollera att Microsoft Defender Antivirus körs</span><span class="sxs-lookup"><span data-stu-id="0977a-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="0977a-148">När Du har installerat Microsoft Defender Antivirus är nästa steg att verifiera att det körs.</span><span class="sxs-lookup"><span data-stu-id="0977a-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="0977a-149">Kör följande PowerShell-cmdlet på Windows Server-slutpunkten:</span><span class="sxs-lookup"><span data-stu-id="0977a-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="0977a-150">Kontrollera att brandväggsskyddet är aktiverat genom att köra följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0977a-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="0977a-151">Som ett alternativ till PowerShell kan du använda Kommandotolken för att verifiera att Microsoft Defender Antivirus körs.</span><span class="sxs-lookup"><span data-stu-id="0977a-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="0977a-152">Det gör du genom att köra följande kommando från en kommandotolk:</span><span class="sxs-lookup"><span data-stu-id="0977a-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="0977a-153">Kommandot `sc query` returnerar information om Microsoft Defender Antivirus-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0977a-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="0977a-154">När Microsoft Defender Antivirus körs visas `STATE` `RUNNING` värdet.</span><span class="sxs-lookup"><span data-stu-id="0977a-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="0977a-155">Uppdatera säkerhetsinformation för program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="0977a-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="0977a-156">För att få uppdaterad säkerhetsinformation för program mot skadlig programvara måste du ha Windows Update-tjänsten igång.</span><span class="sxs-lookup"><span data-stu-id="0977a-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="0977a-157">Om du använder en uppdateringshanteringstjänst, t.ex. Windows Server Update Services (WSUS), ser du till att uppdateringar för Microsoft Defender Antivirus Security Intelligence är godkända för de datorer du hanterar.</span><span class="sxs-lookup"><span data-stu-id="0977a-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="0977a-158">Som standard laddar inte Windows Update ned och installerar uppdateringar automatiskt på Windows Server 2019 eller Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="0977a-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="0977a-159">Du kan ändra den här konfigurationen på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="0977a-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="0977a-160">Metod</span><span class="sxs-lookup"><span data-stu-id="0977a-160">Method</span></span>  |<span data-ttu-id="0977a-161">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0977a-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0977a-162">**Windows Update** på Kontrollpanelen</span><span class="sxs-lookup"><span data-stu-id="0977a-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="0977a-163">- **Om du installerar uppdateringar** installeras alla uppdateringar automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="0977a-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="0977a-164">- **Ladda ned uppdateringar men låt mig välja** om jag vill installera dem så att Windows Defender kan ladda ned och installera säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0977a-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="0977a-165">**Grupprincip**</span><span class="sxs-lookup"><span data-stu-id="0977a-165">**Group Policy**</span></span>     | <span data-ttu-id="0977a-166">Du kan konfigurera och hantera Windows Update med hjälp av inställningarna i Grupprincip på följande sätt: **Administrativa mallar\Windows-komponenter\Windows Update\Konfigurera automatiska uppdateringar**</span><span class="sxs-lookup"><span data-stu-id="0977a-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="0977a-167">Registernyckeln **AUOptions**</span><span class="sxs-lookup"><span data-stu-id="0977a-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="0977a-168">Med följande två värden kan Windows Update ladda ned och installera säkerhetsintelligensuppdateringar automatiskt:</span><span class="sxs-lookup"><span data-stu-id="0977a-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="0977a-169">- **4**  -  **Installera uppdateringar automatiskt.**</span><span class="sxs-lookup"><span data-stu-id="0977a-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="0977a-170">Det här värdet leder till att alla uppdateringar installeras automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="0977a-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="0977a-171">- **3**  -  **Ladda ned uppdateringar men låt mig välja om jag vill installera dem**.</span><span class="sxs-lookup"><span data-stu-id="0977a-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="0977a-172">Med det här värdet kan Windows Defender ladda ned och installera Säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0977a-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="0977a-173">För att säkerställa att skyddet mot skadlig programvara bibehålls rekommenderar vi att du aktiverar följande tjänster:</span><span class="sxs-lookup"><span data-stu-id="0977a-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="0977a-174">Windows felrapporteringstjänst</span><span class="sxs-lookup"><span data-stu-id="0977a-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="0977a-175">Windows Update-tjänst</span><span class="sxs-lookup"><span data-stu-id="0977a-175">Windows Update service</span></span>

<span data-ttu-id="0977a-176">I följande tabell visas tjänsterna för Microsoft Defender Antivirus och de beroende tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="0977a-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="0977a-177">Tjänstnamn</span><span class="sxs-lookup"><span data-stu-id="0977a-177">Service Name</span></span>|<span data-ttu-id="0977a-178">Filplats</span><span class="sxs-lookup"><span data-stu-id="0977a-178">File Location</span></span>|<span data-ttu-id="0977a-179">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0977a-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="0977a-180">Windows Defender-tjänsten (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="0977a-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="0977a-181">Det här är den huvudsakliga Microsoft Defender Antivirus-tjänsten som måste köras hela tiden.</span><span class="sxs-lookup"><span data-stu-id="0977a-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="0977a-182">Windows-felrapporteringstjänst (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="0977a-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="0977a-183">Den här tjänsten skickar felrapporter tillbaka till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0977a-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="0977a-184">Windows Defender-brandväggen (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="0977a-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="0977a-185">Vi rekommenderar att du lämnar windows Defender-brandväggstjänsten aktiverad.</span><span class="sxs-lookup"><span data-stu-id="0977a-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="0977a-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="0977a-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="0977a-187">Windows Update krävs för att få säkerhetsintelligensuppdateringar och uppdateringar av program mot skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="0977a-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="0977a-188">Skicka exempel</span><span class="sxs-lookup"><span data-stu-id="0977a-188">Submit samples</span></span>

<span data-ttu-id="0977a-189">Exempel på inskickning gör att Microsoft kan samla in exempel på potentiellt skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0977a-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="0977a-190">För att ge fortsatt och uppdaterat skydd använder Microsoft forskare dessa exempel för att analysera misstänkta aktiviteter och skapa uppdaterade säkerhetsinformation mot skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="0977a-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="0977a-191">Vi samlar in körbara programfiler, till exempel .exe filer och .dll filer.</span><span class="sxs-lookup"><span data-stu-id="0977a-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="0977a-192">Vi samlar inte in filer som innehåller personuppgifter som Microsoft Word-dokument och PDF-filer.</span><span class="sxs-lookup"><span data-stu-id="0977a-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="0977a-193">Skicka en fil</span><span class="sxs-lookup"><span data-stu-id="0977a-193">Submit a file</span></span>

1. <span data-ttu-id="0977a-194">Läs [inskickingsguiden.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="0977a-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="0977a-195">Besök [exempelportalen för inskicking](https://www.microsoft.com/wdsi/filesubmission)och skicka filen.</span><span class="sxs-lookup"><span data-stu-id="0977a-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="0977a-196">Aktivera automatisk exempelinskickning</span><span class="sxs-lookup"><span data-stu-id="0977a-196">Enable automatic sample submission</span></span>

<span data-ttu-id="0977a-197">Om du vill aktivera automatisk exempelinskickning startar du en Windows PowerShell-konsol som administratör och anger värdedata för **SubmitSamplesConsent** enligt någon av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="0977a-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="0977a-198">Inställning</span><span class="sxs-lookup"><span data-stu-id="0977a-198">Setting</span></span>  |<span data-ttu-id="0977a-199">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0977a-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0977a-200">**0**  -  **Fråga alltid**</span><span class="sxs-lookup"><span data-stu-id="0977a-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="0977a-201">I antivirustjänsten Microsoft Defender uppmanas du att bekräfta inskickningen av alla nödvändiga filer.</span><span class="sxs-lookup"><span data-stu-id="0977a-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="0977a-202">Det här är standardinställningen för Microsoft Defender Antivirus, men rekommenderas inte för installationer på Windows Server 2016 eller 2019 utan guid.</span><span class="sxs-lookup"><span data-stu-id="0977a-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="0977a-203">**1**   -  **Skicka säkra exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="0977a-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="0977a-204">Antivirustjänsten Microsoft Defender skickar alla filer som markerats som "säkra" och frågar efter resten av filerna.</span><span class="sxs-lookup"><span data-stu-id="0977a-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="0977a-205">**2**  -  **Skicka aldrig**</span><span class="sxs-lookup"><span data-stu-id="0977a-205">**2** - **Never send**</span></span>      |<span data-ttu-id="0977a-206">Microsoft Defender Antivirus-tjänsten uppmanas inte och skickar inga filer.</span><span class="sxs-lookup"><span data-stu-id="0977a-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="0977a-207">**3**  -  **Skicka alla exempel automatiskt**</span><span class="sxs-lookup"><span data-stu-id="0977a-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="0977a-208">Antivirustjänsten Microsoft Defender skickar alla filer utan en uppmaning om att bekräfta.</span><span class="sxs-lookup"><span data-stu-id="0977a-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="0977a-209">Konfigurera automatiska undantag</span><span class="sxs-lookup"><span data-stu-id="0977a-209">Configure automatic exclusions</span></span>

<span data-ttu-id="0977a-210">För att säkerställa säkerhet och prestanda läggs vissa undantag till automatiskt utifrån de roller och funktioner som du installerar när du använder Microsoft Defender Antivirus på Windows Server 2016 eller 2019.</span><span class="sxs-lookup"><span data-stu-id="0977a-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="0977a-211">Se [Konfigurera undantag i Microsoft Defender Antivirus på Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0977a-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="0977a-212">Behöver du ställa in Microsoft Defender Antivirus på passiv form?</span><span class="sxs-lookup"><span data-stu-id="0977a-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="0977a-213">Om du använder ett annat antivirusprogram än Microsoft som din primära antiviruslösning på Windows Server måste du ställa in Microsoft Defender Antivirus på passivt läge eller inaktiverat läge.</span><span class="sxs-lookup"><span data-stu-id="0977a-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="0977a-214">På Windows Server, version 1803 eller senare, eller Windows Server 2019, kan du ställa in Microsoft Defender Antivirus på passivt läge.</span><span class="sxs-lookup"><span data-stu-id="0977a-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="0977a-215">I Windows Server 2016 stöds inte Microsoft Defender Antivirus tillsammans med en produkt som inte är en antivirus-/antimalware-produkt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0977a-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="0977a-216">I sådana fall måste du ställa in att Microsoft Defender Antivirus ska inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="0977a-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="0977a-217">Ställ in Microsoft Defender Antivirus på passivt läge med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0977a-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="0977a-218">Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus på passivt läge med hjälp av följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0977a-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="0977a-219">Ställ in Microsoft Defender Antivirus på passivt läge med grupprincip</span><span class="sxs-lookup"><span data-stu-id="0977a-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="0977a-220">PROCEDUR KRÄVS</span><span class="sxs-lookup"><span data-stu-id="0977a-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="0977a-221">Ställ in Microsoft Defender Antivirus på passivt läge med hjälp av en registernyckel</span><span class="sxs-lookup"><span data-stu-id="0977a-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="0977a-222">Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus på passiv form genom att ange följande registernyckel:</span><span class="sxs-lookup"><span data-stu-id="0977a-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="0977a-223">Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="0977a-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="0977a-224">Namn: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="0977a-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="0977a-225">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="0977a-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="0977a-226">Värde: `1`</span><span class="sxs-lookup"><span data-stu-id="0977a-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="0977a-227">Inaktivera Microsoft Defender Antivirus med hjälp av guiden Ta bort roller och funktioner</span><span class="sxs-lookup"><span data-stu-id="0977a-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="0977a-228">Se [Installera eller avinstallera roller, rolltjänster eller funktioner och](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)använd guiden Ta bort roller och **funktioner.**</span><span class="sxs-lookup"><span data-stu-id="0977a-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="0977a-229">När du kommer till **steget Funktioner** i guiden avmarkerar du alternativet **Windows Defender-funktioner.**</span><span class="sxs-lookup"><span data-stu-id="0977a-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="0977a-230">Om du tar **bort Windows Defender** för sig själv under avsnittet Om Windows **Defender-funktioner** uppmanas du att ta bort gränssnittsalternativet GUI för **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="0977a-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="0977a-231">Microsoft Defender Antivirus körs fortfarande normalt utan användargränssnittet, men användargränssnittet kan inte aktiveras om du inaktiverar **Windows Defender-huvudfunktionen.**</span><span class="sxs-lookup"><span data-stu-id="0977a-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="0977a-232">Inaktivera användargränssnittet i Microsoft Defender Antivirus med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0977a-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="0977a-233">Om du vill inaktivera Microsoft Defender Antivirus GUI använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0977a-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="0977a-234">Använder du Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="0977a-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="0977a-235">Om du använder Windows Server 2016 och en antimalware/antivirusprodukt från tredje part som inte erbjuds eller utvecklas av Microsoft, måste du inaktivera/avinstallera Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0977a-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="0977a-236">Du kan inte avinstallera Windows-säkerhetsappen, men du kan inaktivera gränssnittet med hjälp av de här instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="0977a-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="0977a-237">Följande PowerShell-cmdlet avinstallerar Microsoft Defender Antivirus på Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="0977a-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="0977a-238">Om du vill inaktivera Microsoft Defender Antivirus i Windows Server 2016 använder du följande PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0977a-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="0977a-239">Se även</span><span class="sxs-lookup"><span data-stu-id="0977a-239">See also</span></span>

- [<span data-ttu-id="0977a-240">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="0977a-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="0977a-241">Kompatibilitet med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0977a-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
