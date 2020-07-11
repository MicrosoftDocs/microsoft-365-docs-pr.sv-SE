---
title: Hantera tillägg i administrationscentret
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103117"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="8c004-103">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="8c004-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8c004-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8c004-104">The admin center is changing.</span></span> <span data-ttu-id="8c004-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8c004-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8c004-106">Office-tillägg hjälper dig att anpassa dina dokument och effektivisera ditt sätt att komma åt information på webben (se [Börja använda office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="8c004-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="8c004-107">När en administratör har distribuerat tillägg för användare i en organisation kan administratören inaktivera eller aktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.</span><span class="sxs-lookup"><span data-stu-id="8c004-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="8c004-108">Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8c004-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="8c004-109">Tilläggstillstånd</span><span class="sxs-lookup"><span data-stu-id="8c004-109">Add-in states</span></span>

<span data-ttu-id="8c004-110">Ett tillägg kan vara i läget **På** eller **Av.**</span><span class="sxs-lookup"><span data-stu-id="8c004-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="8c004-111">**Statligt**</span><span class="sxs-lookup"><span data-stu-id="8c004-111">**State**</span></span>|<span data-ttu-id="8c004-112">**Hur tillståndet inträffar**</span><span class="sxs-lookup"><span data-stu-id="8c004-112">**How the state occurs**</span></span>|<span data-ttu-id="8c004-113">**Effekt**</span><span class="sxs-lookup"><span data-stu-id="8c004-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8c004-114">**Aktiva**</span><span class="sxs-lookup"><span data-stu-id="8c004-114">**Active**</span></span>  <br/> |<span data-ttu-id="8c004-115">Admin laddade upp tillägget och tilldelade det till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="8c004-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="8c004-116">Användare och grupper som tilldelats tillägget ser det i relevanta klienter.</span><span class="sxs-lookup"><span data-stu-id="8c004-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="8c004-117">**Avstängd**</span><span class="sxs-lookup"><span data-stu-id="8c004-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="8c004-118">Admin har inaktiverat tillägget.</span><span class="sxs-lookup"><span data-stu-id="8c004-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="8c004-119">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="8c004-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="8c004-120">Om tilläggstillståndet ändras till Aktiv har användarna och grupperna åtkomst till det igen.</span><span class="sxs-lookup"><span data-stu-id="8c004-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="8c004-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="8c004-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="8c004-122">Admin har tagit bort tillägget.</span><span class="sxs-lookup"><span data-stu-id="8c004-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="8c004-123">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="8c004-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="8c004-124">Överväg att ta bort ett tillägg om ingen längre använder det.</span><span class="sxs-lookup"><span data-stu-id="8c004-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="8c004-125">Det kan till exempel vara meningsfullt att inaktivera ett tillägg om ett tillägg bara används under vissa tider på året.</span><span class="sxs-lookup"><span data-stu-id="8c004-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="8c004-126">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="8c004-126">Delete an add-in</span></span>

<span data-ttu-id="8c004-127">Du kan också ta bort ett tillägg som har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="8c004-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="8c004-128">Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="8c004-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="8c004-129">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="8c004-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8c004-130">Klicka på **Ta bort tillägget**.</span><span class="sxs-lookup"><span data-stu-id="8c004-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="8c004-131">Ta bort knappen Tillägg i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="8c004-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="8c004-132">Validera dina val och välj **Ta bort tillägget**.</span><span class="sxs-lookup"><span data-stu-id="8c004-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="8c004-133">Redigera tilläggsåtkomst</span><span class="sxs-lookup"><span data-stu-id="8c004-133">Edit add-in access</span></span>

<span data-ttu-id="8c004-134">Efter distribution, administratörer kan också hantera användaråtkomst till tillägg.</span><span class="sxs-lookup"><span data-stu-id="8c004-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="8c004-135">Gå till sidan **Settings**  >  **Inställningarstjänster & tillägg i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="8c004-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="8c004-136">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="8c004-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8c004-137">Klicka på **Redigera** under **Vem har Access**.</span><span class="sxs-lookup"><span data-stu-id="8c004-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="8c004-138">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="8c004-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="8c004-139">Förhindra hämtningar av tillägg genom att stänga av Office Store för alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="8c004-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="8c004-140">Outlook-tilläggsinstallation hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c004-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="8c004-141">Som organisation kanske du vill förhindra hämtning av nya Office-tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="8c004-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="8c004-142">Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisationsgodkända tillägg distribueras till användare inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="8c004-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="8c004-143">**Så här inaktiverar du tilläggsförvärv**</span><span class="sxs-lookup"><span data-stu-id="8c004-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="8c004-144">I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="8c004-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="8c004-145">Välj **Användarindagna appar och tjänster**.</span><span class="sxs-lookup"><span data-stu-id="8c004-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="8c004-146">Avmarkera alternativet om du vill att användarna ska kunna komma åt Office-arkivet.</span><span class="sxs-lookup"><span data-stu-id="8c004-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="8c004-147">Detta förhindrar att alla användare hämtar följande tillägg från butiken.</span><span class="sxs-lookup"><span data-stu-id="8c004-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="8c004-148">Tillägg för Word, Excel och PowerPoint 2016 från:</span><span class="sxs-lookup"><span data-stu-id="8c004-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="8c004-149">Windows</span><span class="sxs-lookup"><span data-stu-id="8c004-149">Windows</span></span>
    
  - <span data-ttu-id="8c004-150">Mac</span><span class="sxs-lookup"><span data-stu-id="8c004-150">Mac</span></span>
    
  - <span data-ttu-id="8c004-151">Office</span><span class="sxs-lookup"><span data-stu-id="8c004-151">Office</span></span>
    
    
