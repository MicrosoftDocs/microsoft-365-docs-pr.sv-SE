---
title: Hantera tillägg i administrationscentret
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Läs mer om hur du använder centraliserade tillägg för att distribuera tillägg till användare och grupper i organisationen.
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636064"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="142d1-103">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="142d1-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="142d1-104">Office tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda [Office tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="142d1-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="142d1-105">När en administratör har distribuerat tillägg för användare i en organisation kan administratören aktivera eller inaktivera tillägg, redigera, ta bort och hantera åtkomst till tilläggen.</span><span class="sxs-lookup"><span data-stu-id="142d1-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="142d1-106">Mer information om hur du installerar tillägg från administrationscentret finns [i Distribuera tillägg i administrationscentret.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="142d1-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="142d1-107">Tilläggsstater</span><span class="sxs-lookup"><span data-stu-id="142d1-107">Add-in states</span></span>

<span data-ttu-id="142d1-108">Ett tillägg kan vara antingen i läget **På** **eller Av.**</span><span class="sxs-lookup"><span data-stu-id="142d1-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="142d1-109">Region</span><span class="sxs-lookup"><span data-stu-id="142d1-109">State</span></span> | <span data-ttu-id="142d1-110">Hur tillståndet uppstår</span><span class="sxs-lookup"><span data-stu-id="142d1-110">How the state occurs</span></span> | <span data-ttu-id="142d1-111">Påverkan</span><span class="sxs-lookup"><span data-stu-id="142d1-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="142d1-112">**Aktiv**</span><span class="sxs-lookup"><span data-stu-id="142d1-112">**Active**</span></span>  <br/> |<span data-ttu-id="142d1-113">Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="142d1-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="142d1-114">Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.</span><span class="sxs-lookup"><span data-stu-id="142d1-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="142d1-115">**Inaktiverad**</span><span class="sxs-lookup"><span data-stu-id="142d1-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="142d1-116">Administratören har inaktiverat tillägget.</span><span class="sxs-lookup"><span data-stu-id="142d1-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="142d1-117">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="142d1-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="142d1-118">Om tilläggstillståndet ändras till Aktivt får användare och grupper åtkomst till det igen.</span><span class="sxs-lookup"><span data-stu-id="142d1-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="142d1-119">**Borttagen**</span><span class="sxs-lookup"><span data-stu-id="142d1-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="142d1-120">Administratören har tagit bort tillägget.</span><span class="sxs-lookup"><span data-stu-id="142d1-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="142d1-121">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="142d1-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="142d1-122">Överväg att ta bort tillägg som ingen använder längre.</span><span class="sxs-lookup"><span data-stu-id="142d1-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="142d1-123">Det kan vara bra att stänga av ett tillägg om ett tillägg bara används under vissa tider på året.</span><span class="sxs-lookup"><span data-stu-id="142d1-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="142d1-124">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="142d1-124">Delete an add-in</span></span>

<span data-ttu-id="142d1-125">Du kan också ta bort ett tillägg som har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="142d1-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="142d1-126">I administrationscentret går du till **sidan Inställningar** tjänster  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="142d1-127">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="142d1-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="142d1-128">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="142d1-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="142d1-129">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="142d1-130">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="142d1-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="142d1-131">Klicka **på Ta bort tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="142d1-132">Ta bort knappen Tillägg längst ned till höger.</span><span class="sxs-lookup"><span data-stu-id="142d1-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="142d1-133">Validera dina val och välj **Ta bort tillägg**.</span><span class="sxs-lookup"><span data-stu-id="142d1-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="142d1-134">Redigera åtkomst till tillägg</span><span class="sxs-lookup"><span data-stu-id="142d1-134">Edit add-in access</span></span>

<span data-ttu-id="142d1-135">Efter distributionen kan administratörer också hantera användaråtkomst till tillägg.</span><span class="sxs-lookup"><span data-stu-id="142d1-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="142d1-136">I administrationscentret går du till **sidan Inställningar** tjänster  >  **& tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="142d1-137">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="142d1-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="142d1-138">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="142d1-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="142d1-139">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="142d1-140">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="142d1-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="142d1-141">Klicka på **Redigera** under **Vem har Access.**</span><span class="sxs-lookup"><span data-stu-id="142d1-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="142d1-142">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="142d1-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="142d1-143">Förhindra nedladdningar av tillägg genom att inaktivera Office Store i alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="142d1-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="142d1-144">Outlook tilläggsinstallation hanteras av en [annan process.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="142d1-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="142d1-145">Som organisation kanske du vill förhindra nedladdning av Office tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="142d1-145">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="142d1-146">Det kan användas tillsammans med centraliserad distribution för att säkerställa att endast av organisationen godkända tillägg distribueras till användare inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="142d1-146">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="142d1-147">**Så här inaktiverar du datainsamling av tillägg**</span><span class="sxs-lookup"><span data-stu-id="142d1-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="142d1-148">I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="142d1-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="142d1-149">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="142d1-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="142d1-150">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **Integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="142d1-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="142d1-151">Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="142d1-152">Välj **Användarägda appar och tjänster.**</span><span class="sxs-lookup"><span data-stu-id="142d1-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="142d1-153">Avmarkera alternativet att ge användare åtkomst till Office store.</span><span class="sxs-lookup"><span data-stu-id="142d1-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="142d1-154">Det hindrar alla användare från att hämta följande tillägg från Store.</span><span class="sxs-lookup"><span data-stu-id="142d1-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="142d1-155">Tillägg för Word, Excel och PowerPoint 2016 från:</span><span class="sxs-lookup"><span data-stu-id="142d1-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="142d1-156">Windows</span><span class="sxs-lookup"><span data-stu-id="142d1-156">Windows</span></span>
      - <span data-ttu-id="142d1-157">Mac</span><span class="sxs-lookup"><span data-stu-id="142d1-157">Mac</span></span>
      - <span data-ttu-id="142d1-158">Office</span><span class="sxs-lookup"><span data-stu-id="142d1-158">Office</span></span>
        
        
    - <span data-ttu-id="142d1-159">Datainsamling som startar i **AppSource**</span><span class="sxs-lookup"><span data-stu-id="142d1-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="142d1-160">Tillägg inom Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="142d1-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="142d1-161">En användare som försöker komma åt Store får ett meddelande om att Microsoft 365 har konfigurerats för att förhindra enskilda datainsamlingar av **Office Store-tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="142d1-162">Stöd för att stänga Office Store är tillgängligt i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="142d1-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="142d1-163">Windows: 16.0.9001 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="142d1-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="142d1-164">Mac: 16.10.18011401 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="142d1-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="142d1-165">iOS: 2.9.18010804 – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="142d1-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="142d1-166">Webben – tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="142d1-166">The web - Currently available.</span></span>
    
<span data-ttu-id="142d1-167">Det hindrar inte en administratör från att använda centraliserad distribution till att tilldela ett tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="142d1-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="142d1-168">Du kan förhindra att en användare loggar in med ett Microsoft-konto genom att begränsa inloggning till organisationskontot.</span><span class="sxs-lookup"><span data-stu-id="142d1-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="142d1-169">Mer information finns i [Identitet, autentisering och auktorisering i Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="142d1-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="142d1-170">Om du hindrar användare från att komma åt Office Store hindras de också från att Office separat inläsning av tillägg för [testning från en nätverksresurs.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="142d1-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="142d1-171">Mer om slutanvändarupplevelsen med tillägg</span><span class="sxs-lookup"><span data-stu-id="142d1-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="142d1-172">När du har distribuerat ett tillägg kan slutanvändarna börja använda det i sina Office-program (se Börja använda [Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="142d1-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="142d1-173">Tillägget visas på alla plattformar som har stöd för det.</span><span class="sxs-lookup"><span data-stu-id="142d1-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="142d1-174">Om tillägget har stöd för tilläggskommandon visas de i det Office menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="142d1-174">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="142d1-175">I följande exempel visas kommandot **Sök källhänvisning** för tillägget **Källhänvisningar.**</span><span class="sxs-lookup"><span data-stu-id="142d1-175">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office menyfliksområde med källhänvisningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="142d1-177">Om det distribuerade tillägget inte har stöd för tilläggskommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="142d1-178">I Word 2016, Excel 2016 eller PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="142d1-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="142d1-179">Välj **\> Infoga mina tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="142d1-180">Välj **fliken Administratör** hanterad Office i fönstret Tillägg.</span><span class="sxs-lookup"><span data-stu-id="142d1-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="142d1-181">Dubbelklicka på tillägget som du distribuerade tidigare (i det här exemplet **Källhänvisningar).**</span><span class="sxs-lookup"><span data-stu-id="142d1-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Fliken Administratör hanterad Office tilläggssidan](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="142d1-183">I Outlook</span><span class="sxs-lookup"><span data-stu-id="142d1-183">In Outlook</span></span>

1. <span data-ttu-id="142d1-184">I **menyfliksområdet** Start **väljer du Hämta tillägg.**</span><span class="sxs-lookup"><span data-stu-id="142d1-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Knappen Lagra i Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="142d1-186">Välj **Administratör hanterad i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="142d1-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="142d1-187">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="142d1-187">Related content</span></span>

<span data-ttu-id="142d1-188">[Distribuera tillägg i administrationscentret](./manage-deployment-of-add-ins.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="142d1-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="142d1-189">Läs mer om att [Office tillägg](/office/dev/add-ins/overview/office-add-ins) (artikel)</span><span class="sxs-lookup"><span data-stu-id="142d1-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="142d1-190">[Använd PowerShell-cmdlets för](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) centraliserad distribution för att hantera tillägg (artikel)</span><span class="sxs-lookup"><span data-stu-id="142d1-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="142d1-191">[Felsökning: Användaren ser inte tillägg](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artikel)</span><span class="sxs-lookup"><span data-stu-id="142d1-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="142d1-192">[Minderåriga och köp av tillägg från Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="142d1-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>