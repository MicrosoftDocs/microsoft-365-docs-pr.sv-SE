---
title: Ta reda på om centraliserad distribution av tillägg fungerar för din organisation
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
description: Ta reda på om din klient och dina användare uppfyller kraven, så att du kan använda centraliserad distribution för att distribuera Office-tillägg.
ms.openlocfilehash: fbf6ce702cfe0fa3c85b634996a38cc4857190b6
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102878"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="5dcfc-103">Ta reda på om centraliserad distribution av tillägg fungerar för din organisation</span><span class="sxs-lookup"><span data-stu-id="5dcfc-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="5dcfc-104">Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta kunder att distribuera Office-tillägg till användare och grupper inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="5dcfc-105">Om du är administratör kan du använda den här vägledningen för att avgöra om din organisation och användare uppfyller kraven så att du kan använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="5dcfc-106">Centraliserad distribution ger följande fördelar:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="5dcfc-107">En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="5dcfc-108">När det aktuella Office-programmet startar hämtas tillägget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="5dcfc-109">Om tillägget stöder tilläggskommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="5dcfc-110">Tillägg visas inte längre för användare om administratören stänger av eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="5dcfc-111">Centraliserad distribution stöder tre skrivbordsplattformar Windows, Mac och Online Office-appar.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="5dcfc-112">Centraliserad distribution stöder även iOS och Android (endast Outlook Mobile-tillägg).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="5dcfc-113">Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="5dcfc-114">Krav</span><span class="sxs-lookup"><span data-stu-id="5dcfc-114">Requirements</span></span>

