---
title: Ta Microsoft 365 licenser från användarkonton med PowerShell
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
description: Här förklaras hur du använder PowerShell Microsoft 365 bort licenser som tidigare har tilldelats till användare.
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920674"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Ta Microsoft 365 licenser från användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

>[!Note]
>[Läs om hur du tar bort licenser från](../admin/manage/remove-licenses-from-users.md) användarkonton Microsoft 365 administrationscentret. En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Lista sedan licensplaner för din klientorganisation med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Hämta sedan inloggningsnamnet för det konto för vilket du vill ta bort en licens, även kallat användarens huvudnamn (UPN).

Slutligen anger du namnen på användarens inloggnings- och licensabonnemang, tar bort tecknen "<" och ">" och kör dessa kommandon.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Om du vill ta bort alla licenser för ett specifikt användarkonto anger du användarens inloggningsnamn, tar bort tecknen "<" och ">" och kör kommandona.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
   
Information om hur du visar **licensplanen (AccountSkuID)** i organisationen finns i följande avsnitt:
    
  - [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Visa kontolicens och tjänstinformation med PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Om du använder **cmdlet:en Get-MsolUser** utan att använda parametern _-All_ returneras bara de första 500 kontona.
    
### <a name="removing-licenses-from-user-accounts"></a>Ta bort licenser från användarkonton

Om du vill ta bort licenser från ett befintligt användarkonto ska du använda följande syntax:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

I det här exemplet tas **licensen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) bort från användarkontot BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>Du kan inte använda `Set-MsolUserLicense` cmdleten för att ta bort licenser för användare *som inte tilldelats.* Du måste göra det var för sig för varje användarkonto Microsoft 365 administrationscentret.
>

Om du vill ta bort alla licenser från en grupp befintliga licensierade användare använder du någon av följande metoder:
  
- **Filtrera kontona baserat på ett befintligt kontoattribut** Det gör du genom att använda följande syntax:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

I det här exemplet tas alla licenser bort från alla användarkonton i försäljningsavdelningen i USA.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Använda en lista med specifika konton för en viss licens** Gör så här:
    
1. Skapa och spara en textfil som innehåller ett konto på varje rad så här:
    
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
I det här exemplet tas **licensen litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) bort från de användarkonton som är definierade i textfilen C:\My Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Om du vill ta bort alla licenser från alla befintliga användarkonton använder du följande syntax:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Ett annat sätt att frigöra en licens är att ta bort användarkontot. Mer information finns i Ta [bort och återställa användarkonton med PowerShell.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
  
## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)