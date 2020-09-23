---
title: Tilldela Microsoft 365-licenser till användar konton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: I den här artikeln lär du dig hur du använder PowerShell till att tilldela en Microsoft 365-licens till olicensierade användare.
ms.openlocfilehash: f042f8109bf9ac9b634bc66509c60a5181fb1af6
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235624"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Tilldela Microsoft 365-licenser till användar konton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Användare kan inte använda några Microsoft 365-tjänster förrän deras konto har tilldelats en licens från en licens plan. Du kan använda PowerShell för att snabbt tilldela licenser till olicensierade konton. 

>[!Note]
>Användar konton måste tilldelas en plats. Du kan göra detta från egenskaperna för ett användar konto i Microsoft 365 Admin Center eller från PowerShell.
>

>[!Note]
>[Lär dig hur du tilldelar licenser till användar konton](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) med Microsoft 365 Admin Center. En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Sedan visar du licens abonnemang för klient organisationen med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sedan hämtar du inloggnings namnet för det konto som du vill lägga till en licens för och det kallas även användarens huvud namn (UPN).

Se sedan till att användar kontot har tilldelats en användnings plats.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Om det inte finns någon användnings plats kan du tilldela en med dessa kommandon:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Ange slutligen användar inloggnings namn och namn på en licens och kör dessa kommandon.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Kör `Get-MsolAccountSku` kommandot för att visa tillgängliga licens planer och antalet tillgängliga licenser för varje plan i organisationen. Antalet tillgängliga licenser för varje abonnemang är **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Mer information om licens planer, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

Kör det här kommandot för att hitta de olicensierade kontona i organisationen.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Du kan bara tilldela licenser till användar konton som har egenskapen **UsageLocation** inställd på en giltig ISO 3166-1 alpha-2-landskod. Till exempel för USA och FR för Frankrike. Vissa Microsoft 365-tjänster är inte tillgängliga i vissa länder. Mer information finns i [om licens begränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Kör det här kommandot för att hitta konton som inte har något **UsageLocation** -värde.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Om du vill ange **UsageLocation** -värdet för ett konto kör du det här kommandot.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Till exempel:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Om du använder cmdleten **Get-MsolUser** utan att använda parametern **-all** returneras bara de första 500-kontona.

### <a name="assigning-licenses-to-user-accounts"></a>Tilldela licenser till användar konton
    
Om du vill tilldela en licens till en användare använder du följande kommando i PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

I det här exemplet tilldelas en licens från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3)-licens plan till den olicensierade användaren ** \@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Om du vill tilldela en licens till alla olicensierade användare kör du det här kommandot.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Du kan inte tilldela flera licenser till en användare från samma licens plan. Om du inte har tillräckligt med licenser är de tilldelade till användarna i den ordning som de returneras av cmdleten **Get-MsolUser** tills de tillgängliga licenserna tar slut.
>

I det här exemplet tilldelas licenser från **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) till alla olicensierade användare:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

I det här exemplet tilldelas dessa licenser till olicensierade användare på försäljnings avdelningen i USA:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Flytta en användare till ett annat abonnemang (licens plan) med Azure Active Directory PowerShell för Graph

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Sedan hämtar du inloggnings namnet för det användar konto som du vill byta abonnemang för och det kallas även användarens huvud namn (UPN).

Sedan visar du abonnemangen (licens planerna) för klient organisationen med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sedan visar du de abonnemang som användar kontot för närvarande har med dessa kommandon.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifiera den prenumeration som användaren för närvarande har (från-prenumerationen) och det abonnemang som användaren flyttar (till-abonnemanget).

Ange slutligen till och från prenumerations namnen (SKU-artikelnummer) och kör dessa kommandon.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

Du kan kontrol lera prenumerationens ändring för användar kontot med dessa kommandon.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Se även

[Hantera användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
