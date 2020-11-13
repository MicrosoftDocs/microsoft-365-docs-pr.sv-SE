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
description: Lär dig mer om hur du använder centraliserade tillägg för att distribuera tillägg till användare och grupper i din organisation.
ms.openlocfilehash: 5521b01e059ca8ae4a97ecb094f9aa1198263701
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071483"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="8427c-103">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="8427c-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8427c-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="8427c-104">The admin center is changing.</span></span> <span data-ttu-id="8427c-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8427c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="8427c-106">Med hjälp av Office-tillägg kan du anpassa dina dokument och förenkla hur du kommer åt informationen på webben (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="8427c-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="8427c-107">När en administratör distribuerar tillägg för användare i en organisation kan administratören aktivera tillägg eller på, redigera, ta bort och hantera åtkomst till tilläggen.</span><span class="sxs-lookup"><span data-stu-id="8427c-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="8427c-108">Mer information om hur du installerar tillägg från administrations centret finns i [distribuera tillägg i administrations centret](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8427c-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="8427c-109">Tilläggs tillstånd</span><span class="sxs-lookup"><span data-stu-id="8427c-109">Add-in states</span></span>

<span data-ttu-id="8427c-110">Ett tillägg kan vara i läget **på** eller **av** .</span><span class="sxs-lookup"><span data-stu-id="8427c-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="8427c-111">**Sessionsläget**</span><span class="sxs-lookup"><span data-stu-id="8427c-111">**State**</span></span>|<span data-ttu-id="8427c-112">**Hur tillståndet uppträder**</span><span class="sxs-lookup"><span data-stu-id="8427c-112">**How the state occurs**</span></span>|<span data-ttu-id="8427c-113">**Påverkan**</span><span class="sxs-lookup"><span data-stu-id="8427c-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8427c-114">**Aktiva**</span><span class="sxs-lookup"><span data-stu-id="8427c-114">**Active**</span></span>  <br/> |<span data-ttu-id="8427c-115">Administratören har laddat upp tillägget och tilldelat det till användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="8427c-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="8427c-116">Användare och grupper som tilldelats tillägget kan se det i relevanta klienter.</span><span class="sxs-lookup"><span data-stu-id="8427c-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="8427c-117">**Inaktiverat**</span><span class="sxs-lookup"><span data-stu-id="8427c-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="8427c-118">Administratören har inaktiverat tillägget.</span><span class="sxs-lookup"><span data-stu-id="8427c-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="8427c-119">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="8427c-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="8427c-120">Om tillägget ändras till Active får användarna och grupperna åtkomst till det igen.</span><span class="sxs-lookup"><span data-stu-id="8427c-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="8427c-121">**Deleted**</span><span class="sxs-lookup"><span data-stu-id="8427c-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="8427c-122">Administratören har tagit bort tillägget.</span><span class="sxs-lookup"><span data-stu-id="8427c-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="8427c-123">Användare och grupper som tilldelats tillägget har inte längre åtkomst till det.</span><span class="sxs-lookup"><span data-stu-id="8427c-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="8427c-124">Överväg att ta bort ett tillägg om det inte längre används.</span><span class="sxs-lookup"><span data-stu-id="8427c-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="8427c-125">Om du till exempel inaktiverar ett tillägg kan det vara bra att använda ett tillägg endast under vissa tider på året.</span><span class="sxs-lookup"><span data-stu-id="8427c-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="8427c-126">Ta bort ett tillägg</span><span class="sxs-lookup"><span data-stu-id="8427c-126">Delete an add-in</span></span>

