---
title: Distributionsguide för den virtuella skrivbordsinfrastrukturen för Microsoft Defender Antivirus
description: Lär dig hur du distribuerar Microsoft Defender Antivirus i en virtuell skrivbordsmiljö för bästa balans mellan skydd och prestanda.
keywords: vdi, hyper-v, VM, virtuell dator, windows defender, antivirus, av, virtuellt skrivbord, rds, fjärrskrivbord
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b81addbcaabb1c5ea0d344dbaab9d76a8b100c2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691487"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="cdb19-104">Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="cdb19-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cdb19-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cdb19-105">**Applies to:**</span></span>

- [<span data-ttu-id="cdb19-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cdb19-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cdb19-107">Förutom standardkonfigurationer för lokal dator eller maskinvara kan du också använda Microsoft Defender Antivirus i en fjärrskrivbordsmiljö (RDS) eller i en VDI-miljö (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="cdb19-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="cdb19-108">Mer [information om Microsoft Fjärrskrivbordstjänster](/azure/virtual-desktop) och VDI-support finns i Dokumentationen för Virtuellt skrivbord för Windows.</span><span class="sxs-lookup"><span data-stu-id="cdb19-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="cdb19-109">För Azure-baserade virtuella datorer, se [Installera Endpoint Protection i Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="cdb19-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="cdb19-110">Med möjlighet att enkelt distribuera uppdateringar till virtuella maskiner som körs i VDE:er har vi förkortat den här guiden för att fokusera på hur du kan få uppdateringar på dina maskiner snabbt och enkelt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="cdb19-111">Du behöver inte längre regelbundet skapa och försegla gyllene bilder eftersom uppdateringarna utökas till sina beståndsdelar på värdservern och sedan hämtas direkt till den virtuella maskinerna när den är påslagen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="cdb19-112">I den här guiden beskrivs hur du konfigurerar virtuella maskiner för optimala skydd och prestanda, inklusive hur du:</span><span class="sxs-lookup"><span data-stu-id="cdb19-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="cdb19-113">Konfigurera en dedikerad VDI-filresurs för säkerhetsintelligensuppdateringar</span><span class="sxs-lookup"><span data-stu-id="cdb19-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="cdb19-114">Slumpmässiga schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="cdb19-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="cdb19-115">Använda snabbsökningar</span><span class="sxs-lookup"><span data-stu-id="cdb19-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="cdb19-116">Förhindra meddelanden</span><span class="sxs-lookup"><span data-stu-id="cdb19-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="cdb19-117">Inaktivera genomsökningar från att inträffa efter varje uppdatering</span><span class="sxs-lookup"><span data-stu-id="cdb19-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="cdb19-118">Skanna in-datera datorer eller datorer som har varit offline ett tag</span><span class="sxs-lookup"><span data-stu-id="cdb19-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="cdb19-119">Använda undantag</span><span class="sxs-lookup"><span data-stu-id="cdb19-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="cdb19-120">Du kan också ladda ned informationsbladet [Microsoft Defender Antivirus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)på Virtual Desktop Infrastructure som tittar på den nya delade säkerhetsintelligensuppdateringsfunktionen, tillsammans med prestandatestning och vägledning om hur du kan testa antivirusprestanda på din egen VDI.</span><span class="sxs-lookup"><span data-stu-id="cdb19-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdb19-121">Även om VDI kan lagras på Windows Server 2012 eller Windows Server 2016 bör virtuella maskinerna (VMs) åtminstone köra Windows 10, 1607, på grund av ökade skyddsteknik och funktioner som inte är tillgängliga i tidigare versioner av Windows.</span><span class="sxs-lookup"><span data-stu-id="cdb19-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="cdb19-122">Det finns prestanda- och funktionsförbättringar för hur Microsoft Defender AV fungerar på virtuella datorer i Windows 10 Insider Preview, version 18323 (och senare).</span><span class="sxs-lookup"><span data-stu-id="cdb19-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="cdb19-123">Vi identifierar dig i den här guiden om du behöver använda en Insider Preview-version. Om den inte anges är Windows 10 1607 den lägsta versionen som krävs för bästa skydd och prestanda.</span><span class="sxs-lookup"><span data-stu-id="cdb19-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="cdb19-124">Konfigurera en dedikerad VDI-filresurs</span><span class="sxs-lookup"><span data-stu-id="cdb19-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="cdb19-125">I Windows 10, version 1903, introducerade vi den delade säkerhetsintelligensfunktionen, som förser packa upp paketering av hämtade säkerhetsintelligensuppdateringar på en värddator – vilket sparar tidigare processor-, disk- och minnesresurser på enskilda datorer.</span><span class="sxs-lookup"><span data-stu-id="cdb19-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="cdb19-126">Den här funktionen har bakåtporterats och fungerar nu i Windows 10 version 1703 och senare.</span><span class="sxs-lookup"><span data-stu-id="cdb19-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="cdb19-127">Du kan ställa in den här funktionen med en grupprincip eller PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cdb19-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="cdb19-128">Använd Grupprincip för att aktivera den delade säkerhetsintelligensfunktionen:</span><span class="sxs-lookup"><span data-stu-id="cdb19-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="cdb19-129">Öppna grupprinciphanteringskonsolen på datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och klicka sedan på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="cdb19-130">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cdb19-131">Klicka **på Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="cdb19-132">Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Security  >  **Intelligence-uppdateringar.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="cdb19-133">Dubbelklicka på Definiera **säkerhetsintelligens för VDI-klienter** och ange sedan alternativet **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="cdb19-134">Ett fält visas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-134">A field automatically appears.</span></span>

6. <span data-ttu-id="cdb19-135">Ange `\\<sharedlocation\>\wdav-update` (om du behöver hjälp med det här värdet går [du till Ladda ned och packa upp](#download-and-unpackage-the-latest-updates)).</span><span class="sxs-lookup"><span data-stu-id="cdb19-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="cdb19-136">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-136">Click **OK**.</span></span>

8. <span data-ttu-id="cdb19-137">Distribuera GPO:t till de virtuella maskinerna som du vill testa.</span><span class="sxs-lookup"><span data-stu-id="cdb19-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="cdb19-138">Använda PowerShell för att aktivera den delade säkerhetsintelligensfunktionen</span><span class="sxs-lookup"><span data-stu-id="cdb19-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="cdb19-139">Använd följande cmdlet för att aktivera funktionen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="cdb19-140">Du måste sedan pusha det här eftersom du normalt skulle pusha PowerShell-baserade konfigurationsprinciper till virtuella maskiner:</span><span class="sxs-lookup"><span data-stu-id="cdb19-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="cdb19-141">Se [avsnittet Ladda ned och packa upp](#download-and-unpackage-the-latest-updates) för information om vad som kommer att \<shared location\> ske.</span><span class="sxs-lookup"><span data-stu-id="cdb19-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="cdb19-142">Ladda ned och packa upp de senaste uppdateringarna</span><span class="sxs-lookup"><span data-stu-id="cdb19-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="cdb19-143">Nu kan du komma igång med att ladda ned och installera nya uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="cdb19-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="cdb19-144">Vi har skapat ett PowerShell-exempelskript nedan.</span><span class="sxs-lookup"><span data-stu-id="cdb19-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="cdb19-145">Det här skriptet är det enklaste sättet att ladda ned nya uppdateringar och förbereda dem för dina virtuella maskiner.</span><span class="sxs-lookup"><span data-stu-id="cdb19-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="cdb19-146">Du bör sedan ange att skriptet ska köras vid en viss tidpunkt på hanteringsdatorn genom att använda en schemalagd aktivitet (eller om du är van vid att använda PowerShell-skript i Azure, Intune eller SCCM kan du också använda de skripten).</span><span class="sxs-lookup"><span data-stu-id="cdb19-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="cdb19-147">Du kan ange att en schemalagd aktivitet ska köras en gång om dagen, så att de virtuella maskinerna får den nya uppdateringen varje gång paketet laddas ned och packas upp.</span><span class="sxs-lookup"><span data-stu-id="cdb19-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="cdb19-148">Vi föreslår att du börjar med en gång om dagen, men du bör experimentera med att öka eller minska frekvensen för att förstå effekten.</span><span class="sxs-lookup"><span data-stu-id="cdb19-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="cdb19-149">Säkerhetsintelligenspaket publiceras vanligtvis en gång var tredje till fyra:e timme.</span><span class="sxs-lookup"><span data-stu-id="cdb19-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="cdb19-150">Vi avråder dig från att ställa in en frekvens som är kortare än fyra timmar eftersom det ökar nätverkskostnaderna på hanteringsdatorn utan någon förmån.</span><span class="sxs-lookup"><span data-stu-id="cdb19-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="cdb19-151">Ange en schemalagd aktivitet för att köra PowerShell-skriptet</span><span class="sxs-lookup"><span data-stu-id="cdb19-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="cdb19-152">Öppna Start-menyn på hanteringsdatorn och skriv **Schemaläggaren.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="cdb19-153">Öppna den och välj **Skapa uppgift...**</span><span class="sxs-lookup"><span data-stu-id="cdb19-153">Open it and select **Create task…**</span></span> <span data-ttu-id="cdb19-154">i sidopanelen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-154">on the side panel.</span></span>

2. <span data-ttu-id="cdb19-155">Ange namnet som **"Security intelligence" för att packa upp**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="cdb19-156">Gå till **fliken Utlösare.** Välj **Nytt...**</span><span class="sxs-lookup"><span data-stu-id="cdb19-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="cdb19-157"> > **Varje** dag och välj **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="cdb19-158">Gå till **fliken** Åtgärder. Välj **Nytt...**</span><span class="sxs-lookup"><span data-stu-id="cdb19-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="cdb19-159">Ange **PowerShell** i **fältet Program/skript.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="cdb19-160">Ange `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` i fältet Lägg **till** argument.</span><span class="sxs-lookup"><span data-stu-id="cdb19-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="cdb19-161">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-161">Select **OK**.</span></span>

4. <span data-ttu-id="cdb19-162">Du kan välja att konfigurera ytterligare inställningar om du vill.</span><span class="sxs-lookup"><span data-stu-id="cdb19-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="cdb19-163">Spara **den schemalagda** aktiviteten genom att välja OK.</span><span class="sxs-lookup"><span data-stu-id="cdb19-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="cdb19-164">Du kan starta uppdateringen manuellt genom att högerklicka på uppgiften och klicka på **Kör**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="cdb19-165">Ladda ned och packa upp manuellt</span><span class="sxs-lookup"><span data-stu-id="cdb19-165">Download and unpackage manually</span></span>

<span data-ttu-id="cdb19-166">Om du föredrar att göra allt manuellt gör du så här för att replikera skriptets beteende:</span><span class="sxs-lookup"><span data-stu-id="cdb19-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="cdb19-167">Skapa en ny mapp i systemroten som `wdav_update` anropas för att lagra informationsuppdateringar, till exempel skapa mappen `c:\wdav_update` .</span><span class="sxs-lookup"><span data-stu-id="cdb19-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="cdb19-168">Skapa en undermapp under *wdav_update* med ett GUID-namn, till exempel `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="cdb19-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="cdb19-169">Här är ett exempel: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="cdb19-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="cdb19-170">I skriptet vi anger det så de sista 12 siffrorna i GUID är år, månad, dag och tid när filen laddades ned så att en ny mapp skapas varje gång.</span><span class="sxs-lookup"><span data-stu-id="cdb19-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="cdb19-171">Du kan ändra detta så att filen laddas ned till samma mapp varje gång.</span><span class="sxs-lookup"><span data-stu-id="cdb19-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="cdb19-172">Hämta ett säkerhetsintelligenspaket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  från mappen GUID.</span><span class="sxs-lookup"><span data-stu-id="cdb19-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="cdb19-173">Filen ska heta `mpam-fe.exe` .</span><span class="sxs-lookup"><span data-stu-id="cdb19-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="cdb19-174">Öppna ett cmd-meddelandefönster och gå till GUID-mappen som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="cdb19-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="cdb19-175">Använd **extraheringskommandot /X** för att extrahera filerna, till exempel `mpam-fe.exe /X` .</span><span class="sxs-lookup"><span data-stu-id="cdb19-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="cdb19-176">Virtuella maskiner hämtar det uppdaterade paketet när en ny GUID-mapp skapas med ett extraherat uppdateringspaket eller när en befintlig mapp uppdateras med ett nytt extraherat paket.</span><span class="sxs-lookup"><span data-stu-id="cdb19-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="cdb19-177">Slumpmässiga schemalagda genomsökningar</span><span class="sxs-lookup"><span data-stu-id="cdb19-177">Randomize scheduled scans</span></span>

<span data-ttu-id="cdb19-178">Schemalagda skanningar körs utöver [realtidsskydd och skanning.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="cdb19-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="cdb19-179">Starttiden för själva genomsökningen baseras fortfarande på principen för schemalagd sökning **(ScheduleDay,** **ScheduleTime** och **ScheduleQuickScanTime).**</span><span class="sxs-lookup"><span data-stu-id="cdb19-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="cdb19-180">Slumpvisisering gör att Microsoft Defender Antivirus startar en genomsökning på varje dator inom 4 timmar från den tid som angetts för den schemalagda genomsökningen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="cdb19-181">Se [Schemalägga genomsökningar för](scheduled-catch-up-scans-microsoft-defender-antivirus.md) andra konfigurationsalternativ som är tillgängliga för schemalagda genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="cdb19-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="cdb19-182">Använda snabbsökningar</span><span class="sxs-lookup"><span data-stu-id="cdb19-182">Use quick scans</span></span>

<span data-ttu-id="cdb19-183">Du kan ange vilken typ av genomsökning som ska utföras vid en schemalagd genomsökning.</span><span class="sxs-lookup"><span data-stu-id="cdb19-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="cdb19-184">Snabbsökningar är den rekommenderade metoden eftersom de är utformade för att leta på alla platser där skadlig programvara måste vara aktiv.</span><span class="sxs-lookup"><span data-stu-id="cdb19-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="cdb19-185">Här beskrivs hur du ställer in snabba genomsökningar med grupprinciper.</span><span class="sxs-lookup"><span data-stu-id="cdb19-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="cdb19-186">I grupprincipredigeraren går du till Administrativa **mallar**  >  **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="cdb19-187">Välj **Ange vilken genomsökningstyp som ska användas för en schemalagd** sökning och redigera sedan principinställningen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="cdb19-188">Ställ in principen på **Aktiverad** och välj sedan **Snabbsökning** under **Alternativ.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="cdb19-189">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-189">Select **OK**.</span></span> 

5. <span data-ttu-id="cdb19-190">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="cdb19-191">Förhindra meddelanden</span><span class="sxs-lookup"><span data-stu-id="cdb19-191">Prevent notifications</span></span>

<span data-ttu-id="cdb19-192">Ibland kan antivirusmeddelanden från Microsoft Defender skickas till eller finns kvar i flera sessioner.</span><span class="sxs-lookup"><span data-stu-id="cdb19-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="cdb19-193">Om du vill minimera det här problemet kan du låsa användargränssnittet i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="cdb19-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="cdb19-194">Här beskrivs hur du förhindrar aviseringar med grupprinciper.</span><span class="sxs-lookup"><span data-stu-id="cdb19-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="cdb19-195">Gå till Windows-komponenter Microsoft Defender Antivirus Client Interface i  >    >  **grupprincipredigeraren.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="cdb19-196">Markera **Ignorera alla meddelanden** och redigera sedan principinställningarna.</span><span class="sxs-lookup"><span data-stu-id="cdb19-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="cdb19-197">Ställ in principen **på Aktiverad** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="cdb19-198">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="cdb19-199">Om du ignorerar meddelanden förhindrar du att meddelanden från Microsoft Defender Antivirus visas i Åtgärdscenter på Windows 10 när genomsökningar görs eller åtgärder vidtas.</span><span class="sxs-lookup"><span data-stu-id="cdb19-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="cdb19-200">Men teamet för säkerhetsåtgärder ser resultatet av genomsökningen i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="cdb19-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="cdb19-201">Öppna Åtgärdscenter i Windows 10 genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="cdb19-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="cdb19-202">Välj ikonen för Åtgärdscenter till höger i aktivitetsfältet.</span><span class="sxs-lookup"><span data-stu-id="cdb19-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="cdb19-203">Tryck på Windows-tangenten + A.</span><span class="sxs-lookup"><span data-stu-id="cdb19-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="cdb19-204">På en enhet med pekskärm sveper du från skärmens högra kant.</span><span class="sxs-lookup"><span data-stu-id="cdb19-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="cdb19-205">Inaktivera genomsökningar efter en uppdatering</span><span class="sxs-lookup"><span data-stu-id="cdb19-205">Disable scans after an update</span></span>

<span data-ttu-id="cdb19-206">Om du inaktiverar en genomsökning efter en uppdatering förhindras en genomsökning efter att en uppdatering har mottagits.</span><span class="sxs-lookup"><span data-stu-id="cdb19-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="cdb19-207">Du kan använda den här inställningen när du skapar basbilden om du också har gjort en snabbsökning.</span><span class="sxs-lookup"><span data-stu-id="cdb19-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="cdb19-208">På så sätt kan du förhindra att den nyligen uppdaterade virtuella maskinerna utför en genomsökning igen (eftersom du redan har skannat den när du skapade basbilden).</span><span class="sxs-lookup"><span data-stu-id="cdb19-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdb19-209">Genom att köra genomsökningar efter en uppdatering kan du säkerställa att dina virtuella maskiner skyddas med de senaste säkerhetsintelligensuppdateringarna.</span><span class="sxs-lookup"><span data-stu-id="cdb19-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="cdb19-210">Om du inaktiverar det här alternativet minskas skyddsnivån för virtuella maskiner och bör endast användas när du skapar eller distribuerar basbilden.</span><span class="sxs-lookup"><span data-stu-id="cdb19-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="cdb19-211">Gå till Windows-komponenterna Microsoft  >  **Defender Antivirus**  >  **Security Intelligence-uppdateringar i grupprincipredigeraren.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="cdb19-212">Välj **Aktivera genomsökning efter säkerhetsintelligensuppdatering** och redigera sedan principinställningen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="cdb19-213">Ställ in principen på **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="cdb19-214">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-214">Select **OK**.</span></span>

5. <span data-ttu-id="cdb19-215">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="cdb19-216">Den här principen förhindrar att en genomsökning körs direkt efter en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="cdb19-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="cdb19-217">Skanna virtuella maskiner som har varit offline</span><span class="sxs-lookup"><span data-stu-id="cdb19-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="cdb19-218">Gå till Windows-komponenterna Microsoft Defender Antivirus Scan i  >  **grupprincipredigeraren.**  >  </span><span class="sxs-lookup"><span data-stu-id="cdb19-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="cdb19-219">Välj **Aktivera snabbsökning och redigera** sedan principinställningen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="cdb19-220">Ställ in principen på **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="cdb19-221">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-221">Select **OK**.</span></span>

5. <span data-ttu-id="cdb19-222">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="cdb19-223">Den här principen tvingar fram en genomsökning om den virtuella maskinerna har missat två eller fler schemalagda genomsökningar i följd.</span><span class="sxs-lookup"><span data-stu-id="cdb19-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="cdb19-224">Aktivera huvudlöst gränssnittsläge</span><span class="sxs-lookup"><span data-stu-id="cdb19-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="cdb19-225">Gå till Windows-komponenter Microsoft Defender Antivirus Client Interface i  >    >  **grupprincipredigeraren.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="cdb19-226">Välj **Aktivera huvudlöst gränssnittsläge** och redigera principen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="cdb19-227">Ställ in principen på **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="cdb19-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="cdb19-228">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="cdb19-228">Click **OK**.</span></span>

5. <span data-ttu-id="cdb19-229">Distribuera grupprincipobjektet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="cdb19-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="cdb19-230">Den här principen döljer hela Microsoft Defender Antivirus-användargränssnittet från slutanvändarna i organisationen.</span><span class="sxs-lookup"><span data-stu-id="cdb19-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="cdb19-231">Undantag</span><span class="sxs-lookup"><span data-stu-id="cdb19-231">Exclusions</span></span>

<span data-ttu-id="cdb19-232">Undantag kan läggas till, tas bort eller anpassas så att de passar dina behov.</span><span class="sxs-lookup"><span data-stu-id="cdb19-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="cdb19-233">Mer information finns i Konfigurera [undantag för Microsoft Defender Antivirus på Windows Server.](configure-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="cdb19-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cdb19-234">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cdb19-234">Additional resources</span></span>

- [<span data-ttu-id="cdb19-235">Tech Community-blogg: Konfigurera Microsoft Defender Antivirus för icke-beständiga VDI-datorer</span><span class="sxs-lookup"><span data-stu-id="cdb19-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="cdb19-236">TechNet-forum på Fjärrskrivbordstjänster och VDI</span><span class="sxs-lookup"><span data-stu-id="cdb19-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="cdb19-237">PowerShell-skript för SignatureDownloadCustomTask</span><span class="sxs-lookup"><span data-stu-id="cdb19-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)