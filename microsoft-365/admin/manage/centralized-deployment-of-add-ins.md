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
ms.openlocfilehash: c89cb801a5b2fcad87227feaf4228b0dcabcf609
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464056"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="26b7e-103">Avgöra om centraliserad distribution av tillägg fungerar för din organisation</span><span class="sxs-lookup"><span data-stu-id="26b7e-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="26b7e-104">Centraliserad distribution är det rekommenderade och mest omfattande sättet för de flesta kunder att distribuera Office-tillägg till användare och grupper inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="26b7e-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="26b7e-105">Om du är administratör kan du använda den här vägledningen för att ta reda på om din organisation och dina användare uppfyller kraven för att kunna använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="26b7e-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="26b7e-106">Centraliserad distribution har följande fördelar:</span><span class="sxs-lookup"><span data-stu-id="26b7e-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="26b7e-107">En global administratör kan tilldela ett tillägg direkt till en användare, till flera användare via en grupp eller till alla i organisationen.</span><span class="sxs-lookup"><span data-stu-id="26b7e-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="26b7e-108">När det relevanta Office-programmet startas hämtas tillägget automatiskt.</span><span class="sxs-lookup"><span data-stu-id="26b7e-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="26b7e-109">Om tillägget har stöd för tilläggs kommandon visas tillägget automatiskt i menyfliksområdet i Office-programmet.</span><span class="sxs-lookup"><span data-stu-id="26b7e-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="26b7e-110">Tillägg visas inte längre för användare om administratören inaktiverar eller tar bort tillägget, eller om användaren tas bort från Azure Active Directory eller från en grupp som tillägget är tilldelat till.</span><span class="sxs-lookup"><span data-stu-id="26b7e-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="26b7e-111">Centraliserad distribution stöder tre Station ära datorer, Mac och online Office-appar.</span><span class="sxs-lookup"><span data-stu-id="26b7e-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="26b7e-112">Centraliserad distribution stöder även iOS och Android (endast Outlook Mobile-tillägg).</span><span class="sxs-lookup"><span data-stu-id="26b7e-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="26b7e-113">Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.</span><span class="sxs-lookup"><span data-stu-id="26b7e-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="26b7e-114">Krav</span><span class="sxs-lookup"><span data-stu-id="26b7e-114">Requirements</span></span>

