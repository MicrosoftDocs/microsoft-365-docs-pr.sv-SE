---
title: Avgöra om centraliserad distribution av tillägg fungerar för din organisation
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Ta reda på om din klient organisation och användare uppfyller kraven och Använd centraliserad distribution för att distribuera Office-tillägg.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519371"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="8d425-103">Avgöra om centraliserad distribution av tillägg fungerar för din organisation</span><span class="sxs-lookup"><span data-stu-id="8d425-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="8d425-104">Centraliserad distribution är det rekommenderade och mest omfattande sättet för de flesta kunder att distribuera Office-tillägg till användare och grupper inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="8d425-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="8d425-105">Om du är administratör kan du använda den här vägledningen för att ta reda på om din organisation och dina användare uppfyller kraven för att kunna använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="8d425-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="8d425-106">Centraliserad distribution har följande fördelar:</span><span class="sxs-lookup"><span data-stu-id="8d425-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="8d425-107">En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8d425-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="8d425-108">När det relevanta Office-programmet startas hämtas tillägget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8d425-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="8d425-109">Om tillägget har stöd för tilläggs kommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.</span><span class="sxs-lookup"><span data-stu-id="8d425-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="8d425-110">Tillägg visas inte längre för användare om administratören inaktiverar eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget är tilldelat till.</span><span class="sxs-lookup"><span data-stu-id="8d425-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="8d425-111">Centraliserad distribution stöder tre Station ära datorer, Mac och online Office-appar.</span><span class="sxs-lookup"><span data-stu-id="8d425-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="8d425-112">Centraliserad distribution stöder även iOS och Android (endast Outlook Mobile-tillägg).</span><span class="sxs-lookup"><span data-stu-id="8d425-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="8d425-113">Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.</span><span class="sxs-lookup"><span data-stu-id="8d425-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="8d425-114">Krav</span><span class="sxs-lookup"><span data-stu-id="8d425-114">Requirements</span></span>

<span data-ttu-id="8d425-115">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365 Enterprise-SKU: E3/E5/F3 eller Business SKU: Business Basic, Business Standard, Business Premium (och är inloggade på Office med deras organisations-ID) och har Exchange Online och aktiva Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="8d425-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="8d425-116">Abonnemangs katalogen måste antingen vara i eller sammankopplad till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8d425-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="8d425-117">Du kan se specifika krav för Office och Exchange nedan eller använda kompatibilitetskontrollen för [centraliserad distribution](#centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="8d425-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="8d425-118">Centraliserad distribution stöder inte följande:</span><span class="sxs-lookup"><span data-stu-id="8d425-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="8d425-119">Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013</span><span class="sxs-lookup"><span data-stu-id="8d425-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="8d425-120">En lokal katalogtjänst</span><span class="sxs-lookup"><span data-stu-id="8d425-120">An on-premises directory service</span></span>
- <span data-ttu-id="8d425-121">Tillägg distribution till en Exchange On-lokala-postlåda</span><span class="sxs-lookup"><span data-stu-id="8d425-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="8d425-122">Tilläggsdistribution till SharePoint</span><span class="sxs-lookup"><span data-stu-id="8d425-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="8d425-123">Teams-appar</span><span class="sxs-lookup"><span data-stu-id="8d425-123">Teams apps</span></span>
- <span data-ttu-id="8d425-124">Distribution av COM (Component Object Model) eller Visual Studio Tools för Office-tillägg (VSTO).</span><span class="sxs-lookup"><span data-stu-id="8d425-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="8d425-125">Distributioner av Microsoft 365 som inte innehåller Exchange Online, till exempel SKU 365: er-appar för företag och Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="8d425-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="8d425-126">Office-krav</span><span class="sxs-lookup"><span data-stu-id="8d425-126">Office Requirements</span></span>

- <span data-ttu-id="8d425-127">För Word-, Excel-och PowerPoint-tillägg måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="8d425-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="8d425-128">På en Windows-enhet, version 1704 eller senare av Microsoft 365 Enterprise SKU: E3/E5/F3 eller företag SKU: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8d425-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="8d425-129">På en Mac, version 15,34 eller senare.</span><span class="sxs-lookup"><span data-stu-id="8d425-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="8d425-130">För Outlook måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="8d425-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="8d425-131">Version 1701 eller senare av Microsoft 365 Enterprise SKU: E3/E5/F3 eller företag SKU: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="8d425-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="8d425-132">Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="8d425-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="8d425-133">Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="8d425-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="8d425-134">Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="8d425-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="8d425-135">Version 16.0.9318.1000 eller senare av Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="8d425-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="8d425-136">Version 2.75.0 eller senare av Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="8d425-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="8d425-137">Version 2.2.145 eller senare av Outlook Mobile för Android</span><span class="sxs-lookup"><span data-stu-id="8d425-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="8d425-138">\* MSI-versioner av Outlook Visa installerade tillägg i Outlook-menyfliksområdet, inte avsnittet "mina tillägg".</span><span class="sxs-lookup"><span data-stu-id="8d425-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="8d425-139">Exchange Online-krav</span><span class="sxs-lookup"><span data-stu-id="8d425-139">Exchange Online requirements</span></span>

