---
title: Få information om grundläggande mobilitet och hanterade enheter
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd Windows PowerShell för att få information om grundläggande mobilitet och säkerhets enheter i din organisation.
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876894"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="99c88-103">Få information om grundläggande mobilitet och hanterade enheter</span><span class="sxs-lookup"><span data-stu-id="99c88-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="99c88-104">I den här artikeln lär du dig hur du använder Windows PowerShell för att få information om de enheter i organisationen som du skapar för grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="99c88-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="99c88-105">Här är en uppdelning av enhets uppgifterna som är tillgängliga för dig.</span><span class="sxs-lookup"><span data-stu-id="99c88-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="99c88-106">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="99c88-106">**Detail**</span></span>|<span data-ttu-id="99c88-107">**Vad du kan söka efter i PowerShell**</span><span class="sxs-lookup"><span data-stu-id="99c88-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="99c88-108">Enheten är registrerad i grundläggande mobilitet och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="99c88-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="99c88-109">Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="99c88-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="99c88-110">Värdet för parametern *isManaged*   är:</span><span class="sxs-lookup"><span data-stu-id="99c88-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="99c88-111">**True**= enheten är registrerad.</span><span class="sxs-lookup"><span data-stu-id="99c88-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="99c88-112">**False**= enheten är inte registrerad.</span><span class="sxs-lookup"><span data-stu-id="99c88-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="99c88-113">Enheten är kompatibel med din enhets säkerhets principer.</span><span class="sxs-lookup"><span data-stu-id="99c88-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="99c88-114">Mer information finns i [skapa säkerhets principer för enheter](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="99c88-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="99c88-115">Värdet för parametern *isCompliant*   är:</span><span class="sxs-lookup"><span data-stu-id="99c88-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="99c88-116">**Sant**   = enheten är kompatibel med principer.</span><span class="sxs-lookup"><span data-stu-id="99c88-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="99c88-117">**Falskt**   = enheten är inte kompatibel med principer.</span><span class="sxs-lookup"><span data-stu-id="99c88-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundläggande PowerShell-parametrar för mobilitet och säkerhet":::

