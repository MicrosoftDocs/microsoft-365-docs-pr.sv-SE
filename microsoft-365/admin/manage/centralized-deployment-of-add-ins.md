---
title: Ta reda på om centraliserad distribution av tillägg fungerar för din organisation
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ta reda på om din Office 365-klientorganisation och -användare uppfyller kraven, så att du kan använda centraliserad distribution för att distribuera Office-tillägg.
ms.openlocfilehash: d6b81a5ac5ef3b5287810110e5d0582bf34bff93
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189017"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="16946-103">Ta reda på om centraliserad distribution av tillägg fungerar för din organisation</span><span class="sxs-lookup"><span data-stu-id="16946-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="16946-104">Centraliserad distribution är den rekommenderade och mest funktionsrika metoden för de flesta kunder att distribuera Office-tillägg till användare och grupper inom Office 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="16946-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization.</span></span> <span data-ttu-id="16946-105">Om du är administratör kan du använda den här vägledningen för att avgöra om din klient och dina användare uppfyller kraven så att du kan använda centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="16946-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="16946-106">Centraliserad distribution stöder Windows-, Mac-, iOS-, Android- och Online Office-appar.</span><span class="sxs-lookup"><span data-stu-id="16946-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="16946-107">Det kan ta upp till 24 timmar för ett tillägg att visas för klienten och alla användare.</span><span class="sxs-lookup"><span data-stu-id="16946-107">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="16946-108">Krav</span><span class="sxs-lookup"><span data-stu-id="16946-108">Requirements</span></span>

