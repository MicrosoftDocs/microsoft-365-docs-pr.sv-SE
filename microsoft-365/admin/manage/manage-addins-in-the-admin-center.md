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
ms.openlocfilehash: 836dfa7a0c1b6cf1550e5c139bc0ca36be8f5424
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470947"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="0a967-103">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="0a967-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="0a967-104">Office-tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda [dina Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="0a967-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="0a967-105">När en administratör har distribuerat tillägg för användare i en organisation kan administratören aktivera eller inaktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.</span><span class="sxs-lookup"><span data-stu-id="0a967-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="0a967-106">Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="0a967-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="0a967-107">Tilläggsstater</span><span class="sxs-lookup"><span data-stu-id="0a967-107">Add-in states</span></span>

<span data-ttu-id="0a967-108">Ett tillägg kan vara antingen i läget **På** **eller Av.**</span><span class="sxs-lookup"><span data-stu-id="0a967-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="0a967-109">**Delstat**</span><span class="sxs-lookup"><span data-stu-id="0a967-109">**State**</span></span>|<span data-ttu-id="0a967-110">**Hur tillståndet uppstår**</span><span class="sxs-lookup"><span data-stu-id="0a967-110">**How the state occurs**</span></span>|<span data-ttu-id="0a967-111">**Påverkan**</span><span class="sxs-lookup"><span data-stu-id="0a967-111">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a967-112">**Aktiv**</span><span class="sxs-lookup"><span data-stu-id="0a967-112">**Active**</span></span>  <br/> |<span data-ttu-id="0a967-113">Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="0a967-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="0a967-114">Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.</span><span class="sxs-lookup"><span data-stu-id="0a967-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="0a967-115">**Inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="0a967-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="0a967-116">Administratören har inaktiverat tillägget.</span><span class="sxs-lookup"><span data-stu-id="0a967-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="0a967-117">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="0a967-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="0a967-118">Om tilläggstillståndet ändras till Aktivt får användare och grupper åtkomst till det igen.</span><span class="sxs-lookup"><span data-stu-id="0a967-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="0a967-119">**Borttagen**</span><span class="sxs-lookup"><span data-stu-id="0a967-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="0a967-120">Administratören har tagit bort tillägget.</span><span class="sxs-lookup"><span data-stu-id="0a967-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="0a967-121">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="0a967-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="0a967-122">Överväg att ta bort tillägg som ingen använder längre.</span><span class="sxs-lookup"><span data-stu-id="0a967-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="0a967-123">Det kan vara bra att stänga av ett tillägg om ett tillägg bara används under vissa tider på året.</span><span class="sxs-lookup"><span data-stu-id="0a967-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="0a967-124">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="0a967-124">Delete an add-in</span></span>

<span data-ttu-id="0a967-125">Du kan också ta bort ett tillägg som har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="0a967-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="0a967-126">I administrationscentret går du till **sidan**  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0a967-127">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="0a967-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0a967-128">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="0a967-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0a967-129">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0a967-130">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="0a967-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0a967-131">Klicka **på Ta bort tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="0a967-132">Ta bort knappen Tillägg längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="0a967-132">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="0a967-133">Validera dina val och välj **Ta bort tillägg**.</span><span class="sxs-lookup"><span data-stu-id="0a967-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="0a967-134">Redigera åtkomst till tillägg</span><span class="sxs-lookup"><span data-stu-id="0a967-134">Edit add-in access</span></span>

<span data-ttu-id="0a967-135">Efter distributionen kan administratörer också hantera användaråtkomst till tillägg.</span><span class="sxs-lookup"><span data-stu-id="0a967-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="0a967-136">I administrationscentret går du till **sidan**  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0a967-137">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="0a967-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0a967-138">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="0a967-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0a967-139">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="0a967-140">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="0a967-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="0a967-141">Klicka på **Redigera** under **Vem som har Åtkomst.**</span><span class="sxs-lookup"><span data-stu-id="0a967-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="0a967-142">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="0a967-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="0a967-143">Förhindra tilläggsnedladdningar genom att inaktivera Office Store för alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="0a967-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="0a967-144">Installation av Outlook-tillägg hanteras av en [annan process.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="0a967-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="0a967-145">Som organisation kanske du vill förhindra nedladdning av nya Office-tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="0a967-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="0a967-146">Det kan användas tillsammans med centraliserad distribution för att säkerställa att endast av organisationen godkända tillägg distribueras till användare inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="0a967-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="0a967-147">**Så här inaktiverar du datainsamling av tillägg**</span><span class="sxs-lookup"><span data-stu-id="0a967-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="0a967-148">I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="0a967-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="0a967-149">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="0a967-149">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="0a967-150">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="0a967-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="0a967-151">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="0a967-152">Välj **Användarägda appar och tjänster.**</span><span class="sxs-lookup"><span data-stu-id="0a967-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="0a967-153">Avmarkera alternativet att ge användare åtkomst till Office Store.</span><span class="sxs-lookup"><span data-stu-id="0a967-153">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="0a967-154">Det hindrar alla användare från att hämta följande tillägg från Store.</span><span class="sxs-lookup"><span data-stu-id="0a967-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="0a967-155">Tillägg för Word, Excel och PowerPoint 2016 från:</span><span class="sxs-lookup"><span data-stu-id="0a967-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="0a967-156">Windows</span><span class="sxs-lookup"><span data-stu-id="0a967-156">Windows</span></span>
    
  - <span data-ttu-id="0a967-157">Mac</span><span class="sxs-lookup"><span data-stu-id="0a967-157">Mac</span></span>
    
  - <span data-ttu-id="0a967-158">Office</span><span class="sxs-lookup"><span data-stu-id="0a967-158">Office</span></span>
    
    
- <span data-ttu-id="0a967-159">Datainsamling som startar i **AppSource**</span><span class="sxs-lookup"><span data-stu-id="0a967-159">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="0a967-160">Tillägg i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a967-160">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="0a967-161">En användare som försöker komma åt Office Store får ett meddelande om att Microsoft 365 har konfigurerats för att förhindra enskilda datainsamlingar av **Office Store-tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="0a967-162">Stöd för att inaktivera Office Store är tillgängligt i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="0a967-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="0a967-163">Windows: 16.0.9001 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0a967-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="0a967-164">Mac: 16.10.18011401 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0a967-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="0a967-165">iOS: 2.9.18010804 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0a967-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="0a967-166">Webben – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0a967-166">The web - Currently available.</span></span>
    
<span data-ttu-id="0a967-167">Det hindrar inte att en administratör använder centraliserad distribution till att tilldela ett tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="0a967-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="0a967-168">Du kan förhindra att en användare loggar in med ett Microsoft-konto genom att begränsa inloggning till organisationskontot.</span><span class="sxs-lookup"><span data-stu-id="0a967-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="0a967-169">Mer information finns i [Identitet, autentisering och auktorisering i Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="0a967-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE]
> <span data-ttu-id="0a967-170">Om du hindrar användare från att komma åt Office Store hindrar du dem också från att [separatinstallera Office-tillägg för testning.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="0a967-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="0a967-171">Mer om slutanvändarupplevelsen med tillägg</span><span class="sxs-lookup"><span data-stu-id="0a967-171">More about the end user experience with add-ins</span></span>

<span data-ttu-id="0a967-172">När du har distribuerat ett tillägg kan slutanvändarna börja använda det i Office-programmen (se Börja använda [ditt Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="0a967-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="0a967-173">Tillägget visas på alla plattformar som har stöd för det.</span><span class="sxs-lookup"><span data-stu-id="0a967-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="0a967-174">Om tillägget har stöd för tilläggskommandon visas de i Office menyfliksområde.</span><span class="sxs-lookup"><span data-stu-id="0a967-174">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="0a967-175">I följande exempel visas kommandot **Sök källhänvisning** för tillägget **Källhänvisningar.**</span><span class="sxs-lookup"><span data-stu-id="0a967-175">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Menyfliksområdet i Office med källhänvisningar för sökningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="0a967-177">Om det distribuerade tillägget inte har stöd för tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="0a967-178">I Word 2016, Excel 2016 eller PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="0a967-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="0a967-179">Välj **\> Infoga mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="0a967-180">Välj **fliken Administratör** hanterad i fönstret Office-tillägg.</span><span class="sxs-lookup"><span data-stu-id="0a967-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="0a967-181">Dubbelklicka på tillägget som du distribuerade tidigare (i det här exemplet **Källhänvisningar).**</span><span class="sxs-lookup"><span data-stu-id="0a967-181">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="0a967-182">![Fliken Administratör hanterad på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="0a967-182">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="0a967-183">I Outlook</span><span class="sxs-lookup"><span data-stu-id="0a967-183">In Outlook</span></span>

1. <span data-ttu-id="0a967-184">I **menyfliksområdet** Start **väljer du Hämta tillägg.**</span><span class="sxs-lookup"><span data-stu-id="0a967-184">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="0a967-185">![Knappen Lagra i Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="0a967-185">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="0a967-186">Välj **Administratör hanterad i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="0a967-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="0a967-187">Mer information</span><span class="sxs-lookup"><span data-stu-id="0a967-187">Learn more</span></span>

[<span data-ttu-id="0a967-188">Distribuera tillägg i administrations centret för</span><span class="sxs-lookup"><span data-stu-id="0a967-188">Deploy add-ins in the admin center</span></span>](./manage-deployment-of-add-ins.md)

<span data-ttu-id="0a967-189">Läs mer om att skapa [och skapa Office-tillägg.](/office/dev/add-ins/overview/office-add-ins)</span><span class="sxs-lookup"><span data-stu-id="0a967-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="0a967-190">[Använd PowerShell-cmdlets för](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)centraliserad distribution för att hantera tillägg.</span><span class="sxs-lookup"><span data-stu-id="0a967-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md).</span></span>
  
[<span data-ttu-id="0a967-191">Felsökning: Användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="0a967-191">Troubleshoot: User not seeing add-ins</span></span>](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="0a967-192">Minderåriga och köp av tillägg från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0a967-192">Minors and acquiring add-ins from the Microsoft Store</span></span>](./minors-and-acquiring-addins-from-the-store.md)