>[!NOTE]
><span data-ttu-id="99c88-119">Kommandona och skripten i den här artikeln returnerar också information om vilka enheter som hanteras av [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="99c88-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="99c88-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="99c88-120">Before you begin</span></span>

<span data-ttu-id="99c88-121">Det finns några saker du måste ställa in för att köra de kommandon och skript som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99c88-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="99c88-122">Steg 1: Ladda ned och installera Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99c88-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="99c88-123">Mer information om de här stegen finns i [ansluta till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="99c88-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="99c88-124">Gå till [Microsoft Online services Sign-In Assistant för IT-experter RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   och välj  **Hämta för Microsoft Online Services-inloggnings assistent**.</span><span class="sxs-lookup"><span data-stu-id="99c88-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="99c88-125">Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="99c88-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="99c88-126">Öppna en kommando tolk för PowerShell på administratörs nivå.</span><span class="sxs-lookup"><span data-stu-id="99c88-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="99c88-127">Kör kommandot Installera-modul MSOnline.</span><span class="sxs-lookup"><span data-stu-id="99c88-127">Run the Install-Module MSOnline command.</span></span>

    3. <span data-ttu-id="99c88-128">Om du uppmanas att installera NuGet-leverantör skriver du Y och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="99c88-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="99c88-129">Om du uppmanas att installera modulen från PSGGallery, skriver du Y och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="99c88-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="99c88-130">När installationen är slutförd stänger du PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="99c88-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="99c88-131">Steg 2: Anslut till din Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="99c88-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="99c88-132">Kör följande kommando i Windows Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c88-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="99c88-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="99c88-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="99c88-134">I dialog rutan begäran om autentiseringsuppgifter för Windows PowerShell anger du användar namn och lösen ord för ditt Microsoft 365-globala administratörs konto och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="99c88-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="99c88-135">Kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99c88-135">Run the following command.</span></span>

    <span data-ttu-id="99c88-136">Connect-MsolService-autentiseringsuppgifter $UserCredential</span><span class="sxs-lookup"><span data-stu-id="99c88-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="99c88-137">Steg 3: kontrol lera att du kan köra PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="99c88-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="99c88-138">Du kan hoppa över det här steget om du redan har konfigurerat för att köra PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="99c88-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="99c88-139">Om du vill köra det Get-MsolUserDeviceComplianceStatus.ps1 skriptet måste du aktivera körningen av PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="99c88-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="99c88-140">I Skriv bords versionen av Windows väljer du **Start** och skriver sedan Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c88-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="99c88-141">Högerklicka på Windows PowerShell och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="99c88-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="99c88-142">Kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99c88-142">Run the following command.</span></span>

    <span data-ttu-id="99c88-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="99c88-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="99c88-144">Skriv Y när du uppmanas till det och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="99c88-144">When prompted, type Y and then press Enter.</span></span>

<span data-ttu-id="99c88-145">**Kör cmdleten Get-MsolDevice för att visa information för alla enheter i organisationen**</span><span class="sxs-lookup"><span data-stu-id="99c88-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="99c88-146">Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c88-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="99c88-147">Kör följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99c88-147">Run the following command.</span></span>

    <span data-ttu-id="99c88-148">Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="99c88-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="99c88-149">Fler exempel finns i  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="99c88-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="99c88-150">Köra ett skript för att få enhets information</span><span class="sxs-lookup"><span data-stu-id="99c88-150">Run a script to get device details</span></span>

<span data-ttu-id="99c88-151">Spara först skriptet till datorn.</span><span class="sxs-lookup"><span data-stu-id="99c88-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="99c88-152">Kopiera och klistra in följande text i anteckningar.</span><span class="sxs-lookup"><span data-stu-id="99c88-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="99c88-153">parametrar</span><span class="sxs-lookup"><span data-stu-id="99c88-153">param (</span></span>

3.  <span data-ttu-id="99c88-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="99c88-154">[PSObject[]]$users = @(),</span></span>

4.  <span data-ttu-id="99c88-155">[Växel] $export</span><span class="sxs-lookup"><span data-stu-id="99c88-155">[Switch]$export,</span></span>

5.  <span data-ttu-id="99c88-156">[Sträng] $exportFileName = "UserDeviceComplianceStatus_" + (Hämta-datum-format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="99c88-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>

6.  <span data-ttu-id="99c88-157">[Sträng] $exportPath = [miljö]:: GetFolderPath ("Skriv bord")</span><span class="sxs-lookup"><span data-stu-id="99c88-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>

7.  <span data-ttu-id="99c88-158">)</span><span class="sxs-lookup"><span data-stu-id="99c88-158">)</span></span>

9.  <span data-ttu-id="99c88-159">[System. Collection. IDictionary] $script: schema = @ {</span><span class="sxs-lookup"><span data-stu-id="99c88-159">[System.Collections.IDictionary]$script:schema = @{</span></span>

11.  <span data-ttu-id="99c88-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-160">DeviceId = ''</span></span>

12.  <span data-ttu-id="99c88-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-161">DeviceOSType = ''</span></span>

13.  <span data-ttu-id="99c88-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-162">DeviceOSVersion = ''</span></span>

14.  <span data-ttu-id="99c88-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-163">DeviceTrustLevel = ''</span></span>

15.  <span data-ttu-id="99c88-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-164">DisplayName = ''</span></span>

16.  <span data-ttu-id="99c88-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-165">IsCompliant = ''</span></span>

17.  <span data-ttu-id="99c88-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-166">IsManaged = ''</span></span>

18.  <span data-ttu-id="99c88-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-167">ApproximateLastLogonTimestamp = ''</span></span>

19.  <span data-ttu-id="99c88-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-168">DeviceObjectId = ''</span></span>

20.  <span data-ttu-id="99c88-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-169">RegisteredOwnerUpn = ''</span></span>

21.  <span data-ttu-id="99c88-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="99c88-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="99c88-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="99c88-172">}</span><span class="sxs-lookup"><span data-stu-id="99c88-172">}</span></span>
    

25.  <span data-ttu-id="99c88-173">funktionen createResultObject</span><span class="sxs-lookup"><span data-stu-id="99c88-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="99c88-174">{</span><span class="sxs-lookup"><span data-stu-id="99c88-174">{</span></span>
    

28.  <span data-ttu-id="99c88-175">[PSObject] $resultObject = New-Object-TypeName PSObject-egenskap $script: schema</span><span class="sxs-lookup"><span data-stu-id="99c88-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="99c88-176">returnera $resultObject</span><span class="sxs-lookup"><span data-stu-id="99c88-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="99c88-177">}</span><span class="sxs-lookup"><span data-stu-id="99c88-177">}</span></span>
    

33.  <span data-ttu-id="99c88-178">Om ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="99c88-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="99c88-179">{</span><span class="sxs-lookup"><span data-stu-id="99c88-179">{</span></span>
    

35.  <span data-ttu-id="99c88-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="99c88-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="99c88-181">}</span><span class="sxs-lookup"><span data-stu-id="99c88-181">}</span></span>
    

38.  <span data-ttu-id="99c88-182">[PSObject []] $result = ($u i $users)</span><span class="sxs-lookup"><span data-stu-id="99c88-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="99c88-183">{</span><span class="sxs-lookup"><span data-stu-id="99c88-183">{</span></span>
    

