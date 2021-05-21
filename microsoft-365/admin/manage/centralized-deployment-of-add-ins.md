---
title: Avgöra om centraliserad distribution av tillägg fungerar för din organisation
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Avgör om klientorganisationen och användarna uppfyller kraven, så att du kan använda centraliserad distribution för Office tillägg.
ms.openlocfilehash: e5d3337cdf1bbb0dc18ee6940ab8bd289d2e5f65
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593927"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="2ef43-103">Avgöra om centraliserad distribution av tillägg fungerar för din organisation</span><span class="sxs-lookup"><span data-stu-id="2ef43-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="2ef43-104">Centraliserad distribution är den rekommenderade och mest funktionsrika sättet för de flesta kunder att Office tillägg till användare och grupper i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2ef43-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="2ef43-105">Om du är administratör kan du använda den här vägledningen för att ta reda på om organisationen och användarna uppfyller kraven för centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="2ef43-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="2ef43-106">Centraliserad distribution har följande fördelar:</span><span class="sxs-lookup"><span data-stu-id="2ef43-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="2ef43-107">En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="2ef43-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="2ef43-108">När det Office programmet startas laddas tillägget ned automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2ef43-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="2ef43-109">Om tillägget har stöd för tilläggskommandon visas det automatiskt i menyfliksområdet i Office program.</span><span class="sxs-lookup"><span data-stu-id="2ef43-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="2ef43-110">Tillägg visas inte längre för användare om administratören stänger av eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="2ef43-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="2ef43-111">Centraliserad distribution har stöd för tre plattformar Windows, Mac och Online Office program.</span><span class="sxs-lookup"><span data-stu-id="2ef43-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="2ef43-112">Centraliserad distribution har också stöd för iOS Outlook Android (endast för mobila tillägg).</span><span class="sxs-lookup"><span data-stu-id="2ef43-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="2ef43-113">Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.</span><span class="sxs-lookup"><span data-stu-id="2ef43-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="2ef43-114">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="2ef43-114">Before you begin</span></span>

<span data-ttu-id="2ef43-115">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365 Enterprise SKU:er: E3/E5/F3 eller Företags-SKU:er: Business Basic, Business Standard, Business Premium (och är inloggade på Office med sitt organisations-ID) och har Exchange Online och aktiva Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="2ef43-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="2ef43-116">Prenumerationskatalogen måste finnas i eller vara extern till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ef43-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="2ef43-117">Du kan visa specifika krav för Office och Exchange nedan, eller använda kompatibilitetskontrollen för [centraliserad distribution.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="2ef43-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="2ef43-118">Centraliserad distribution stöder inte följande:</span><span class="sxs-lookup"><span data-stu-id="2ef43-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="2ef43-119">Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013</span><span class="sxs-lookup"><span data-stu-id="2ef43-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="2ef43-120">En lokal katalogtjänst</span><span class="sxs-lookup"><span data-stu-id="2ef43-120">An on-premises directory service</span></span>
- <span data-ttu-id="2ef43-121">Tilläggsdistribution till en Exchange-postlåda</span><span class="sxs-lookup"><span data-stu-id="2ef43-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="2ef43-122">Tilläggsdistribution till SharePoint</span><span class="sxs-lookup"><span data-stu-id="2ef43-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="2ef43-123">Teams appar</span><span class="sxs-lookup"><span data-stu-id="2ef43-123">Teams apps</span></span>
- <span data-ttu-id="2ef43-124">Distribution av COM- (Component Object Model) Visual Studio VSTO-tillägg (Component Object Model) Office Tools for Office.</span><span class="sxs-lookup"><span data-stu-id="2ef43-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="2ef43-125">Distributioner av Microsoft 365 som inte inkluderar Exchange Online till exempel SKU:er: Microsoft 365 Program för företag och Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="2ef43-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="2ef43-126">Office Krav</span><span class="sxs-lookup"><span data-stu-id="2ef43-126">Office Requirements</span></span>

