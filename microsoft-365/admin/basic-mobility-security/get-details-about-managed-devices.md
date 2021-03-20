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
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904258"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Få information om hanterade enheter för enkel rörlighet och säkerhet

Den här artikeln visar hur du använder Windows PowerShell för att få information om de enheter i din organisation som du konfigurerade för grundläggande rörlighet och säkerhet.

Här är en sammanfattning av den enhetsinformation som är tillgänglig för dig.

|**Beskrivning**|**Vad du ska leta efter i PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Enheten är registrerad i Basic Mobility and Security. Mer information finns i [Registrera din mobila enhet med basic mobility and security](enroll-your-mobile-device.md)|Värdet för *parametern isManaged*   är:<br/>**True**= enheten är registrerad.<br/>**False**= device is notrolled. |
|Enheten följer enhetens säkerhetsprinciper. Mer information finns i Skapa [säkerhetsprinciper för enheter](create-device-security-policies.md)|Värdet för *parametern isComp parameter*   är:<br/>**True**   = enheten följer principer.<br/>**False**   = enheten följer inte principerna.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="PowerShell-parametrarna Basic Mobility and Security":::

>[!NOTE]
>Kommandona och skripten i den här artikeln returnerar också information om enheter som hanteras av [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Innan du börjar

Det finns några saker du behöver konfigurera för att köra de kommandon och skript som beskrivs i den här artikeln.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Steg 1: Ladda ned och installera Azure Active Directory-modulen för Windows PowerShell

Mer information om de här instruktionerna finns i [Ansluta till Microsoft 365 med PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Gå till [Microsoft Online Services Sign-In assistenten för IT-proffs RTWl](https://www.microsoft.com/download/details.aspx?id=41950)och välj Ladda   ned för Microsoft Online Services –  **inloggningsassistent.**

2. Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:

    1. Öppna PowerShell-kommandotolken på administratörsnivå.  

    2. Kör kommandot Installera-modul MSOnline.

    3. Om du uppmanas att installera NuGet-leverantör skriver du Y och trycker på RETUR.

    4. Om du uppmanas att installera modulen från PSGGallery, skriver du Y och trycker på RETUR.

    5. Stäng PowerShell-kommandofönstret efter installationen.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Steg 2: Anslut till din Microsoft 365-prenumeration

1. Kör följande kommando i Windows Azure Active Directory-modulen för Windows PowerShell.  

    $UserCredential = Get-Credential

2. I dialogrutan Begäran om autentiseringsuppgifter för Windows PowerShell anger du användarnamn och lösenord för ditt globala administratörskonto för Microsoft 365 och väljer sedan **OK.**

3. Kör följande kommando.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Steg 3: Kontrollera att du kan köra PowerShell-skript

>[!NOTE]
>Du kan hoppa över det här steget om du redan är konfigurerad för att köra PowerShell-skript.

Om du Get-MsolUserDeviceComplianceStatus.ps1 skriptet måste du aktivera körningen av PowerShell-skript.

1. Välj Start på skrivbordet i **Windows** och skriv sedan Windows PowerShell. Högerklicka på Windows PowerShell och välj sedan **Kör som administratör.**

2. Kör följande kommando.

    Set-ExecutionPolicy RemoteSigned

3. När du uppmanas till det skriver du Y och trycker på Retur.

**Kör cmdleten Get-MsolDevice-cmdleten för att visa information om alla enheter i organisationen**

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.  

2. Kör följande kommando.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Fler exempel finns i  [Get-MsolDevice.](https://go.microsoft.com/fwlink/?linkid=2157939)

## <a name="run-a-script-to-get-device-details"></a>Köra ett skript för att få enhetsinformation

Börja med att spara skriptet på datorn.

1. Kopiera och klistra in följande text i Anteckningar.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [Sträng]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliet = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  returnera $resultObject
    

31.  }
    

33.  Om ($users. Antal -ekv 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u i $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d i $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsComp scriptt = $d.GraphDeviceObject.IsComp scriptt
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  Om ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Spara den som en Windows PowerShell-skriptfil med filtillägget PS1. till exempel Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Kör skriptet för att hämta enhetsinformation för ett enskilt användarkonto

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.
    
2. Gå till mappen där du sparade skriptet. Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.
    
    cd C:\PS-Scripts

3. Kör följande kommando för att identifiera den användare du vill hämta enhetsinformation för. I det här exemplet får du information bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Kör följande kommando för att starta skriptet.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Informationen exporteras till Windows-skrivbordet som en CSV-fil. Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Kör skriptet för att hämta enhetsinformation för en grupp användare

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.
    
2. Gå till mappen där du sparade skriptet. Om du till exempel sparade det i C:\PS-Scripts kör du följande kommando.   

    cd C:\PS-Scripts

3. Kör följande kommando för att identifiera den grupp du vill hämta enhetsinformation för. Det här exemplet hämtar information för användare i gruppen Ekonomiavdelning. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Kör följande kommando för att starta skriptet.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

Informationen exporteras till Windows-skrivbordet som en CSV-fil. Du kan använda ytterligare parametrar för att ange CSV-filens namn och sökväg.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft Connect har tagits bort](/collaborate/connect-redirect)

[Översikt över grundläggande Mobility and Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)