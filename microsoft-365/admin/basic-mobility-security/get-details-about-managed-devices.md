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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Få information om grundläggande mobilitet och hanterade enheter

I den här artikeln lär du dig hur du använder Windows PowerShell för att få information om de enheter i organisationen som du skapar för grundläggande mobilitet och säkerhet.

Här är en uppdelning av enhets uppgifterna som är tillgängliga för dig.

|**Beskrivning**|**Vad du kan söka efter i PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|Enheten är registrerad i grundläggande mobilitet och säkerhet. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md)|Värdet för parametern *isManaged*   är:<br/>**True**= enheten är registrerad.<br/>**False**= enheten är inte registrerad. |
|Enheten är kompatibel med din enhets säkerhets principer. Mer information finns i [skapa säkerhets principer för enheter](create-device-security-policies.md)|Värdet för parametern *isCompliant*   är:<br/>**Sant**   = enheten är kompatibel med principer.<br/>**Falskt**   = enheten är inte kompatibel med principer.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Grundläggande PowerShell-parametrar för mobilitet och säkerhet":::

>[!NOTE]
>Kommandona och skripten i den här artikeln returnerar också information om vilka enheter som hanteras av [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Innan du börjar

Det finns några saker du måste ställa in för att köra de kommandon och skript som beskrivs i den här artikeln.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Steg 1: Ladda ned och installera Azure Active Directory-modulen för Windows PowerShell

Mer information om de här stegen finns i [ansluta till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Gå till [Microsoft Online services Sign-In Assistant för IT-experter RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   och välj  **Hämta för Microsoft Online Services-inloggnings assistent**.   

2. Installera Microsoft Azure Active Directory-modulen för Windows PowerShell genom att följa de här stegen:

    1. Öppna en kommando tolk för PowerShell på administratörs nivå.  

    2. Kör kommandot Installera-modul MSOnline.

    3. Om du uppmanas att installera NuGet-leverantör skriver du Y och trycker på RETUR.

    4. Om du uppmanas att installera modulen från PSGGallery, skriver du Y och trycker på RETUR.

    5. När installationen är slutförd stänger du PowerShell-Kommandotolken.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Steg 2: Anslut till din Microsoft 365-prenumeration

1. Kör följande kommando i Windows Azure Active Directory-modulen för Windows PowerShell.  

    $UserCredential = Get-Credential

2. I dialog rutan begäran om autentiseringsuppgifter för Windows PowerShell anger du användar namn och lösen ord för ditt Microsoft 365-globala administratörs konto och väljer sedan **OK**.

3. Kör följande kommando.

    Connect-MsolService-autentiseringsuppgifter $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Steg 3: kontrol lera att du kan köra PowerShell-skript

>[!NOTE]
>Du kan hoppa över det här steget om du redan har konfigurerat för att köra PowerShell-skript.

Om du vill köra det Get-MsolUserDeviceComplianceStatus.ps1 skriptet måste du aktivera körningen av PowerShell-skript.

1. I Skriv bords versionen av Windows väljer du **Start** och skriver sedan Windows PowerShell. Högerklicka på Windows PowerShell och välj **Kör som administratör**.

2. Kör följande kommando.

    Set-ExecutionPolicy RemoteSigned

3. Skriv Y när du uppmanas till det och tryck sedan på RETUR.

**Kör cmdleten Get-MsolDevice för att visa information för alla enheter i organisationen**

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.  

2. Kör följande kommando.

    Get-MsolDevice-all-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. count-gt 0}

Fler exempel finns i  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Köra ett skript för att få enhets information

Spara först skriptet till datorn.

1. Kopiera och klistra in följande text i anteckningar.  

2.  parametrar

3.  [PSObject []] $users = @ (),

4.  [Växel] $export

5.  [Sträng] $exportFileName = "UserDeviceComplianceStatus_" + (Hämta-datum-format "yyMMdd_HHMMss") + ". csv",

6.  [Sträng] $exportPath = [miljö]:: GetFolderPath ("Skriv bord")

7.  )

9.  [System. Collection. IDictionary] $script: schema = @ {

11.  DeviceId = ' '

12.  DeviceOSType = ' '

13.  DeviceOSVersion = ' '

14.  DeviceTrustLevel = ' '

15.  DisplayName = ' '

16.  IsCompliant = ' '

17.  IsManaged = ' '

18.  ApproximateLastLogonTimestamp = ' '

19.  DeviceObjectId = ' '

20.  RegisteredOwnerUpn = ' '

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  funktionen createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-egenskap $script: schema
    

30.  returnera $resultObject
    

31.  }
    

33.  Om ($users. Count-EQ 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = ($u i $users)
    

39.  {
    

41.  [PSObject] $devices = get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  $d i $devices
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged
    

52.  $deviceResult. DeviceObjectId = $d. ObjectId
    

53.  $deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  Om ($export)
    

64.  {
    

65.  $result | Export-Csv-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Person
    

68.  {
    

69.  $result
    

70.  }
    

71.  Spara den som en Windows PowerShell-skriptfil genom att använda fil namns tillägget. ps1; till exempel Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Kör skriptet för att hämta enhets information för ett enskilt användar konto

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.
    
2. Gå till mappen där du sparade skriptet. Om du till exempel sparade den på C:\PS-Scripts kör du följande kommando.
    
    CD-C:\PS-Scripts

3. Kör följande kommando för att identifiera den användare som du vill hämta enhets information för. Det här exemplet får information om bar@example.com.
    
    $u = Get-MsolUser-UserPrincipalName bar@example.com

4. Kör följande kommando för att starta skriptet.

    .\Get-MsolUserDeviceComplianceStatus.ps1-användare $u-exportera

Informationen exporteras till Windows-skrivbordet som en CSV-fil. Du kan använda ytterligare parametrar för att ange fil namnet och sökvägen för CSV-filen.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Köra skriptet för att hämta enhets information för en grupp användare

1. Öppna Microsoft Azure Active Directory-modulen för Windows PowerShell.
    
2. Gå till mappen där du sparade skriptet. Om du till exempel sparade den på C:\PS-Scripts kör du följande kommando.   

    CD-C:\PS-Scripts

3. Kör följande kommando för att identifiera gruppen som du vill hämta enhets information för. I det här exemplet får du information om användare i gruppen FinanceStaff. 

    $u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. Tillägg

4. Kör följande kommando för att starta skriptet.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-användare $u-exportera

Informationen exporteras till Windows-skrivbordet som en CSV-fil. Du kan använda ytterligare parametrar för att ange fil namnet och sökvägen för CSV-filen.

## <a name="related-topics"></a>Relaterade ämnen

[Microsoft Connect har avbrutits](https://docs.microsoft.com/collaborate/connect-redirect)

[Översikt över grundläggande Mobility and Security](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)