- <span data-ttu-id="8c004-152">Förvärv som startar inom **AppSource**</span><span class="sxs-lookup"><span data-stu-id="8c004-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="8c004-153">Tillägg i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c004-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="8c004-154">En användare som försöker komma åt arkivet ser följande meddelande: **Tyvärr har Microsoft 365 konfigurerats för att förhindra individuellt förvärv av Office Store-tillägg.**</span><span class="sxs-lookup"><span data-stu-id="8c004-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="8c004-155">Stöd för att stänga av Office Store finns i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="8c004-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="8c004-156">Windows: 16.0.9001 - För närvarande tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8c004-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="8c004-157">Mac: 16.10.18011401 - För närvarande tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8c004-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="8c004-158">iOS: 2.9.18010804 - För närvarande tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8c004-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="8c004-159">Webben - För närvarande tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8c004-159">The web - Currently available.</span></span>
    
<span data-ttu-id="8c004-160">Detta hindrar inte en administratör från att använda centraliserad distribution för att tilldela ett tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="8c004-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="8c004-161">Om du vill förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggningen så att den bara använder organisationskontot.</span><span class="sxs-lookup"><span data-stu-id="8c004-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="8c004-162">Mer information finns [i Identitet, autentisering och auktorisering i Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c004-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="8c004-163">Mer om slutanvändarens upplevelse med tillägg</span><span class="sxs-lookup"><span data-stu-id="8c004-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="8c004-164">När du har distribuerat ett tillägg kan slutanvändarna börja använda det i sina Office-program (se [Börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="8c004-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="8c004-165">Tillägget visas på alla plattformar som tillägget stöder.</span><span class="sxs-lookup"><span data-stu-id="8c004-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="8c004-166">Om tillägget stöder tilläggskommandon visas kommandona i menyfliksområdet i Office.</span><span class="sxs-lookup"><span data-stu-id="8c004-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="8c004-167">I följande exempel visas kommandot **Sökcitning** för tillägget **Källhänvisning.**</span><span class="sxs-lookup"><span data-stu-id="8c004-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Menyfliksområdet i Office med sökhänvisning](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="8c004-169">Om det distribuerade tillägget inte stöder tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8c004-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="8c004-170">I Word 2016, Excel 2016 eller PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="8c004-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="8c004-171">Välj **Infoga \> mina tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8c004-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="8c004-172">Välj fliken **Administratörshanterad** i fönstret Office-tillägg.</span><span class="sxs-lookup"><span data-stu-id="8c004-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="8c004-173">Dubbelklicka på det tillägg som du distribuerade tidigare (i det här exemplet **Citat** ).</span><span class="sxs-lookup"><span data-stu-id="8c004-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="8c004-174">![Fliken Hanterad administratör på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="8c004-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="8c004-175">I Outlook</span><span class="sxs-lookup"><span data-stu-id="8c004-175">In Outlook</span></span>

1. <span data-ttu-id="8c004-176">I **menyfliksområdet Hem** väljer du **Hämta tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8c004-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="8c004-177">![Knappen Butik i Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="8c004-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="8c004-178">Välj **Admin-hanterad** i den vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="8c004-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="8c004-179">Mer information</span><span class="sxs-lookup"><span data-stu-id="8c004-179">Learn more</span></span>

[<span data-ttu-id="8c004-180">Distribuera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="8c004-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="8c004-181">Läs mer om hur du skapar och skapar [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362).</span><span class="sxs-lookup"><span data-stu-id="8c004-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="8c004-182">[Använd centraliserade PowerShell-cmdlets för att hantera tillägg](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8c004-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="8c004-183">Felsöka: Användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="8c004-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="8c004-184">Minderåriga och förvärva tillägg från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8c004-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)