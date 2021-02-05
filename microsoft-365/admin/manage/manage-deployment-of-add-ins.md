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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen genom att använda centraliserad distribution i administrationscentret.
ms.openlocfilehash: 5d17242d98f0e58ec4bfbcfd5b7014e6a6e0a6c5
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114507"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="d0644-103">Distribuera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d0644-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d0644-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="d0644-104">The admin center is changing.</span></span> <span data-ttu-id="d0644-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="d0644-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="d0644-106">Office-tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Komma igång med [ditt Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="d0644-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="d0644-107">Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen för centraliserad distribution i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0644-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d0644-108">Centraliserad distribution är den rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="d0644-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="d0644-109">Mer information om hur du fastställer om organisationen har stöd för centraliserad distribution finns i Avgöra om centraliserad distribution av tillägg [fungerar för din organisation.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d0644-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="d0644-110">Mer information om hur du hanterar tillägg efter distributionen finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d0644-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d0644-111">För Word, Excel och PowerPoint används en [SharePoint-programkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg.</span><span class="sxs-lookup"><span data-stu-id="d0644-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="d0644-112">För Outlook använder du Kontrollpanelen i Exchange för att distribuera i en lokal miljö utan anslutning till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0644-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="d0644-113">Rekommenderad metod för distribution av Office-tillägg</span><span class="sxs-lookup"><span data-stu-id="d0644-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="d0644-114">Om du vill distribuera tillägg med en fasad metod rekommenderar vi följande:</span><span class="sxs-lookup"><span data-stu-id="d0644-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="d0644-115">Distribuera tillägget till ett mindre antal personer i företaget och till medlemmar i IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="d0644-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="d0644-116">Om distributionen lyckas går du vidare till steg 2.</span><span class="sxs-lookup"><span data-stu-id="d0644-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="d0644-117">Distribuera tillägget till fler personer inom företaget.</span><span class="sxs-lookup"><span data-stu-id="d0644-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="d0644-118">Utvärdera resultatet på nytt och fortsätt med fullständig distribution om det lyckas.</span><span class="sxs-lookup"><span data-stu-id="d0644-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="d0644-119">Utför en fullständig utrullning för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d0644-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="d0644-120">Beroende på målgruppens storlek kan du lägga till eller ta bort steg för utrullning.</span><span class="sxs-lookup"><span data-stu-id="d0644-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="d0644-121">Distribuera ett Office-tillägg med hjälp av administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d0644-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="d0644-122">Innan du börjar kan du [kontrollera om centraliserad distribution av tillägg fungerar för din organisation.](centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="d0644-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="d0644-123">Gå till sidan  \> **Inställningar-tillägg i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="d0644-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span> <span data-ttu-id="d0644-124">Om du inte ser **tilläggssidan går** du  till sidan Inställningar \> **för** integrerade \> **appar.**</span><span class="sxs-lookup"><span data-stu-id="d0644-124">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="d0644-125">Välj **Distribuera tillägg högst** upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="d0644-125">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="d0644-126">Administrationscentret uppdateras för användning av integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="d0644-126">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="d0644-127">Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.**</span><span class="sxs-lookup"><span data-stu-id="d0644-127">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="d0644-128">Välj Tillägg högst **upp på** sidan Integrerade **appar.**</span><span class="sxs-lookup"><span data-stu-id="d0644-128">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="d0644-129">Välj ett alternativ och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="d0644-129">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="d0644-130">Om du valde alternativet att lägga till ett tillägg från Office Store gör du ditt tilläggsalternativ.</span><span class="sxs-lookup"><span data-stu-id="d0644-130">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="d0644-131">Du kan visa tillgängliga tillägg efter kategorier: Förslag **till dig,** **Klassificering** eller **Namn.**</span><span class="sxs-lookup"><span data-stu-id="d0644-131">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="d0644-132">Endast kostnadsfria tillägg är tillgängliga från Office Store.</span><span class="sxs-lookup"><span data-stu-id="d0644-132">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="d0644-133">Betalda tillägg stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="d0644-133">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="d0644-134">När du har valt ett tillägg accepterar du villkoren för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="d0644-134">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="d0644-135">Med alternativet Office Store distribueras uppdateringar och förbättringar automatiskt till användarna.</span><span class="sxs-lookup"><span data-stu-id="d0644-135">With the Office Store option, updates and enhancements are automatically deployed to users.</span></span>

5. <span data-ttu-id="d0644-136">På nästa sida väljer du **Alla,** Specifika  **användare/grupper** eller Bara jag för att ange vem tillägget ska distribueras till.</span><span class="sxs-lookup"><span data-stu-id="d0644-136">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="d0644-137">Använd sökrutan för att söka efter specifika användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="d0644-137">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="d0644-138">Mer information om andra tillstånd som gäller för ett tillägg finns i [tilläggsstater.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="d0644-138">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="d0644-139">Välj **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="d0644-139">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="d0644-140">Ett grönt skalstreck visas när tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="d0644-140">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="d0644-141">Följ anvisningarna på sidan för att testa tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-141">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0644-142">Användare kan behöva köra om Office för att visa tilläggsikonen i menyfliksområdet för appen.</span><span class="sxs-lookup"><span data-stu-id="d0644-142">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="d0644-143">Det kan ta upp till 24 timmar innan Outlook-tillägg visas i appfliksområde.</span><span class="sxs-lookup"><span data-stu-id="d0644-143">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="d0644-144">Välj Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="d0644-144">When finished, select **Next**.</span></span> <span data-ttu-id="d0644-145">Om du bara har distribuerat till dig själv kan du välja Ändra vem som har åtkomst till tillägget **för** distribution till fler användare.</span><span class="sxs-lookup"><span data-stu-id="d0644-145">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="d0644-146">Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-146">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="d0644-147">Vi är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="d0644-147">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="d0644-148">Du kan skicka ett e-postmeddelande som beskriver när och hur du använder tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-148">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="d0644-149">Ta med eller länka till hjälpinnehåll eller vanliga frågor som kan hjälpa användare om de har problem med tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-149">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="d0644-150">Att tänka på när du tilldelar ett tillägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="d0644-150">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="d0644-151">Administratörer kan tilldela ett tillägg till alla eller till vissa användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="d0644-151">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="d0644-152">Varje alternativ har sina konsekvenser:</span><span class="sxs-lookup"><span data-stu-id="d0644-152">Each option has implications:</span></span>
  
- <span data-ttu-id="d0644-153">**Alla** Med det här alternativet tilldelas tillägget till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d0644-153">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="d0644-154">Använd det här alternativet sparsamt och bara för tillägg som verkligen är till för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="d0644-154">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="d0644-155">**Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.</span><span class="sxs-lookup"><span data-stu-id="d0644-155">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="d0644-156">**Grupper** Om du tilldelar ett tillägg till en grupp tilldelas tillägget automatiskt till användare som läggs till i gruppen.</span><span class="sxs-lookup"><span data-stu-id="d0644-156">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="d0644-157">När en användare tas bort från en grupp förlorar användaren åtkomsten till tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-157">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="d0644-158">I båda fallen krävs inga ytterligare åtgärder från administratören.</span><span class="sxs-lookup"><span data-stu-id="d0644-158">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="d0644-159">**Bara jag** Om du tilldelar ett tillägg till bara dig själv tilldelas tillägget bara till ditt konto, vilket är perfekt för att testa tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-159">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="d0644-160">Rätt alternativ för din organisation beror på din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d0644-160">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="d0644-161">Vi rekommenderar emellertid att tilldelningar görs med hjälp av grupper.</span><span class="sxs-lookup"><span data-stu-id="d0644-161">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="d0644-162">Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrollera medlemskapet i de grupperna i stället för att tilldela enskilda användare varje gång.</span><span class="sxs-lookup"><span data-stu-id="d0644-162">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="d0644-163">I vissa situationer kan du vilja begränsa åtkomsten till en liten uppsättning användare genom att tilldela tilldelningar till specifika användare genom att tilldela användare manuellt.</span><span class="sxs-lookup"><span data-stu-id="d0644-163">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="d0644-164">Mer om säkerhet för Office-tillägg</span><span class="sxs-lookup"><span data-stu-id="d0644-164">More about Office add-ins security</span></span>

<span data-ttu-id="d0644-165">Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men det viktigaste är att de pekar på ett webbprogram som innehåller all kod och logik.</span><span class="sxs-lookup"><span data-stu-id="d0644-165">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic.</span></span> <span data-ttu-id="d0644-166">Tillägg kan ha olika funktioner.</span><span class="sxs-lookup"><span data-stu-id="d0644-166">Add-ins can range in their capabilities.</span></span> <span data-ttu-id="d0644-167">Tillägg kan till exempel:</span><span class="sxs-lookup"><span data-stu-id="d0644-167">For example, add-ins can:</span></span>
  
- <span data-ttu-id="d0644-168">Visa data.</span><span class="sxs-lookup"><span data-stu-id="d0644-168">Display data.</span></span>
    
- <span data-ttu-id="d0644-169">Läsa en användares dokument för att tillhandahålla sammanhangsberoende tjänster.</span><span class="sxs-lookup"><span data-stu-id="d0644-169">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="d0644-170">Läsa och skriva data till och från en användares dokument för att ge värde till användaren.</span><span class="sxs-lookup"><span data-stu-id="d0644-170">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="d0644-171">Mer information om typer och funktioner i Office-tillägg finns i plattformsöversikten för [Office-tillägg,](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)särskilt avsnittet "Beskrivning av ett Office-tillägg".</span><span class="sxs-lookup"><span data-stu-id="d0644-171">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="d0644-172">För att tillägget ska kunna interagera med användarens dokument måste det deklarera vilken behörighet som krävs i manifestet.</span><span class="sxs-lookup"><span data-stu-id="d0644-172">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="d0644-173">En JavaScript API-åtkomstbehörighetsmodell med fem nivåer utgör grunden för sekretess och säkerhet för åtgärdsfönster tillägg. Majoriteten av tilläggen i Office Store är på nivån ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument-nivå.</span><span class="sxs-lookup"><span data-stu-id="d0644-173">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="d0644-174">Mer information om behörighetsnivåer finns i [Begära behörigheter för API-användning i innehåll åtgärdsfönster tillägg.](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)</span><span class="sxs-lookup"><span data-stu-id="d0644-174">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="d0644-175">När du uppdaterar ett manifest är det vanligtvis ändringar av ikon och text för ett tillägg.</span><span class="sxs-lookup"><span data-stu-id="d0644-175">When updating a manifest, the typical changes are to an add-in's icon and text.</span></span> <span data-ttu-id="d0644-176">Ibland kan tilläggskommandon ändras.</span><span class="sxs-lookup"><span data-stu-id="d0644-176">Occasionally, add-in commands change.</span></span> <span data-ttu-id="d0644-177">Tilläggets behörigheter ändras dock inte.</span><span class="sxs-lookup"><span data-stu-id="d0644-177">However, the permissions of the add-in do not change.</span></span> <span data-ttu-id="d0644-178">Webbprogrammet där all kod och logik för tillägget körs kan ändras när som helst, vilket är natur hos webbprogram.</span><span class="sxs-lookup"><span data-stu-id="d0644-178">The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="d0644-179">Uppdateringar för tillägg sker så här:</span><span class="sxs-lookup"><span data-stu-id="d0644-179">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="d0644-180">**Verksamhets tillägg:** I det här fallet, där en administratör uttryckligen har laddat upp ett manifest, kräver tillägget att administratören laddar upp ett nytt manifest för att ge stöd för metadataändringar.</span><span class="sxs-lookup"><span data-stu-id="d0644-180">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="d0644-181">Nästa gång Office-programmen startar uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-181">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="d0644-182">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="d0644-182">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d0644-183">Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="d0644-183">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="d0644-184">I avsnittet Tillägg kan administratören helt enkelt klicka på tillägget LOB och välja uppdateringsknappen **i** det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d0644-184">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="d0644-185">Uppdateringen fungerar endast om versionen av det nya tillägget är senare än det befintliga tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-185">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="d0644-186">**Office Store-tillägg:** När en administratör har valt ett tillägg från Office Store uppdateras tillägget senare i centraliserad distribution om ett tillägg uppdateras i Office Store.</span><span class="sxs-lookup"><span data-stu-id="d0644-186">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="d0644-187">Nästa gång Office-programmen startar uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="d0644-187">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="d0644-188">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="d0644-188">The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="d0644-189">Mer information</span><span class="sxs-lookup"><span data-stu-id="d0644-189">Learn more</span></span>

[<span data-ttu-id="d0644-190">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="d0644-190">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="d0644-191">[Skapa ditt första Word åtgärdsfönster-tillägg.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)</span><span class="sxs-lookup"><span data-stu-id="d0644-191">[Build your first Word task pane add-in](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator).</span></span>

[<span data-ttu-id="d0644-192">Minderåriga och skaffa tillägg från Store</span><span class="sxs-lookup"><span data-stu-id="d0644-192">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="d0644-193">Använda PowerShell-cmdlets för centraliserad distribution för att hantera tillägg</span><span class="sxs-lookup"><span data-stu-id="d0644-193">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="d0644-194">Felsökning: Användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="d0644-194">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