<span data-ttu-id="8427c-127">Du kan också ta bort ett tillägg som har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="8427c-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="8427c-128">I administrations centret går du till sidan **Inställningar**  >  **& tillägg** .</span><span class="sxs-lookup"><span data-stu-id="8427c-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="8427c-129">Administrations centret uppdateras till distributions miljön med integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="8427c-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="8427c-130">Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**.</span><span class="sxs-lookup"><span data-stu-id="8427c-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="8427c-131">**Välj tillägg** högst upp på sidan för **integrerade appar** .</span><span class="sxs-lookup"><span data-stu-id="8427c-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="8427c-132">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="8427c-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8427c-133">Klicka på **ta bort tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8427c-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="8427c-134">Ta bort knappen tillägg i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="8427c-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="8427c-135">Validera dina val och välj **ta bort tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8427c-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="8427c-136">Redigera tilläggs åtkomst</span><span class="sxs-lookup"><span data-stu-id="8427c-136">Edit add-in access</span></span>

<span data-ttu-id="8427c-137">Efter distribution kan administratörer även hantera användar åtkomst till tillägg.</span><span class="sxs-lookup"><span data-stu-id="8427c-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="8427c-138">I administrations centret går du till sidan **Inställningar**  >  **& tillägg** .</span><span class="sxs-lookup"><span data-stu-id="8427c-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="8427c-139">Administrations centret uppdateras till distributions miljön med integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="8427c-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="8427c-140">Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**.</span><span class="sxs-lookup"><span data-stu-id="8427c-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="8427c-141">**Välj tillägg** högst upp på sidan för **integrerade appar** .</span><span class="sxs-lookup"><span data-stu-id="8427c-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="8427c-142">Välj det distribuerade tillägget.</span><span class="sxs-lookup"><span data-stu-id="8427c-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="8427c-143">Klicka på **redigera** under **vem har åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="8427c-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="8427c-144">Spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="8427c-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="8427c-145">Förhindra hämtning av tillägg genom att stänga av Office Store på alla klienter (utom Outlook)</span><span class="sxs-lookup"><span data-stu-id="8427c-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="8427c-146">Installation av Outlook-tillägg hanteras av en [annan process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8427c-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="8427c-147">Som en organisation kanske du vill förhindra nedladdning av nya Office-tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="8427c-147">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="8427c-148">Detta kan användas tillsammans med centraliserad distribution för att säkerställa att endast organisations godkända tillägg distribueras till användare inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="8427c-148">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="8427c-149">**Så här inaktiverar du tilläggs förvärv**</span><span class="sxs-lookup"><span data-stu-id="8427c-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="8427c-150">I administrationscentret går du till sidan **Inställningar** \> [Tjänster och tillägg](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="8427c-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="8427c-151">Administrations centret uppdateras till distributions miljön med integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="8427c-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="8427c-152">Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar** för  >  **integrerade appar**.</span><span class="sxs-lookup"><span data-stu-id="8427c-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="8427c-153">**Välj tillägg** högst upp på sidan för **integrerade appar** .</span><span class="sxs-lookup"><span data-stu-id="8427c-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="8427c-154">Välj **ägda appar och tjänster**.</span><span class="sxs-lookup"><span data-stu-id="8427c-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="8427c-155">Avmarkera alternativet för att låta användare komma åt Office Store.</span><span class="sxs-lookup"><span data-stu-id="8427c-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="8427c-156">Detta hindrar alla användare från att hämta följande tillägg från Store.</span><span class="sxs-lookup"><span data-stu-id="8427c-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="8427c-157">Tillägg för Word, Excel och PowerPoint 2016 från:</span><span class="sxs-lookup"><span data-stu-id="8427c-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="8427c-158">Windows</span><span class="sxs-lookup"><span data-stu-id="8427c-158">Windows</span></span>
    
  - <span data-ttu-id="8427c-159">Mac</span><span class="sxs-lookup"><span data-stu-id="8427c-159">Mac</span></span>
    
  - <span data-ttu-id="8427c-160">Office</span><span class="sxs-lookup"><span data-stu-id="8427c-160">Office</span></span>
    
    
- <span data-ttu-id="8427c-161">Förvärv från **AppSource**</span><span class="sxs-lookup"><span data-stu-id="8427c-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="8427c-162">Tillägg i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8427c-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="8427c-163">En användare som försöker nå butiken ser följande meddelande: **Microsoft 365 har kon figurer ATS för att förhindra enskilda köp av Office Store-tillägg.**</span><span class="sxs-lookup"><span data-stu-id="8427c-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="8427c-164">Stöd för att stänga av Office Store är tillgängligt i följande versioner:</span><span class="sxs-lookup"><span data-stu-id="8427c-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="8427c-165">Windows: 16.0.9001-tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8427c-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="8427c-166">Mac: 16.10.18011401-tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8427c-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="8427c-167">iOS: 2.9.18010804-tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8427c-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="8427c-168">Webbplatsen finns för närvarande.</span><span class="sxs-lookup"><span data-stu-id="8427c-168">The web - Currently available.</span></span>
    
<span data-ttu-id="8427c-169">Detta förhindrar inte att administratörer använder centraliserad distribution för att tilldela ett tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="8427c-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="8427c-170">För att förhindra att en användare loggar in med ett Microsoft-konto kan du begränsa inloggningen så att endast organisations kontot används.</span><span class="sxs-lookup"><span data-stu-id="8427c-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="8427c-171">Mer information finns i [identitet, autentisering och auktorisering i Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8427c-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="8427c-172">Att förhindra att användare som använder Office Store kan hindra dem från att läsa in [Office-tillägg för testning](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8427c-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="8427c-173">Mer om slut användar upplevelsen med tillägg</span><span class="sxs-lookup"><span data-stu-id="8427c-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="8427c-174">När du har distribuerat ett tillägg kan slutanvändarna börja använda det i deras Office-program (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="8427c-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="8427c-175">Tillägget visas på alla plattformar som stöds av tillägget.</span><span class="sxs-lookup"><span data-stu-id="8427c-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="8427c-176">Om tillägget har stöd för tilläggs kommandon visas kommandona i menyfliksområdet i Office.</span><span class="sxs-lookup"><span data-stu-id="8427c-176">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="8427c-177">I följande exempel visas kommandot **Sök hänvisning** för **käll hänvisning** .</span><span class="sxs-lookup"><span data-stu-id="8427c-177">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-menyfliksområde med Sök käll hänvisningar](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="8427c-179">Om det distribuerade tillägget inte har stöd för tilläggs kommandon eller om du vill visa alla distribuerade tillägg kan du visa dem via **Mina tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8427c-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="8427c-180">I Word 2016, Excel 2016 eller PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="8427c-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="8427c-181">Välj **infoga \> Mina tillägg**.</span><span class="sxs-lookup"><span data-stu-id="8427c-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="8427c-182">Välj fliken **hanterad administratör** i fönstret Office-tillägg.</span><span class="sxs-lookup"><span data-stu-id="8427c-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="8427c-183">Dubbelklicka på tillägget du distribuerat tidigare (i det här exemplet **käll hänvisningar** ).</span><span class="sxs-lookup"><span data-stu-id="8427c-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="8427c-184">![Fliken hanterad administratör på sidan Office-tillägg](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="8427c-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="8427c-185">I Outlook</span><span class="sxs-lookup"><span data-stu-id="8427c-185">In Outlook</span></span>

1. <span data-ttu-id="8427c-186">Välj **Hämta tillägg** **i menyfliksområdet** .</span><span class="sxs-lookup"><span data-stu-id="8427c-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="8427c-187">![Knappen lagra i Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="8427c-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="8427c-188">Välj **administrativ hantering** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="8427c-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="8427c-189">Mer information</span><span class="sxs-lookup"><span data-stu-id="8427c-189">Learn more</span></span>

[<span data-ttu-id="8427c-190">Distribuera tillägg i administrations centret för</span><span class="sxs-lookup"><span data-stu-id="8427c-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="8427c-191">Läs mer om att skapa och skapa [Office-tillägg](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8427c-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="8427c-192">[Hantera tillägg genom att använda PowerShell-cmdlets för centraliserad distribution](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="8427c-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="8427c-193">Fel sökning: användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="8427c-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="8427c-194">Minderåriga och förvärvade tillägg från Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8427c-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
