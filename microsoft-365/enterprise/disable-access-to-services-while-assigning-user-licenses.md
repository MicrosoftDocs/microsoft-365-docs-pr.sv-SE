---
title: Inaktivera åtkomst till Microsoft 365 när du tilldelar användarlicenser
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
description: Läs om hur du tilldelar licenser till användarkonton och inaktiverar specifika tjänstplaner samtidigt med hjälp av PowerShell för Microsoft 365.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228909"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Inaktivera åtkomst till Microsoft 365 när du tilldelar användarlicenser

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft 365-prenumerationer följer med tjänstplaner för enskilda tjänster. Microsoft 365 administratörer måste ofta inaktivera vissa abonnemang när de tilldelar licenser till användare. Med hjälp av anvisningarna i den här artikeln kan du tilldela en Microsoft 365 licens samtidigt som du inaktiverar specifika tjänstplaner med hjälp av PowerShell för ett enskilt användarkonto eller flera användarkonton.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph modul

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)


Lista sedan licensplaner för din klientorganisation med det här kommandot.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Hämta sedan inloggningsnamnet för det konto som du vill lägga till en licens för, även kallat användarens huvudnamn (UPN).

Sammanställ sedan en lista med tjänster som du kan aktivera. En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

För kommandoblocket nedan fyller du i användarkontons huvudnamn, SKU-delens nummer och listan över tjänstplaner för att aktivera och ta bort den förklarande texten och \< and > tecknen. Kör sedan resulterande kommandon i PowerShell-kommandotolken.

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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory för Windows PowerShell

Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Kör sedan det här kommandot för att se dina aktuella prenumerationer:

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet. Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.
>

I visningen av  `Get-MsolAccountSku` kommandot:

- **AccountSkuId** är en prenumeration för din organisation i \<OrganizationName> : \<Subscription> format. Det \<OrganizationName> är det värde som du angav när du registrerade dig i Microsoft 365, och är unikt för din organisation. Värdet \<Subscription> är för en viss prenumeration. För litwareinc:ENTERPRISEPACK är till exempel organisationsnamnet litwareinc och prenumerationsnamnet ENTERPRISEPACK (Office 365 Enterprise E3).

- **ActiveUnits** är antalet licenser som du har köpt för prenumerationen.

- **WarningUnits** är antalet licenser i en prenumeration som du inte har förnyat och som upphör efter respitperioden på 30 dagar.

- **ConsumedUnits** är antalet licenser som du har tilldelat användare för prenumerationen.

Observera AccountSkuId för din Microsoft 365-prenumeration som innehåller de användare du vill licensiera. Se också till att det finns tillräckligt med licenser att tilldela (subtrahera **ConsumedUnits** från **ActiveUnits).**

Kör sedan det här kommandot för att visa information om Microsoft 365 tjänstplaner som är tillgängliga i alla dina prenumerationer:

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

På skärmen för det här kommandot kan du bestämma vilka tjänstplaner du vill inaktivera när du tilldelar licenser till användare.

Här är en delvis lista över tjänstplaner och deras motsvarande Microsoft 365 tjänster.

I följande tabell visas Microsoft 365 tjänstplaner och deras eget namn för de vanligaste tjänsterna. Listan med tjänstplaner kan se annorlunda ut.

|**Serviceplan**|**Beskrivning**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365-appar för företag *(kallades tidigare Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype för företag – Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online-abonnemang 2  <br/> |

En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

Nu när du har AccountSkuId och tjänstplanerna som ska inaktiveras kan du tilldela licenser för en enskild användare eller för flera användare.

### <a name="for-a-single-user"></a>För en enskild användare

För en enskild användare fyller du i användarkontons huvudnamn, AccountSkuId och listan över tjänstplaner för att inaktivera och ta bort den förklarande texten och \< and > tecknen. Kör sedan resulterande kommandon i PowerShell-kommandotolken.

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Här är ett exempel på ett kommandoblock för kontot belindan@contoso.com, för contoso:ENTERPRISEPACK-licensen och för tjänstplaner som inaktiveras är RMS_S_ENTERPRISE, SWAY, INTUNE_O365 och YAMMER_ENTERPRISE:

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

Om du vill utföra den här administrationsuppgiften för flera användare skapar du en fil med kommaavgränsade värden (CSV) som innehåller fälten UserPrincipalName och UsageLocation. Här är ett exempel:

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Fyll sedan i platsen för CSV-indata- och utdatafilerna, kontots SKU-ID och listan över tjänstplaner som du vill inaktivera och kör sedan resulterande kommandon i PowerShell-kommandotolken.

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

Det här PowerShell-kommandoblocket:

- Visar användarens huvudnamn.

- Tilldelar anpassade licenser till varje användare.

- Skapar en CSV-fil med alla användare som har bearbetats och visar deras licensstatus.

## <a name="see-also"></a>Se även

[Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)

[Inaktivera åtkomst till Sway med PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)