- <span data-ttu-id="2ef43-127">För Word Excel och PowerPoint tillägg måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="2ef43-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="2ef43-128">På en Windows enhet, version 1704 eller senare av Microsoft 365 Enterprise-SKU:er: E3/E5/F3 eller företags-SKU:er: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2ef43-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="2ef43-129">På Mac, version 15.34 eller senare.</span><span class="sxs-lookup"><span data-stu-id="2ef43-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="2ef43-130">Användarna Outlook till exempel använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="2ef43-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="2ef43-131">Version 1701 eller senare av Microsoft 365 Enterprise: E3/E5/F3 eller företags-SKU:er: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="2ef43-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="2ef43-132">Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="2ef43-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="2ef43-133">Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="2ef43-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="2ef43-134">Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="2ef43-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="2ef43-135">Version 16.0.9318.1000 eller senare av Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="2ef43-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="2ef43-136">Version 2.75.0 eller senare av Outlook för iOS</span><span class="sxs-lookup"><span data-stu-id="2ef43-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="2ef43-137">Version 2.2.145 eller senare av Outlook för Android</span><span class="sxs-lookup"><span data-stu-id="2ef43-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="2ef43-138">\*MSI-Outlook visar administratörsinstallerade tillägg i rätt menyfliksområde Outlook program, inte avsnittet Mina tillägg.</span><span class="sxs-lookup"><span data-stu-id="2ef43-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="2ef43-139">Exchange Online krav</span><span class="sxs-lookup"><span data-stu-id="2ef43-139">Exchange Online requirements</span></span>

<span data-ttu-id="2ef43-140">Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="2ef43-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="2ef43-141">Administratören som distribuerar tillägg och användarna som tar emot dessa tillägg måste använda en version av Exchange Online som stöder OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="2ef43-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="2ef43-p106">Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity).</span><span class="sxs-lookup"><span data-stu-id="2ef43-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="2ef43-144">Kompatibilitetskontroll för centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="2ef43-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="2ef43-145">Med hjälp av kompatibilitetskontrollen för centraliserad distribution kan du kontrollera om användarna i klientorganisationen är konfigurerade för att använda centraliserad distribution för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="2ef43-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="2ef43-146">Kompatibilitetskontrollen krävs inte för Outlook-stöd.</span><span class="sxs-lookup"><span data-stu-id="2ef43-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="2ef43-147">Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="2ef43-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="2ef43-148">Köra kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="2ef43-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="2ef43-149">Öppna ett PowerShell.exe-fönster med förhöjd rättighet.</span><span class="sxs-lookup"><span data-stu-id="2ef43-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="2ef43-150">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="2ef43-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="2ef43-151">Kör **kommandot Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="2ef43-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="2ef43-152">Det här kommandot uppmanar dig att  *_ange TenantDomain_* (till exempel *TailspinToysIncorporated.onmicrosoft. </span> com*) och  *_TenantAdmin-autentiseringsuppgifter_* (använd dina autentiseringsuppgifter som global administratör) och begär sedan medgivande.</span><span class="sxs-lookup"><span data-stu-id="2ef43-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="2ef43-153">Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="2ef43-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="2ef43-154">När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats.</span><span class="sxs-lookup"><span data-stu-id="2ef43-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="2ef43-155">Filen sparas som standard **till C:\windows\system32.**</span><span class="sxs-lookup"><span data-stu-id="2ef43-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="2ef43-156">Utdatafilen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="2ef43-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="2ef43-157">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="2ef43-157">User Name</span></span>
    
- <span data-ttu-id="2ef43-158">Användar-ID (användarens e-postadress)</span><span class="sxs-lookup"><span data-stu-id="2ef43-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="2ef43-159">Centraliserad distribution är klar - om de återstående objekten har värdet sant</span><span class="sxs-lookup"><span data-stu-id="2ef43-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="2ef43-160">Office – abonnemanget de Office är licensierade för</span><span class="sxs-lookup"><span data-stu-id="2ef43-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="2ef43-161">Office aktiverat - om de har aktiverat Office</span><span class="sxs-lookup"><span data-stu-id="2ef43-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="2ef43-162">Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda</span><span class="sxs-lookup"><span data-stu-id="2ef43-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="2ef43-163">Multifaktorautentisering stöds inte när du använder PowerShell-modulen för central distribution.</span><span class="sxs-lookup"><span data-stu-id="2ef43-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="2ef43-164">Användar- och grupptilldelningar</span><span class="sxs-lookup"><span data-stu-id="2ef43-164">User and group assignments</span></span>

