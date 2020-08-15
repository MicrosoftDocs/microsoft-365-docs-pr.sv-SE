---
title: Visa Microsoft 365-konto och tjänste uppgifter med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Förklarar hur du använder PowerShell för att kontrol lera vilka Microsoft 365-tjänster som har tilldelats till användarna.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694911"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>Visa Microsoft 365-konto och tjänste uppgifter med PowerShell

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

I Microsoft 365 ger licenser från licens planer (även kallade SKU: er eller Microsoft 365-abonnemang) åtkomst till de Microsoft 365-tjänster som är definierade för dessa abonnemang. En användare kanske inte har till gång till alla tjänster som är tillgängliga i en licens som är tilldelad till dem. Du kan använda PowerShell för Microsoft 365 för att visa statusen för tjänster på användar konton. 

Mer information om licens planer, licenser och tjänster finns i [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Sedan visar du licens abonnemang för klient organisationen med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Använd dessa kommandon för att lista de tjänster som är tillgängliga i varje licens plan.

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

Använd dessa kommandon för att lista de licenser som har tilldelats ett användar konto.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Kör sedan det här kommandot för att visa vilka licens abonnemang som är tillgängliga i din organisation. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

Kör sedan det här kommandot för att lista de tjänster som är tillgängliga i varje telefon plan och i vilken ordning de visas (index numret).

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
Använd det här kommandot för att lista de licenser som har tilldelats till en användare, och i vilken ordning de visas (index numret).

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>Visa tjänster för ett användar konto

Om du vill visa alla Microsoft 365-tjänster som en användare har till gång till använder du följande syntax:
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

I det här exemplet visas de tjänster som användaren BelindaN@litwareinc.com har åtkomst till. Då visas de tjänster som är kopplade till alla licenser som har tilldelats hennes konto.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

I det här exemplet visas de tjänster som användaren BelindaN@litwareinc.com har åtkomst till från den första licens som tilldelats henne (index numret är 0).
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

Om du vill visa alla tjänster för en användare som har tilldelats *flera licenser*använder du följande syntax:

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Komma igång med PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)
