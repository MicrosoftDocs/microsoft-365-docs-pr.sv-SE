---
title: Kom igång med Microsofts efterlevnadstillägg
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Förbered och distribuera Microsofts efterlevnadstillägg.
ms.openlocfilehash: 5a2fa5958117d14715292245924dce2ff63b09a0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843836"
---
# <a name="get-started-with-microsoft-compliance-extension"></a><span data-ttu-id="4ca57-103">Kom igång med Microsofts efterlevnadstillägg</span><span class="sxs-lookup"><span data-stu-id="4ca57-103">Get started with Microsoft Compliance Extension</span></span>

<span data-ttu-id="4ca57-104">Använd de här metoderna för att distribuera Microsofts efterlevnadstillägg.</span><span class="sxs-lookup"><span data-stu-id="4ca57-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4ca57-105">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="4ca57-105">Before you begin</span></span>

<span data-ttu-id="4ca57-106">Om du vill använda Microsofts efterlevnadstillägg måste enheten vara registrerad i slutpunkts-DLP:n.</span><span class="sxs-lookup"><span data-stu-id="4ca57-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="4ca57-107">Läs de här artiklarna om du är nybörjare på DLP eller slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="4ca57-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="4ca57-108">Mer information om Microsofts efterlevnadstillägg</span><span class="sxs-lookup"><span data-stu-id="4ca57-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="4ca57-109">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="4ca57-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4ca57-110">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="4ca57-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4ca57-111">Skapa en DLP-princip från en mall</span><span class="sxs-lookup"><span data-stu-id="4ca57-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="4ca57-112">Mer information om dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="4ca57-113">Komma igång med dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="4ca57-114">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="4ca57-115">Konfigurera enhetsproxy och Internetanslutningsinställningar för slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="4ca57-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="4ca57-116">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="4ca57-117">Licensiering av SKU/prenumerationer</span><span class="sxs-lookup"><span data-stu-id="4ca57-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="4ca57-118">Innan du börjar måste du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) och eventuella tillägg.</span><span class="sxs-lookup"><span data-stu-id="4ca57-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="4ca57-119">Om du vill komma åt och använda slutpunkts-DLP, måste du ha någon av dessa prenumerationer eller tillägg.</span><span class="sxs-lookup"><span data-stu-id="4ca57-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="4ca57-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ca57-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="4ca57-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="4ca57-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="4ca57-122">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="4ca57-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="4ca57-123">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="4ca57-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="4ca57-124">Microsoft 365 E5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="4ca57-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="4ca57-125">Microsoft 365 A5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="4ca57-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="4ca57-126">Detaljerad licensvägledning finns i [Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="4ca57-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="4ca57-127">Organisationen måste vara licensierad för slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="4ca57-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="4ca57-128">Dina enheter måste köra Windows 10 x64 version 1809 eller senare.</span><span class="sxs-lookup"><span data-stu-id="4ca57-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="4ca57-129">Enheten måste ha klientversion 4.18.2101.9 för program mot skadlig kod eller senare.</span><span class="sxs-lookup"><span data-stu-id="4ca57-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="4ca57-130">Kontrollera din aktuella version genom att öppna **Windows-säkerhet**, välj ikonen **Inställningar** och välj sedan **Om**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="4ca57-131">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-131">Permissions</span></span>