<span data-ttu-id="2ef43-165">Funktionen för centraliserad distribution har för närvarande stöd för de flesta grupper som stöds av Azure Active Directory, inklusive Microsoft 365, distributionslistor och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="2ef43-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ef43-166">Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="2ef43-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="2ef43-167">Centraliserad distribution har stöd för tilldelningar till enskilda användare, grupper och alla i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2ef43-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="2ef43-168">Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="2ef43-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="2ef43-p110">Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="2ef43-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="2ef43-172">Ta reda på om en grupp innehåller kapslade grupper</span><span class="sxs-lookup"><span data-stu-id="2ef43-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="2ef43-173">Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook.</span><span class="sxs-lookup"><span data-stu-id="2ef43-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="2ef43-174">Om du anger gruppens  namn i fältet Till i ett e-postmeddelande och sedan väljer gruppens namn när det matchas visas om den innehåller användare eller kapslade grupper.</span><span class="sxs-lookup"><span data-stu-id="2ef43-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="2ef43-175">I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.</span><span class="sxs-lookup"><span data-stu-id="2ef43-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Fliken Medlemmar på Outlook kontaktkort](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="2ef43-p112">Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet.</span><span class="sxs-lookup"><span data-stu-id="2ef43-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Fliken Medlemskap på Outlook kontaktkort](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="2ef43-p113">Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](/previous-versions/azure/ad/graph/api/groups-operations).</span><span class="sxs-lookup"><span data-stu-id="2ef43-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="2ef43-182">Kontakta Microsoft om du behöver support</span><span class="sxs-lookup"><span data-stu-id="2ef43-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="2ef43-183">Om du eller dina användare stöter på problem med att läsa in tillägget när du använder Office-appar för webben (Word, Excel osv.), som distribuerats centralt, kan du behöva kontakta Microsofts support (så här[gör du).](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="2ef43-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="2ef43-184">Ange följande information om din Microsoft 365 i supporten.</span><span class="sxs-lookup"><span data-stu-id="2ef43-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="2ef43-185">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="2ef43-185">**Platform**</span></span>|<span data-ttu-id="2ef43-186">**Felsökningsinformation**</span><span class="sxs-lookup"><span data-stu-id="2ef43-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2ef43-187">Office</span><span class="sxs-lookup"><span data-stu-id="2ef43-187">Office</span></span>  <br/> | <span data-ttu-id="2ef43-188">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="2ef43-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="2ef43-189">Klientorganisationens id ( [så här gör du](/onedrive/find-your-office-365-tenant-id.md))</span><span class="sxs-lookup"><span data-stu-id="2ef43-189">Tenant ID ( [learn how](/onedrive/find-your-office-365-tenant-id.md))</span></span>  <br/>  <span data-ttu-id="2ef43-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="2ef43-190">CorrelationID.</span></span> <span data-ttu-id="2ef43-191">Visa källan för en av Office-sidorna, leta efter värdet för Korrelations-ID och skicka det till supporten:</span><span class="sxs-lookup"><span data-stu-id="2ef43-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="2ef43-192">RTF-klienter (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="2ef43-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="2ef43-193">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="2ef43-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="2ef43-194">Versionsnummer för klientappen (helst som en skärmbild från **Arkiv/Konto**)</span><span class="sxs-lookup"><span data-stu-id="2ef43-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="2ef43-195">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="2ef43-195">Related content</span></span>

<span data-ttu-id="2ef43-196">[Distribuera tillägg i administrationscentret](../manage/manage-deployment-of-add-ins.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2ef43-196">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>

<span data-ttu-id="2ef43-197">[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2ef43-197">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>

<span data-ttu-id="2ef43-198">[Vanliga frågor och svar om centraliserad distribution](../manage/centralized-deployment-faq.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2ef43-198">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>

<span data-ttu-id="2ef43-199">[Uppgradera dina Microsoft 365 för företag-användare till den senaste Office klient](../setup/upgrade-users-to-latest-office-client.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="2ef43-199">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 