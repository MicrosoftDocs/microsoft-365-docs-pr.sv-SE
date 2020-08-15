---
title: Hantera Microsoft 365-klient organisationer med Windows PowerShell för DAP partners
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: I den här artikeln lär du dig hur du använder PowerShell för Microsoft 365 för att hantera kund innehav.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694447"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="b9c22-103">Hantera Microsoft 365-klient organisationer med Windows PowerShell för DAP-partners (delegerade åtkomst behörigheter)</span><span class="sxs-lookup"><span data-stu-id="b9c22-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="b9c22-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b9c22-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b9c22-105">Med Windows PowerShell kan syndikerings-och moln lösnings partners (CSP) enkelt administrera och rapportera kund innehavs inställningar som inte är tillgängliga i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9c22-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b9c22-106">Observera att för partner administratörs kontot för att administrera AOBO behörigheter måste du ha åtkomst till dess kund innehavare.</span><span class="sxs-lookup"><span data-stu-id="b9c22-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="b9c22-107">DAP-partners (delegerade åtkomst behörigheter) för syndikering och moln lösnings leverantörer.</span><span class="sxs-lookup"><span data-stu-id="b9c22-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="b9c22-108">De är ofta nätverks-eller Telekom-leverantörer i andra företag.</span><span class="sxs-lookup"><span data-stu-id="b9c22-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="b9c22-109">De fördelar Microsoft 365-abonnemang till sina kunder.</span><span class="sxs-lookup"><span data-stu-id="b9c22-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="b9c22-110">När de säljer en Microsoft 365-prenumeration beviljas de automatiskt administration på uppdrag av (AOBO) behörigheter till kundens innehav så att de kan administrera och rapportera om kundens innehavare.</span><span class="sxs-lookup"><span data-stu-id="b9c22-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b9c22-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b9c22-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="b9c22-112">Procedurerna i det här avsnittet kräver att du ansluter till [Microsoft 365 med PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="b9c22-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="b9c22-113">Du behöver också dina autentiseringsuppgifter för partner klient organisation.</span><span class="sxs-lookup"><span data-stu-id="b9c22-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="b9c22-114">Vad vill du göra?</span><span class="sxs-lookup"><span data-stu-id="b9c22-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="b9c22-115">Lista alla klient-ID</span><span class="sxs-lookup"><span data-stu-id="b9c22-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="b9c22-116">Om du har fler än 500 klient organisationer kan du använda cmdlet-syntaxen med antingen  _-all_ eller _-MaxResultsParameter_.</span><span class="sxs-lookup"><span data-stu-id="b9c22-116">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_.</span></span> <span data-ttu-id="b9c22-117">Detta gäller för andra cmdlets som kan ge en stor utmatning, till exempel **Get-MsolUser**.</span><span class="sxs-lookup"><span data-stu-id="b9c22-117">This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="b9c22-118">Om du vill visa alla klient organisations-ID: n som du har åtkomst till kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="b9c22-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="b9c22-119">Då visas en lista över alla dina kund innehavare av **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="b9c22-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="b9c22-120">PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets med **MSOL** .</span><span class="sxs-lookup"><span data-stu-id="b9c22-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b9c22-121">För att kunna fortsätta använda dessa cmdletar måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9c22-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="b9c22-122">Skaffa ett klient-ID genom att använda domän namnet</span><span class="sxs-lookup"><span data-stu-id="b9c22-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="b9c22-123">Kör det här kommandot för att hämta **TenantId** för en viss kund klient organisation via domän namn.</span><span class="sxs-lookup"><span data-stu-id="b9c22-123">To get the **TenantId** for a specific customer tenant by domain name, run this command.</span></span> <span data-ttu-id="b9c22-124">Ersätt _<domainname.onmicrosoft.com>_ med det faktiska domän namnet för den klient organisation som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="b9c22-124">Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="b9c22-125">Visa en lista över alla domäner för en innehavare</span><span class="sxs-lookup"><span data-stu-id="b9c22-125">List all domains for a tenant</span></span>

<span data-ttu-id="b9c22-126">Kör det här kommandot för att få alla domäner för en klient organisation.</span><span class="sxs-lookup"><span data-stu-id="b9c22-126">To get all domains for any one customer tenant, run this command.</span></span> <span data-ttu-id="b9c22-127">Ersätt  _<customer TenantId value>_ med det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="b9c22-127">Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="b9c22-128">Om du har registrerat fler domäner kommer detta att returnera alla domäner som är kopplade till kunden **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="b9c22-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="b9c22-129">Få en mappning av alla innehavare och registrerade domäner</span><span class="sxs-lookup"><span data-stu-id="b9c22-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="b9c22-130">De föregående PowerShell för Microsoft 365-kommandon visar hur du hämtar antingen klient-ID: n eller domäner, men inte båda samtidigt, och utan en tydlig mappning mellan dem.</span><span class="sxs-lookup"><span data-stu-id="b9c22-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="b9c22-131">Det här kommandot skapar en lista över alla klient organisations-ID: n och deras domäner.</span><span class="sxs-lookup"><span data-stu-id="b9c22-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="b9c22-132">Skaffa alla användare för en klient organisation</span><span class="sxs-lookup"><span data-stu-id="b9c22-132">Get all users for a tenant</span></span>

<span data-ttu-id="b9c22-133">Då visas **userPrincipalName**, **DisplayName**och **ärlicensierad** status för alla användare för en viss klient organisation.</span><span class="sxs-lookup"><span data-stu-id="b9c22-133">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant.</span></span> <span data-ttu-id="b9c22-134">Ersätt _<customer TenantId value>_ med det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="b9c22-134">Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="b9c22-135">Få all information om en användare</span><span class="sxs-lookup"><span data-stu-id="b9c22-135">Get all details about a user</span></span>

<span data-ttu-id="b9c22-136">Om du vill se alla egenskaper för en viss användare kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="b9c22-136">If you want to see all the properties of a particular user, run this command.</span></span> <span data-ttu-id="b9c22-137">Ersätt  _<customer TenantId value>_ och _<user principal name value>_ med faktiska värden.</span><span class="sxs-lookup"><span data-stu-id="b9c22-137">Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="b9c22-138">Lägga till användare, ange alternativ och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="b9c22-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="b9c22-139">Det är särskilt effektivt att skapa, konfigurera och licensiera för Microsoft 365-användare genom att använda PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9c22-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="b9c22-140">I den här processen skapar du först poster för alla användare som du vill lägga till i en CSV-fil och sedan importerar filen genom att använda PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9c22-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="b9c22-141">Skapa en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="b9c22-141">Create a CSV file</span></span>

<span data-ttu-id="b9c22-142">Skapa en CSV-fil i det här formatet:</span><span class="sxs-lookup"><span data-stu-id="b9c22-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="b9c22-143">där:</span><span class="sxs-lookup"><span data-stu-id="b9c22-143">where:</span></span>
  
- <span data-ttu-id="b9c22-144">**UsageLocation**: värdet för det här är ISO-lands-/regionkoden för användaren.</span><span class="sxs-lookup"><span data-stu-id="b9c22-144">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user.</span></span> <span data-ttu-id="b9c22-145">Lands-/regionkoder kan hittas på[ISO online-webbplattformen](https://go.microsoft.com/fwlink/p/?LinkId=532703).</span><span class="sxs-lookup"><span data-stu-id="b9c22-145">The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703).</span></span> <span data-ttu-id="b9c22-146">Koden för USA är till exempel amerikansk och koden för Brasilien är BR.</span><span class="sxs-lookup"><span data-stu-id="b9c22-146">For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="b9c22-147">**LicenseAssignment**: värdet för detta format: `syndication-account:<PROVISIONING_ID>` .</span><span class="sxs-lookup"><span data-stu-id="b9c22-147">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`.</span></span> <span data-ttu-id="b9c22-148">Om du till exempel tilldelar kund klient organisationer O365_Business_Premium-licenser, ser det **LicenseAssignment** värdet ut så här: **syndikering-konto: O365_Business_Premium**.</span><span class="sxs-lookup"><span data-stu-id="b9c22-148">For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**.</span></span> <span data-ttu-id="b9c22-149">Du hittar PROVISIONING_IDs i syndikerings partner portalen som du har åtkomst till som syndikering eller CSP-partner.</span><span class="sxs-lookup"><span data-stu-id="b9c22-149">You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="b9c22-150">Importera CSV-filen och skapa användare</span><span class="sxs-lookup"><span data-stu-id="b9c22-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="b9c22-151">När du har skapat CSV-filen kör du det här kommandot för att skapa användar konton med lösen ord som inte upphör att gälla när du loggar in för första gången och att den licens du anger tilldelas.</span><span class="sxs-lookup"><span data-stu-id="b9c22-151">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify.</span></span> <span data-ttu-id="b9c22-152">Glöm inte att ersätta rätt CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="b9c22-152">Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="b9c22-153">Se även</span><span class="sxs-lookup"><span data-stu-id="b9c22-153">See also</span></span>

#### 

[<span data-ttu-id="b9c22-154">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="b9c22-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

