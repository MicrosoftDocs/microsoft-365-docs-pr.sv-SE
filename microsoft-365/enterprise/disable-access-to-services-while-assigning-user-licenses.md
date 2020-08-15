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
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="183d4-103">Inaktivera åtkomst till Microsoft 365-tjänster när du tilldelar användar licenser</span><span class="sxs-lookup"><span data-stu-id="183d4-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="183d4-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="183d4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="183d4-105">Microsoft 365-abonnemang innehåller tjänste abonnemang för enskilda tjänster.</span><span class="sxs-lookup"><span data-stu-id="183d4-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="183d4-106">Microsoft 365-administratörer behöver ofta inaktivera vissa abonnemang när de tilldelar användare licenser.</span><span class="sxs-lookup"><span data-stu-id="183d4-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="183d4-107">Med instruktionerna i den här artikeln kan du tilldela en Microsoft 365-licens när du inaktiverar specifika tjänste abonnemang med PowerShell för ett enskilt användar konto eller flera användar konton.</span><span class="sxs-lookup"><span data-stu-id="183d4-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="183d4-108">Använda Azure Active Directory PowerShell för diagramvyn</span><span class="sxs-lookup"><span data-stu-id="183d4-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="183d4-109">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="183d4-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="183d4-110">Sedan visar du licens abonnemang för klient organisationen med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="183d4-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="183d4-111">Sedan hämtar du inloggnings namnet för det konto som du vill lägga till en licens för och det kallas även användarens huvud namn (UPN).</span><span class="sxs-lookup"><span data-stu-id="183d4-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="183d4-112">Sedan kompilerar du en lista över tjänster att aktivera.</span><span class="sxs-lookup"><span data-stu-id="183d4-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="183d4-113">En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="183d4-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="183d4-114">För kommando blocket nedan fyller du i användar kontots huvud namn, SKU-delen och listan över tjänste planer för att aktivera och ta bort för klar ande text och \< and > tecken.</span><span class="sxs-lookup"><span data-stu-id="183d4-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="183d4-115">Kör sedan de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="183d4-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="183d4-116">Använda Microsoft Azure Active Directory-modulen för Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="183d4-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="183d4-117">Börja [med att ansluta till din Microsoft 365-klient organisation](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="183d4-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="183d4-118">Kör sedan det här kommandot för att se dina nuvarande abonnemang:</span><span class="sxs-lookup"><span data-stu-id="183d4-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="183d4-119">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="183d4-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="183d4-120">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="183d4-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="183d4-121">I visningen av  `Get-MsolAccountSku` kommandot:</span><span class="sxs-lookup"><span data-stu-id="183d4-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="183d4-122">**AccountSkuId** är ett abonnemang för din organisation i \<OrganizationName> : \<Subscription> format.</span><span class="sxs-lookup"><span data-stu-id="183d4-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="183d4-123">Det \<OrganizationName> är det värde som du angav när du registrerade dig i Microsoft 365 och det är unikt för organisationen.</span><span class="sxs-lookup"><span data-stu-id="183d4-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="183d4-124">\<Subscription>Värdet är för en specifik prenumeration.</span><span class="sxs-lookup"><span data-stu-id="183d4-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="183d4-125">Till exempel för licens planen litwareinc: ENTERPRISEPACK, organisations namnet är licens planen litwareinc och prenumerations namnet är ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="183d4-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="183d4-126">**ActiveUnits** är antalet licenser som du har köpt för abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="183d4-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="183d4-127">**WarningUnits** är antalet licenser i en prenumeration som du inte har förnyat och som upphör efter 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="183d4-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="183d4-128">**ConsumedUnits** är antalet licenser som du har tilldelat användare för abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="183d4-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="183d4-129">Notera AccountSkuId för din Microsoft 365-prenumeration som innehåller de användare du vill licensiera.</span><span class="sxs-lookup"><span data-stu-id="183d4-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="183d4-130">Se också till att det finns tillräckligt många licenser att tilldela (subtrahera **ConsumedUnits** från **ActiveUnits** ).</span><span class="sxs-lookup"><span data-stu-id="183d4-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="183d4-131">Kör sedan det här kommandot för att visa information om de Microsoft 365-tjänste abonnemang som är tillgängliga i alla dina abonnemang:</span><span class="sxs-lookup"><span data-stu-id="183d4-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="183d4-132">I visningen av det här kommandot kan du bestämma vilka tjänste abonnemang du vill inaktivera när du tilldelar användare licenser.</span><span class="sxs-lookup"><span data-stu-id="183d4-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="183d4-133">Här är en del av en lista över tjänste abonnemang och deras motsvarande Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="183d4-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="183d4-134">I följande tabell visas Microsoft 365-tjänstens abonnemang och deras egna namn för de vanligaste tjänsterna.</span><span class="sxs-lookup"><span data-stu-id="183d4-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="183d4-135">Din lista över tjänste abonnemang kan skilja sig från varandra.</span><span class="sxs-lookup"><span data-stu-id="183d4-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="183d4-136">**Service plan**</span><span class="sxs-lookup"><span data-stu-id="183d4-136">**Service plan**</span></span>|<span data-ttu-id="183d4-137">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="183d4-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="183d4-138">Sway</span><span class="sxs-lookup"><span data-stu-id="183d4-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="183d4-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="183d4-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="183d4-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="183d4-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="183d4-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="183d4-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="183d4-142">Microsoft 365-appar för företag *(tidigare kallat Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="183d4-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="183d4-143">Skype för företag – Online</span><span class="sxs-lookup"><span data-stu-id="183d4-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="183d4-144">Office</span><span class="sxs-lookup"><span data-stu-id="183d4-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="183d4-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="183d4-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="183d4-146">Exchange Online-abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="183d4-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="183d4-147">En fullständig lista över licens planer (kallas även produkt namn), deras inkluderade tjänste abonnemang och deras motsvarande namn finns i [produkt namn och service plan-ID: n för licensiering](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="183d4-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="183d4-148">Nu när du har AccountSkuId och tjänste abonnemangen för att inaktivera kan du tilldela licenser för enskilda användare eller för flera användare.</span><span class="sxs-lookup"><span data-stu-id="183d4-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="183d4-149">För en enskild användare</span><span class="sxs-lookup"><span data-stu-id="183d4-149">For a single user</span></span>

<span data-ttu-id="183d4-150">För en enskild användare fyller du i användarens huvud namn, AccountSkuId och listan över tjänste planer för att inaktivera och ta bort den för klar ande texten och \< and > tecknen.</span><span class="sxs-lookup"><span data-stu-id="183d4-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="183d4-151">Kör sedan de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="183d4-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="183d4-152">Här är ett exempel på ett kommando block för kontot som heter belindan@contoso.com, för avtalet contoso: ENTERPRISEPACK och tjänste abonnemangen för att inaktivera är RMS_S_ENTERPRISE, SWAY, INTUNE_O365 och YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="183d4-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="183d4-153">För flera användare</span><span class="sxs-lookup"><span data-stu-id="183d4-153">For multiple users</span></span>

<span data-ttu-id="183d4-154">Om du vill utföra den här administrationen för flera användare kan du skapa en CSV-textfil som innehåller fälten UserPrincipalName och UsageLocation.</span><span class="sxs-lookup"><span data-stu-id="183d4-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="183d4-155">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="183d4-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="183d4-156">Fyll sedan i placeringen av CSV-filer för in-och utdata, konto-SKU-ID: t och listan över tjänst planer att inaktivera och kör sedan de resulterande kommandona i PowerShell-Kommandotolken.</span><span class="sxs-lookup"><span data-stu-id="183d4-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
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

<span data-ttu-id="183d4-157">Det här PowerShell-kommando blocket:</span><span class="sxs-lookup"><span data-stu-id="183d4-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="183d4-158">Visar användarens huvud namn för varje användare.</span><span class="sxs-lookup"><span data-stu-id="183d4-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="183d4-159">Tilldelar alla användare egna licenser.</span><span class="sxs-lookup"><span data-stu-id="183d4-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="183d4-160">Skapar en CSV-fil med alla användare som har bearbetats och visar deras licens status.</span><span class="sxs-lookup"><span data-stu-id="183d4-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="183d4-161">Se även</span><span class="sxs-lookup"><span data-stu-id="183d4-161">See also</span></span>

[<span data-ttu-id="183d4-162">Inaktivera åtkomst till Microsoft 365-tjänster med PowerShell</span><span class="sxs-lookup"><span data-stu-id="183d4-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="183d4-163">Inaktivera åtkomst till Sway med PowerShell</span><span class="sxs-lookup"><span data-stu-id="183d4-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="183d4-164">Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell</span><span class="sxs-lookup"><span data-stu-id="183d4-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="183d4-165">Hantera Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="183d4-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