<span data-ttu-id="16946-109">Centraliserad distribution av tillägg kräver att användarna använder Office 365 ProPlus (och är inloggade på Office med sitt organisations-ID) och har Exchange Online- och active Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="16946-109">Centralized deployment of add-ins requires that the users are using Office 365 ProPlus (and are signed into Office using their Organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="16946-110">Din subscription'd-katalog måste antingen vara i eller federeras med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="16946-110">Your subscription'd directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="16946-111">Du kan visa specifika krav för Office och Exchange nedan eller använda [kompatibilitetskontrollen för centraliserad distribution i Office 365](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="16946-111">You can view specific requirements for Office and Exchange below, or use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="16946-112">Centraliserad distribution stöder inte följande:</span><span class="sxs-lookup"><span data-stu-id="16946-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="16946-113">Tillägg som är inriktade på Word, Excel eller PowerPoint i Office 2013</span><span class="sxs-lookup"><span data-stu-id="16946-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="16946-114">En lokal katalogtjänst</span><span class="sxs-lookup"><span data-stu-id="16946-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="16946-115">Tilläggsdistribution till SharePoint</span><span class="sxs-lookup"><span data-stu-id="16946-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="16946-116">Team-appar</span><span class="sxs-lookup"><span data-stu-id="16946-116">Teams apps</span></span>
   
- <span data-ttu-id="16946-117">Distribution av COM- (Component Object Model) och VSTO-tilläggen (Visual Studio Tools for Office)</span><span class="sxs-lookup"><span data-stu-id="16946-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="16946-118">Distributioner av Office 365 som inte inkluderar Exchange, till exempel Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="16946-118">Deployments of Office 365 that do not include Exchange such as Office 365 Business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="16946-119">Office-krav</span><span class="sxs-lookup"><span data-stu-id="16946-119">Office Requirements</span></span>

- <span data-ttu-id="16946-120">För Word-, Excel- och PowerPoint-tillägg måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="16946-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="16946-121">På en Windows-enhet, version 1704 eller senare av Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="16946-121">On a Windows device, Version 1704 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="16946-122">På en Mac, version 15.34 eller senare.</span><span class="sxs-lookup"><span data-stu-id="16946-122">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="16946-123">För Outlook måste användarna använda något av följande:</span><span class="sxs-lookup"><span data-stu-id="16946-123">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="16946-124">Version 1701 eller senare av Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="16946-124">Version 1701 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="16946-125">Version 1808 eller senare av Office Professional Plus 2019 eller Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="16946-125">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="16946-126">Version 16.0.4494.1000 eller senare av Office Professional Plus 2016 (MSI) eller Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="16946-126">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="16946-127">Version 15.0.4937.1000 eller senare av Office Professional Plus 2013 (MSI) eller Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="16946-127">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="16946-128">Version 16.0.9318.1000 eller senare av Office 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="16946-128">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="16946-129">Version 2.75.0 eller senare av Outlook Mobile för iOS</span><span class="sxs-lookup"><span data-stu-id="16946-129">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="16946-130">Version 2.2.145 eller senare av Outlook Mobile för Android</span><span class="sxs-lookup"><span data-stu-id="16946-130">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="16946-131">\*MSI-versioner av Outlook visar administratörsinstallerade tillägg i lämpligt menyfliksområdet i Outlook, inte avsnittet "Mina tillägg".</span><span class="sxs-lookup"><span data-stu-id="16946-131">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a><span data-ttu-id="16946-132">Ta reda på om Office 365 ProPlus är installerat</span><span class="sxs-lookup"><span data-stu-id="16946-132">Find out if Office 365 ProPlus is installed</span></span>

<span data-ttu-id="16946-133">Om du vill använda Office 365 ProPlus måste en användare ha ett Office 365-konto och ha tilldelats en licens.</span><span class="sxs-lookup"><span data-stu-id="16946-133">To use Office 365 ProPlus, a user must have an Office 365 account and must have been assigned a license.</span></span> <span data-ttu-id="16946-134">Mer information finns i [Översikt över Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="16946-134">For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="16946-135">Det enklaste sättet att identifiera om en användare har Office 365 ProPlus installerat och har använt det nyligen är att använda Microsoft Office Aktiveringsrapporten, som finns i Microsoft 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="16946-135">The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="16946-136">Rapporten innehåller en lista med alla användare som har aktiverat Office 365 ProPlus inom de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna.</span><span class="sxs-lookup"><span data-stu-id="16946-136">The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="16946-137">De kolumner i rapporten som är viktiga för centraliserad distribution är de för datoraktiveringar för Windows och Mac.</span><span class="sxs-lookup"><span data-stu-id="16946-137">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="16946-138">Du kan exportera rapporten till Excel.</span><span class="sxs-lookup"><span data-stu-id="16946-138">You can export the report to Excel.</span></span> <span data-ttu-id="16946-139">Mer information om rapporten finns i [Office 365-rapporter i administrationscenter - Microsoft Office-aktiveringar](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="16946-139">For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="16946-140">Om du inte vill använda rapporten Aktiveringar kan du be en användare att öppna ett Office-program som Word på datorn och sedan välja \> **Arkivkonto**. **File**</span><span class="sxs-lookup"><span data-stu-id="16946-140">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="16946-141">Under **Produktinformation** bör du se **Prenumerationsprodukt** och **Microsoft Office 365 ProPlus** som på bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="16946-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span></span>

![Produktinformation i ett Office-program](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
<span data-ttu-id="16946-143">Om du behöver hjälp med Office 365 ProPlus kan du läsa [Felsökningstips för Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="16946-143">For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="16946-144">Exchange Online-krav</span><span class="sxs-lookup"><span data-stu-id="16946-144">Exchange Online requirements</span></span>

<span data-ttu-id="16946-145">Microsoft Exchange lagrar tilläggsmanifesten i organisationens klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="16946-145">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="16946-146">Administratören som distribuerar tillägg och de användare som tar emot dessa tillägg måste finnas på en version av Exchange Online som stöder OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="16946-146">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="16946-p107">Fråga organisationens Exchange-administratör om vilken konfiguration som används. OAuth-anslutning per användare kan verifieras med hjälp av PowerShell-cmdleten [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="16946-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="office-365-centralized-deployment-compatibility-checker"></a><span data-ttu-id="16946-149">Kompatibilitetskontroll för centraliserad distribution av Office 365</span><span class="sxs-lookup"><span data-stu-id="16946-149">Office 365 Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="16946-p108">Med hjälp av kompatibilitetskontrollen för centraliserad distribution av Office 365 kan du kontrollera om användarna i klientorganisationen har konfigurerats för användning av centraliserad distribution för Word, Excel och PowerPoint. Kompatibilitetskontrollen krävs inte för Outlook-stöd. Ladda ned kompatibilitetskontrollen [här](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="16946-p108">Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="16946-153">Kör kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="16946-153">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="16946-154">Öppna ett PowerShell.exe-fönster med förhöjd rättighet.</span><span class="sxs-lookup"><span data-stu-id="16946-154">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="16946-155">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="16946-155">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="16946-156">Kör kommandot **Anropa-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="16946-156">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="16946-157">som uppmanar dig för *_TenantDomain_* (till exempel *TailspinToysIncorporated.onmicrosoft.</span> com*) och *_TenantAdmin-autentiseringsuppgifter_* (använd dina globala administratörsautentiseringsuppgifter) och begär sedan samtycke.</span><span class="sxs-lookup"><span data-stu-id="16946-157">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="16946-158">Beroende på antalet användare i klientorganisationen kan det ta några minuter eller några timmar att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="16946-158">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="16946-159">När verktyget körts klart har en utdatafil i kommaavgränsat format (.csv) genererats.</span><span class="sxs-lookup"><span data-stu-id="16946-159">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="16946-160">Filen sparas i **C:\windows\system32** som standard.</span><span class="sxs-lookup"><span data-stu-id="16946-160">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="16946-161">Utdatafilen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="16946-161">The output file contains the following information:</span></span>
  
- <span data-ttu-id="16946-162">Användarnamn</span><span class="sxs-lookup"><span data-stu-id="16946-162">User Name</span></span>
    
- <span data-ttu-id="16946-163">Användar-ID (användarens e-postadress)</span><span class="sxs-lookup"><span data-stu-id="16946-163">User ID (User's email address)</span></span>
    
- <span data-ttu-id="16946-164">Centraliserad distribution är klar - om de återstående objekten har värdet sant</span><span class="sxs-lookup"><span data-stu-id="16946-164">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="16946-165">Office-plan - Planen för Office de är licensierade för</span><span class="sxs-lookup"><span data-stu-id="16946-165">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="16946-166">Office aktiverat - om de har aktiverat Office</span><span class="sxs-lookup"><span data-stu-id="16946-166">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="16946-167">Postlåda som stöds - om de finns på en OAuth-aktiverad postlåda</span><span class="sxs-lookup"><span data-stu-id="16946-167">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="16946-168">Användar- och grupptilldelningar</span><span class="sxs-lookup"><span data-stu-id="16946-168">User and group assignments</span></span>

<span data-ttu-id="16946-169">Funktionen för centraliserad distribution har för närvarande stöd för de flesta grupper som stöds av Azure Active Directory, inklusive grupper, distributionslistor och säkerhetsgrupper för Office 365.</span><span class="sxs-lookup"><span data-stu-id="16946-169">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16946-170">Säkerhetsgrupper utan e-postaktivering stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="16946-170">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="16946-171">Centraliserad distribution stöder tilldelningar till enskilda användare, grupper och alla i klienten.</span><span class="sxs-lookup"><span data-stu-id="16946-171">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="16946-172">Centraliserad distribution har stöd för användare i grupper på översta nivå och grupper utan överordnade grupper, men inte för användare i kapslade grupper och grupper som har överordnade grupper.</span><span class="sxs-lookup"><span data-stu-id="16946-172">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="16946-p111">Ta en titt på följande exempel där Sandra, Sheila och gruppen Sales Department har tilldelats till ett tillägg. Eftersom West Coast Sales Department är en kapslad grupp, tilldelas Jens och Erik inte till ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="16946-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagram över försäljningsavdelningen](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="16946-176">Ta reda på om en grupp innehåller kapslade grupper</span><span class="sxs-lookup"><span data-stu-id="16946-176">Find out if a group contains nested groups</span></span>

<span data-ttu-id="16946-177">Det enklaste sättet att upptäcka om en grupp innehåller kapslade grupper är att visa gruppens kontaktkort i Outlook.</span><span class="sxs-lookup"><span data-stu-id="16946-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="16946-178">Om du anger gruppnamnet i fältet **Till** i ett e-postmeddelande och sedan väljer gruppnamnet när det lösers visas om det innehåller användare eller kapslade grupper.</span><span class="sxs-lookup"><span data-stu-id="16946-178">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="16946-179">I exemplet nedan visas inga användare och bara två undergrupper på fliken **Medlemmar** för Outlook-kontaktkortet för Test Group.</span><span class="sxs-lookup"><span data-stu-id="16946-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Fliken Medlemmar på Kontaktkortet i Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="16946-p113">Du kan göra motsatt fråga genom att matcha gruppen och ta reda på om den är medlem i en grupp. I exemplet nedan kan du se att Sub Group 1 är medlem i Test Group under fliken **medlemskap** för Outlook-kontaktkortet.</span><span class="sxs-lookup"><span data-stu-id="16946-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Fliken Medlemskap i Outlook-kontaktkortet](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="16946-p114">Du kan också använda Azure Active Directory Graph API till att köra frågor för att hitta listan med grupper inom en grupp. Mer information finns i [Åtgärder för grupper | Referens för Graph API](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="16946-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="16946-186">Kontakta Microsoft om du behöver support</span><span class="sxs-lookup"><span data-stu-id="16946-186">Contacting Microsoft for support</span></span>

<span data-ttu-id="16946-187">Om du eller dina användare stöter på problem med att läsa in tillägget när du använder Office-appar för webben (Word, Excel osv.), som har distribuerats centralt, kan du behöva kontakta Microsoft-supporten ([läs mer](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="16946-187">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="16946-188">Ange följande information om din Office 365-miljö i supportärendet.</span><span class="sxs-lookup"><span data-stu-id="16946-188">Provide the following information about your Office 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="16946-189">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="16946-189">**Platform**</span></span>|<span data-ttu-id="16946-190">**Felsökningsinformation**</span><span class="sxs-lookup"><span data-stu-id="16946-190">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="16946-191">Office</span><span class="sxs-lookup"><span data-stu-id="16946-191">Office</span></span>  <br/> | <span data-ttu-id="16946-192">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="16946-192">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="16946-193">Klientorganisationens id ( [så här gör du](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span><span class="sxs-lookup"><span data-stu-id="16946-193">Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span></span>  <br/>  <span data-ttu-id="16946-194">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="16946-194">CorrelationID.</span></span> <span data-ttu-id="16946-195">Visa källan till en av kontorssidorna och leta efter värdet för korrelations-ID och skicka det till stöd:</span><span class="sxs-lookup"><span data-stu-id="16946-195">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="16946-196">RTF-klienter (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="16946-196">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="16946-197">Charles-/Fiddler-loggar</span><span class="sxs-lookup"><span data-stu-id="16946-197">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="16946-198">Bygg nummer på klientappen (helst som en skärmdump från **Arkiv/Konto)**</span><span class="sxs-lookup"><span data-stu-id="16946-198">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

