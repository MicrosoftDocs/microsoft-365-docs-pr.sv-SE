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
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="6890b-103">Inaktivera åtkomst till Microsoft 365 när du tilldelar användarlicenser</span><span class="sxs-lookup"><span data-stu-id="6890b-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="6890b-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6890b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6890b-105">Microsoft 365-prenumerationer följer med tjänstplaner för enskilda tjänster.</span><span class="sxs-lookup"><span data-stu-id="6890b-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="6890b-106">Microsoft 365 administratörer måste ofta inaktivera vissa abonnemang när de tilldelar licenser till användare.</span><span class="sxs-lookup"><span data-stu-id="6890b-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="6890b-107">Med hjälp av anvisningarna i den här artikeln kan du tilldela en Microsoft 365 licens samtidigt som du inaktiverar specifika tjänstplaner med hjälp av PowerShell för ett enskilt användarkonto eller flera användarkonton.</span><span class="sxs-lookup"><span data-stu-id="6890b-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6890b-108">Använda Azure Active Directory PowerShell för Graph modul</span><span class="sxs-lookup"><span data-stu-id="6890b-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6890b-109">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6890b-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>


<span data-ttu-id="6890b-110">Lista sedan licensplaner för din klientorganisation med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="6890b-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6890b-111">Hämta sedan inloggningsnamnet för det konto som du vill lägga till en licens för, även kallat användarens huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="6890b-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6890b-112">Sammanställ sedan en lista med tjänster som du kan aktivera.</span><span class="sxs-lookup"><span data-stu-id="6890b-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="6890b-113">En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="6890b-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="6890b-114">För kommandoblocket nedan fyller du i användarkontons huvudnamn, SKU-delens nummer och listan över tjänstplaner för att aktivera och ta bort den förklarande texten och \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="6890b-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="6890b-115">Kör sedan resulterande kommandon i PowerShell-kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="6890b-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>

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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6890b-116">Använda Microsoft Azure Active Directory för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6890b-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6890b-117">Börja med [att ansluta till Microsoft 365 klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="6890b-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="6890b-118">Kör sedan det här kommandot för att se dina aktuella prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="6890b-118">Next, run this command to see your current subscriptions:</span></span>

```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="6890b-119">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="6890b-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6890b-120">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6890b-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6890b-121">I visningen av  `Get-MsolAccountSku` kommandot:</span><span class="sxs-lookup"><span data-stu-id="6890b-121">In the display of the  `Get-MsolAccountSku` command:</span></span>

- <span data-ttu-id="6890b-122">**AccountSkuId** är en prenumeration för din organisation i \<OrganizationName> : \<Subscription> format.</span><span class="sxs-lookup"><span data-stu-id="6890b-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="6890b-123">Det \<OrganizationName> är det värde som du angav när du registrerade dig i Microsoft 365, och är unikt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6890b-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="6890b-124">Värdet \<Subscription> är för en viss prenumeration.</span><span class="sxs-lookup"><span data-stu-id="6890b-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="6890b-125">För litwareinc:ENTERPRISEPACK är till exempel organisationsnamnet litwareinc och prenumerationsnamnet ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="6890b-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>

- <span data-ttu-id="6890b-126">**ActiveUnits** är antalet licenser som du har köpt för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="6890b-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>

- <span data-ttu-id="6890b-127">**WarningUnits** är antalet licenser i en prenumeration som du inte har förnyat och som upphör efter respitperioden på 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="6890b-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>

- <span data-ttu-id="6890b-128">**ConsumedUnits** är antalet licenser som du har tilldelat användare för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="6890b-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>

<span data-ttu-id="6890b-129">Observera AccountSkuId för din Microsoft 365-prenumeration som innehåller de användare du vill licensiera.</span><span class="sxs-lookup"><span data-stu-id="6890b-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="6890b-130">Se också till att det finns tillräckligt med licenser att tilldela (subtrahera **ConsumedUnits** från **ActiveUnits).**</span><span class="sxs-lookup"><span data-stu-id="6890b-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits**).</span></span>

<span data-ttu-id="6890b-131">Kör sedan det här kommandot för att visa information om Microsoft 365 tjänstplaner som är tillgängliga i alla dina prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="6890b-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="6890b-132">På skärmen för det här kommandot kan du bestämma vilka tjänstplaner du vill inaktivera när du tilldelar licenser till användare.</span><span class="sxs-lookup"><span data-stu-id="6890b-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>

<span data-ttu-id="6890b-133">Här är en delvis lista över tjänstplaner och deras motsvarande Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="6890b-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="6890b-134">I följande tabell visas Microsoft 365 tjänstplaner och deras eget namn för de vanligaste tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="6890b-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="6890b-135">Listan med tjänstplaner kan se annorlunda ut.</span><span class="sxs-lookup"><span data-stu-id="6890b-135">Your list of service plans might be different.</span></span>

|<span data-ttu-id="6890b-136">**Serviceplan**</span><span class="sxs-lookup"><span data-stu-id="6890b-136">**Service plan**</span></span>|<span data-ttu-id="6890b-137">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="6890b-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="6890b-138">Sway</span><span class="sxs-lookup"><span data-stu-id="6890b-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="6890b-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6890b-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="6890b-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="6890b-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="6890b-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="6890b-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="6890b-142">Microsoft 365-appar för företag *(kallades tidigare Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="6890b-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="6890b-143">Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="6890b-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="6890b-144">Office</span><span class="sxs-lookup"><span data-stu-id="6890b-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="6890b-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6890b-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="6890b-146">Exchange Online-abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="6890b-146">Exchange Online Plan 2</span></span>  <br/> |

<span data-ttu-id="6890b-147">En fullständig lista över licensplaner (kallas även produktnamn), deras inkluderade tjänstplaner och deras motsvarande eget namn finns i Produktnamn och [tjänstplansidentifierare för licensiering.](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="6890b-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="6890b-148">Nu när du har AccountSkuId och tjänstplanerna som ska inaktiveras kan du tilldela licenser för en enskild användare eller för flera användare.</span><span class="sxs-lookup"><span data-stu-id="6890b-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>

### <a name="for-a-single-user"></a><span data-ttu-id="6890b-149">För en enskild användare</span><span class="sxs-lookup"><span data-stu-id="6890b-149">For a single user</span></span>

<span data-ttu-id="6890b-150">För en enskild användare fyller du i användarkontons huvudnamn, AccountSkuId och listan över tjänstplaner för att inaktivera och ta bort den förklarande texten och \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="6890b-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="6890b-151">Kör sedan resulterande kommandon i PowerShell-kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="6890b-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="6890b-152">Här är ett exempel på ett kommandoblock för kontot belindan@contoso.com, för contoso:ENTERPRISEPACK-licensen och för tjänstplaner som inaktiveras är RMS_S_ENTERPRISE, SWAY, INTUNE_O365 och YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="6890b-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="6890b-153">För flera användare</span><span class="sxs-lookup"><span data-stu-id="6890b-153">For multiple users</span></span>

<span data-ttu-id="6890b-154">Om du vill utföra den här administrationsuppgiften för flera användare skapar du en fil med kommaavgränsade värden (CSV) som innehåller fälten UserPrincipalName och UsageLocation.</span><span class="sxs-lookup"><span data-stu-id="6890b-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="6890b-155">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="6890b-155">Here is an example:</span></span>

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="6890b-156">Fyll sedan i platsen för CSV-indata- och utdatafilerna, kontots SKU-ID och listan över tjänstplaner som du vill inaktivera och kör sedan resulterande kommandon i PowerShell-kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="6890b-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>

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

<span data-ttu-id="6890b-157">Det här PowerShell-kommandoblocket:</span><span class="sxs-lookup"><span data-stu-id="6890b-157">This PowerShell command block:</span></span>

- <span data-ttu-id="6890b-158">Visar användarens huvudnamn.</span><span class="sxs-lookup"><span data-stu-id="6890b-158">Displays the user principal name of each user.</span></span>

- <span data-ttu-id="6890b-159">Tilldelar anpassade licenser till varje användare.</span><span class="sxs-lookup"><span data-stu-id="6890b-159">Assigns customized licenses to each user.</span></span>

- <span data-ttu-id="6890b-160">Skapar en CSV-fil med alla användare som har bearbetats och visar deras licensstatus.</span><span class="sxs-lookup"><span data-stu-id="6890b-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>

## <a name="see-also"></a><span data-ttu-id="6890b-161">Se även</span><span class="sxs-lookup"><span data-stu-id="6890b-161">See also</span></span>

[<span data-ttu-id="6890b-162">Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6890b-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)

[<span data-ttu-id="6890b-163">Inaktivera åtkomst till Sway med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6890b-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)

[<span data-ttu-id="6890b-164">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6890b-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="6890b-165">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="6890b-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)