<span data-ttu-id="8d425-140">Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="8d425-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="8d425-141">Administratörs distributionen av tillägg och de användare som tar emot dessa tillägg måste finnas i en version av Exchange Online som stöder OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="8d425-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="8d425-p106">Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="8d425-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="8d425-144">Kompatibilitetskontroll för centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="8d425-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="8d425-145">Med kompatibilitetskontrollen för centraliserad distribution kan du kontrol lera om användarna på din klient organisation har ställts in för att använda centraliserad distribution för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="8d425-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="8d425-146">Kompatibilitetskontrollen krävs inte för Outlook-stöd.</span><span class="sxs-lookup"><span data-stu-id="8d425-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="8d425-147">Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="8d425-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="8d425-148">Köra kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="8d425-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="8d425-149">Öppna ett PowerShell.exe-fönster med förhöjd rättighet.</span><span class="sxs-lookup"><span data-stu-id="8d425-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="8d425-150">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="8d425-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="8d425-151">Kör kommandot **Invoke-CompatabilityCheck** :</span><span class="sxs-lookup"><span data-stu-id="8d425-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="8d425-152">I det här kommandot uppmanas du att ange  *_TenantDomain_* (till exempel *TailspinToysIncorporated. onmicrosoft. </span> com*) och  *_TenantAdmin_* -autentiseringsuppgifter (Använd dina globala administratörs uppgifter) och begär sedan medgivande.</span><span class="sxs-lookup"><span data-stu-id="8d425-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="8d425-153">Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="8d425-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="8d425-154">När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats.</span><span class="sxs-lookup"><span data-stu-id="8d425-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="8d425-155">Filen sparas som standard till **C:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="8d425-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="8d425-156">Utdatafilen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="8d425-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="8d425-157">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="8d425-157">User Name</span></span>
    
- <span data-ttu-id="8d425-158">Användar-ID (användarens e-postadress)</span><span class="sxs-lookup"><span data-stu-id="8d425-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="8d425-159">Centraliserad distribution är klar - om de återstående objekten har värdet sant</span><span class="sxs-lookup"><span data-stu-id="8d425-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="8d425-160">Kontors plan – den plan där Office de är licensierade för</span><span class="sxs-lookup"><span data-stu-id="8d425-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="8d425-161">Office aktiverat - om de har aktiverat Office</span><span class="sxs-lookup"><span data-stu-id="8d425-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="8d425-162">Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda</span><span class="sxs-lookup"><span data-stu-id="8d425-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="8d425-163">Multifaktorautentisering stöds inte när du använder PowerShell-modulen för central distribution.</span><span class="sxs-lookup"><span data-stu-id="8d425-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="8d425-164">Användar- och grupptilldelningar</span><span class="sxs-lookup"><span data-stu-id="8d425-164">User and group assignments</span></span>

<span data-ttu-id="8d425-165">Funktionen för centraliserad distribution stöder för närvarande de flesta av grupperna som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributions listor och säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="8d425-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8d425-166">Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="8d425-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="8d425-167">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="8d425-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="8d425-168">Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="8d425-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="8d425-p110">Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="8d425-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram över försäljnings avdelning](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="8d425-172">Ta reda på om en grupp innehåller kapslade grupper</span><span class="sxs-lookup"><span data-stu-id="8d425-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="8d425-173">Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook.</span><span class="sxs-lookup"><span data-stu-id="8d425-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="8d425-174">Om du anger grupp namnet i fältet **till** i ett e-postmeddelande och sedan väljer grupp namnet när det matchas visas det om det innehåller användare eller kapslade grupper.</span><span class="sxs-lookup"><span data-stu-id="8d425-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="8d425-175">I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.</span><span class="sxs-lookup"><span data-stu-id="8d425-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Fliken medlemmar på kontakt kortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="8d425-p112">Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet.</span><span class="sxs-lookup"><span data-stu-id="8d425-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Fliken medlemskap på kontakt kortet i Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="8d425-p113">Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="8d425-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="8d425-182">Kontakta Microsoft om du behöver support</span><span class="sxs-lookup"><span data-stu-id="8d425-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="8d425-183">Om du eller användarna drabbas av problem med att ladda tillägget när du använder Office-program för webben (Word, Excel, osv.), kan det hända att du måste kontakta Microsoft Support ([Läs mer](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="8d425-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="8d425-184">Ange följande information om din Microsoft 365-miljö i support ärendet.</span><span class="sxs-lookup"><span data-stu-id="8d425-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="8d425-185">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="8d425-185">**Platform**</span></span>|<span data-ttu-id="8d425-186">**Felsökningsinformation**</span><span class="sxs-lookup"><span data-stu-id="8d425-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d425-187">Office</span><span class="sxs-lookup"><span data-stu-id="8d425-187">Office</span></span>  <br/> | <span data-ttu-id="8d425-188">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="8d425-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="8d425-189">Klientorganisationens id ( [så här gör du](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="8d425-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="8d425-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="8d425-190">CorrelationID.</span></span> <span data-ttu-id="8d425-191">Visa källan för en av Office-sidorna och leta efter Correlation-ID-värdet och skicka det till stöd:</span><span class="sxs-lookup"><span data-stu-id="8d425-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="8d425-192">RTF-klienter (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="8d425-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="8d425-193">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="8d425-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="8d425-194">Build-nummer för klient programmet (helst som en skärm bild från **fil/konto**)</span><span class="sxs-lookup"><span data-stu-id="8d425-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
