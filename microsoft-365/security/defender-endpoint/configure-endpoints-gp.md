---
title: Introducera Windows 10-enheter i Microsoft Defender för Slutpunkt via Grupprincip
description: Använd Grupprincip för att distribuera konfigurationspaketet på Windows 10-enheter så att de introduceras till tjänsten.
keywords: konfigurera enheter med grupprincip, enhetshantering, konfigurera Windows ATP-enheter, hantera Microsoft Defender för slutpunktsenheter, grupprincip
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b839cf204e8ab042e0c88a8f8c48df79770e7b4f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893643"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="51524-104">Introducera Windows 10-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="51524-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51524-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="51524-105">**Applies to:**</span></span>

- <span data-ttu-id="51524-106">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="51524-106">Group Policy</span></span>
- [<span data-ttu-id="51524-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="51524-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51524-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51524-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51524-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="51524-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="51524-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="51524-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="51524-111">Om du vill använda grupprincipuppdateringar (GP) för att distribuera paketet måste du använda Windows Server 2008 R2 eller senare.</span><span class="sxs-lookup"><span data-stu-id="51524-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="51524-112">För Windows Server 2019 kan du behöva ersätta NT AUTHORITY\Well-Known-System-Account med NT AUTHORITY\SYSTEM för den XML-fil som grupprincipinställning skapar.</span><span class="sxs-lookup"><span data-stu-id="51524-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="51524-113">Registrera enheter med grupprinciper</span><span class="sxs-lookup"><span data-stu-id="51524-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="51524-114">[![Bild av PDF-filen som visar de olika distributionssökvägarna](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="51524-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="51524-115">Ta en titta på [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  [eller Visio-filen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) för att se de olika sökvägarna i distribuera Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="51524-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="51524-116">Öppna ZIP-filen för GP-konfigurationspaket *(WindowsDefenderATPOnboardingPackage.zip)* som du laddade ned från guiden för service onboarding.</span><span class="sxs-lookup"><span data-stu-id="51524-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="51524-117">Du kan också hämta paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="51524-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="51524-118">Välj Inställningar Onboarding **i**  >  **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="51524-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="51524-119">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="51524-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="51524-120">Välj **Grupprincip i** fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="51524-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="51524-121">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="51524-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="51524-122">Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av enheten.</span><span class="sxs-lookup"><span data-stu-id="51524-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="51524-123">Du bör ha en mapp med namnet *OptionalParamsPolicy* och filen *WindowsDefenderATPOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="51524-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="51524-124">Öppna GPMC [(Group Policy Management Console),](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="51524-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="51524-125">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration** **och** sedan Inställningar och **inställningar för Kontrollpanelen.**</span><span class="sxs-lookup"><span data-stu-id="51524-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="51524-126">Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på Direkt **aktivitet (minst Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="51524-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="51524-127">I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Under **Säkerhetsalternativ klickar** du **på Ändra användare eller grupp,** skriver SYSTEM och klickar sedan **på Kontrollera namn** och sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="51524-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="51524-128">NT AUTHORITY\SYSTEM visas som det användarkonto som aktiviteten körs som.</span><span class="sxs-lookup"><span data-stu-id="51524-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="51524-129">Välj **Kör om användaren är inloggad eller inte** och markera kryssrutan Kör med **högst** behörighet.</span><span class="sxs-lookup"><span data-stu-id="51524-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="51524-130">Gå till fliken **Åtgärder** och klicka på **Ny...** Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="51524-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="51524-131">Ange filnamnet och platsen för den delade *filen WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="51524-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="51524-132">Klicka **på OK** och stäng alla öppna GPMC-fönster.</span><span class="sxs-lookup"><span data-stu-id="51524-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="51524-133">När du har introducerat enheten kan du välja att köra ett identifieringstest för att verifiera att enheten är korrekt onboarded till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="51524-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="51524-134">Mer information finns i Köra [ett identifieringstest på en nyligen onboarded Defender för Slutpunkt-enhet](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="51524-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="51524-135">Ytterligare Defender för konfigurationsinställningar för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="51524-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="51524-136">För varje enhet kan du ange om exempel kan samlas in från enheten när en begäran görs via Microsoft Defender Säkerhetscenter för att skicka in en fil för djupanalys.</span><span class="sxs-lookup"><span data-stu-id="51524-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="51524-137">Du kan använda Grupprincip (GP) för att konfigurera inställningar, till exempel inställningar för exempeldelningen som används i funktionen djupanalys.</span><span class="sxs-lookup"><span data-stu-id="51524-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="51524-138">Konfigurera exempelsamlingsinställningar</span><span class="sxs-lookup"><span data-stu-id="51524-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="51524-139">Kopiera följande filer från konfigurationspaketet på GP-hanteringsenheten:</span><span class="sxs-lookup"><span data-stu-id="51524-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="51524-140">Kopiera _AtpConfiguration.admx_ till _C: \\ Windows \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="51524-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="51524-141">Kopiera _AtpConfiguration.adml_ till _C: \\ Windows \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="51524-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="51524-142">Om du använder en [central lagring för administrativa mallar för grupprinciper](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)kopierar du följande filer från konfigurationspaketet:</span><span class="sxs-lookup"><span data-stu-id="51524-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="51524-143">Kopiera _AtpConfiguration.admx till_ _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="51524-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="51524-144">Kopiera _AtpConfiguration.adml_ till _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="51524-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="51524-145">Öppna konsolen [grupprinciphantering,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)högerklicka på det GPO du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="51524-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="51524-146">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="51524-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="51524-147">Klicka **på Principer** och sedan på Administrativa **mallar.**</span><span class="sxs-lookup"><span data-stu-id="51524-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="51524-148">Klicka **på Windows-komponenter** och **sedan på Windows Defender ATP.**</span><span class="sxs-lookup"><span data-stu-id="51524-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="51524-149">Välj för att aktivera eller inaktivera exempeldelning från dina enheter.</span><span class="sxs-lookup"><span data-stu-id="51524-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="51524-150">Om du inte anger något värde är standardvärdet att aktivera exempelsamling.</span><span class="sxs-lookup"><span data-stu-id="51524-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="51524-151">Andra rekommenderade konfigurationsinställningar</span><span class="sxs-lookup"><span data-stu-id="51524-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="51524-152">Uppdatera konfiguration av slutpunktsskydd</span><span class="sxs-lookup"><span data-stu-id="51524-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="51524-153">När du har konfigurerat onboarding-skriptet fortsätter du att redigera samma grupprincip för att lägga till slutpunktsskyddskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="51524-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="51524-154">Utför grupprincipredigeringar från ett system med Windows 10 eller Server 2019 för att säkerställa att du har alla nödvändiga Microsoft Defender Antivirus-funktioner.</span><span class="sxs-lookup"><span data-stu-id="51524-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="51524-155">Du kan behöva stänga och öppna grupprincipobjektet igen för att registrera Defender ATP-konfigurationsinställningarna.</span><span class="sxs-lookup"><span data-stu-id="51524-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="51524-156">Alla principer finns under `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="51524-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="51524-157">**Plats för principen:** \Windows Components\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="51524-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="51524-158">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-158">Policy</span></span> | <span data-ttu-id="51524-159">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-159">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-160">Aktivera\Inaktivera exempelsamling</span><span class="sxs-lookup"><span data-stu-id="51524-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="51524-161">Aktiverad – "Aktivera exempelsamling på datorer" markerat</span><span class="sxs-lookup"><span data-stu-id="51524-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="51524-162">**Plats för principen:**  \Windows Components\Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="51524-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="51524-163">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-163">Policy</span></span> | <span data-ttu-id="51524-164">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-164">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-165">Konfigurera identifiering för potentiellt oönskade program</span><span class="sxs-lookup"><span data-stu-id="51524-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="51524-166">Aktiverad, Blockera</span><span class="sxs-lookup"><span data-stu-id="51524-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="51524-167">**Plats för principen:** \Windows Components\Windows Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="51524-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="51524-168">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-168">Policy</span></span> | <span data-ttu-id="51524-169">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-169">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-170">Ansluta till Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="51524-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="51524-171">Aktiverade, avancerade KARTOR</span><span class="sxs-lookup"><span data-stu-id="51524-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="51524-172">Skicka filexempel när ytterligare analys krävs</span><span class="sxs-lookup"><span data-stu-id="51524-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="51524-173">Aktiverad, Skicka säkra exempel</span><span class="sxs-lookup"><span data-stu-id="51524-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="51524-174">**Policyplats:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span><span class="sxs-lookup"><span data-stu-id="51524-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="51524-175">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-175">Policy</span></span> | <span data-ttu-id="51524-176">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-176">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-177">Inaktivera realtidsskydd</span><span class="sxs-lookup"><span data-stu-id="51524-177">Turn off real-time protection</span></span>|<span data-ttu-id="51524-178">Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="51524-178">Disabled</span></span>
<span data-ttu-id="51524-179">Aktivera beteendeövervakning</span><span class="sxs-lookup"><span data-stu-id="51524-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="51524-180">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="51524-180">Enabled</span></span>
<span data-ttu-id="51524-181">Genomsöka alla nedladdade filer och bifogade filer</span><span class="sxs-lookup"><span data-stu-id="51524-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="51524-182">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="51524-182">Enabled</span></span>
<span data-ttu-id="51524-183">Övervaka fil- och programaktivitet på datorn</span><span class="sxs-lookup"><span data-stu-id="51524-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="51524-184">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="51524-184">Enabled</span></span>

<br/>

<span data-ttu-id="51524-185">**Plats för principen:**  \Windows Components\Windows Defender Antivirus\Scan</span><span class="sxs-lookup"><span data-stu-id="51524-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="51524-186">De här inställningarna konfigurerar periodiska genomsökningar av slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="51524-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="51524-187">Vi rekommenderar att du gör en snabbsökning varje vecka, om det är möjligt med prestanda.</span><span class="sxs-lookup"><span data-stu-id="51524-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="51524-188">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-188">Policy</span></span> | <span data-ttu-id="51524-189">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-189">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-190">Sök efter den senaste säkerhetsinformation om virus och spionprogram innan du kör en schemalagd sökning</span><span class="sxs-lookup"><span data-stu-id="51524-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="51524-191">Aktiverad</span><span class="sxs-lookup"><span data-stu-id="51524-191">Enabled</span></span>


<br/>

<span data-ttu-id="51524-192">**Plats för policy:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span><span class="sxs-lookup"><span data-stu-id="51524-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="51524-193">Hämta den aktuella listan med GUID för att minska attackytan från Anpassa minskning [av attackytor](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="51524-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="51524-194">Öppna principen **Konfigurera minskning av attackytan.**</span><span class="sxs-lookup"><span data-stu-id="51524-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="51524-195">Välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="51524-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="51524-196">Välj **knappen** Visa.</span><span class="sxs-lookup"><span data-stu-id="51524-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="51524-197">Lägg till varje GUID i **fältet Värdenamn** med värdet 2.</span><span class="sxs-lookup"><span data-stu-id="51524-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="51524-198">Var och en konfigureras endast för granskning.</span><span class="sxs-lookup"><span data-stu-id="51524-198">This will set each up for audit only.</span></span>

   ![Bild av konfiguration för att minska attackytan](images/asr-guid.png)



<span data-ttu-id="51524-200">Princip</span><span class="sxs-lookup"><span data-stu-id="51524-200">Policy</span></span> | <span data-ttu-id="51524-201">Inställning</span><span class="sxs-lookup"><span data-stu-id="51524-201">Setting</span></span> 
:---|:---
<span data-ttu-id="51524-202">Konfigurera reglerad mappåtkomst</span><span class="sxs-lookup"><span data-stu-id="51524-202">Configure Controlled folder access</span></span>| <span data-ttu-id="51524-203">Aktiverat, granskningsläge</span><span class="sxs-lookup"><span data-stu-id="51524-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="51524-204">Offboard-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="51524-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="51524-205">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="51524-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="51524-206">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="51524-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="51524-207">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="51524-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="51524-208">Principer för onboarding och offboarding får inte distribueras på samma enhet samtidigt, annars kan det orsaka oförutsägbara tavlor.</span><span class="sxs-lookup"><span data-stu-id="51524-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="51524-209">Hämta offboarding-paketet från [Microsoft Defender Säkerhetscenter:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="51524-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="51524-210">I navigeringsfönstret väljer du **Inställningar**  >  **offboarding**.</span><span class="sxs-lookup"><span data-stu-id="51524-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="51524-211">Välj Windows 10 som operativsystem.</span><span class="sxs-lookup"><span data-stu-id="51524-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="51524-212">Välj **Grupprincip i** fältet **Distributionsmetod.**</span><span class="sxs-lookup"><span data-stu-id="51524-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="51524-213">Klicka **på Ladda ned** paket och spara ZIP-filen.</span><span class="sxs-lookup"><span data-stu-id="51524-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="51524-214">Extrahera innehållet i ZIP-filen till en delad, skrivskyddad plats som kan nås av enheten.</span><span class="sxs-lookup"><span data-stu-id="51524-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="51524-215">Du bör ha en fil med *namnet WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="51524-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="51524-216">Öppna GPMC [(Group Policy Management Console),](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) högerklicka på det grupprincipobjekt (GPO) du vill konfigurera och klicka på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="51524-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="51524-217">I **redigeraren för grupprinciphantering** går du **till Datorkonfiguration,** **inställningar** och sedan Inställningar på **Kontrollpanelen.**</span><span class="sxs-lookup"><span data-stu-id="51524-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="51524-218">Högerklicka på **Schemalagda aktiviteter**, peka på **Nytt** och klicka sedan på **Direktaktivitet.**</span><span class="sxs-lookup"><span data-stu-id="51524-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="51524-219">I **uppgiftsfönstret** som öppnas går du till **fliken** Allmänt. Välj det lokala systemanvändarkontot (INBYGGD\SYSTEM) under **Säkerhetsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="51524-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="51524-220">Markera **Kör om användaren är inloggad eller inte** och markera **kryssrutan** Kör med högst behörighet.</span><span class="sxs-lookup"><span data-stu-id="51524-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="51524-221">Gå till fliken **Åtgärder** och klicka på **Nytt...**. Kontrollera att **Starta ett program** är markerat i **fältet** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="51524-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="51524-222">Ange filnamn och plats för den delade filen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd.*</span><span class="sxs-lookup"><span data-stu-id="51524-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="51524-223">Klicka **på OK** och stäng alla öppna GPMC-fönster.</span><span class="sxs-lookup"><span data-stu-id="51524-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51524-224">Offboarding gör att enheten slutar skicka sensordata till portalen men data från enheten, inklusive referens till aviseringar som den haft kommer att behållas i upp till 6 månader.</span><span class="sxs-lookup"><span data-stu-id="51524-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="51524-225">Övervaka enhetskonfiguration</span><span class="sxs-lookup"><span data-stu-id="51524-225">Monitor device configuration</span></span>
<span data-ttu-id="51524-226">Med Grupprincip finns det inte något alternativ för att övervaka distribution av principer på enheter.</span><span class="sxs-lookup"><span data-stu-id="51524-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="51524-227">Övervakning kan utföras direkt i portalen eller med hjälp av de olika distributionsverktygen.</span><span class="sxs-lookup"><span data-stu-id="51524-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="51524-228">Övervaka enheter med hjälp av portalen</span><span class="sxs-lookup"><span data-stu-id="51524-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="51524-229">Gå till [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="51524-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="51524-230">Klicka **på listan Enheter.**</span><span class="sxs-lookup"><span data-stu-id="51524-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="51524-231">Kontrollera att enheter visas.</span><span class="sxs-lookup"><span data-stu-id="51524-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="51524-232">Det kan ta flera dagar innan enheter börjar visas i **listan Enheter.**</span><span class="sxs-lookup"><span data-stu-id="51524-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="51524-233">Det inkluderar den tid det tar för principerna att distribueras till enheten, den tid det tar innan användaren loggar in och den tid det tar för slutpunkten att starta rapporteringen.</span><span class="sxs-lookup"><span data-stu-id="51524-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="51524-234">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="51524-234">Related topics</span></span>
- [<span data-ttu-id="51524-235">Introducera Windows 10-enheter med Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="51524-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="51524-236">Registrera Windows 10-enheter med hanteringsverktyg för mobila enheter</span><span class="sxs-lookup"><span data-stu-id="51524-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="51524-237">Registrera Windows 10-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="51524-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="51524-238">Registrera enheter för icke beständiga VDI-enheter (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="51524-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="51524-239">Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Slutpunkt-enheter</span><span class="sxs-lookup"><span data-stu-id="51524-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="51524-240">Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51524-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
