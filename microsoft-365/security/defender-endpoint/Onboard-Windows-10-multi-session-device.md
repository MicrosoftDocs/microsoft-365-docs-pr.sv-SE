---
title: Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop
description: Läs mer i den här artikeln om registrering av Windows 10 flersessionsenheter i Windows virtuellt skrivbord
keywords: Windows Virtuellt skrivbord, WVD, microsoft defender, slutpunkt, onboard
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7ade1ae1e045cb52f48d231acbc1712e753b6bc3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841852"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="d18a8-104">Registrera Windows 10-multisessionsenheter i det Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="d18a8-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="d18a8-105">6 minuter att läsa</span><span class="sxs-lookup"><span data-stu-id="d18a8-105">6 minutes to read</span></span> 

<span data-ttu-id="d18a8-106">Gäller för:</span><span class="sxs-lookup"><span data-stu-id="d18a8-106">Applies to:</span></span> 
- <span data-ttu-id="d18a8-107">Windows 10 flersessionssession på Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="d18a8-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="d18a8-108">Microsoft Defender för Endpoint har stöd för övervakning av både VDI Windows sessioner för virtuellt skrivbord.</span><span class="sxs-lookup"><span data-stu-id="d18a8-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="d18a8-109">Beroende på organisationens behov kan du behöva implementera VDI- eller Windows Virtual Desktop-sessioner för att hjälpa dina anställda att få åtkomst till företagsdata och appar från en ohanterad enhet, fjärransluten plats eller liknande scenario.</span><span class="sxs-lookup"><span data-stu-id="d18a8-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="d18a8-110">Med Microsoft Defender för Endpoint kan du övervaka dessa virtuella datorer efter avvikande aktivitet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="d18a8-111">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="d18a8-111">Before you begin</span></span>
<span data-ttu-id="d18a8-112">Bekanta dig med överväganden [för icke-beständiga VDI.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="d18a8-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="d18a8-113">Även [om Windows Virtual Desktop](/azure/virtual-desktop/overview) inte har alternativ för att inte ha möjlighet att beständighet, erbjuder den ett sätt att använda en gyllene Windows-bild som kan användas för att tillhandahålla nya värdar och distribuera om datorer.</span><span class="sxs-lookup"><span data-stu-id="d18a8-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="d18a8-114">Det här ökar säkerheten i miljön och påverkar därmed vilka poster som skapas och underhålls i Microsoft Defender för Endpoint-portalen, vilket potentiellt minskar synligheten för dina säkerhetsanalytiker.</span><span class="sxs-lookup"><span data-stu-id="d18a8-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="d18a8-115">Beroende på ditt val av onboarding-metod kan enheter visas i Microsoft Defender för Endpoint-portalen som antingen:</span><span class="sxs-lookup"><span data-stu-id="d18a8-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="d18a8-116">Enskild post för varje virtuellt skrivbord</span><span class="sxs-lookup"><span data-stu-id="d18a8-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="d18a8-117">Flera poster för varje virtuellt skrivbord</span><span class="sxs-lookup"><span data-stu-id="d18a8-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="d18a8-118">Microsoft rekommenderar registrering av Windows virtuella skrivbordet som en enskild post per virtuellt skrivbord.</span><span class="sxs-lookup"><span data-stu-id="d18a8-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="d18a8-119">Det säkerställer att undersökningsupplevelsen i Microsoft Defender Endpoint-portalen är i en enhets kontext baserat på datornamnet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="d18a8-120">Organisationer som ofta tar bort och distribuerar WVD-värdar bör överväga att använda den här metoden eftersom det förhindrar att flera objekt för samma dator skapas i Microsoft Defender för Endpoint-portalen.</span><span class="sxs-lookup"><span data-stu-id="d18a8-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="d18a8-121">Det kan skapa förvirring när du undersöker incidenter.</span><span class="sxs-lookup"><span data-stu-id="d18a8-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="d18a8-122">För testmiljöer eller ej ej beständiga miljöer kan du välja att välja ett annat.</span><span class="sxs-lookup"><span data-stu-id="d18a8-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="d18a8-123">Microsoft rekommenderar att du lägger till Microsoft Defender för slutpunkts onboarding-skriptet i den gyllene bilden i WVD.</span><span class="sxs-lookup"><span data-stu-id="d18a8-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="d18a8-124">På så sätt kan du vara säker på att det här onboarding-skriptet körs direkt vid första starten.</span><span class="sxs-lookup"><span data-stu-id="d18a8-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="d18a8-125">Den körs som ett startskript vid första starten på alla WVD-datorer som är etablerade från den gyllene bilden i WVD.</span><span class="sxs-lookup"><span data-stu-id="d18a8-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="d18a8-126">Men om du använder någon av galleribilderna utan att ändra det placerar du skriptet på en delad plats och anropar det från antingen lokal grupprincip eller domängruppsprincip.</span><span class="sxs-lookup"><span data-stu-id="d18a8-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="d18a8-127">Startskriptet för VDI-onboarding placeras och konfigureras på den gyllene bilden i WVD som ett startskript som körs när WVD startas.</span><span class="sxs-lookup"><span data-stu-id="d18a8-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="d18a8-128">Vi rekommenderar INTE att du visar den faktiska gyllene bilden i WVD.</span><span class="sxs-lookup"><span data-stu-id="d18a8-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="d18a8-129">En annan faktor är metoden som används för att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="d18a8-130">Den bör köras så tidigt i start-/etableringsprocessen som möjligt för att minska tiden mellan den dator som är tillgänglig för att ta emot sessioner och enhetens registrering till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d18a8-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="d18a8-131">Ta hänsyn till detta & 2 under scenarier 1.</span><span class="sxs-lookup"><span data-stu-id="d18a8-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="d18a8-132">Scenarier</span><span class="sxs-lookup"><span data-stu-id="d18a8-132">Scenarios</span></span>
<span data-ttu-id="d18a8-133">Det finns flera sätt att introducera en WVD-värddator:</span><span class="sxs-lookup"><span data-stu-id="d18a8-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="d18a8-134">Kör skriptet i den gyllene bilden (eller från en delad plats) vid start.</span><span class="sxs-lookup"><span data-stu-id="d18a8-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="d18a8-135">Använd ett hanteringsverktyg för att köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="d18a8-136">*Scenario 1: Använda lokal grupprincip*</span><span class="sxs-lookup"><span data-stu-id="d18a8-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="d18a8-137">Det här scenariot kräver att skriptet placeras i en gyllene bild och att lokala grupprinciper används för att köras tidigt i startprocessen.</span><span class="sxs-lookup"><span data-stu-id="d18a8-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="d18a8-138">Följ anvisningarna i Hantera [icke-beständiga VDI-enheter med virtuell skrivbordsinfrastruktur.](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="d18a8-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="d18a8-139">Följ instruktionerna för en enskild post för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="d18a8-140">*Scenario 2: Använda domängruppsprincip*</span><span class="sxs-lookup"><span data-stu-id="d18a8-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="d18a8-141">Det här scenariot använder ett centralt placerade skript och kör det med en domänbaserad grupprincip.</span><span class="sxs-lookup"><span data-stu-id="d18a8-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="d18a8-142">Du kan också placera skriptet i den gyllene bilden och köra det på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="d18a8-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="d18a8-143">**Ladda WindowsDefenderATPOnboardingPackage.zip filen från säkerhetscentret Windows Defender säkerhetscentret**</span><span class="sxs-lookup"><span data-stu-id="d18a8-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="d18a8-144">Öppna filen för VDI-.zip (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="d18a8-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="d18a8-145">I Microsoft Defender Säkerhetscenter väljer du Inställningar   >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="d18a8-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="d18a8-146">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="d18a8-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="d18a8-147">I fältet **Distributionsmetod** väljer du VDI-onboardingskript för icke-beständiga slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="d18a8-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="d18a8-148">Klicka **på Ladda ned** paket och spara .zip filen.</span><span class="sxs-lookup"><span data-stu-id="d18a8-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="d18a8-149">Extrahera innehållet i filen .zip till en delad, skrivskyddad plats som kan nås av enheten.</span><span class="sxs-lookup"><span data-stu-id="d18a8-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="d18a8-150">Du bör ha en mapp med namnet **OptionalParamsPolicy** och filerna **WindowsDefenderATPOnboardingScript.cmd** **ochOnboard-NonPersistentMachine.ps1**.</span><span class="sxs-lookup"><span data-stu-id="d18a8-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="d18a8-151">**Använda konsolen för hantering av grupprinciper för att köra skriptet när den virtuella datorn startar**</span><span class="sxs-lookup"><span data-stu-id="d18a8-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="d18a8-152">Öppna GPMC (Group Policy Management Console), högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="d18a8-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d18a8-153">Gå till Inställningar för datorkonfiguration i **redigeraren för hantering** av \>  \> **grupprinciper på Kontrollpanelen.**</span><span class="sxs-lookup"><span data-stu-id="d18a8-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="d18a8-154">Högerklicka på **Schemalagda aktiviteter,** klicka **på Ny** och klicka sedan på Direkt **aktivitet** (minst Windows 7).</span><span class="sxs-lookup"><span data-stu-id="d18a8-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="d18a8-155">I uppgiftsfönstret som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp** och skriver SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="d18a8-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="d18a8-156">Klicka **på Kontrollera namn** och sedan på OK.</span><span class="sxs-lookup"><span data-stu-id="d18a8-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="d18a8-157">NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som.</span><span class="sxs-lookup"><span data-stu-id="d18a8-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="d18a8-158">Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="d18a8-159">Gå till fliken **Åtgärder** och klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d18a8-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="d18a8-160">Kontrollera att **Starta ett program** är markerat i fältet Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="d18a8-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="d18a8-161">Ange följande:</span><span class="sxs-lookup"><span data-stu-id="d18a8-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="d18a8-162">Välj sedan **OK** och stäng alla öppna GPMC-fönster.</span><span class="sxs-lookup"><span data-stu-id="d18a8-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="d18a8-163">*Scenario 3: Introduktion med hanteringsverktyg*</span><span class="sxs-lookup"><span data-stu-id="d18a8-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="d18a8-164">Om du planerar att hantera dina maskiner med ett hanteringsverktyg kan du hantera enheter Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d18a8-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="d18a8-165">Mer information finns i Informera [Windows 10 enheter med Konfigurationshanteraren.](configure-endpoints-sccm.md)</span><span class="sxs-lookup"><span data-stu-id="d18a8-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="d18a8-166">Om du tänker använda minskningsregler för [attackytan](attack-surface-reduction.md)bör du observera att regeln " Blockera processskapanden som kommer från[PSExec-](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)och WMI-kommandon " inte bör användas, eftersom regeln är inkompatibel med hantering via Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d18a8-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="d18a8-167">Regeln blockerar WMI-kommandon som Configuration Manager-klienten använder för att fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="d18a8-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="d18a8-168">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att enheten är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d18a8-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="d18a8-169">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet.](run-detection-test.md)</span><span class="sxs-lookup"><span data-stu-id="d18a8-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="d18a8-170">Tagga dina maskiner när du skapar en gyllene bild</span><span class="sxs-lookup"><span data-stu-id="d18a8-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="d18a8-171">Som en del av introduktionen kan du överväga att ställa in en maskintagg så att det blir lättare att skilja WVD-maskinerna åt i Microsofts säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="d18a8-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="d18a8-172">Mer information finns i Lägga [till enhetstaggar genom att ange ett registernyckelvärde.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="d18a8-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="d18a8-173">Andra rekommenderade konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="d18a8-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="d18a8-174">När du skapar den gyllene bilden kanske du även vill konfigurera inställningar för det första skyddet.</span><span class="sxs-lookup"><span data-stu-id="d18a8-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="d18a8-175">Mer information finns i [Andra rekommenderade konfigurationsinställningar](configure-endpoints-gp.md#other-recommended-configuration-settings).</span><span class="sxs-lookup"><span data-stu-id="d18a8-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="d18a8-176">Om du använder FSlogix-användarprofiler rekommenderar vi att du undantar följande filer från alltid-on-skydd:</span><span class="sxs-lookup"><span data-stu-id="d18a8-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="d18a8-177">**Undanta filer:**</span><span class="sxs-lookup"><span data-stu-id="d18a8-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="d18a8-178">**Exkludera processer:**</span><span class="sxs-lookup"><span data-stu-id="d18a8-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="d18a8-179">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="d18a8-179">Licensing requirements</span></span> 

<span data-ttu-id="d18a8-180">Anmärkning om licensiering: När du använder Windows 10 Enterprise flera sessioner, beroende på dina krav, kan du välja att antingen ha alla användare licensierade via Microsoft Defender för slutpunkt (per användare), Windows Enterprise E5, Microsoft 365 Security eller Microsoft 365 E5, eller ha VM-licensen licensierad via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="d18a8-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="d18a8-181">Licenskrav för Microsoft Defender för slutpunkt finns i: [Licenskrav](minimum-requirements.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="d18a8-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
