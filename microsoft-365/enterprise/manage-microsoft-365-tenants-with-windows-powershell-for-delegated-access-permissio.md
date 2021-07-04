---
title: Hantera Microsoft 365 med Windows PowerShell dap-partner
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
description: I den här artikeln lär du dig att använda PowerShell för Microsoft 365 att hantera dina kundantag.
ms.openlocfilehash: 96c2c148b64d638ea977922f6a0ae3d5e23a8ace
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289109"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="fd1fc-103">Hantera Microsoft 365-klientorganisationen med Windows PowerShell för DAP-partner (Delegerade åtkomstbehörigheter)</span><span class="sxs-lookup"><span data-stu-id="fd1fc-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="fd1fc-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fd1fc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fd1fc-105">Windows PowerShell tillåter att Syndication- och Molnlösningsleverantör-partner (CSP) enkelt kan administrera och rapportera inställningar för kundföretag som inte är tillgängliga i Administrationscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="fd1fc-106">Observera att Behörigheten Administrera för AOBO krävs för att partneradministratörens konto ska kunna ansluta till sina kundantag.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>

<span data-ttu-id="fd1fc-107">DAP-partner (Delegerad åtkomstbehörighet) är syndicerings- och molnlösningsleverantörer (CSP).</span><span class="sxs-lookup"><span data-stu-id="fd1fc-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="fd1fc-108">De är ofta nätverks- eller telekommunikationsleverantörer till andra företag.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="fd1fc-109">De paketar Microsoft 365 prenumerationer till sina tjänsteerbjudanden till sina kunder.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="fd1fc-110">När de säljer en Microsoft 365-prenumeration tilldelas de automatiskt behörigheten Administrera för (AOBO) för kundens företag så att de kan administrera och rapportera om kundrelationerna.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fd1fc-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="fd1fc-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="fd1fc-112">Procedurerna i det här avsnittet kräver att du ansluter [till Anslut och Microsoft 365 med PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fd1fc-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="fd1fc-113">Du behöver också autentiseringsuppgifterna för partnerklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-113">You also need your partner tenant administrator credentials.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="fd1fc-114">Vad vill du göra?</span><span class="sxs-lookup"><span data-stu-id="fd1fc-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="fd1fc-115">Visa alla klientorganisations-ID</span><span class="sxs-lookup"><span data-stu-id="fd1fc-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="fd1fc-116">Om du har fler än 500 innehavare kan du begränsa cmdlet-syntaxen med _antingen -All_ eller _-MaxResultsParameter._</span><span class="sxs-lookup"><span data-stu-id="fd1fc-116">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_.</span></span> <span data-ttu-id="fd1fc-117">Det här gäller andra cmdlets som kan ge stora utdata, till exempel **Get-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="fd1fc-117">This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>

<span data-ttu-id="fd1fc-118">Om du vill visa alla klientorganisations-ID:n som du har tillgång till kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-118">To list all customer tenant Ids that you have access to, run this command.</span></span>

```powershell
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="fd1fc-119">Då visas en lista över alla dina kundklienter efter **TenantId.**</span><span class="sxs-lookup"><span data-stu-id="fd1fc-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="fd1fc-120">PowerShell Core stöder inte Microsoft Azure Active Directory-modul för Windows PowerShell-modulen och-cmdlets med **MSOL** i namnet.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="fd1fc-121">Om du vill fortsätta använda dessa cmdlets måste du köra dem från Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="fd1fc-122">Hämta ett klientorganisations-ID genom att använda domännamnet</span><span class="sxs-lookup"><span data-stu-id="fd1fc-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="fd1fc-123">Kör det här **kommandot för att** få klientorganisationens ID för en viss kundklient genom att köra det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-123">To get the **TenantId** for a specific customer tenant by domain name, run this command.</span></span> <span data-ttu-id="fd1fc-124">Ersätt _<domainname.onmicrosoft.com>_ domännamnet för den kundklientorganisation som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-124">Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>

```powershell
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="fd1fc-125">Lista alla domäner för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="fd1fc-125">List all domains for a tenant</span></span>

<span data-ttu-id="fd1fc-126">Om du vill skaffa alla domäner för en kundklientorganisation kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-126">To get all domains for any one customer tenant, run this command.</span></span> <span data-ttu-id="fd1fc-127">Ersätt  _<customer TenantId value>_ med det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-127">Replace  _<customer TenantId value>_ with the actual value.</span></span>

```powershell
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="fd1fc-128">Om du har registrerat ytterligare domäner returneras alla domäner som är kopplade till kundens **Klientorganisations-ID.**</span><span class="sxs-lookup"><span data-stu-id="fd1fc-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>

### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="fd1fc-129">Få en mappning av alla klienter och registrerade domäner</span><span class="sxs-lookup"><span data-stu-id="fd1fc-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="fd1fc-130">I de tidigare kommandona för PowerShell för Microsoft 365 visades hur du hämtar antingen klientorganisations-ID:er eller domäner, men inte båda samtidigt, och utan en tydlig mappning mellan dem alla.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="fd1fc-131">Det här kommandot genererar en lista över alla dina klientorganisations-ID och deras domäner.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>

```powershell
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="fd1fc-132">Skaffa alla användare för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="fd1fc-132">Get all users for a tenant</span></span>

<span data-ttu-id="fd1fc-133">Då visas **UserPrincipalName,** **DisplayName** och **statusen ärLicensed för** alla användare för en viss klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-133">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant.</span></span> <span data-ttu-id="fd1fc-134">Ersätt _<customer TenantId value>_ med det faktiska värdet.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-134">Replace _<customer TenantId value>_ with the actual value.</span></span>

```powershell
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="fd1fc-135">Få all information om en användare</span><span class="sxs-lookup"><span data-stu-id="fd1fc-135">Get all details about a user</span></span>

<span data-ttu-id="fd1fc-136">Om du vill se alla egenskaper för en viss användare kör du det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-136">If you want to see all the properties of a particular user, run this command.</span></span> <span data-ttu-id="fd1fc-137">Ersätt  _<customer TenantId value>_ och med de faktiska _<user principal name value>_ värdena.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-137">Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>

```powershell
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="fd1fc-138">Lägga till användare, ange alternativ och tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="fd1fc-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="fd1fc-139">Att massskapa, konfigurera och licensiera Microsoft 365 är särskilt effektivt med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="fd1fc-140">I den här tvåstegsprocessen skapar du först poster för alla användare som du vill lägga till i en fil med kommaavgränsade värden (CSV) och sedan importerar du filen med PowerShell för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span>

#### <a name="create-a-csv-file"></a><span data-ttu-id="fd1fc-141">Skapa en CSV-fil</span><span class="sxs-lookup"><span data-stu-id="fd1fc-141">Create a CSV file</span></span>

<span data-ttu-id="fd1fc-142">Skapa en CSV-fil med det här formatet:</span><span class="sxs-lookup"><span data-stu-id="fd1fc-142">Create a CSV file by using this format:</span></span>

`UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`

<span data-ttu-id="fd1fc-143">där:</span><span class="sxs-lookup"><span data-stu-id="fd1fc-143">where:</span></span>

- <span data-ttu-id="fd1fc-144">**Användninglokalisering:** Värdet för det här är användarens ISO-lands-/regionskod på två bokstäver.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-144">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user.</span></span> <span data-ttu-id="fd1fc-145">Landskoderna/regionskoderna kan du hitta på[ISO-webbplattformen online.](https://go.microsoft.com/fwlink/p/?LinkId=532703)</span><span class="sxs-lookup"><span data-stu-id="fd1fc-145">The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703).</span></span> <span data-ttu-id="fd1fc-146">Koden för USA är till exempel USA och koden för Brasilien är BR.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-146">For example, the code for the United States is US, and the code for Brazil is BR.</span></span>

- <span data-ttu-id="fd1fc-147">**LicenseAssignment:** Värdet för det här använder följande format: `syndication-account:<PROVISIONING_ID>` .</span><span class="sxs-lookup"><span data-stu-id="fd1fc-147">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`.</span></span> <span data-ttu-id="fd1fc-148">Om du till exempel tilldelar kunder klientorganisationsanvändare O365_Business_Premium licenser ser värdet **Licenstilldelning** ut så här: **syndication-account:O365_Business_Premium**.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-148">For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**.</span></span> <span data-ttu-id="fd1fc-149">Du hittar de PROVISIONING_IDs i Syndication-partnerportalen som du har åtkomst till som Syndication- eller CSP-partner.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-149">You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>

#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="fd1fc-150">Importera CSV-filen och skapa användarna</span><span class="sxs-lookup"><span data-stu-id="fd1fc-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="fd1fc-151">När du har skapat CSV-filen kör du det här kommandot för att skapa användarkonton med lösenord som inte upphör att gälla och som användaren måste ändra vid första inloggningen och som tilldelar licensen du anger.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-151">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify.</span></span> <span data-ttu-id="fd1fc-152">Se till att ersätta rätt CSV-filnamn.</span><span class="sxs-lookup"><span data-stu-id="fd1fc-152">Be sure to substitute the correct CSV file name.</span></span>

```powershell
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="fd1fc-153">Se även</span><span class="sxs-lookup"><span data-stu-id="fd1fc-153">See also</span></span>

[<span data-ttu-id="fd1fc-154">Hjälp för partners</span><span class="sxs-lookup"><span data-stu-id="fd1fc-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)
