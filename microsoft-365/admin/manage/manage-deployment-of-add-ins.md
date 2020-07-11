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
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102866"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="921d7-103">Distribuera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="921d7-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="921d7-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="921d7-104">The admin center is changing.</span></span> <span data-ttu-id="921d7-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="921d7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="921d7-106">Office-tillägg hjälper dig att anpassa dina dokument och effektivisera ditt sätt att komma åt information på webben (se [Börja använda office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="921d7-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="921d7-107">Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen Centraliserad distribution i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="921d7-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="921d7-108">Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation.</span><span class="sxs-lookup"><span data-stu-id="921d7-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="921d7-109">Mer information om hur du tar reda på om din organisation kan stödja centraliserad distribution finns [i Avgöra om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="921d7-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="921d7-110">Mer information om hur du hanterar tillägg efter distributionen finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="921d7-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="921d7-111">För Word, Excel och PowerPoint används en [SharePoint-appkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs.</span><span class="sxs-lookup"><span data-stu-id="921d7-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="921d7-112">I Outlook används Exchange-kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="921d7-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="921d7-113">Rekommenderad metod för distribution av Office-tillägg</span><span class="sxs-lookup"><span data-stu-id="921d7-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="921d7-114">Om du vill distribuera tillägg med hjälp av en stegvis metod rekommenderar vi följande:</span><span class="sxs-lookup"><span data-stu-id="921d7-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="921d7-115">Rulla ut tillägget till en liten uppsättning affärsintressenter och medlemmar på IT-avdelningen.</span><span class="sxs-lookup"><span data-stu-id="921d7-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="921d7-116">Om distributionen lyckas går du vidare till steg 2.</span><span class="sxs-lookup"><span data-stu-id="921d7-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="921d7-117">Rulla ut tillägget till fler individer inom verksamheten.</span><span class="sxs-lookup"><span data-stu-id="921d7-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="921d7-118">Återigen utvärdera resultaten och, om det lyckas, fortsätta med fullständig distribution.</span><span class="sxs-lookup"><span data-stu-id="921d7-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="921d7-119">Utför en fullständig distribution för alla användare.</span><span class="sxs-lookup"><span data-stu-id="921d7-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="921d7-120">Beroende på målgruppens storlek kan du lägga till eller ta bort utrullningssteg.</span><span class="sxs-lookup"><span data-stu-id="921d7-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="921d7-121">Distribuera ett Office-tillägg med administrationscentret</span><span class="sxs-lookup"><span data-stu-id="921d7-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="921d7-122">Innan du börjar läser du [Ta reda på om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="921d7-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="921d7-123">Gå till sidan Inställningar **Settings** \> **i administrationscentret.**</span><span class="sxs-lookup"><span data-stu-id="921d7-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="921d7-124">Välj **Distribuera tillägg högst** upp på sidan och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="921d7-124">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
    
3. <span data-ttu-id="921d7-125">Välj ett alternativ och följ instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="921d7-125">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="921d7-126">Om du valde alternativet att lägga till ett tillägg från Office Store gör du ditt tilläggsval.</span><span class="sxs-lookup"><span data-stu-id="921d7-126">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="921d7-127">Du kan visa tillgängliga tillägg efter kategorier: **Förslag på för dig**, **Betyg**eller **Namn**.</span><span class="sxs-lookup"><span data-stu-id="921d7-127">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="921d7-128">Endast kostnadsfria tillägg är tillgängliga i Office Store.</span><span class="sxs-lookup"><span data-stu-id="921d7-128">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="921d7-129">Betalda tillägg stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="921d7-129">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="921d7-130">När du har valt ett tillägg godkänner du villkoren för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="921d7-130">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="921d7-131">Med alternativet Office Store uppdateras och förbättringar automatiskt för användarna.</span><span class="sxs-lookup"><span data-stu-id="921d7-131">With the Office Store option, updates and enhancements are automatically to users.</span></span>

5. <span data-ttu-id="921d7-132">På nästa sida väljer du **Alla**, **Specifika användare/grupper**eller **Bara jag** för att ange vem tillägget ska distribueras till.</span><span class="sxs-lookup"><span data-stu-id="921d7-132">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="921d7-133">Använd sökrutan för att hitta specifika användare eller grupper.</span><span class="sxs-lookup"><span data-stu-id="921d7-133">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="921d7-134">Mer information om andra tillstånd som gäller för ett tillägg finns [i Tilläggstillstånd](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="921d7-134">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="921d7-135">Välj **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="921d7-135">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="921d7-136">En grön bock visas när tillägget distribueras.</span><span class="sxs-lookup"><span data-stu-id="921d7-136">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="921d7-137">Följ instruktionerna på sidan för att testa tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-137">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="921d7-138">Användare kan behöva starta om Office för att visa tilläggsikonen i menyfliksområdet för appen.</span><span class="sxs-lookup"><span data-stu-id="921d7-138">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="921d7-139">Det kan ta upp till 24 timmar innan Outlook-tillägg visas i menyfliksområdet för appar.</span><span class="sxs-lookup"><span data-stu-id="921d7-139">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="921d7-140">När du är klar väljer du **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="921d7-140">When finished, select **Next**.</span></span> <span data-ttu-id="921d7-141">Om du har distribuerat till bara dig själv kan du välja **Ändra vem som har åtkomst till tillägg** för att distribuera till fler användare.</span><span class="sxs-lookup"><span data-stu-id="921d7-141">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="921d7-142">Om du har distribuerat tillägget till andra medlemmar i organisationen följer du instruktionerna för att meddela distributionen av tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-142">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="921d7-143">Det är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="921d7-143">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="921d7-144">Överväg att skicka ett e-postmeddelande som beskriver när och hur du använder tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-144">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="921d7-145">Inkludera eller länka till Hjälpinnehåll eller vanliga frågor som kan hjälpa användarna om de har problem med tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-145">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="921d7-146">Överväganden när du tilldelar ett tillägg till användare och grupper</span><span class="sxs-lookup"><span data-stu-id="921d7-146">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="921d7-147">Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper.</span><span class="sxs-lookup"><span data-stu-id="921d7-147">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="921d7-148">Varje alternativ har konsekvenser:</span><span class="sxs-lookup"><span data-stu-id="921d7-148">Each option has implications:</span></span>
  
- <span data-ttu-id="921d7-149">**Alla** Det här alternativet tilldelar tillägget till alla användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="921d7-149">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="921d7-150">Använd det här alternativet sparsamt och endast för tillägg som verkligen är universella för din organisation.</span><span class="sxs-lookup"><span data-stu-id="921d7-150">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="921d7-151">**Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.</span><span class="sxs-lookup"><span data-stu-id="921d7-151">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="921d7-152">**Grupper** Om du tilldelar ett tillägg till en grupp tilldelas användare som läggs till i gruppen automatiskt tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-152">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="921d7-153">När en användare tas bort från en grupp förlorar användaren åtkomst till tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-153">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="921d7-154">I båda fallen krävs ingen ytterligare åtgärd från administratören.</span><span class="sxs-lookup"><span data-stu-id="921d7-154">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="921d7-155">**Bara jag** Om du tilldelar ett tillägg till bara dig själv tilldelas tillägget till endast ditt konto, vilket är idealiskt för att testa tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-155">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="921d7-156">Det rätta alternativet för din organisation beror på din konfiguration.</span><span class="sxs-lookup"><span data-stu-id="921d7-156">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="921d7-157">Vi rekommenderar dock att du gör tilldelningar med hjälp av grupper.</span><span class="sxs-lookup"><span data-stu-id="921d7-157">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="921d7-158">Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och styra medlemskapet i dessa grupper i stället för att tilldela enskilda användare varje gång.</span><span class="sxs-lookup"><span data-stu-id="921d7-158">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="921d7-159">I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att göra tilldelningar till specifika användare genom att tilldela användare manuellt.</span><span class="sxs-lookup"><span data-stu-id="921d7-159">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="921d7-160">Mer om office-tilläggssäkerhet</span><span class="sxs-lookup"><span data-stu-id="921d7-160">More about Office add-ins security</span></span>

<span data-ttu-id="921d7-161">Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men viktigast av allt pekar på ett webbprogram som innehåller all kod och logik.</span><span class="sxs-lookup"><span data-stu-id="921d7-161">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic.</span></span> <span data-ttu-id="921d7-162">Tillägg kan variera i sina funktioner.</span><span class="sxs-lookup"><span data-stu-id="921d7-162">Add-ins can range in their capabilities.</span></span> <span data-ttu-id="921d7-163">Tillägg kan till exempel:</span><span class="sxs-lookup"><span data-stu-id="921d7-163">For example, add-ins can:</span></span>
  
- <span data-ttu-id="921d7-164">Visa data.</span><span class="sxs-lookup"><span data-stu-id="921d7-164">Display data.</span></span>
    
- <span data-ttu-id="921d7-165">Läs en användares dokument för att tillhandahålla kontextuella tjänster.</span><span class="sxs-lookup"><span data-stu-id="921d7-165">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="921d7-166">Läs och skriv data till och från en användares dokument för att ge användaren värde.</span><span class="sxs-lookup"><span data-stu-id="921d7-166">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="921d7-167">Mer information om typerna och funktionerna i Office-tillägg finns i [plattformsöversikt för Office-tillägg,](https://go.microsoft.com/fwlink/p/?linkid=846362)särskilt avsnittet "Anatomi för ett Office-tillägg".</span><span class="sxs-lookup"><span data-stu-id="921d7-167">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://go.microsoft.com/fwlink/p/?linkid=846362), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="921d7-168">Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet det behöver i manifestet.</span><span class="sxs-lookup"><span data-stu-id="921d7-168">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest.</span></span> <span data-ttu-id="921d7-169">En javascript-api-åtkomstbehörighetsmodell på fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg i åtgärdsfönstret. Majoriteten av tilläggen i Office Store är lässkrivdokument på nivå med nästan alla tillägg som stöder åtminstone ReadDocument-nivån.</span><span class="sxs-lookup"><span data-stu-id="921d7-169">A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level.</span></span> <span data-ttu-id="921d7-170">Mer information om [behörighetsnivåerna finns i Begära behörigheter för API-användning i innehåll och tillägg till åtgärdsfönstret](https://go.microsoft.com/fwlink/p/?linkid=848863).</span><span class="sxs-lookup"><span data-stu-id="921d7-170">For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).</span></span>
  
<span data-ttu-id="921d7-171">När du uppdaterar ett manifest är de typiska ändringarna i ett tilläggs ikon och text.</span><span class="sxs-lookup"><span data-stu-id="921d7-171">When updating a manifest, the typical changes are to an add-in's icon and text.</span></span> <span data-ttu-id="921d7-172">Ibland ändras tilläggskommandon.</span><span class="sxs-lookup"><span data-stu-id="921d7-172">Occasionally, add-in commands change.</span></span> <span data-ttu-id="921d7-173">Men behörigheterna för tillägget ändras inte.</span><span class="sxs-lookup"><span data-stu-id="921d7-173">However, the permissions of the add-in do not change.</span></span> <span data-ttu-id="921d7-174">Webbprogrammet där all kod och logik för tilläggskörningar kan ändras när som helst, vilket är webbprogrammens natur.</span><span class="sxs-lookup"><span data-stu-id="921d7-174">The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="921d7-175">Uppdateringar för tillägg sker på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="921d7-175">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="921d7-176">**Tillägg för företagsrader:** I det här fallet, när en administratör uttryckligen laddade upp ett manifest, kräver tillägget att administratören överför en ny manifestfil för att stödja metadataändringar.</span><span class="sxs-lookup"><span data-stu-id="921d7-176">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes.</span></span> <span data-ttu-id="921d7-177">Nästa gång de relevanta Office-programmen startar uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-177">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="921d7-178">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="921d7-178">The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="921d7-179">Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="921d7-179">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="921d7-180">I avsnittet Tillägg kan admin helt enkelt klicka på LOB-tillägget och välja **uppdateringsknappen** i det nedre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="921d7-180">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="921d7-181">Uppdateringen fungerar bara om versionen av det nya tillägget är större än det befintliga tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-181">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="921d7-182">**Office Store-tillägg:** När en administratör valde ett tillägg från Office Store, om ett tillägg uppdateras i Office Store, uppdateras tillägget senare i Centraliserad distribution.</span><span class="sxs-lookup"><span data-stu-id="921d7-182">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment.</span></span> <span data-ttu-id="921d7-183">Nästa gång de relevanta Office-programmen startar uppdateras tillägget.</span><span class="sxs-lookup"><span data-stu-id="921d7-183">The next time the relevant Office applications start, the add-in will update.</span></span> <span data-ttu-id="921d7-184">Webbprogrammet kan ändras när som helst.</span><span class="sxs-lookup"><span data-stu-id="921d7-184">The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="921d7-185">Mer information</span><span class="sxs-lookup"><span data-stu-id="921d7-185">Learn more</span></span>

<span data-ttu-id="921d7-186">Skapa och bygga [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362)</span><span class="sxs-lookup"><span data-stu-id="921d7-186">Creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362)</span></span>

[<span data-ttu-id="921d7-187">Hantera tillägg i administrationscentret</span><span class="sxs-lookup"><span data-stu-id="921d7-187">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

[<span data-ttu-id="921d7-188">Minderåriga och förvärva tillägg från butiken</span><span class="sxs-lookup"><span data-stu-id="921d7-188">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="921d7-189">Använda centraliserade PowerShell-cmdlets för att hantera tillägg</span><span class="sxs-lookup"><span data-stu-id="921d7-189">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="921d7-190">Felsöka: Användaren ser inte tillägg</span><span class="sxs-lookup"><span data-stu-id="921d7-190">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
