---
title: Ta bort Microsoft 365-licenser från användar konton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Förklarar hur du använder PowerShell för att ta bort Microsoft 365-licenser som tidigare tilldelats till användare.
ms.openlocfilehash: 7651f300dbf7a57ce163096d500401365e624663
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235460"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Ta bort Microsoft 365-licenser från användar konton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

>[!Note]
>[Lär dig hur du tar bort licenser från användar konton](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) med Microsoft 365 Admin Center. En lista över ytterligare resurser finns i [Hantera användare och grupper](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Sedan visar du licens abonnemang för klient organisationen med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sedan hämtar du inloggnings namnet för det konto som du vill ta bort en licens för, även kallat UPN-namnet.

Ange slutligen användar namn för inloggning och licens plan för att ta bort tecknen "<" och ">" och kör dessa kommandon.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Om du vill ta bort alla licenser för ett visst användar konto anger du användarens inloggnings namn, tar bort tecknen "<" och ">" och kör dessa kommandon.

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
   
Information om hur du visar**AccountSkuID**-informationen i organisationen finns i följande avsnitt:
    
  - [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Visa information om konto licenser och tjänster med PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Om du använder cmdleten **Get-MsolUser** utan att använda parametern _-all_ returneras bara de första 500-kontona.
    
### <a name="removing-licenses-from-user-accounts"></a>Ta bort licenser från användar konton

Om du vill ta bort licenser från ett befintligt användar konto använder du följande syntax:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

I det här exemplet tas licensen **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) bort från användar kontot BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>Du kan inte använda `Set-MsolUserLicense` cmdleten för att koppla bort användare från *avbrutna* licenser. Du måste göra detta individuellt för varje användar konto i Microsoft 365 Admin Center.
>

Använd någon av följande metoder för att ta bort alla licenser från en grupp med befintliga licensierade användare:
  
- **Filtrera konton baserat på ett befintligt konto-attribut** Använd följande syntax:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

I det här exemplet tas alla licenser bort från alla användar konton i USA.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Använda en lista över specifika konton för en viss licens** Gör så här:
    
1. Skapa och spara en textfil som innehåller ett konto på varje rad, så här:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. Använd följande syntax:
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
I det här exemplet tas licensen för **licens planen litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) bort från användar kontona i text filen c:\Mina Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Använd följande syntax för att ta bort alla licenser från alla befintliga användar konton:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Ett annat sätt att frigöra en licens är genom att ta bort användar kontot. Mer information finns i [ta bort och återställa användar konton med PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).
  
## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)