<span data-ttu-id="4ca57-132">Data från slutpunkts-DLP kan visas i [Aktivitetsutforskaren](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="4ca57-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="4ca57-133">Det finns sju roller som ger behörighet till aktivitetsutforskaren och det konto som du använder för att komma åt datan måste vara medlem i någon av dem.</span><span class="sxs-lookup"><span data-stu-id="4ca57-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="4ca57-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="4ca57-134">Global admin</span></span>
- <span data-ttu-id="4ca57-135">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="4ca57-135">Compliance admin</span></span>
- <span data-ttu-id="4ca57-136">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="4ca57-136">Security admin</span></span>
- <span data-ttu-id="4ca57-137">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="4ca57-137">Compliance data admin</span></span>
- <span data-ttu-id="4ca57-138">Global läsare</span><span class="sxs-lookup"><span data-stu-id="4ca57-138">Global reader</span></span>
- <span data-ttu-id="4ca57-139">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="4ca57-139">Security reader</span></span>
- <span data-ttu-id="4ca57-140">Rapportläsare</span><span class="sxs-lookup"><span data-stu-id="4ca57-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="4ca57-141">Övergripande installationsarbetsflöde</span><span class="sxs-lookup"><span data-stu-id="4ca57-141">Overall installation workflow</span></span>

<span data-ttu-id="4ca57-p105">Distributionen av Microsofts efterlevnadstillägg är en process med flera faser. Du kan välja att installera på en dator i taget, använda Microsoft Endpoint Manager eller en grupprincip för organisationsomfattande distributioner.</span><span class="sxs-lookup"><span data-stu-id="4ca57-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="4ca57-144">[Förbered dina enheter](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="4ca57-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="4ca57-145">Grundläggande konfiguration av en dator med selfhost</span><span class="sxs-lookup"><span data-stu-id="4ca57-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="4ca57-146">Distribuera med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4ca57-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="4ca57-147">Distribuera med grupprincip</span><span class="sxs-lookup"><span data-stu-id="4ca57-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="4ca57-148">Testa tillägget</span><span class="sxs-lookup"><span data-stu-id="4ca57-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="4ca57-149">Använda instrumentpanelen för hantering av aviseringar till att visa Chrome DLP-aviseringar</span><span class="sxs-lookup"><span data-stu-id="4ca57-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="4ca57-150">Visa Chrome DLP-data i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="4ca57-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="4ca57-151">Förbereda infrastrukturen</span><span class="sxs-lookup"><span data-stu-id="4ca57-151">Prepare infrastructure</span></span>

<span data-ttu-id="4ca57-152">Om du distribuerar Microsofts efterlevnadstillägg till alla övervakade Windows 10-enheter, bör du ta bort Google Chrome från listan med otillåtna appar och listan med otillåtna webbläsare.</span><span class="sxs-lookup"><span data-stu-id="4ca57-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="4ca57-153">Mer information finns i [Otillåtna webbläsare](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="4ca57-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="4ca57-154">Om du bara distribuerar det till några få enheter kan du låta Chrome finnas kvar i listorna med otillåtna webbläsare eller appar.</span><span class="sxs-lookup"><span data-stu-id="4ca57-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="4ca57-155">Microsofts efterlevnadstillägg kringgår begränsningarna i båda listorna för de datorer där det är installerat.</span><span class="sxs-lookup"><span data-stu-id="4ca57-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="4ca57-156">Förbereda dina enheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-156">Prepare your devices</span></span>

1. <span data-ttu-id="4ca57-157">Använd metoderna i följande avsnitt för att registrera dina enheter:</span><span class="sxs-lookup"><span data-stu-id="4ca57-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="4ca57-158">Komma igång med dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="4ca57-159">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="4ca57-160">Konfigurera enhetsproxy och Internetanslutningsinställningar för slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="4ca57-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="4ca57-161">Grundläggande konfiguration av en dator med selfhost</span><span class="sxs-lookup"><span data-stu-id="4ca57-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="4ca57-162">Detta är den rekommenderade metoden.</span><span class="sxs-lookup"><span data-stu-id="4ca57-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="4ca57-163">Logga in på den Windows 10-dator där du vill installera Microsofts efterlevnadstillägg och kör PowerShell-skriptet som administratör.</span><span class="sxs-lookup"><span data-stu-id="4ca57-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="4ca57-164">Gå till [Microsofts efterlevnadstillägg – Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="4ca57-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="4ca57-165">Installera tillägget med hjälp av anvisningarna på Chrome Web Store-sidan.</span><span class="sxs-lookup"><span data-stu-id="4ca57-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="4ca57-166">Distribuera med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4ca57-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="4ca57-167">Använd konfigurationsmetoden vid distributioner till hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="4ca57-168">Aktivera den obligatoriska registernyckeln via Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4ca57-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="4ca57-169">Skapa ett PowerShell-skript med följande innehåll:</span><span class="sxs-lookup"><span data-stu-id="4ca57-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="4ca57-170">Logga in på [Administrationscenter för Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4ca57-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="4ca57-171">Gå till **Enheter** > **Skript** och välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="4ca57-172">Bläddra till platsen för skriptet som skapades när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="4ca57-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="4ca57-173">Välj följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4ca57-173">Select the following settings:</span></span>
    1. <span data-ttu-id="4ca57-174">Kör skriptet med de inloggade autentiseringsuppgifterna: JA</span><span class="sxs-lookup"><span data-stu-id="4ca57-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="4ca57-175">Framtvinga signaturkontroll av skript: NEJ</span><span class="sxs-lookup"><span data-stu-id="4ca57-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="4ca57-176">Kör skript i 64-bitars PowerShell-värd: JA</span><span class="sxs-lookup"><span data-stu-id="4ca57-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="4ca57-177">Välj enhetsgrupper och tillämpa principen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="4ca57-178">Installera alltid med Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="4ca57-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="4ca57-179">Innan du lägger till Microsofts efterlevnadstillägg i listan med tillägg som alltid installeras, är det viktigt att mata in Chrome ADMX.</span><span class="sxs-lookup"><span data-stu-id="4ca57-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="4ca57-180">Stegen för den här processen i Microsoft Endpoint Manager har dokumenterats av Google: [Hantera Chrome-webbläsaren med Microsoft Intune – Hjälp för Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="4ca57-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="4ca57-181">När du har matat in ADMX kan du följa stegen nedan för att skapa en konfigurationsprofil för tillägget.</span><span class="sxs-lookup"><span data-stu-id="4ca57-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="4ca57-182">Logga in på Administrationscenter för Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4ca57-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="4ca57-183">Gå till konfigurationsprofilerna.</span><span class="sxs-lookup"><span data-stu-id="4ca57-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="4ca57-184">Välj **Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="4ca57-185">Välj **Windows 10** som plattform.</span><span class="sxs-lookup"><span data-stu-id="4ca57-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="4ca57-186">Välj **Anpassad** som profiltyp.</span><span class="sxs-lookup"><span data-stu-id="4ca57-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="4ca57-187">Välj fliken **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="4ca57-188">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-188">Select **Add**.</span></span>

8.  <span data-ttu-id="4ca57-189">Ange nedanstående principinformation.</span><span class="sxs-lookup"><span data-stu-id="4ca57-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="4ca57-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="4ca57-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="4ca57-191">Datatyp: `String`</span><span class="sxs-lookup"><span data-stu-id="4ca57-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="4ca57-192">Värde: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="4ca57-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="4ca57-193">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="4ca57-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="4ca57-194">Distribuera med grupprincip</span><span class="sxs-lookup"><span data-stu-id="4ca57-194">Deploy using Group Policy</span></span>

<span data-ttu-id="4ca57-195">Om du inte vill använda Microsoft Endpoint Manager kan du använda grupprinciper till att distribuera Microsofts efterlevnadstillägg i hela organisationen</span><span class="sxs-lookup"><span data-stu-id="4ca57-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="4ca57-196">Enheterna måste vara hanterbara via grupprincipen och du måste importera alla Chrome ADMX till den centrala lagringsplatsen för grupprincipen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="4ca57-197">Mer information finns i [Skapa och hantera den centrala lagringsplatsen för grupprincipens administrativa mallar i Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="4ca57-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="4ca57-198">Skapa ett PowerShell-skript med PowerShell-kommandot:</span><span class="sxs-lookup"><span data-stu-id="4ca57-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="4ca57-199">Öppna **konsolen Grupprinciphantering** och gå till din organisationsenhet.</span><span class="sxs-lookup"><span data-stu-id="4ca57-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="4ca57-200">Högerklicka och välj **Skapa ett GPO på den här domänen och länka den här**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="4ca57-201">När du uppmanas till det tilldelar du ett beskrivande namn till grupprincipobjektet (GPO) och slutför.</span><span class="sxs-lookup"><span data-stu-id="4ca57-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="4ca57-202">Högerklicka på GPO:et och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="4ca57-203">Gå till **Datorkonfiguration** > **Inställningar** > **Inställningar för Kontrollpanel** > **Schemalagda aktiviteter**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="4ca57-204">Skapa en ny omedelbar aktivitet genom att högerklicka och välja **Nytt** > **Omedelbar aktivitet (minst Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="4ca57-205">Ge uppgiften ett namn och en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4ca57-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="4ca57-206">Välj motsvarande konto för att köra den omedelbara aktiviteten, t.ex. NT Authority</span><span class="sxs-lookup"><span data-stu-id="4ca57-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="4ca57-207">Välj **Kör med högsta behörighet**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="4ca57-208">Konfigurera principen för Windows 10.</span><span class="sxs-lookup"><span data-stu-id="4ca57-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="4ca57-209">På fliken **Åtgärder** väljer du åtgärden **Starta ett program**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="4ca57-210">Ange sökvägen till det program/skript som skapades i steg 1.</span><span class="sxs-lookup"><span data-stu-id="4ca57-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="4ca57-211">Välj **Använd**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="4ca57-212">Lägga till Chrome-tillägget i ForceInstall-listan</span><span class="sxs-lookup"><span data-stu-id="4ca57-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="4ca57-213">Gå till organisationsenheten i redigeringsprogrammet för grupprinciphantering.</span><span class="sxs-lookup"><span data-stu-id="4ca57-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="4ca57-214">Expandera följande sökväg **Konfiguration av dator/användare** > **Principer** > **Administrativa mallar** > **Klassiska administrativa mallar** > **Google** > **Google Chrome** > **Tillägg**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="4ca57-215">Sökvägen kan variera beroende på din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ca57-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="4ca57-216">Välj **Konfigurera listan med tillägg som alltid installeras**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="4ca57-217">Högerklicka och välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="4ca57-218">Välj **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="4ca57-219">Välj **Visa**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-219">Select **Show**.</span></span>

7.  <span data-ttu-id="4ca57-220">Under **Värde** lägger du till följande post: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="4ca57-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="4ca57-221">Välj **OK** och sedan **Använd**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="4ca57-222">Testa tillägget</span><span class="sxs-lookup"><span data-stu-id="4ca57-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="4ca57-223">Ladda upp till molntjänst eller åtkomst av otillåtna webbläsare med utgående moln</span><span class="sxs-lookup"><span data-stu-id="4ca57-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="4ca57-224">Skapa eller hämta ett känsligt objekt och försök att ladda upp en fil till någon av organisationens begränsade tjänstdomäner.</span><span class="sxs-lookup"><span data-stu-id="4ca57-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="4ca57-225">Den känsliga datan måste matcha någon av våra inbyggda [typer av känslig information](sensitive-information-type-entity-definitions.md), eller någon av organisationens typer av känslig information.</span><span class="sxs-lookup"><span data-stu-id="4ca57-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="4ca57-226">Du bör få ett popup-meddelande från DLP:n på den enhet du testar från, som visar att åtgärden inte är tillåten när filen är öppen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="4ca57-227">Testa andra DLP-scenarier i Chrome</span><span class="sxs-lookup"><span data-stu-id="4ca57-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="4ca57-228">Nu när du har tagit bort Chrome från listan med otillåtna webbläsare/appar kan du testa scenarierna nedan för att kontrollera att beteendet uppfyller organisationens krav:</span><span class="sxs-lookup"><span data-stu-id="4ca57-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="4ca57-229">Kopiera data från ett känsligt objekt till ett annat dokument med hjälp av Urklipp</span><span class="sxs-lookup"><span data-stu-id="4ca57-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="4ca57-230">Testa genom att öppna en fil som är skyddad från att kopiera till Urklipp i webbläsaren Chrome och försök kopiera data från filen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="4ca57-231">Förväntat resultat: Ett popup-meddelande från DLP om att åtgärden inte är tillåten när filen är öppen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="4ca57-232">Skriva ut ett dokument</span><span class="sxs-lookup"><span data-stu-id="4ca57-232">Print a document</span></span>
    - <span data-ttu-id="4ca57-233">Testa genom att öppna en fil som är skyddad mot utskriftsåtgärder i webbläsaren Chrome och försök att skriva ut filen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="4ca57-234">Förväntat resultat: Ett popup-meddelande från DLP om att åtgärden inte är tillåten när filen är öppen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="4ca57-235">Kopiera till USB-flyttbart medium</span><span class="sxs-lookup"><span data-stu-id="4ca57-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="4ca57-236">Prova att spara filen i en flyttbar medielagring.</span><span class="sxs-lookup"><span data-stu-id="4ca57-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="4ca57-237">Förväntat resultat: Ett popup-meddelande från DLP om att åtgärden inte är tillåten när filen är öppen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="4ca57-238">Kopiera till en nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="4ca57-238">Copy to Network Share</span></span>
    - <span data-ttu-id="4ca57-239">Prova att spara filen på en nätverksresurs.</span><span class="sxs-lookup"><span data-stu-id="4ca57-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="4ca57-240">Förväntat resultat: Ett popup-meddelande från DLP om att åtgärden inte är tillåten när filen är öppen.</span><span class="sxs-lookup"><span data-stu-id="4ca57-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="4ca57-241">Använda instrumentpanelen för hantering av aviseringar till att visa DLP-aviseringar för Chrome</span><span class="sxs-lookup"><span data-stu-id="4ca57-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="4ca57-242">Öppna sidan **Dataförlustskydd** i [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com) och välj **Aviseringar**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="4ca57-243">Se metoderna i [Konfigurera och visa aviseringar för DLP-principer](dlp-configure-view-alerts-policies.md) om du vill se aviseringarna för slutpunkts-DLP:ns principer.</span><span class="sxs-lookup"><span data-stu-id="4ca57-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="4ca57-244">Visa Chrome DLP-data i aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="4ca57-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="4ca57-245">Öppna [sidan Dataklassificering](https://compliance.microsoft.com/dataclassification?viewid=overview) för din domän i Microsoft 365 Efterlevnadscenter och välj **Aktivitetsutforskare**.</span><span class="sxs-lookup"><span data-stu-id="4ca57-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="4ca57-246">Se metoderna i [Kom igång med aktivitetsutforskaren](data-classification-activity-explorer.md) för att komma åt och filtrera alla data för slutpunktsenheterna.</span><span class="sxs-lookup"><span data-stu-id="4ca57-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4ca57-247">![aktivitetsutforskarens filter för slutpunktsenheter](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="4ca57-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="4ca57-248">Kända problem och begränsningar</span><span class="sxs-lookup"><span data-stu-id="4ca57-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="4ca57-249">Användning av åsidosättning av blockering för utgående moln stöds inte.</span><span class="sxs-lookup"><span data-stu-id="4ca57-249">Block Override enforcement for cloud egress is not supported.</span></span>
2. <span data-ttu-id="4ca57-250">Inkognitoläge stöds inte och måste vara inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="4ca57-250">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ca57-251">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4ca57-251">Next steps</span></span>
<span data-ttu-id="4ca57-252">Nu när du har registrerat enheter och kan se aktivitetsdata i aktivitetsutforskaren, kan du gå vidare till nästa steg där du skapar DLP-principer som skyddar dina känsliga objekt.</span><span class="sxs-lookup"><span data-stu-id="4ca57-252">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="4ca57-253">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-253">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="4ca57-254">Se även</span><span class="sxs-lookup"><span data-stu-id="4ca57-254">See also</span></span>

- [<span data-ttu-id="4ca57-255">Mer information om dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-255">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="4ca57-256">Använda dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="4ca57-256">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="4ca57-257">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="4ca57-257">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4ca57-258">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="4ca57-258">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4ca57-259">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="4ca57-259">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4ca57-260">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="4ca57-260">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="4ca57-261">Registreringsverktyg och metoder för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-261">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="4ca57-262">Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="4ca57-262">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="4ca57-263">Azure AD-anslutna enheter</span><span class="sxs-lookup"><span data-stu-id="4ca57-263">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="4ca57-264">Ladda ned nya Microsoft Edge som baseras på Chromium</span><span class="sxs-lookup"><span data-stu-id="4ca57-264">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
