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
description: Läs mer om hur du använder centraliserade tillägg för att distribuera tillägg till användare och grupper i organisationen.
ms.openlocfilehash: 0750b6c9b91bc5cbd67d227fadb304bfc6cf7537
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915404"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="6352c-103">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="6352c-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6352c-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="6352c-104">The admin center is changing.</span></span> <span data-ttu-id="6352c-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6352c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="6352c-106">Office-tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda [dina Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="6352c-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="6352c-107">När en administratör har distribuerat tillägg för användare i en organisation kan administratören aktivera eller inaktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.</span><span class="sxs-lookup"><span data-stu-id="6352c-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="6352c-108">Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="6352c-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="6352c-109">Tilläggsstater</span><span class="sxs-lookup"><span data-stu-id="6352c-109">Add-in states</span></span>

<span data-ttu-id="6352c-110">Ett tillägg kan vara antingen i läget **På** **eller Av.**</span><span class="sxs-lookup"><span data-stu-id="6352c-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="6352c-111">**Delstat**</span><span class="sxs-lookup"><span data-stu-id="6352c-111">**State**</span></span>|<span data-ttu-id="6352c-112">**Hur tillståndet uppstår**</span><span class="sxs-lookup"><span data-stu-id="6352c-112">**How the state occurs**</span></span>|<span data-ttu-id="6352c-113">**Påverkan**</span><span class="sxs-lookup"><span data-stu-id="6352c-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6352c-114">**Aktiv**</span><span class="sxs-lookup"><span data-stu-id="6352c-114">**Active**</span></span>  <br/> |<span data-ttu-id="6352c-115">Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="6352c-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="6352c-116">Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.</span><span class="sxs-lookup"><span data-stu-id="6352c-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="6352c-117">**Inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="6352c-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="6352c-118">Administratören har inaktiverat tillägget.</span><span class="sxs-lookup"><span data-stu-id="6352c-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="6352c-119">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="6352c-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="6352c-120">Om tilläggstillståndet ändras till Aktivt får användare och grupper åtkomst till det igen.</span><span class="sxs-lookup"><span data-stu-id="6352c-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="6352c-121">**Borttagen**</span><span class="sxs-lookup"><span data-stu-id="6352c-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="6352c-122">Administratören har tagit bort tillägget.</span><span class="sxs-lookup"><span data-stu-id="6352c-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="6352c-123">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="6352c-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="6352c-124">Överväg att ta bort tillägg som ingen använder längre.</span><span class="sxs-lookup"><span data-stu-id="6352c-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="6352c-125">Det kan vara bra att stänga av ett tillägg om ett tillägg bara används under vissa tider på året.</span><span class="sxs-lookup"><span data-stu-id="6352c-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="6352c-126">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="6352c-126">Delete an add-in</span></span>

<span data-ttu-id="6352c-127">Du kan också ta bort ett tillägg som har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="6352c-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="6352c-128">I administrationscentret går du till **sidan**  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="6352c-129">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="6352c-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="6352c-130">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="6352c-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="6352c-131">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="6352c-132">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="6352c-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="6352c-133">Klicka **på Ta bort tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="6352c-134">Ta bort knappen Tillägg längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="6352c-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="6352c-135">Validera dina val och välj **Ta bort tillägg**.</span><span class="sxs-lookup"><span data-stu-id="6352c-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="6352c-136">Redigera åtkomst till tillägg</span><span class="sxs-lookup"><span data-stu-id="6352c-136">Edit add-in access</span></span>

<span data-ttu-id="6352c-137">Efter distributionen kan administratörer också hantera användaråtkomst till tillägg.</span><span class="sxs-lookup"><span data-stu-id="6352c-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="6352c-138">I administrationscentret går du till **sidan**  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="6352c-139">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="6352c-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="6352c-140">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="6352c-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="6352c-141">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="6352c-142">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="6352c-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="6352c-143">Klicka på **Redigera** under **Vem som har Åtkomst.**</span><span class="sxs-lookup"><span data-stu-id="6352c-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="6352c-144">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="6352c-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="6352c-145">Förhindra tilläggsnedladdningar genom att inaktivera Office Store för alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="6352c-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="6352c-146">Installation av Outlook-tillägg hanteras av en [annan process.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="6352c-146">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="6352c-147">Som organisation kanske du vill förhindra nedladdning av nya Office-tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="6352c-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="6352c-148">Det kan användas tillsammans med centraliserad distribution för att säkerställa att endast av organisationen godkända tillägg distribueras till användare inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="6352c-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="6352c-149">**Så här inaktiverar du datainsamling av tillägg**</span><span class="sxs-lookup"><span data-stu-id="6352c-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="6352c-150">I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="6352c-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="6352c-151">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="6352c-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="6352c-152">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="6352c-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="6352c-153">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="6352c-154">Välj **Användarägda appar och tjänster.**</span><span class="sxs-lookup"><span data-stu-id="6352c-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="6352c-155">Avmarkera alternativet att ge användare åtkomst till Office Store.</span><span class="sxs-lookup"><span data-stu-id="6352c-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="6352c-156">Det hindrar alla användare från att hämta följande tillägg från Store.</span><span class="sxs-lookup"><span data-stu-id="6352c-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="6352c-157">Tillägg för Word, Excel och PowerPoint 2016 från:</span><span class="sxs-lookup"><span data-stu-id="6352c-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="6352c-158">Windows</span><span class="sxs-lookup"><span data-stu-id="6352c-158">Windows</span></span>
    
  - <span data-ttu-id="6352c-159">Mac</span><span class="sxs-lookup"><span data-stu-id="6352c-159">Mac</span></span>
    
  - <span data-ttu-id="6352c-160">Office</span><span class="sxs-lookup"><span data-stu-id="6352c-160">Office</span></span>
    
    
