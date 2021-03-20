---
title: Tilldela Microsoft 365-licenser till användarkonton med PowerShell
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
description: I den här artikeln lär du dig hur du använder PowerShell för att tilldela en Microsoft 365-licens till olicensierade användare.
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905470"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Tilldela Microsoft 365-licenser till användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Användare kan inte använda några Microsoft 365-tjänster förrän deras konto har tilldelats en licens från en licensplan. Du kan använda PowerShell för att snabbt tilldela licenser till olicensierade konton. 

Användarkonton måste först tilldelas en plats. Att ange en plats är en nödvändig del av att skapa ett nytt användarkonto i administrationscentret för [Microsoft 365.](../admin/add-users/add-users.md) 

Konton som synkroniseras från din lokala Active Directory Domain Services har inte en angiven plats som standard. Du kan konfigurera en plats för dessa konton från:

- Administrationscentret för Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - [Azure-portalen](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **(Active**  >  **Directory-användare >** användarkonto > **land** eller region med  >    >  **profilkontaktinformation).**

>[!Note]
>[Läs om hur du tilldelar licenser till användarkonton](../admin/manage/assign-licenses-to-users.md) i administrationscentret för Microsoft 365. En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph-modulen

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Lista sedan licensplaner för din klientorganisation med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Hämta sedan inloggningsnamnet för det konto som du vill lägga till en licens för, även kallat användarens huvudnamn (UPN).

Kontrollera sedan att användarkontot har en tilldelad användningsplats.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Om det inte finns någon tilldelad användningsplats kan du tilldela ett med följande kommandon:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Slutligen anger du användarens inloggningsnamn och licensplansnamn och kör kommandona.

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

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Kör kommandot `Get-MsolAccountSku` för att visa tillgängliga licensabonnemang och antalet tillgängliga licenser i varje abonnemang i organisationen. Antalet tillgängliga licenser i varje abonnemang är **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits.** Mer information om licensplaner, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

Kör det här kommandot för att hitta olicensierade konton i organisationen.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Du kan bara tilldela licenser till användarkonton som har egenskapen **UsageLocation** inställd på en giltig landskod i ISO 3166-1 alfa-2. Till exempel USA för USA och FR för Frankrike. Vissa Microsoft 365-tjänster är inte tillgängliga i vissa länder. Mer information finns i [Om licensbegränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Om du vill hitta konton som inte har ett **UsageLocation-värde** kör du det här kommandot.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Kör det här **kommandot om** du vill ange värdet Användningsbeläggning för ett konto.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Ett exempel:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Om du använder **cmdlet:en Get-MsolUser** utan att använda parametern **-All** returneras bara de första 500 kontona.

### <a name="assigning-licenses-to-user-accounts"></a>Tilldela licenser till användarkonton
    
Om du vill tilldela en licens till en användare använder du följande kommando i PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

I det här exemplet tilldelas en licens från licensplanen **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise, E3) till den olicensierade **användaren belindan \@ litwareinc.com:**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Kör det här kommandot om du vill tilldela en licens till alla olicensierade användare.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Du kan inte tilldela flera licenser till en användare från samma licensplan. Om du inte har tillräckligt många tillgängliga licenser tilldelas licenserna till användare i den ordning som de returneras av **cmdlet:en Get-MsolUser** tills de tillgängliga licenserna tar slut.
>

I det här exemplet tilldelas licenser från **licensplanen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise, E3) till alla olicensierade användare:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

I det här exemplet tilldelas samma licenser till olicensierade användare i försäljningsavdelningen i USA:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Flytta en användare till en annan prenumeration (licensplan) med Azure Active Directory PowerShell för Graph-modulen

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Hämta sedan inloggningsnamnet för användarkontot som du vill byta prenumeration för, det vill säga användarens huvudnamn (UPN).

Lista sedan prenumerationerna (licensabonnemangen) för din klientorganisation med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Lista sedan de prenumerationer som användarkontot för närvarande har med dessa kommandon.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifiera prenumerationen som användaren har för närvarande (FROM-prenumerationen) och den prenumeration som användaren flyttar till (TO-prenumerationen).

Slutligen anger du TILL- och FROM-prenumerationsnamn (SKU-artikelnummer) och kör de här kommandona.

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

Du kan verifiera ändringen i prenumerationen för användarkontot med dessa kommandon.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Se även

[Hantera användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)