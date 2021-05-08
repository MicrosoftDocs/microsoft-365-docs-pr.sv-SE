---
title: Starta portalen med hjälp av portalstartschemaläggeren
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: I den här artikeln beskrivs hur du kan starta portalen med hjälp av portalstartschemaläggeren
ms.openlocfilehash: 1e62446054f91ff5d2c99520ca65c1681d899ac9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272078"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="9adab-103">Starta portalen med hjälp av SharePoint Portal-startschemat</span><span class="sxs-lookup"><span data-stu-id="9adab-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="9adab-104">En portal är en SharePoint-kommunikationswebbplats i intranätet med hög trafik – en webbplats med allt från 10 000 till över 100 000 användare under några veckor.</span><span class="sxs-lookup"><span data-stu-id="9adab-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="9adab-105">Använd schemaläggaren för portalen för att starta portalen för att se till att användarna får en smidigare visningsupplevelse när de kommer åt den nya SharePoint-portalen.</span><span class="sxs-lookup"><span data-stu-id="9adab-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="9adab-106">Med portalstartschemaläggeren får du hjälp med att fasa in lanseringen genom att samla användare i vågor och hantera URL-omdirigeringar för den nya portalen.</span><span class="sxs-lookup"><span data-stu-id="9adab-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="9adab-107">Under lanseringen av varje omgång kan du samla in feedback från användare, övervaka portalens prestanda och pausa lanseringen för att lösa problem innan du fortsätter med nästa omgång.</span><span class="sxs-lookup"><span data-stu-id="9adab-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="9adab-108">Läs mer om hur du [planerar en portallansering i SharePoint.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="9adab-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="9adab-109">**Det finns två typer av omdirigeringar:**</span><span class="sxs-lookup"><span data-stu-id="9adab-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="9adab-110">**Dubbelriktad**: starta en ny modern SharePoint-portal för att ersätta en befintlig klassisk eller modern SharePoint-portal</span><span class="sxs-lookup"><span data-stu-id="9adab-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="9adab-111">**Omdirigera till en tillfällig sida**: starta en ny modern SharePoint-portal utan en befintlig SharePoint-portal</span><span class="sxs-lookup"><span data-stu-id="9adab-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="9adab-112">Webbplatsbehörigheter måste ställas in separat från vågor som en del av lanseringen.</span><span class="sxs-lookup"><span data-stu-id="9adab-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="9adab-113">Om du till exempel släpper en organisationsomfattande portal kan du ange behörigheter till "Alla utom externa användare" och sedan dela upp användarna i vågor med hjälp av säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="9adab-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="9adab-114">Att lägga till en säkerhetsgrupp i en omgång ger inte säkerhetsgruppen åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="9adab-115">Den här funktionen blir tillgänglig  från panelen Inställningar på startsidan för SharePoint-kommunikationswebbplatser för användare med riktad version från och med maj 2021 och blir tillgänglig för alla kunder senast i juli 2021</span><span class="sxs-lookup"><span data-stu-id="9adab-115">This will feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="9adab-116">PowerShell-versionen av det här verktyget är tillgänglig i dag</span><span class="sxs-lookup"><span data-stu-id="9adab-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="9adab-117">Den här funktionen kan endast användas på moderna SharePoint-kommunikationswebbplatser</span><span class="sxs-lookup"><span data-stu-id="9adab-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="9adab-118">Du måste ha behörigheten webbplatsägare för webbplatsen för att anpassa och schemalägga lanseringen av en portal</span><span class="sxs-lookup"><span data-stu-id="9adab-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="9adab-119">Lanseringar måste schemaläggas minst sju dagar i förväg och varje omgång kan pågå i en till sju dagar</span><span class="sxs-lookup"><span data-stu-id="9adab-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="9adab-120">Antalet vågor som krävs bestäms automatiskt av det förväntade antalet användare</span><span class="sxs-lookup"><span data-stu-id="9adab-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="9adab-121">Innan du schemalägger en portalstart måste verktyget Siddiagnostik för [SharePoint](https://aka.ms/perftool) köras för att kontrollera att startsidan för webbplatsen är felfri</span><span class="sxs-lookup"><span data-stu-id="9adab-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="9adab-122">I slutet av lanseringen kommer alla användare med behörighet till webbplatsen att kunna komma åt den nya webbplatsen</span><span class="sxs-lookup"><span data-stu-id="9adab-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="9adab-123">Om din organisation använder [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections)kan användarna se organisationens ikon i appfältet i Microsoft Teams, men när ikonen väljs kan användarna inte komma åt portalen förrän deras omgång har startat</span><span class="sxs-lookup"><span data-stu-id="9adab-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="9adab-124">Den här funktionen är inte tillgänglig för Office 365 Germany-, Office 365-abonnemang som drivs av 21Vianet (Kina) eller Microsoft 365 för amerikanska myndigheter</span><span class="sxs-lookup"><span data-stu-id="9adab-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="9adab-125">Förstå skillnaderna mellan alternativen för portalstartschemaläggare:</span><span class="sxs-lookup"><span data-stu-id="9adab-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="9adab-126">Tidigare kunde portalstarter bara schemaläggas via SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9adab-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="9adab-127">Nu har du två alternativ som hjälper dig att schemalägga och hantera portalens lansering.</span><span class="sxs-lookup"><span data-stu-id="9adab-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="9adab-128">Lär dig mer om de viktigaste skillnaderna mellan båda verktygen:</span><span class="sxs-lookup"><span data-stu-id="9adab-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="9adab-129">**SharePoint PowerShell-version:**</span><span class="sxs-lookup"><span data-stu-id="9adab-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="9adab-130">Administratörsautentiseringsuppgifter krävs för att [använda SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="9adab-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="9adab-131">Minimikravet för en våg</span><span class="sxs-lookup"><span data-stu-id="9adab-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="9adab-132">Schemalägg lanseringen baserat på UTC-tidszon (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="9adab-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="9adab-133">**I produktversion:**</span><span class="sxs-lookup"><span data-stu-id="9adab-133">**In-product version:**</span></span>

- <span data-ttu-id="9adab-134">Autentiseringsuppgifter för webbplatsägare krävs</span><span class="sxs-lookup"><span data-stu-id="9adab-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="9adab-135">Minimikravet för två vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="9adab-136">Schemalägga lanseringen baserat på portalens lokala tidszon enligt de nationella inställningarna</span><span class="sxs-lookup"><span data-stu-id="9adab-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="9adab-137">Komma igång med portalstartschemaläggeren</span><span class="sxs-lookup"><span data-stu-id="9adab-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="9adab-138">Innan du använder schemaläggaren [](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) för portalen ska du lägga till  alla användare som behöver åtkomst till den här webbplatsen via Webbplatsbehörigheter som webbplatsägare, Webbplatsmedlem eller Besökare.</span><span class="sxs-lookup"><span data-stu-id="9adab-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="9adab-139">Börja sedan schemalägga portalens lansering genom att öppna portalstartschemaläggningen på ett av två sätt:</span><span class="sxs-lookup"><span data-stu-id="9adab-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="9adab-140">**Alternativ 1:** De första gånger som du redigerar och publicerar om ändringar på startsidan – eller upp till startsidan version 3.0 – uppmanas du att använda schemaläggningsverktyget för portalstart.</span><span class="sxs-lookup"><span data-stu-id="9adab-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="9adab-141">Välj **Schemalägg lansering** för att gå framåt med schemaläggning.</span><span class="sxs-lookup"><span data-stu-id="9adab-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="9adab-142">Eller välj **Publicera om** för att publicera om sidredigeringarna utan att schemalägga lanseringen.</span><span class="sxs-lookup"><span data-stu-id="9adab-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![Bild av uppmaningen att använda portalstartschemaläggeren när du publicerar om startsidan](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="9adab-144">**Alternativ 2:** Du kan när som helst gå till startsidan  för  SharePoint-kommunikationswebbplatsen, välja Inställningar och sedan Schemalägga webbplatslansering för att schemalägga portalens lansering.</span><span class="sxs-lookup"><span data-stu-id="9adab-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![Bild av fönstret Inställningar med Schemalägg en webbplatslansering markerat](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="9adab-146">Bekräfta sedan portalens hälsoresultat och gör förbättringar i portalen om det behövs med hjälp av verktyget Siddiagnostik för [SharePoint](https://aka.ms/perftool) tills portalen får ett **felfritt** resultat.</span><span class="sxs-lookup"><span data-stu-id="9adab-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="9adab-147">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="9adab-147">Then, select **Next**.</span></span>

    ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="9adab-149">Du kan inte redigera webbplatsens namn och beskrivning från portalstartschemaläggeren, utan  du kan i stället ändra den genom att välja Inställningar och sedan Webbplatsinformation på startsidan. </span><span class="sxs-lookup"><span data-stu-id="9adab-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="9adab-150">Välj **antalet förväntade användare** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="9adab-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="9adab-151">I den här bilden visas det antal användare som troligen behöver åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="9adab-152">Uppstartsschemat för portalen bestämmer automatiskt det bästa antalet vågor beroende på vilka användare som förväntas göra så här:</span><span class="sxs-lookup"><span data-stu-id="9adab-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="9adab-153">Mindre än 10 000 användare: två vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="9adab-154">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="9adab-155">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="9adab-156">Fler än 100 000 användare: Fem vågor och kontakta ditt Microsoft-kontoteam</span><span class="sxs-lookup"><span data-stu-id="9adab-156">More than 100k users: Five waves and contact your Microsoft account team</span></span>

5.  <span data-ttu-id="9adab-157">Fastställ sedan vilken **typ av omdirigering som** behövs:</span><span class="sxs-lookup"><span data-stu-id="9adab-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="9adab-158">Alternativ 1: Skicka användare till en befintlig **SharePoint-sida (dubbelriktad)** – Använd det här alternativet när du startar en ny modern SharePoint-portal för att ersätta en befintlig SharePoint-portal.</span><span class="sxs-lookup"><span data-stu-id="9adab-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="9adab-159">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="9adab-160">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="9adab-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="9adab-161">När du använder dubbelriktat alternativ måste den person som schemalägger lanseringen också ha webbplatsägaresbehörighet till den andra SharePoint-portalen.</span><span class="sxs-lookup"><span data-stu-id="9adab-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="9adab-162">**Alternativ 2:** Skicka användare till en automatiskt genererad tillfällig sida (tillfällig sidomdirigering) – Använd en tillfällig sidomdirigering när det inte finns någon befintlig SharePoint-portal.</span><span class="sxs-lookup"><span data-stu-id="9adab-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="9adab-163">Användare dirigeras till en ny modern SharePoint-portal och om en användare befinner sig i en omgång som inte har startats omdirigeras de till en tillfällig sida.</span><span class="sxs-lookup"><span data-stu-id="9adab-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="9adab-164">**Alternativ 3: Skicka användare** till en extern sida – Ge en extern URL till en tillfällig landningssida tills användaromgången lanseras.</span><span class="sxs-lookup"><span data-stu-id="9adab-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="9adab-165">Dela upp åhörarna i vågor.</span><span class="sxs-lookup"><span data-stu-id="9adab-165">Break up your audience into waves.</span></span> <span data-ttu-id="9adab-166">Addera upp till 20 säkerhetsgrupper per omgång.</span><span class="sxs-lookup"><span data-stu-id="9adab-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="9adab-167">Omgångsinformation kan redigeras till lanseringen av varje omgång.</span><span class="sxs-lookup"><span data-stu-id="9adab-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="9adab-168">Varje omgång kan pågå minst en dag (24 timmar) och som mest sju dagar.</span><span class="sxs-lookup"><span data-stu-id="9adab-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="9adab-169">Det gör att SharePoint och den tekniska miljön kan anpassa sig till och skala för det stora antalet webbplatsanvändare.</span><span class="sxs-lookup"><span data-stu-id="9adab-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="9adab-170">När du schemalägger en start via användargränssnittet baseras tidszonen på webbplatsens nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="9adab-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="9adab-171">Startschemat för portalen används automatiskt i minst två omgångar.</span><span class="sxs-lookup"><span data-stu-id="9adab-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="9adab-172">Men PowerShell-versionen av det här verktyget ger möjlighet till 1 omgång.</span><span class="sxs-lookup"><span data-stu-id="9adab-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="9adab-173">Microsoft 365-grupper stöds inte av den här versionen av portalstartschemaläggeren.</span><span class="sxs-lookup"><span data-stu-id="9adab-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="9adab-174">Bestäm vilka som behöver visa webbplatsen direkt och ange sin information i fältet **Användare undantas från vågor.**</span><span class="sxs-lookup"><span data-stu-id="9adab-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="9adab-175">Dessa användare utesluts från vågor och omdirigeras inte före, under eller efter lanseringen.</span><span class="sxs-lookup"><span data-stu-id="9adab-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="9adab-176">Bekräfta portalstartinformationen och välj **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="9adab-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="9adab-177">När lanseringen har schemalagts måste ändringar på startsidan för SharePoint-portalen få ett felfritt diagnostikresultat innan portalstarten återupptas.</span><span class="sxs-lookup"><span data-stu-id="9adab-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>


## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="9adab-178">Göra ändringar i en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="9adab-178">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="9adab-179">Information om lanseringen kan redigeras för varje omgång fram till datumet för vågens lansering.</span><span class="sxs-lookup"><span data-stu-id="9adab-179">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="9adab-180">Om du vill redigera informationen om portalstart går du **till Inställningar** och **väljer Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="9adab-180">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="9adab-181">Välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9adab-181">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="9adab-182">När du är klar med redigeringarna väljer du **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9adab-182">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="9adab-183">Ta bort en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="9adab-183">Delete a scheduled portal launch</span></span>

<span data-ttu-id="9adab-184">Startar schemalagda med hjälp av schemaläggningsverktyget för portalstart kan avbrytas eller tas bort när som helst även om vissa vågor redan har startats.</span><span class="sxs-lookup"><span data-stu-id="9adab-184">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="9adab-185">Om du vill avbryta lanseringen av portalen går du **till Inställningar** och **Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="9adab-185">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="9adab-186">Välj sedan Ta **bort** och när du ser meddelandet nedan väljer du Ta **bort** igen.</span><span class="sxs-lookup"><span data-stu-id="9adab-186">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="9adab-188">Använda PowerShell-portalens startschemaläggare</span><span class="sxs-lookup"><span data-stu-id="9adab-188">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="9adab-189">Startschemaverktyget för SharePoint Portal var ursprungligen endast tillgängligt via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) och kommer att fortsätta stödjas via PowerShell för kunder som föredrar den här metoden.</span><span class="sxs-lookup"><span data-stu-id="9adab-189">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="9adab-190">Samma anteckningar i början av den här artikeln gäller båda versionerna av portalstartschemaläggeren.</span><span class="sxs-lookup"><span data-stu-id="9adab-190">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="9adab-191">Du behöver administratörsbehörighet för att använda SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9adab-191">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="9adab-192">Information om portalstart för lanseringar som skapas i PowerShell visas och kan hanteras i det nya startschemaverktyget för portal i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9adab-192">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="9adab-193">Appkonfiguration och anslutning till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9adab-193">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="9adab-194">[Ladda ned den senaste versionen av SharePoint Online Management Shell.](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="9adab-194">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9adab-195">Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägga till eller ta bort program och avinstallerar "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="9adab-195">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="9adab-196">På sidan Download Center väljer du språk och klickar sedan på knappen Ladda ned.</span><span class="sxs-lookup"><span data-stu-id="9adab-196">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="9adab-197">Du uppmanas att välja mellan att ladda ned en x64- och x86-.msi fil.</span><span class="sxs-lookup"><span data-stu-id="9adab-197">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="9adab-198">Ladda ned x64-filen om du kör 64-bitarsversionen av Windows eller x86-filen om du kör 32-bitarsversionen.</span><span class="sxs-lookup"><span data-stu-id="9adab-198">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="9adab-199">Om du inte vet, se Vilken [version av Windows-operativsystemet använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="9adab-199">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="9adab-200">När filen har laddats ned kör du den och följer anvisningarna i Installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="9adab-200">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="9adab-201">Anslut till SharePoint som [global administratör eller SharePoint-administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9adab-201">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="9adab-202">Mer information finns i Komma [igång med SharePoint Online Management Shell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="9adab-202">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="9adab-203">Visa eventuella befintliga startinställningar för portalen</span><span class="sxs-lookup"><span data-stu-id="9adab-203">View any existing portal launch setups</span></span>

<span data-ttu-id="9adab-204">Så här ser du om det finns befintliga konfigurationer för portalstart:</span><span class="sxs-lookup"><span data-stu-id="9adab-204">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="9adab-205">Schemalägga en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="9adab-205">Schedule a portal launch on the site</span></span>

<span data-ttu-id="9adab-206">Antalet vågor som krävs beror på den förväntade startstorleken.</span><span class="sxs-lookup"><span data-stu-id="9adab-206">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="9adab-207">Färre än 10 000 användare: en omgång</span><span class="sxs-lookup"><span data-stu-id="9adab-207">Less than 10k users: One wave</span></span>
- <span data-ttu-id="9adab-208">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-208">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="9adab-209">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="9adab-209">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="9adab-210">Fler än 100 000 användare: Fem vågor och kontakta ditt Microsoft-kontoteam</span><span class="sxs-lookup"><span data-stu-id="9adab-210">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="9adab-211">Steg för dubbelriktad omdirigering</span><span class="sxs-lookup"><span data-stu-id="9adab-211">Steps for bidirectional redirection</span></span>

<span data-ttu-id="9adab-212">Dubbelriktad omdirigering innebär att en ny modern SharePoint Online-portal lanseras så att en befintlig klassisk eller modern SharePoint-portal ersätts.</span><span class="sxs-lookup"><span data-stu-id="9adab-212">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="9adab-213">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-213">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="9adab-214">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="9adab-214">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="9adab-215">Vi stöder endast omdirigering mellan standardhemsidan på den gamla webbplatsen och standardhemsidan på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-215">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="9adab-216">Om du har administratörer eller ägare som behöver åtkomst till de gamla och nya webbplatserna utan att omdirigeras, se till att de listas med `WaveOverrideUsers` parametern.</span><span class="sxs-lookup"><span data-stu-id="9adab-216">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="9adab-217">Så här migrerar du användare från en befintlig SharePoint-webbplats till en ny SharePoint-webbplats på ett stegat sätt:</span><span class="sxs-lookup"><span data-stu-id="9adab-217">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="9adab-218">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="9adab-218">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="9adab-219">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9adab-219">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="9adab-220">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="9adab-220">Complete validation.</span></span> <span data-ttu-id="9adab-221">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9adab-221">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="9adab-222">Steg för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="9adab-222">Steps for redirection to temporary page</span></span>

<span data-ttu-id="9adab-223">Tillfällig sidomdirigering bör användas när det inte finns någon befintlig SharePoint-portal.</span><span class="sxs-lookup"><span data-stu-id="9adab-223">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="9adab-224">Användare dirigeras till en ny modern SharePoint Online-portal på ett enhetligt sätt.</span><span class="sxs-lookup"><span data-stu-id="9adab-224">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="9adab-225">Om en användare går i en omgång som inte har startats omdirigeras de till en tillfällig sida (alla URL-adresser).</span><span class="sxs-lookup"><span data-stu-id="9adab-225">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="9adab-226">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="9adab-226">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="9adab-227">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9adab-227">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="9adab-228">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="9adab-228">Complete validation.</span></span> <span data-ttu-id="9adab-229">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9adab-229">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="9adab-230">Pausa eller starta om en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="9adab-230">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="9adab-231">Kör följande kommando för att pausa en pågående portalstart och tillfälligt förhindra att kommande omgångsförlopp uppstår:</span><span class="sxs-lookup"><span data-stu-id="9adab-231">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="9adab-232">Verifiera att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9adab-232">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="9adab-233">Om du vill starta om en portalstart som har pausats kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="9adab-233">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="9adab-234">Kontrollera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="9adab-234">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="9adab-235">Ta bort en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="9adab-235">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="9adab-236">Kör följande kommando för att ta bort en portalstart som är schemalagd eller pågår för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="9adab-236">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="9adab-237">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="9adab-237">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="9adab-238">Mer information</span><span class="sxs-lookup"><span data-stu-id="9adab-238">Learn more</span></span>

[<span data-ttu-id="9adab-239">Planera lanseringsplanen för portalen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9adab-239">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="9adab-240">Planera din kommunikationswebbplats</span><span class="sxs-lookup"><span data-stu-id="9adab-240">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)