<span data-ttu-id="5dcfc-115">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365 Apps for Enterprise (och är inloggade på Office med sitt organisations-ID) och har Exchange Online- och active Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="5dcfc-116">Din prenumerationskatalog måste antingen vara i eller federeras med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="5dcfc-117">Du kan visa specifika krav för Office och Exchange nedan eller använda den [centraliserade kompatibilitetskontrollen för distribution](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="5dcfc-118">Centraliserad distribution stöder inte följande:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="5dcfc-119">Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013</span><span class="sxs-lookup"><span data-stu-id="5dcfc-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="5dcfc-120">En lokal katalogtjänst</span><span class="sxs-lookup"><span data-stu-id="5dcfc-120">An on-premises directory service</span></span>
- <span data-ttu-id="5dcfc-121">Tilläggsdistribution till en Exchange On-Prem-postlåda</span><span class="sxs-lookup"><span data-stu-id="5dcfc-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="5dcfc-122">Tilläggsdistribution till SharePoint</span><span class="sxs-lookup"><span data-stu-id="5dcfc-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="5dcfc-123">Team-appar</span><span class="sxs-lookup"><span data-stu-id="5dcfc-123">Teams apps</span></span>
- <span data-ttu-id="5dcfc-124">Distribution av COM- (Component Object Model) och VSTO-tilläggen (Visual Studio Tools for Office)</span><span class="sxs-lookup"><span data-stu-id="5dcfc-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="5dcfc-125">Distributioner av Microsoft 365 som inte inkluderar Exchange, till exempel Microsoft 365 Apps for business</span><span class="sxs-lookup"><span data-stu-id="5dcfc-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="5dcfc-126">Office-krav</span><span class="sxs-lookup"><span data-stu-id="5dcfc-126">Office Requirements</span></span>

- <span data-ttu-id="5dcfc-127">För Word-, Excel- och PowerPoint-tillägg måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="5dcfc-128">På en Windows-enhet, version 1704 eller senare av Microsoft 365 Apps för företag.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="5dcfc-129">På en Mac, version 15.34 eller senare.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="5dcfc-130">För Outlook måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="5dcfc-131">Version 1701 eller senare av Microsoft 365 Apps för företag.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-131">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="5dcfc-132">Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="5dcfc-133">Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="5dcfc-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="5dcfc-134">Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="5dcfc-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="5dcfc-135">Version 16.0.9318.1000 eller senare av Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="5dcfc-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="5dcfc-136">Version 2.75.0 eller senare av Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="5dcfc-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="5dcfc-137">Version 2.2.145 eller senare av Outlook Mobile för Android</span><span class="sxs-lookup"><span data-stu-id="5dcfc-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="5dcfc-138">\*MSI-versioner av Outlook visar administratörsinstallerade tillägg i lämpligt menyfliksområdet i Outlook, inte avsnittet "Mina tillägg".</span><span class="sxs-lookup"><span data-stu-id="5dcfc-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="5dcfc-139">Ta reda på om Microsoft 365 Apps for Enterprise är installerat</span><span class="sxs-lookup"><span data-stu-id="5dcfc-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="5dcfc-140">Om du vill använda Microsoft 365 Apps för företag måste en användare ha ett Microsoft 365-konto och ha tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="5dcfc-141">Mer information finns i [Översikt över Microsoft 365 Apps för företag](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="5dcfc-142">Det enklaste sättet att identifiera om en användare har Microsoft 365 Apps för företag installerat och har använt det nyligen är att använda Microsoft Office Aktiveringsrapporten, som är tillgänglig i Microsoft 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5dcfc-143">Rapporten innehåller en lista över alla användare som har aktiverat Microsoft 365 Apps för företag under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="5dcfc-144">De kolumner i rapporten som är viktiga för centraliserad distribution är de för datoraktiveringar för Windows och Mac.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="5dcfc-145">Du kan exportera rapporten till Excel.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-145">You can export the report to Excel.</span></span> <span data-ttu-id="5dcfc-146">Mer information om rapporten finns [i Microsoft 365 Reports i Administrationscenter – Microsoft Office-aktiveringar](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="5dcfc-147">Om du inte vill använda rapporten Aktiveringar kan du be en användare att öppna ett Office-program som Word på datorn och sedan välja **File** \> **Arkivkonto**.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="5dcfc-148">Under **Produktinformation**bör du se **Prenumerationsprodukt** och **Microsoft 365 för företag**, vilket visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Produktinformation i ett Office-program](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="5dcfc-150">Mer information om Microsoft 365 Apps for enterprise finns i [Felsökningstips för Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="5dcfc-151">Exchange Online-krav</span><span class="sxs-lookup"><span data-stu-id="5dcfc-151">Exchange Online requirements</span></span>

<span data-ttu-id="5dcfc-152">Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="5dcfc-153">Administratören som distribuerar tillägg och de användare som tar emot dessa tillägg måste finnas på en version av Exchange Online som stöder OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="5dcfc-154">Check with your organization's Exchange admin to find out which configuration is in use.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-154">Check with your organization's Exchange admin to find out which configuration is in use.</span></span> <span data-ttu-id="5dcfc-155">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-155">OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="5dcfc-156">Centraliserad kompatibilitetskontroll för distribution</span><span class="sxs-lookup"><span data-stu-id="5dcfc-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="5dcfc-157">Med hjälp av den centraliserade kompatibilitetskontrollen för distribution kan du kontrollera om användarna på klienten är konfigurerade för att använda centraliserad distribution för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="5dcfc-158">Kompatibilitetskontrollen krävs inte för Outlook-stöd.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="5dcfc-159">Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="5dcfc-160">Kör kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="5dcfc-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="5dcfc-161">Öppna ett PowerShell.exe-fönster med förhöjd rättighet.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="5dcfc-162">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="5dcfc-163">Kör kommandot **Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="5dcfc-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="5dcfc-164">Det här kommandot uppmanar dig för *_TenantDomain_* (till exempel *TailspinToysIncorporated.onmicrosoft. </span> com*) och *_TenantAdmin-autentiseringsuppgifter_* (använd dina globala administratörsautentiseringsuppgifter) och begär sedan samtycke.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="5dcfc-165">Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="5dcfc-166">När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="5dcfc-167">Filen sparas i **C:\windows\system32** som standard.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="5dcfc-168">Utdatafilen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="5dcfc-169">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="5dcfc-169">User Name</span></span>
    
- <span data-ttu-id="5dcfc-170">Användar-ID (användarens e-postadress)</span><span class="sxs-lookup"><span data-stu-id="5dcfc-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="5dcfc-171">Centraliserad distribution är klar - om de återstående objekten har värdet sant</span><span class="sxs-lookup"><span data-stu-id="5dcfc-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="5dcfc-172">Office-plan - Planen för Office de är licensierade för</span><span class="sxs-lookup"><span data-stu-id="5dcfc-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="5dcfc-173">Office aktiverat - om de har aktiverat Office</span><span class="sxs-lookup"><span data-stu-id="5dcfc-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="5dcfc-174">Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda</span><span class="sxs-lookup"><span data-stu-id="5dcfc-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="5dcfc-175">Användar- och grupptilldelningar</span><span class="sxs-lookup"><span data-stu-id="5dcfc-175">User and group assignments</span></span>

<span data-ttu-id="5dcfc-176">Funktionen Centraliserad distribution stöder för närvarande de flesta grupper som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributionslistor och säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-176">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5dcfc-177">Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-177">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="5dcfc-178">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klienten.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-178">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="5dcfc-179">Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-179">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="5dcfc-180">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-180">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in.</span></span> <span data-ttu-id="5dcfc-181">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-181">Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="5dcfc-183">Ta reda på om en grupp innehåller kapslade grupper</span><span class="sxs-lookup"><span data-stu-id="5dcfc-183">Find out if a group contains nested groups</span></span>

<span data-ttu-id="5dcfc-184">Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-184">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="5dcfc-185">Om du anger gruppnamnet i fältet **Till** i ett e-postmeddelande och sedan väljer gruppnamnet när det lösers visas om det innehåller användare eller kapslade grupper.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-185">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="5dcfc-186">I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-186">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Fliken Medlemmar på Kontaktkortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="5dcfc-188">You can do the opposite query by resolving the group to see if it's a member of any group.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-188">You can do the opposite query by resolving the group to see if it's a member of any group.</span></span> <span data-ttu-id="5dcfc-189">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-189">In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Fliken Medlemskap i Kontaktkortet i Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="5dcfc-191">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-191">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group.</span></span> <span data-ttu-id="5dcfc-192">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-192">For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="5dcfc-193">Kontakta Microsoft om du behöver support</span><span class="sxs-lookup"><span data-stu-id="5dcfc-193">Contacting Microsoft for support</span></span>

<span data-ttu-id="5dcfc-194">Om du eller dina användare stöter på problem med att läsa in tillägget när du använder Office-appar för webben (Word, Excel osv.), som har distribuerats centralt, kan du behöva kontakta Microsoft-supporten ([läs mer](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="5dcfc-194">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="5dcfc-195">Ange följande information om din Microsoft 365-miljö i supportbiljetten.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-195">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="5dcfc-196">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="5dcfc-196">**Platform**</span></span>|<span data-ttu-id="5dcfc-197">**Felsökningsinformation**</span><span class="sxs-lookup"><span data-stu-id="5dcfc-197">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5dcfc-198">Office</span><span class="sxs-lookup"><span data-stu-id="5dcfc-198">Office</span></span>  <br/> | <span data-ttu-id="5dcfc-199">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="5dcfc-199">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="5dcfc-200">Klientorganisationens id ( [så här gör du](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="5dcfc-200">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="5dcfc-201">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="5dcfc-201">CorrelationID.</span></span> <span data-ttu-id="5dcfc-202">Visa källan till en av kontorets sidor och leta efter värdet för korrelations-ID och skicka det till stöd:</span><span class="sxs-lookup"><span data-stu-id="5dcfc-202">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="5dcfc-203">RTF-klienter (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="5dcfc-203">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="5dcfc-204">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="5dcfc-204">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="5dcfc-205">Bygg nummer på klientappen (helst som en skärmdump från **Fil/konto)**</span><span class="sxs-lookup"><span data-stu-id="5dcfc-205">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