- <span data-ttu-id="6352c-161">Datainsamling som startar i **AppSource**</span><span class="sxs-lookup"><span data-stu-id="6352c-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="6352c-162">Tillägg i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6352c-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="6352c-163">En användare som försöker komma åt Office Store får ett meddelande om att Microsoft 365 har konfigurerats för att förhindra enskilda datainsamlingar av **Office Store-tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="6352c-164">Stöd för att inaktivera Office Store är tillgängligt i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="6352c-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="6352c-165">Windows: 16.0.9001 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6352c-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="6352c-166">Mac: 16.10.18011401 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6352c-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="6352c-167">iOS: 2.9.18010804 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6352c-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="6352c-168">Webben – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6352c-168">The web - Currently available.</span></span>
    
<span data-ttu-id="6352c-169">Det hindrar inte att en administratör använder centraliserad distribution till att tilldela ett tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="6352c-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="6352c-170">Du kan förhindra att en användare loggar in med ett Microsoft-konto genom att begränsa inloggning till organisationskontot.</span><span class="sxs-lookup"><span data-stu-id="6352c-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="6352c-171">Mer information finns i [Identitet, autentisering och auktorisering i Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="6352c-171">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="6352c-172">Om du hindrar användare från att komma åt Office Store hindrar du dem också från att [separatinstallera Office-tillägg för testning.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="6352c-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="6352c-173">Mer om slutanvändarupplevelsen med tillägg</span><span class="sxs-lookup"><span data-stu-id="6352c-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="6352c-174">När du har distribuerat ett tillägg kan slutanvändarna börja använda det i Office-programmen (se Börja använda [ditt Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="6352c-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="6352c-175">Tillägget visas på alla plattformar som har stöd för det.</span><span class="sxs-lookup"><span data-stu-id="6352c-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="6352c-176">Om tillägget har stöd för tilläggskommandon visas de i Office menyfliksområde.</span><span class="sxs-lookup"><span data-stu-id="6352c-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="6352c-177">I följande exempel visas kommandot **Sök källhänvisning** för tillägget **Källhänvisningar.**</span><span class="sxs-lookup"><span data-stu-id="6352c-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Menyfliksområdet i Office med källhänvisningar för sökningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="6352c-179">Om det distribuerade tillägget inte har stöd för tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="6352c-180">I Word 2016, Excel 2016 eller PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="6352c-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="6352c-181">Välj **\> Infoga mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="6352c-182">Välj **fliken Administratör** hanterad i fönstret Office-tillägg.</span><span class="sxs-lookup"><span data-stu-id="6352c-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="6352c-183">Dubbelklicka på tillägget som du distribuerade tidigare (i det här exemplet **Källhänvisningar).**</span><span class="sxs-lookup"><span data-stu-id="6352c-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="6352c-184">![Fliken Administratör hanterad på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="6352c-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="6352c-185">I Outlook</span><span class="sxs-lookup"><span data-stu-id="6352c-185">In Outlook</span></span>

1. <span data-ttu-id="6352c-186">I **menyfliksområdet** Start **väljer du Hämta tillägg.**</span><span class="sxs-lookup"><span data-stu-id="6352c-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="6352c-187">![Knappen Lagra i Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="6352c-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="6352c-188">Välj **Administratör hanterad i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="6352c-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="6352c-189">Mer information</span><span class="sxs-lookup"><span data-stu-id="6352c-189">Learn more</span></span>

[<span data-ttu-id="6352c-190">Distribuera tillägg i administrations centret för</span><span class="sxs-lookup"><span data-stu-id="6352c-190">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="6352c-191">Läs mer om att skapa [och skapa Office-tillägg.](/office/dev/add-ins/overview/office-add-ins)</span><span class="sxs-lookup"><span data-stu-id="6352c-191">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="6352c-192">[Använd PowerShell-cmdlets för](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)centraliserad distribution för att hantera tillägg.</span><span class="sxs-lookup"><span data-stu-id="6352c-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="6352c-193">Felsökning: Användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="6352c-193">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="6352c-194">Minderåriga och köp av tillägg från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6352c-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)