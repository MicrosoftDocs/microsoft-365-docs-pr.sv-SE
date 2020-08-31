---
title: Distribuera tillägg i administrationscentret
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
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av centraliserad distribution i administrations centret.
ms.openlocfilehash: aec2adab7735a2be5670210abf05f88f081fe4ed
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306533"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="d773c-103">Distribuera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d773c-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d773c-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="d773c-104">The admin center is changing.</span></span> <span data-ttu-id="d773c-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="d773c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="d773c-106">Med hjälp av Office-tillägg kan du anpassa dina dokument och förenkla hur du kommer åt informationen på webben (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="d773c-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="d773c-107">Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen centraliserad distribution i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d773c-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d773c-108">Centraliserad distribution är det rekommenderade och mest omfattande sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="d773c-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="d773c-109">Mer information om hur du tar reda på om din organisation har stöd för centraliserad distribution finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="d773c-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="d773c-110">Mer information om hur du hanterar tillägg efter distribution finns i [Hantera tillägg i administrations centret](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d773c-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d773c-111">I Excel och PowerPoint används en SharePoint- [programkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs.</span><span class="sxs-lookup"><span data-stu-id="d773c-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="d773c-112">För Outlook använder du Exchange-Kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d773c-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="d773c-113">Rekommenderad metod för att distribuera Office-tillägg</span><span class="sxs-lookup"><span data-stu-id="d773c-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="d773c-114">För att kunna distribuera tillägg med hjälp av en stegvis lösning rekommenderar vi följande:</span><span class="sxs-lookup"><span data-stu-id="d773c-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="d773c-115">Distribuera tillägget till en mindre uppsättning intressenter och medlemmar i IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="d773c-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="d773c-116">Om distributionen lyckades går du vidare till steg 2.</span><span class="sxs-lookup"><span data-stu-id="d773c-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="d773c-117">Distribuera tillägget till fler personer inom företaget.</span><span class="sxs-lookup"><span data-stu-id="d773c-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="d773c-118">Utvärdera resultatet och fortsätt med fullständig distribution om det lyckades.</span><span class="sxs-lookup"><span data-stu-id="d773c-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="d773c-119">Utför fullständig installation för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d773c-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="d773c-120">Beroende på mål gruppens storlek kan du lägga till eller ta bort distributions steg.</span><span class="sxs-lookup"><span data-stu-id="d773c-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="d773c-121">Distribuera ett Office-tillägg med administrations Center</span><span class="sxs-lookup"><span data-stu-id="d773c-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="d773c-122">Innan du börjar läser du [kontrol lera om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="d773c-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="d773c-123">Gå till sidan tillägg i administrations centret **Settings** \> **Add-ins** .</span><span class="sxs-lookup"><span data-stu-id="d773c-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="d773c-124">Välj **distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d773c-124">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
    
3. <span data-ttu-id="d773c-125">Välj ett alternativ och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="d773c-125">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="d773c-126">Om du valde alternativet att lägga till ett tillägg från Office Store gör du tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-126">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="d773c-127">Du kan visa tillgängliga tillägg efter kategorier: **föreslaget för dig**, **betyg**eller **namn**.</span><span class="sxs-lookup"><span data-stu-id="d773c-127">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="d773c-128">Det finns bara kostnads fria tillägg från Office Store.</span><span class="sxs-lookup"><span data-stu-id="d773c-128">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="d773c-129">Betalda tillägg stöds för närvarande inte.</span><span class="sxs-lookup"><span data-stu-id="d773c-129">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="d773c-130">När du har valt ett tillägg accepterar du villkoren och villkoren för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="d773c-130">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="d773c-131">Med Office Store-alternativet uppdateras uppdateringar och förbättringar automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="d773c-131">With the Office Store option, updates and enhancements are automatically to users.</span></span>

5. <span data-ttu-id="d773c-132">På nästa sida väljer du **alla**, **specifika användare/grupper**eller **bara jag** för att ange vem tillägget distribueras till.</span><span class="sxs-lookup"><span data-stu-id="d773c-132">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="d773c-133">Använd sökrutan för att hitta specifika användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="d773c-133">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="d773c-134">Om du vill veta mer om andra tillstånd som gäller för ett tillägg läser du [i tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="d773c-134">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="d773c-135">Välj **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="d773c-135">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="d773c-136">En grön markering visas när tillägget distribueras.</span><span class="sxs-lookup"><span data-stu-id="d773c-136">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="d773c-137">Följ instruktionerna på sidan för att testa tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-137">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d773c-138">Användare kan behöva starta om Office för att Visa tilläggs ikonen i menyfliksområdet app.</span><span class="sxs-lookup"><span data-stu-id="d773c-138">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="d773c-139">Outlook-tillägg kan ta upp till 24 timmar att visas på menyfliksområdet i appen.</span><span class="sxs-lookup"><span data-stu-id="d773c-139">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="d773c-140">När du är klar väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d773c-140">When finished, select **Next**.</span></span> <span data-ttu-id="d773c-141">Om du har distribuerat dig själv kan du välja **ändra vem som har åtkomst till tillägget** för att distribueras till fler användare.</span><span class="sxs-lookup"><span data-stu-id="d773c-141">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="d773c-142">Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-142">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="d773c-143">Det är en bra idé att informera användare och grupper om att det distribuerade tillägget är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="d773c-143">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="d773c-144">Överväg att skicka ett e-postmeddelande som beskriver när och hur du ska använda tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-144">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="d773c-145">Infoga eller länka till hjälp innehåll och vanliga frågor om problem med tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-145">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="d773c-146">Att tänka på när du tilldelar ett tillägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="d773c-146">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="d773c-147">Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="d773c-147">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="d773c-148">Varje alternativ har betydelse:</span><span class="sxs-lookup"><span data-stu-id="d773c-148">Each option has implications:</span></span>
  
- <span data-ttu-id="d773c-149">**Alla** Det här alternativet tilldelar tillägget till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d773c-149">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="d773c-150">Använd det här alternativet sparsamt och bara för tillägg som är universella för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d773c-150">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="d773c-151">**Användare** Om du tilldelar ett tillägg till en enskild användare, och sedan distribuerar tillägget till en ny användare, måste du först lägga till den nya användaren.</span><span class="sxs-lookup"><span data-stu-id="d773c-151">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="d773c-152">**Grupper** Om du tilldelar ett tillägg till en grupp, tilldelas användare som läggs till i gruppen automatiskt tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-152">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="d773c-153">När en användare tas bort från en grupp förlorar användaren åtkomst till tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-153">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="d773c-154">I båda fallen krävs ingen ytterligare åtgärd från administratören.</span><span class="sxs-lookup"><span data-stu-id="d773c-154">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="d773c-155">**Bara jag** Om du tilldelar ett tillägg till dig själv tilldelas tillägget bara till ditt konto, som är idealiskt för testning av tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-155">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="d773c-156">Det bästa alternativet för din organisation beror på din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d773c-156">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="d773c-157">Vi rekommenderar att du gör uppgifter med hjälp av grupper.</span><span class="sxs-lookup"><span data-stu-id="d773c-157">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="d773c-158">Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrol lera medlemskap för dessa grupper i stället för att tilldela enskilda användare varje gång.</span><span class="sxs-lookup"><span data-stu-id="d773c-158">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="d773c-159">I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att göra uppgifter till specifika användare genom att tilldela användare manuellt.</span><span class="sxs-lookup"><span data-stu-id="d773c-159">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="d773c-160">Mer om säkerhet för Office-tillägg</span><span class="sxs-lookup"><span data-stu-id="d773c-160">More about Office add-ins security</span></span>

<span data-ttu-id="d773c-161">Office-tillägg kombinerar en XML-manifest fil som innehåller vissa metadata om tillägget, men det viktigaste är att peka på ett webb program som innehåller all kod och logik.</span><span class="sxs-lookup"><span data-stu-id="d773c-161">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic.</span></span> <span data-ttu-id="d773c-162">Tillägg kan variera efter deras kapacitet.</span><span class="sxs-lookup"><span data-stu-id="d773c-162">Add-ins can range in their capabilities.</span></span> <span data-ttu-id="d773c-163">Tillägg kan till exempel:</span><span class="sxs-lookup"><span data-stu-id="d773c-163">For example, add-ins can:</span></span>
  
- <span data-ttu-id="d773c-164">Visa data.</span><span class="sxs-lookup"><span data-stu-id="d773c-164">Display data.</span></span>
    
- <span data-ttu-id="d773c-165">Läs en användares dokument för att tillhandahålla kontextuella tjänster.</span><span class="sxs-lookup"><span data-stu-id="d773c-165">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="d773c-166">Läsa och skriva data till och från en användares dokument för att ange värde för den användaren.</span><span class="sxs-lookup"><span data-stu-id="d773c-166">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="d773c-167">Mer information om olika typer av Office-tillägg finns i avsnittet om hur du lägger till en översikt över Office- [tilläggsprogram](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)</span><span class="sxs-lookup"><span data-stu-id="d773c-167">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="d773c-168">Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet som krävs i manifestet.</span><span class="sxs-lookup"><span data-stu-id="d773c-168">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="d773c-169">En JavaScript-behörighets modell med fem nivåer är grunden för sekretess och säkerhet för användare av åtgärds fönstrets tillägg. De flesta tilläggen i Office Store är nivå ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument nivå.</span><span class="sxs-lookup"><span data-stu-id="d773c-169">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="d773c-170">Mer information om behörighets nivåer finns i [begära behörigheter för API-användning i tillägg för innehåll och åtgärds fönster](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="d773c-170">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="d773c-171">När du uppdaterar ett manifest är de typiska ändringarna för ett tilläggs ikon och text.</span><span class="sxs-lookup"><span data-stu-id="d773c-171">When updating a manifest, the typical changes are to an add-in's icon and text.</span></span> <span data-ttu-id="d773c-172">Ibland kommer kommandon för tillägg att ändras.</span><span class="sxs-lookup"><span data-stu-id="d773c-172">Occasionally, add-in commands change.</span></span> <span data-ttu-id="d773c-173">Men behörigheterna för tillägget ändras inte.</span><span class="sxs-lookup"><span data-stu-id="d773c-173">However, the permissions of the add-in do not change.</span></span> <span data-ttu-id="d773c-174">Webb programmet där all kod och logik för tillägget körs kan ändras när som helst, vilket är webb programs beskaffenhet.</span><span class="sxs-lookup"><span data-stu-id="d773c-174">The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="d773c-175">Uppdateringar för tillägg sker på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d773c-175">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="d773c-176">**Tillägg för affärs område:** I det här fallet när en administratör explicit har laddat upp ett manifest kräver tillägget att administratören laddar upp en ny manifest fil för att stödja metadata ändringar.</span><span class="sxs-lookup"><span data-stu-id="d773c-176">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="d773c-177">Nästa gång Office-programmen startas uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-177">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="d773c-178">Webb programmet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="d773c-178">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d773c-179">Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="d773c-179">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="d773c-180">I avsnittet tillägg kan administratören helt enkelt klicka på LOB-tillägget och välja **knappen Uppdatera** i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d773c-180">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="d773c-181">Update fungerar bara om den version av det nya tillägget är större än det befintliga tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-181">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="d773c-182">**Office Store-tillägg:** När en administratör valde ett tillägg från Office Store, om en tilläggs uppdatering i Office Store, uppdateras tillägget senare i centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="d773c-182">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="d773c-183">Nästa gång Office-programmen startas uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="d773c-183">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="d773c-184">Webb programmet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="d773c-184">The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="d773c-185">Mer information</span><span class="sxs-lookup"><span data-stu-id="d773c-185">Learn more</span></span>

[<span data-ttu-id="d773c-186">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d773c-186">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="d773c-187">[Skapar Office-tillägg](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span><span class="sxs-lookup"><span data-stu-id="d773c-187">[Building Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span></span>

[<span data-ttu-id="d773c-188">Minderåriga och förvärvade tillägg från Store</span><span class="sxs-lookup"><span data-stu-id="d773c-188">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="d773c-189">Använda PowerShell-cmdlets för centraliserad distribution för att hantera tillägg</span><span class="sxs-lookup"><span data-stu-id="d773c-189">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="d773c-190">Fel sökning: användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="d773c-190">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
