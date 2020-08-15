---
title: Inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Lär dig hur du tilldelar licenser till användar konton och inaktiverar specifika Service planer samtidigt med PowerShell för Microsoft 365.
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694540"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365-abonnemang innehåller tjänste abonnemang för enskilda tjänster. Microsoft 365-administratörer behöver ofta inaktivera vissa abonnemang när de tilldelar användare licenser. Med instruktionerna i den här artikeln kan du tilldela en Microsoft 365-licens när du inaktiverar specifika tjänste abonnemang med PowerShell för ett enskilt användar konto eller flera användar konton.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för diagramvyn

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Sedan visar du licens abonnemang för klient organisationen med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Sedan hämtar du inloggnings namnet för det konto som du vill lägga till en licens för och det kallas även användarens huvud namn (UPN).

Sedan kompilerar du en lista över tjänster att aktivera. En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

För kommando blocket nedan fyller du i användar kontots huvud namn, SKU-delen och listan över tjänste planer för att aktivera och ta bort för klar ande text och \< and > tecken. Kör sedan de resulterande kommandona i PowerShell-Kommandotolken.
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Kör sedan det här kommandot för att se dina nuvarande abonnemang:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** . För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.
>

I visningen av  `Get-MsolAccountSku` kommandot:
  
- **AccountSkuId** är ett abonnemang för din organisation i \<OrganizationName> : \<Subscription> format. Det \<OrganizationName> är det värde som du angav när du registrerade dig i Microsoft 365 och det är unikt för organisationen. \<Subscription>Värdet är för en specifik prenumeration. Till exempel för licens planen litwareinc: ENTERPRISEPACK, organisations namnet är licens planen litwareinc och prenumerations namnet är ENTERPRISEPACK (Office 365 Enterprise E3).
    
- **ActiveUnits** är antalet licenser som du har köpt för abonnemanget.
    
- **WarningUnits** är antalet licenser i en prenumeration som du inte har förnyat och som upphör efter 30 dagar.
    
- **ConsumedUnits** är antalet licenser som du har tilldelat användare för abonnemanget.
    
Notera AccountSkuId för din Microsoft 365-prenumeration som innehåller de användare du vill licensiera. Se också till att det finns tillräckligt många licenser att tilldela (subtrahera **ConsumedUnits** från **ActiveUnits** ).
  
Kör sedan det här kommandot för att visa information om de Microsoft 365-tjänste abonnemang som är tillgängliga i alla dina abonnemang:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

I visningen av det här kommandot kan du bestämma vilka tjänste abonnemang du vill inaktivera när du tilldelar användare licenser.
  
Här är en del av en lista över tjänste abonnemang och deras motsvarande Microsoft 365-tjänster.

I följande tabell visas Microsoft 365-tjänstens abonnemang och deras egna namn för de vanligaste tjänsterna. Din lista över tjänste abonnemang kan skilja sig från varandra. 
  
|**Service plan**|**Beskrivning**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-appar för företag *(tidigare kallat Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype för företag – Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online-abonnemang 2  <br/> |
   
En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
   
Nu när du har AccountSkuId och tjänste abonnemangen för att inaktivera kan du tilldela licenser för enskilda användare eller för flera användare.
  
### <a name="for-a-single-user"></a>För en enskild användare

För en enskild användare fyller du i användarens huvud namn, AccountSkuId och listan över tjänste planer för att inaktivera och ta bort den för klar ande texten och \< and > tecknen. Kör sedan de resulterande kommandona i PowerShell-Kommandotolken.
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Här är ett exempel på ett kommando block för kontot som heter belindan@contoso.com, för avtalet contoso: ENTERPRISEPACK och tjänste abonnemangen för att inaktivera är RMS_S_ENTERPRISE, SWAY, INTUNE_O365 och YAMMER_ENTERPRISE:
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>För flera användare

Om du vill utföra den här administrationen för flera användare kan du skapa en CSV-textfil som innehåller fälten UserPrincipalName och UsageLocation. Här är ett exempel:
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Fyll sedan i placeringen av CSV-filer för in-och utdata, konto-SKU-ID: t och listan över tjänst planer att inaktivera och kör sedan de resulterande kommandona i PowerShell-Kommandotolken.
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Det här PowerShell-kommando blocket:
  
- Visar användarens huvud namn för varje användare.
    
- Tilldelar alla användare egna licenser.
    
- Skapar en CSV-fil med alla användare som har bearbetats och visar deras licens status.
    
## <a name="see-also"></a>Se även

[Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)
  
[Inaktivera åtkomst till Sway med PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