41.  <span data-ttu-id="99c88-184">[PSObject] $devices = get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="99c88-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="99c88-185">$d i $devices</span><span class="sxs-lookup"><span data-stu-id="99c88-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="99c88-186">{</span><span class="sxs-lookup"><span data-stu-id="99c88-186">{</span></span>
    

44.  <span data-ttu-id="99c88-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="99c88-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="99c88-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="99c88-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="99c88-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="99c88-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="99c88-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="99c88-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="99c88-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="99c88-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="99c88-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="99c88-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="99c88-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="99c88-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="99c88-194">$deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged</span><span class="sxs-lookup"><span data-stu-id="99c88-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="99c88-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="99c88-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="99c88-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="99c88-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="99c88-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="99c88-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="99c88-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="99c88-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="99c88-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="99c88-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="99c88-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="99c88-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="99c88-201">}</span><span class="sxs-lookup"><span data-stu-id="99c88-201">}</span></span>
    

61.  <span data-ttu-id="99c88-202">}</span><span class="sxs-lookup"><span data-stu-id="99c88-202">}</span></span>
    

63.  <span data-ttu-id="99c88-203">Om ($export)</span><span class="sxs-lookup"><span data-stu-id="99c88-203">If ($export)</span></span>
    

64.  <span data-ttu-id="99c88-204">{</span><span class="sxs-lookup"><span data-stu-id="99c88-204">{</span></span>
    

65.  <span data-ttu-id="99c88-205">$result | Export-Csv-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="99c88-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="99c88-206">}</span><span class="sxs-lookup"><span data-stu-id="99c88-206">}</span></span>
    

67.  <span data-ttu-id="99c88-207">Person</span><span class="sxs-lookup"><span data-stu-id="99c88-207">Else</span></span>
    

68.  <span data-ttu-id="99c88-208">{</span><span class="sxs-lookup"><span data-stu-id="99c88-208">{</span></span>
    

69.  <span data-ttu-id="99c88-209">$result</span><span class="sxs-lookup"><span data-stu-id="99c88-209">$result</span></span>
    

70.  <span data-ttu-id="99c88-210">}</span><span class="sxs-lookup"><span data-stu-id="99c88-210">}</span></span>
    

71.  <span data-ttu-id="99c88-211">Spara den som en Windows PowerShell-skriptfil genom att använda fil namns tillägget. ps1; till exempel Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="99c88-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="99c88-212">Kör skriptet för att hämta enhets information för ett enskilt användar konto</span><span class="sxs-lookup"><span data-stu-id="99c88-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="99c88-213">Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c88-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="99c88-214">Gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="99c88-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="99c88-215">Om du till exempel sparade den på C:\PS-Scripts kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99c88-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="99c88-216">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="99c88-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="99c88-217">Kör följande kommando för att identifiera den användare som du vill hämta enhets information för.</span><span class="sxs-lookup"><span data-stu-id="99c88-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="99c88-218">Det här exemplet får information om bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="99c88-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="99c88-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="99c88-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="99c88-220">Kör följande kommando för att starta skriptet.</span><span class="sxs-lookup"><span data-stu-id="99c88-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="99c88-221">.\Get-MsolUserDeviceComplianceStatus.ps1-användare $u-exportera</span><span class="sxs-lookup"><span data-stu-id="99c88-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="99c88-222">Informationen exporteras till Windows-skrivbordet som en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="99c88-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="99c88-223">Du kan använda ytterligare parametrar för att ange fil namnet och sökvägen för CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="99c88-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="99c88-224">Köra skriptet för att hämta enhets information för en grupp användare</span><span class="sxs-lookup"><span data-stu-id="99c88-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="99c88-225">Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="99c88-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="99c88-226">Gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="99c88-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="99c88-227">Om du till exempel sparade den på C:\PS-Scripts kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="99c88-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="99c88-228">CD-C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="99c88-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="99c88-229">Kör följande kommando för att identifiera gruppen som du vill hämta enhets information för.</span><span class="sxs-lookup"><span data-stu-id="99c88-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="99c88-230">I det här exemplet får du information om användare i gruppen FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="99c88-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="99c88-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. Tillägg</span><span class="sxs-lookup"><span data-stu-id="99c88-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="99c88-232">Kör följande kommando för att starta skriptet.</span><span class="sxs-lookup"><span data-stu-id="99c88-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="99c88-233">.\Get-MsolUserDeviceComplianceStatus.ps1-användare $u-exportera</span><span class="sxs-lookup"><span data-stu-id="99c88-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="99c88-234">Informationen exporteras till Windows-skrivbordet som en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="99c88-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="99c88-235">Du kan använda ytterligare parametrar för att ange fil namnet och sökvägen för CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="99c88-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99c88-236">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="99c88-236">Related topics</span></span>

[<span data-ttu-id="99c88-237">Microsoft Connect har avbrutits</span><span class="sxs-lookup"><span data-stu-id="99c88-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="99c88-238">Översikt över grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="99c88-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="99c88-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="99c88-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)