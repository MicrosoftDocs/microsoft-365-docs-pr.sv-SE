---
title: Få information om hanterade enheter för enkel rörlighet och säkerhet
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
description: Använd Windows PowerShell för att få information om Basic Mobility- och Security-enheter i din organisation.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228177"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="0c26a-103">Få information om hanterade enheter för enkel rörlighet och säkerhet</span><span class="sxs-lookup"><span data-stu-id="0c26a-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="0c26a-104">Den här artikeln visar hur du Windows PowerShell för att få information om de enheter i din organisation som du konfigurerade för Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="0c26a-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="0c26a-105">Här är en sammanfattning av den enhetsinformation som är tillgänglig för dig.</span><span class="sxs-lookup"><span data-stu-id="0c26a-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="0c26a-106">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0c26a-106">**Detail**</span></span>|<span data-ttu-id="0c26a-107">**Vad du ska leta efter i PowerShell**</span><span class="sxs-lookup"><span data-stu-id="0c26a-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="0c26a-108">Enheten är registrerad i Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="0c26a-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="0c26a-109">Mer information finns i [Registrera din mobila enhet med basic mobility and security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="0c26a-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="0c26a-110">Värdet för *parametern isManaged*   är:</span><span class="sxs-lookup"><span data-stu-id="0c26a-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="0c26a-111">**True**= enheten är registrerad.</span><span class="sxs-lookup"><span data-stu-id="0c26a-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="0c26a-112">**False**= device is notrolled.</span><span class="sxs-lookup"><span data-stu-id="0c26a-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="0c26a-113">Enheten följer enhetens säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="0c26a-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="0c26a-114">Mer information finns i Skapa [säkerhetsprinciper för enheter](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="0c26a-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="0c26a-115">Värdet för *parametern isComp parameter*   är:</span><span class="sxs-lookup"><span data-stu-id="0c26a-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="0c26a-116">**True**   = enheten följer principer.</span><span class="sxs-lookup"><span data-stu-id="0c26a-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="0c26a-117">**False**   = enheten följer inte principerna.</span><span class="sxs-lookup"><span data-stu-id="0c26a-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parametrarna Basic Mobility and Security":::

> [!NOTE]
> <span data-ttu-id="0c26a-119">Kommandona och skripten i den här artikeln returnerar också information om enheter som hanteras [av Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0c26a-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0c26a-120">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="0c26a-120">Before you begin</span></span>

<span data-ttu-id="0c26a-121">Det finns några saker du behöver konfigurera för att köra de kommandon och skript som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="0c26a-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="0c26a-122">Steg 1: Ladda ned och installera Azure Active Directory modul för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c26a-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="0c26a-123">Mer information om de här anvisningarna finns i [Anslut att Microsoft 365 med PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="0c26a-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="0c26a-124">Gå till [Microsoft Online Services Sign-In assistenten för IT-proffs RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)och välj Ladda   ned för Microsoft Online Services –  **inloggningsassistent.**</span><span class="sxs-lookup"><span data-stu-id="0c26a-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="0c26a-125">Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="0c26a-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="0c26a-126">Öppna PowerShell-kommandotolken på administratörsnivå.</span><span class="sxs-lookup"><span data-stu-id="0c26a-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="0c26a-127">Kör `Install-Module MSOnline` kommandot.</span><span class="sxs-lookup"><span data-stu-id="0c26a-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="0c26a-128">Om du uppmanas att installera NuGet-leverantör skriver du Y och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="0c26a-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="0c26a-129">Om du uppmanas att installera modulen från PSGGallery, skriver du Y och trycker på RETUR.</span><span class="sxs-lookup"><span data-stu-id="0c26a-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="0c26a-130">Stäng PowerShell-kommandofönstret efter installationen.</span><span class="sxs-lookup"><span data-stu-id="0c26a-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="0c26a-131">Steg 2: Anslut din Microsoft 365 prenumeration</span><span class="sxs-lookup"><span data-stu-id="0c26a-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="0c26a-132">Kör Windows Azure Active Directory i Windows PowerShell i modulen för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c26a-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="0c26a-133">I dialogrutan Windows PowerShell Begäran om autentiseringsuppgifter anger du användarnamn och lösenord för ditt Microsoft 365 globala administratörskonto och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="0c26a-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="0c26a-134">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0c26a-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="0c26a-135">Steg 3: Kontrollera att du kan köra PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="0c26a-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="0c26a-136">Du kan hoppa över det här steget om du redan är konfigurerad för att köra PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="0c26a-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="0c26a-137">Om du Get-MsolUserDeviceComplianceStatus.ps1 skriptet måste du aktivera körningen av PowerShell-skript.</span><span class="sxs-lookup"><span data-stu-id="0c26a-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="0c26a-138">Välj Start Windows skrivbordet **och** skriv sedan texten Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c26a-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="0c26a-139">Högerklicka på Windows PowerShell välj sedan **Kör som administratör.**</span><span class="sxs-lookup"><span data-stu-id="0c26a-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="0c26a-140">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0c26a-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="0c26a-141">När du uppmanas till det skriver du Y och trycker på Retur.</span><span class="sxs-lookup"><span data-stu-id="0c26a-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="0c26a-142">Kör cmdleten Get-MsolDevice-cmdleten för att visa information om alla enheter i organisationen</span><span class="sxs-lookup"><span data-stu-id="0c26a-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="0c26a-143">Öppna Microsoft Azure Active Directory för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c26a-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="0c26a-144">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0c26a-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="0c26a-145">Fler exempel finns i  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)</span><span class="sxs-lookup"><span data-stu-id="0c26a-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="0c26a-146">Köra ett skript för att få enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="0c26a-146">Run a script to get device details</span></span>

<span data-ttu-id="0c26a-147">Börja med att spara skriptet på datorn.</span><span class="sxs-lookup"><span data-stu-id="0c26a-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="0c26a-148">Kopiera och klistra in följande text i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="0c26a-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="0c26a-149">Spara den som Windows PowerShell skriptfil med filtillägget .ps1; till exempel Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="0c26a-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="0c26a-150">Kör skriptet för att hämta enhetsinformation för ett enskilt användarkonto</span><span class="sxs-lookup"><span data-stu-id="0c26a-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="0c26a-151">Öppna Microsoft Azure Active Directory för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c26a-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="0c26a-152">Gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="0c26a-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="0c26a-153">Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="0c26a-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="0c26a-154">Kör följande kommando för att identifiera den användare du vill hämta enhetsinformation för.</span><span class="sxs-lookup"><span data-stu-id="0c26a-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="0c26a-155">I det här exemplet får du information bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="0c26a-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="0c26a-156">Kör följande kommando för att starta skriptet.</span><span class="sxs-lookup"><span data-stu-id="0c26a-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="0c26a-157">Informationen exporteras till ditt Windows som en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="0c26a-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="0c26a-158">Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.</span><span class="sxs-lookup"><span data-stu-id="0c26a-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="0c26a-159">Kör skriptet för att hämta enhetsinformation för en grupp användare</span><span class="sxs-lookup"><span data-stu-id="0c26a-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="0c26a-160">Öppna Microsoft Azure Active Directory för Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c26a-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="0c26a-161">Gå till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="0c26a-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="0c26a-162">Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="0c26a-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="0c26a-163">Kör följande kommando för att identifiera den grupp du vill hämta enhetsinformation för.</span><span class="sxs-lookup"><span data-stu-id="0c26a-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="0c26a-164">Det här exemplet hämtar information för användare i gruppen Ekonomiavdelning.</span><span class="sxs-lookup"><span data-stu-id="0c26a-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="0c26a-165">Kör följande kommando för att starta skriptet.</span><span class="sxs-lookup"><span data-stu-id="0c26a-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="0c26a-166">Informationen exporteras till ditt Windows som en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="0c26a-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="0c26a-167">Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.</span><span class="sxs-lookup"><span data-stu-id="0c26a-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c26a-168">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0c26a-168">Related topics</span></span>

[<span data-ttu-id="0c26a-169">Microsoft Anslut har tagits ur bruk</span><span class="sxs-lookup"><span data-stu-id="0c26a-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="0c26a-170">Översikt över grundläggande Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="0c26a-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="0c26a-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="0c26a-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