<span data-ttu-id="26b7e-115">Centraliserad distribution av tillägg kräver att användarna använder Microsoft 365-appar för Enterprise eller Microsoft 365 Business Premium (och är inloggade på Office med deras organisations-ID) och har Exchange Online och aktiva Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="26b7e-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="26b7e-116">Abonnemangs katalogen måste antingen vara i eller sammankopplad till Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="26b7e-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="26b7e-117">Du kan se specifika krav för Office och Exchange nedan eller använda kompatibilitetskontrollen för [centraliserad distribution](#centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="26b7e-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="26b7e-118">Centraliserad distribution stöder inte följande:</span><span class="sxs-lookup"><span data-stu-id="26b7e-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="26b7e-119">Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013</span><span class="sxs-lookup"><span data-stu-id="26b7e-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="26b7e-120">En lokal katalogtjänst</span><span class="sxs-lookup"><span data-stu-id="26b7e-120">An on-premises directory service</span></span>
- <span data-ttu-id="26b7e-121">Tillägg distribution till en Exchange On-lokala-postlåda</span><span class="sxs-lookup"><span data-stu-id="26b7e-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="26b7e-122">Tilläggsdistribution till SharePoint</span><span class="sxs-lookup"><span data-stu-id="26b7e-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="26b7e-123">Teams-appar</span><span class="sxs-lookup"><span data-stu-id="26b7e-123">Teams apps</span></span>
- <span data-ttu-id="26b7e-124">Distribution av COM- (Component Object Model) och VSTO-tilläggen (Visual Studio Tools for Office)</span><span class="sxs-lookup"><span data-stu-id="26b7e-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="26b7e-125">Distributioner av Microsoft 365 som inte innehåller Exchange, till exempel Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="26b7e-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="26b7e-126">Office-krav</span><span class="sxs-lookup"><span data-stu-id="26b7e-126">Office Requirements</span></span>

- <span data-ttu-id="26b7e-127">För Word-, Excel-och PowerPoint-tillägg måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="26b7e-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="26b7e-128">På en Windows-enhet, version 1704 eller senare av Microsoft 365-program för företag eller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="26b7e-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="26b7e-129">På en Mac, version 15,34 eller senare.</span><span class="sxs-lookup"><span data-stu-id="26b7e-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="26b7e-130">För Outlook måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="26b7e-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="26b7e-131">Version 1701 eller senare av Microsoft 365-appar för Enterprise eller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="26b7e-131">Version 1701 or later of Microsoft 365 Apps for enterprise, or Microsoft 365 Business Premium.</span></span>
  - <span data-ttu-id="26b7e-132">Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="26b7e-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="26b7e-133">Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="26b7e-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="26b7e-134">Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="26b7e-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="26b7e-135">Version 16.0.9318.1000 eller senare av Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="26b7e-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="26b7e-136">Version 2.75.0 eller senare av Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="26b7e-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="26b7e-137">Version 2.2.145 eller senare av Outlook Mobile för Android</span><span class="sxs-lookup"><span data-stu-id="26b7e-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="26b7e-138">\* MSI-versioner av Outlook Visa installerade tillägg i Outlook-menyfliksområdet, inte avsnittet "mina tillägg".</span><span class="sxs-lookup"><span data-stu-id="26b7e-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="26b7e-139">Ta reda på om Microsoft 365-appar för företag är installerat</span><span class="sxs-lookup"><span data-stu-id="26b7e-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="26b7e-140">För att använda Microsoft 365-appar för företag måste en användare ha ett Microsoft 365-konto och ha tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="26b7e-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="26b7e-141">Mer information finns i [Översikt över Microsoft 365-appar för företag](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="26b7e-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="26b7e-142">Det enklaste sättet att upptäcka om en användare har Microsoft 365-appar för företag installerat och har använt det nyligen, är att använda Microsoft Office-aktiverings rapporten, som är tillgänglig i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26b7e-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="26b7e-143">I rapporten visas en lista med alla användare som har aktiverat Microsoft 365-appar för företag under de senaste 7, 30, dagar, 90 eller 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="26b7e-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="26b7e-144">De kolumner i rapporten som är viktiga för centraliserad distribution är de för datoraktiveringar för Windows och Mac.</span><span class="sxs-lookup"><span data-stu-id="26b7e-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="26b7e-145">Du kan exportera rapporten till Excel.</span><span class="sxs-lookup"><span data-stu-id="26b7e-145">You can export the report to Excel.</span></span> <span data-ttu-id="26b7e-146">Mer information om rapporten finns i [Microsoft 365-rapporter i administrations centret – Microsoft Office-aktiveringar](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="26b7e-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="26b7e-147">Om du inte vill använda aktiverings rapporten kan du be en användare öppna ett Office-program som Word på sin dator och sedan välja ett **fil** \> **konto**.</span><span class="sxs-lookup"><span data-stu-id="26b7e-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="26b7e-148">Under **produkt information**bör du se **abonnemangs produkten** och **Microsoft 365 för företag**eller Microsoft 365 Business Premium, liknande vad som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="26b7e-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**,or Microsoft 365 Business Premium, similar to what is shown in the following image.</span></span>

![Produkt information i ett Office-program](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="26b7e-150">Om du behöver hjälp med Microsoft 365-appar för företag kan du läsa [fel söknings tips för microsoft 365-appar för företag](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="26b7e-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="26b7e-151">Exchange Online-krav</span><span class="sxs-lookup"><span data-stu-id="26b7e-151">Exchange Online requirements</span></span>

<span data-ttu-id="26b7e-152">Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="26b7e-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="26b7e-153">Administratörs distributionen av tillägg och de användare som tar emot dessa tillägg måste finnas i en version av Exchange Online som stöder OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="26b7e-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="26b7e-p109">Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="26b7e-p109">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="26b7e-156">Kompatibilitetskontroll för centraliserad distribution</span><span class="sxs-lookup"><span data-stu-id="26b7e-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="26b7e-157">Med kompatibilitetskontrollen för centraliserad distribution kan du kontrol lera om användarna på din klient organisation har ställts in för att använda centraliserad distribution för Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="26b7e-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="26b7e-158">Kompatibilitetskontrollen krävs inte för Outlook-stöd.</span><span class="sxs-lookup"><span data-stu-id="26b7e-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="26b7e-159">Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="26b7e-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="26b7e-160">Köra kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="26b7e-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="26b7e-161">Öppna ett PowerShell.exe-fönster med förhöjd rättighet.</span><span class="sxs-lookup"><span data-stu-id="26b7e-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="26b7e-162">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="26b7e-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="26b7e-163">Kör kommandot **Invoke-CompatabilityCheck** :</span><span class="sxs-lookup"><span data-stu-id="26b7e-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="26b7e-164">I det här kommandot uppmanas du att ange  *_TenantDomain_* (till exempel *TailspinToysIncorporated. onmicrosoft. </span> com*) och  *_TenantAdmin_* -autentiseringsuppgifter (Använd dina globala administratörs uppgifter) och begär sedan medgivande.</span><span class="sxs-lookup"><span data-stu-id="26b7e-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="26b7e-165">Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="26b7e-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="26b7e-166">När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats.</span><span class="sxs-lookup"><span data-stu-id="26b7e-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="26b7e-167">Filen sparas som standard till **C:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="26b7e-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="26b7e-168">Utdatafilen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="26b7e-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="26b7e-169">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="26b7e-169">User Name</span></span>
    
- <span data-ttu-id="26b7e-170">Användar-ID (användarens e-postadress)</span><span class="sxs-lookup"><span data-stu-id="26b7e-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="26b7e-171">Centraliserad distribution är klar - om de återstående objekten har värdet sant</span><span class="sxs-lookup"><span data-stu-id="26b7e-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="26b7e-172">Kontors plan – den plan där Office de är licensierade för</span><span class="sxs-lookup"><span data-stu-id="26b7e-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="26b7e-173">Office aktiverat - om de har aktiverat Office</span><span class="sxs-lookup"><span data-stu-id="26b7e-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="26b7e-174">Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda</span><span class="sxs-lookup"><span data-stu-id="26b7e-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="26b7e-175">Multifaktorautentisering stöds inte när du använder PowerShell-modulen för central distribution.</span><span class="sxs-lookup"><span data-stu-id="26b7e-175">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="26b7e-176">Användar- och grupptilldelningar</span><span class="sxs-lookup"><span data-stu-id="26b7e-176">User and group assignments</span></span>

<span data-ttu-id="26b7e-177">Funktionen för centraliserad distribution stöder för närvarande de flesta av grupperna som stöds av Azure Active Directory, inklusive Microsoft 365-grupper, distributions listor och säkerhets grupper.</span><span class="sxs-lookup"><span data-stu-id="26b7e-177">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="26b7e-178">Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="26b7e-178">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="26b7e-179">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="26b7e-179">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="26b7e-180">Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="26b7e-180">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="26b7e-p113">Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="26b7e-p113">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram över försäljnings avdelning](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="26b7e-184">Ta reda på om en grupp innehåller kapslade grupper</span><span class="sxs-lookup"><span data-stu-id="26b7e-184">Find out if a group contains nested groups</span></span>

<span data-ttu-id="26b7e-185">Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook.</span><span class="sxs-lookup"><span data-stu-id="26b7e-185">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="26b7e-186">Om du anger grupp namnet i fältet **till** i ett e-postmeddelande och sedan väljer grupp namnet när det matchas visas det om det innehåller användare eller kapslade grupper.</span><span class="sxs-lookup"><span data-stu-id="26b7e-186">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="26b7e-187">I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.</span><span class="sxs-lookup"><span data-stu-id="26b7e-187">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Fliken medlemmar på kontakt kortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="26b7e-p115">Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet.</span><span class="sxs-lookup"><span data-stu-id="26b7e-p115">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Fliken medlemskap på kontakt kortet i Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="26b7e-p116">Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="26b7e-p116">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="26b7e-194">Kontakta Microsoft om du behöver support</span><span class="sxs-lookup"><span data-stu-id="26b7e-194">Contacting Microsoft for support</span></span>

<span data-ttu-id="26b7e-195">Om du eller användarna drabbas av problem med att ladda tillägget när du använder Office-program för webben (Word, Excel, osv.), kan det hända att du måste kontakta Microsoft Support ([Läs mer](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="26b7e-195">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="26b7e-196">Ange följande information om din Microsoft 365-miljö i support ärendet.</span><span class="sxs-lookup"><span data-stu-id="26b7e-196">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="26b7e-197">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="26b7e-197">**Platform**</span></span>|<span data-ttu-id="26b7e-198">**Felsökningsinformation**</span><span class="sxs-lookup"><span data-stu-id="26b7e-198">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="26b7e-199">Office</span><span class="sxs-lookup"><span data-stu-id="26b7e-199">Office</span></span>  <br/> | <span data-ttu-id="26b7e-200">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="26b7e-200">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="26b7e-201">Klientorganisationens id ( [så här gör du](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="26b7e-201">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="26b7e-202">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="26b7e-202">CorrelationID.</span></span> <span data-ttu-id="26b7e-203">Visa källan för en av Office-sidorna och leta efter Correlation-ID-värdet och skicka det till stöd:</span><span class="sxs-lookup"><span data-stu-id="26b7e-203">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="26b7e-204">RTF-klienter (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="26b7e-204">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="26b7e-205">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="26b7e-205">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="26b7e-206">Build-nummer för klient programmet (helst som en skärm bild från **fil/konto**)</span><span class="sxs-lookup"><span data-stu-id="26b7e-206">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
