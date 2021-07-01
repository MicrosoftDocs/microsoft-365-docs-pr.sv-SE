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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Få information om hanterade enheter för enkel rörlighet och säkerhet

Den här artikeln visar hur du Windows PowerShell för att få information om de enheter i din organisation som du konfigurerade för Basic Mobility and Security.

Här är en sammanfattning av den enhetsinformation som är tillgänglig för dig.

|**Beskrivning**|**Vad du ska leta efter i PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Enheten är registrerad i Basic Mobility and Security. Mer information finns i [Registrera din mobila enhet med basic mobility and security](enroll-your-mobile-device.md)|Värdet för *parametern isManaged*   är:<br/>**True**= enheten är registrerad.<br/>**False**= device is notrolled. |
|Enheten följer enhetens säkerhetsprinciper. Mer information finns i Skapa [säkerhetsprinciper för enheter](create-device-security-policies.md)|Värdet för *parametern isComp parameter*   är:<br/>**True**   = enheten följer principer.<br/>**False**   = enheten följer inte principerna.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parametrarna Basic Mobility and Security":::

> [!NOTE]
> Kommandona och skripten i den här artikeln returnerar också information om enheter som hanteras [av Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Innan du börjar

Det finns några saker du behöver konfigurera för att köra de kommandon och skript som beskrivs i den här artikeln.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Steg 1: Ladda ned och installera Azure Active Directory modul för Windows PowerShell

Mer information om de här anvisningarna finns i [Anslut att Microsoft 365 med PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Gå till [Microsoft Online Services Sign-In assistenten för IT-proffs RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)och välj Ladda   ned för Microsoft Online Services –  **inloggningsassistent.**

2. Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:

    1. Öppna PowerShell-kommandotolken på administratörsnivå.

    2. Kör `Install-Module MSOnline` kommandot.

    3. Om du uppmanas att installera NuGet-leverantör skriver du Y och trycker på RETUR.

    4. Om du uppmanas att installera modulen från PSGGallery, skriver du Y och trycker på RETUR.

    5. Stäng PowerShell-kommandofönstret efter installationen.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Steg 2: Anslut din Microsoft 365 prenumeration

1. Kör Windows Azure Active Directory i Windows PowerShell i modulen för Windows PowerShell.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. I dialogrutan Windows PowerShell Begäran om autentiseringsuppgifter anger du användarnamn och lösenord för ditt Microsoft 365 globala administratörskonto och väljer sedan **OK.**

3. Kör följande kommando:

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Steg 3: Kontrollera att du kan köra PowerShell-skript

> [!NOTE]
> Du kan hoppa över det här steget om du redan är konfigurerad för att köra PowerShell-skript.

Om du Get-MsolUserDeviceComplianceStatus.ps1 skriptet måste du aktivera körningen av PowerShell-skript.

1. Välj Start Windows skrivbordet **och** skriv sedan texten Windows PowerShell. Högerklicka på Windows PowerShell välj sedan **Kör som administratör.**

2. Kör följande kommando:

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. När du uppmanas till det skriver du Y och trycker på Retur.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Kör cmdleten Get-MsolDevice-cmdleten för att visa information om alla enheter i organisationen

1. Öppna Microsoft Azure Active Directory för Windows PowerShell.

2. Kör följande kommando:

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Fler exempel finns i  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)

## <a name="run-a-script-to-get-device-details"></a>Köra ett skript för att få enhetsinformation

Börja med att spara skriptet på datorn.

1. Kopiera och klistra in följande text i Anteckningar.

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

2. Spara den som Windows PowerShell skriptfil med filtillägget .ps1; till exempel Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Kör skriptet för att hämta enhetsinformation för ett enskilt användarkonto

1. Öppna Microsoft Azure Active Directory för Windows PowerShell.

2. Gå till mappen där du sparade skriptet. Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Kör följande kommando för att identifiera den användare du vill hämta enhetsinformation för. I det här exemplet får du information bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Kör följande kommando för att starta skriptet.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Informationen exporteras till ditt Windows som en CSV-fil. Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Kör skriptet för att hämta enhetsinformation för en grupp användare

1. Öppna Microsoft Azure Active Directory för Windows PowerShell.

2. Gå till mappen där du sparade skriptet. Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Kör följande kommando för att identifiera den grupp du vill hämta enhetsinformation för. Det här exemplet hämtar information för användare i gruppen Ekonomiavdelning.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Kör följande kommando för att starta skriptet.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

Informationen exporteras till ditt Windows som en CSV-fil. Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft Anslut har tagits ur bruk](/collaborate/connect-redirect)

[Översikt över grundläggande Mobility and Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
