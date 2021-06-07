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
ms.openlocfilehash: e77668b3c21b43de1a2e30dc7181842770a24784
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769210"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="94dd6-103">Starta portalen med hjälp SharePoint- eller portalstartschemaläggeren</span><span class="sxs-lookup"><span data-stu-id="94dd6-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="94dd6-104">En portal är en SharePoint-kommunikationswebbplats i intranätet med hög trafik – en webbplats med allt från 10 000 till över 100 000 användare under några veckor.</span><span class="sxs-lookup"><span data-stu-id="94dd6-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="94dd6-105">Använd portalstartschemaläggren för att starta portalen för att se till att användarna får en smidigare visningsupplevelse när de använder den nya SharePoint portalen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="94dd6-106">Med portalstartschemaläggeren får du hjälp med att fasa in lanseringen genom att samla användare i vågor och hantera URL-omdirigeringar för den nya portalen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="94dd6-107">Under lanseringen av varje omgång kan du samla in feedback från användare, övervaka portalens prestanda och pausa lanseringen för att lösa problem innan du fortsätter med nästa omgång.</span><span class="sxs-lookup"><span data-stu-id="94dd6-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="94dd6-108">Läs mer om hur du [planerar en portalstart i SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="94dd6-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="94dd6-109">**Det finns två typer av omdirigeringar:**</span><span class="sxs-lookup"><span data-stu-id="94dd6-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="94dd6-110">**Dubbelriktad**: starta en ny modern SharePoint att ersätta en befintlig klassisk SharePoint eller modern portal</span><span class="sxs-lookup"><span data-stu-id="94dd6-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="94dd6-111">**Omdirigera till en tillfällig sida**: starta en ny modern SharePoint portal utan befintlig SharePoint portal</span><span class="sxs-lookup"><span data-stu-id="94dd6-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="94dd6-112">Webbplatsbehörigheter måste ställas in separat från vågor som en del av lanseringen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="94dd6-113">Om du till exempel släpper en organisationsomfattande portal kan du ange behörigheter till "Alla utom externa användare" och sedan dela upp användarna i vågor med hjälp av säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="94dd6-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="94dd6-114">Att lägga till en säkerhetsgrupp i en omgång ger inte säkerhetsgruppen åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="94dd6-115">Den här funktionen kommer att vara åtkomlig från **panelen Inställningar** på startsidan för SharePoint-kommunikationswebbplatser för kunder med riktad version från och med maj 2021 och blir tillgänglig för alla kunder senast i juli 2021</span><span class="sxs-lookup"><span data-stu-id="94dd6-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="94dd6-116">PowerShell-versionen av det här verktyget är tillgänglig i dag</span><span class="sxs-lookup"><span data-stu-id="94dd6-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="94dd6-117">Den här funktionen kan endast användas på moderna SharePoint kommunikationswebbplatser</span><span class="sxs-lookup"><span data-stu-id="94dd6-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="94dd6-118">Du måste ha behörigheten webbplatsägare för webbplatsen för att anpassa och schemalägga lanseringen av en portal</span><span class="sxs-lookup"><span data-stu-id="94dd6-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="94dd6-119">Lanseringar måste schemaläggas minst sju dagar i förväg och varje omgång kan pågå i en till sju dagar</span><span class="sxs-lookup"><span data-stu-id="94dd6-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="94dd6-120">Antalet vågor som krävs bestäms automatiskt av det förväntade antalet användare</span><span class="sxs-lookup"><span data-stu-id="94dd6-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="94dd6-121">Innan du schemalägger en portalstart [måste SharePoint för](https://aka.ms/perftool) att kontrollera att startsidan på webbplatsen är felfri</span><span class="sxs-lookup"><span data-stu-id="94dd6-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="94dd6-122">I slutet av lanseringen kommer alla användare med behörighet till webbplatsen att kunna komma åt den nya webbplatsen</span><span class="sxs-lookup"><span data-stu-id="94dd6-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="94dd6-123">Om din organisation använder [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections)kan användarna se organisationens ikon i appfältet i Microsoft Teams, men när ikonen väljs kan användarna inte komma åt portalen förrän deras omgång har startats</span><span class="sxs-lookup"><span data-stu-id="94dd6-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="94dd6-124">Den här funktionen är inte tillgänglig för Office 365 Germany, Office 365 som drivs av 21Vianet (Kina) eller i Microsoft 365 för myndigheter i USA</span><span class="sxs-lookup"><span data-stu-id="94dd6-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="94dd6-125">Förstå skillnaderna mellan alternativen för portalstartschemaläggare:</span><span class="sxs-lookup"><span data-stu-id="94dd6-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="94dd6-126">Tidigare kunde portalstarter bara schemaläggas via SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94dd6-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="94dd6-127">Nu har du två alternativ som hjälper dig att schemalägga och hantera portalens lansering.</span><span class="sxs-lookup"><span data-stu-id="94dd6-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="94dd6-128">Lär dig mer om de viktigaste skillnaderna mellan båda verktygen:</span><span class="sxs-lookup"><span data-stu-id="94dd6-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="94dd6-129">**SharePoint PowerShell-version:**</span><span class="sxs-lookup"><span data-stu-id="94dd6-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="94dd6-130">Administratörsautentiseringsuppgifter krävs [för att använda SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="94dd6-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="94dd6-131">Minimikravet för en våg</span><span class="sxs-lookup"><span data-stu-id="94dd6-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="94dd6-132">Schemalägg lanseringen baserat på UTC-tidszon (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="94dd6-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="94dd6-133">**I produktversion:**</span><span class="sxs-lookup"><span data-stu-id="94dd6-133">**In-product version:**</span></span>

- <span data-ttu-id="94dd6-134">Autentiseringsuppgifter för webbplatsägare krävs</span><span class="sxs-lookup"><span data-stu-id="94dd6-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="94dd6-135">Minimikravet för två vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="94dd6-136">Schemalägga lanseringen baserat på portalens lokala tidszon enligt de nationella inställningarna</span><span class="sxs-lookup"><span data-stu-id="94dd6-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="94dd6-137">Komma igång med portalstartschemaläggeren</span><span class="sxs-lookup"><span data-stu-id="94dd6-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="94dd6-138">Innan du använder schemaläggaren [](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) för portalen ska du lägga till  alla användare som behöver åtkomst till den här webbplatsen via Webbplatsbehörigheter som webbplatsägare, Webbplatsmedlem eller Besökare.</span><span class="sxs-lookup"><span data-stu-id="94dd6-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="94dd6-139">Börja sedan schemalägga portalens lansering genom att öppna portalstartschemaläggningen på ett av två sätt:</span><span class="sxs-lookup"><span data-stu-id="94dd6-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="94dd6-140">**Alternativ 1:** De första gånger som du redigerar och publicerar om ändringar på startsidan – eller upp till startsidan version 3.0 – uppmanas du att använda schemaläggningsverktyget för portalstart.</span><span class="sxs-lookup"><span data-stu-id="94dd6-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="94dd6-141">Välj **Schemalägg lansering** för att gå framåt med schemaläggning.</span><span class="sxs-lookup"><span data-stu-id="94dd6-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="94dd6-142">Eller välj **Publicera om** för att publicera om sidredigeringarna utan att schemalägga lanseringen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![Bild av uppmaningen att använda portalstartschemaläggeren när du publicerar om startsidan](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="94dd6-144">**Alternativ 2:** Du kan när som helst gå till startsidan för SharePoint-kommunikationswebbplatsen, välja **Inställningar** och sedan Schemalägga lanseringen av webbplatsen för att schemalägga portalens lansering. </span><span class="sxs-lookup"><span data-stu-id="94dd6-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![Bild av Inställningar med Schemalägg en webbplatslansering markerat](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="94dd6-146">Bekräfta sedan portalens hälsoresultat och gör förbättringar i portalen om det **behövs** med hjälp av siddiagnostik för [SharePoint](https://aka.ms/perftool) tills portalen får ett hälsoresultat.</span><span class="sxs-lookup"><span data-stu-id="94dd6-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="94dd6-147">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="94dd6-147">Then, select **Next**.</span></span>

    ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="94dd6-149">Du kan inte redigera webbplatsens namn och beskrivning från portalstartschemaläggaren och i stället  ändra den genom att **välja Inställningar** och sedan Webbplatsinformation på startsidan.</span><span class="sxs-lookup"><span data-stu-id="94dd6-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="94dd6-150">Välj **antalet förväntade användare** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="94dd6-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="94dd6-151">I den här bilden visas det antal användare som troligen behöver åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="94dd6-152">Uppstartsschemat för portalen bestämmer automatiskt det bästa antalet vågor beroende på vilka användare som förväntas göra så här:</span><span class="sxs-lookup"><span data-stu-id="94dd6-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="94dd6-153">Mindre än 10 000 användare: två vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="94dd6-154">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="94dd6-155">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="94dd6-156">Fler än 100 000 användare: Fem vågor och kontakta microsoft via stegen som anges i Starta portalen med över 100 000 användare.</span><span class="sxs-lookup"><span data-stu-id="94dd6-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span> 

5.  <span data-ttu-id="94dd6-157">Fastställ sedan vilken **typ av omdirigering som** behövs:</span><span class="sxs-lookup"><span data-stu-id="94dd6-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="94dd6-158">Alternativ 1: Skicka användare till en **befintlig SharePoint -sida (dubbelriktad)** – Använd det här alternativet när du startar en ny modern SharePoint-portal för att ersätta en SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="94dd6-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="94dd6-159">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="94dd6-160">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="94dd6-161">När du använder dubbelriktat alternativ måste den person som schemalägger lanseringen också ha webbplatsägaresbehörighet till den andra SharePoint portalen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="94dd6-162">**Alternativ 2:** Skicka användare till en automatiskt genererad tillfällig sida (tillfällig sidomdirigering) – Använd en tillfällig sidomdirigering när det inte finns någon SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="94dd6-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="94dd6-163">Användare dirigeras till en ny modern SharePoint-portal och om en användare befinner sig i en omgång som inte har startats omdirigeras de till en tillfällig sida.</span><span class="sxs-lookup"><span data-stu-id="94dd6-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="94dd6-164">**Alternativ 3: Skicka användare** till en extern sida – Ge en extern URL till en tillfällig landningssida tills användaromgången lanseras.</span><span class="sxs-lookup"><span data-stu-id="94dd6-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="94dd6-165">Dela upp åhörarna i vågor.</span><span class="sxs-lookup"><span data-stu-id="94dd6-165">Break up your audience into waves.</span></span> <span data-ttu-id="94dd6-166">Addera upp till 20 säkerhetsgrupper per omgång.</span><span class="sxs-lookup"><span data-stu-id="94dd6-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="94dd6-167">Omgångsinformation kan redigeras till lanseringen av varje omgång.</span><span class="sxs-lookup"><span data-stu-id="94dd6-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="94dd6-168">Varje omgång kan pågå minst en dag (24 timmar) och som mest sju dagar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="94dd6-169">Det gör SharePoint och den tekniska miljön en möjlighet att anpassa sig till och skala till det stora antalet webbplatsanvändare.</span><span class="sxs-lookup"><span data-stu-id="94dd6-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="94dd6-170">När du schemalägger en start via användargränssnittet baseras tidszonen på webbplatsens nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="94dd6-171">Startschemat för portalen används automatiskt i minst två omgångar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="94dd6-172">Men PowerShell-versionen av det här verktyget ger möjlighet till 1 omgång.</span><span class="sxs-lookup"><span data-stu-id="94dd6-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="94dd6-173">Microsoft 365-grupper stöds inte av den här versionen av portalstartschemaläggaren.</span><span class="sxs-lookup"><span data-stu-id="94dd6-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="94dd6-174">Bestäm vilka som behöver visa webbplatsen direkt och ange sin information i fältet **Användare undantas från vågor.**</span><span class="sxs-lookup"><span data-stu-id="94dd6-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="94dd6-175">Dessa användare utesluts från vågor och omdirigeras inte före, under eller efter lanseringen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    >[!NOTE]
    > <span data-ttu-id="94dd6-176">Upp till 50 distinkta användare eller säkerhetsgrupper max kan läggas till.</span><span class="sxs-lookup"><span data-stu-id="94dd6-176">Up to 50 distinct users or security groups max can be added.</span></span> <span data-ttu-id="94dd6-177">Använd säkerhetsgrupper när fler än 50 personer behövs för att få åtkomst till portalen innan vågorna ska starta.</span><span class="sxs-lookup"><span data-stu-id="94dd6-177">Use security groups when you need more than 50 individuals to get access to the portal before the waves start launching.</span></span> 

8.  <span data-ttu-id="94dd6-178">Bekräfta portalstartinformationen och välj **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="94dd6-178">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="94dd6-179">När lanseringen har schemalagts måste ändringar på startsidan för SharePoint-portalen få ett felfritt diagnostikresultat innan portalstarten återupptas.</span><span class="sxs-lookup"><span data-stu-id="94dd6-179">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="94dd6-180">Starta en portal med fler än 100 000 användare</span><span class="sxs-lookup"><span data-stu-id="94dd6-180">Launch a portal with over 100k users</span></span>

<span data-ttu-id="94dd6-181">Om du planerar att starta en portal med över 100 000 användare kan du skicka en supportbegäran enligt anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="94dd6-181">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="94dd6-182">Se till att inkludera all information som efterfrågas.</span><span class="sxs-lookup"><span data-stu-id="94dd6-182">Make sure to include all the requested information.</span></span>

<span data-ttu-id="94dd6-183">**Gör så här:**</span><span class="sxs-lookup"><span data-stu-id="94dd6-183">**Follow these steps:**</span></span>
1. <span data-ttu-id="94dd6-184">Gå till https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="94dd6-184">Go to https://admin.microsoft.com</span></span>
2. <span data-ttu-id="94dd6-185">Se till att du använder den nya förhandsversionen av administrationscentret</span><span class="sxs-lookup"><span data-stu-id="94dd6-185">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="94dd6-186">I det vänstra navigeringsfönstret väljer du **Support** och sedan **Ny tjänstbegäran**</span><span class="sxs-lookup"><span data-stu-id="94dd6-186">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="94dd6-187">Detta aktiverar fönstret **Behöver du hjälp?** till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-187">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="94dd6-188">Ange **"Starta e-SharePoint** med 100 000 användare" för Kort beskrivning av problemet</span><span class="sxs-lookup"><span data-stu-id="94dd6-188">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="94dd6-189">Välj sedan **Kontakta support**</span><span class="sxs-lookup"><span data-stu-id="94dd6-189">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="94dd6-190">Under **Beskrivning** anger du "Starta SharePoint portal med 100 000 användare"</span><span class="sxs-lookup"><span data-stu-id="94dd6-190">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="94dd6-191">Fyll i resten av informationen och välj **sedan Kontakta mig**</span><span class="sxs-lookup"><span data-stu-id="94dd6-191">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="94dd6-192">När biljetten har skapats bör du ange följande information för supportagenten:</span><span class="sxs-lookup"><span data-stu-id="94dd6-192">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="94dd6-193">URL:er för portalen</span><span class="sxs-lookup"><span data-stu-id="94dd6-193">Portal URL's</span></span> 
   - <span data-ttu-id="94dd6-194">Antal användare som förväntat</span><span class="sxs-lookup"><span data-stu-id="94dd6-194">Number of users expected</span></span>
   - <span data-ttu-id="94dd6-195">Beräknat startschema</span><span class="sxs-lookup"><span data-stu-id="94dd6-195">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="94dd6-196">Göra ändringar i en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="94dd6-196">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="94dd6-197">Information om lanseringen kan redigeras för varje omgång fram till datumet för vågens lansering.</span><span class="sxs-lookup"><span data-stu-id="94dd6-197">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="94dd6-198">Om du vill redigera informationen om portalstart går **du Inställningar** väljer **Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="94dd6-198">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="94dd6-199">Välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="94dd6-199">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="94dd6-200">När du är klar med redigeringarna väljer du **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="94dd6-200">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="94dd6-201">Ta bort en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="94dd6-201">Delete a scheduled portal launch</span></span>

<span data-ttu-id="94dd6-202">Startar schemalagda med hjälp av schemaläggningsverktyget för portalstart kan avbrytas eller tas bort när som helst även om vissa vågor redan har startats.</span><span class="sxs-lookup"><span data-stu-id="94dd6-202">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="94dd6-203">Om du vill avbryta portalens lansering går du till **Inställningar** **Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="94dd6-203">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="94dd6-204">Välj sedan Ta **bort** och när du ser meddelandet nedan väljer du Ta **bort** igen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-204">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="94dd6-206">Använda PowerShell-portalens startschemaläggare</span><span class="sxs-lookup"><span data-stu-id="94dd6-206">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="94dd6-207">Startschemaverktyget SharePoint Portal var ursprungligen endast tillgängligt via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) och kommer att fortsätta stödjas via PowerShell för kunder som föredrar den här metoden.</span><span class="sxs-lookup"><span data-stu-id="94dd6-207">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="94dd6-208">Samma anteckningar i början av den här artikeln gäller båda versionerna av portalstartschemaläggeren.</span><span class="sxs-lookup"><span data-stu-id="94dd6-208">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="94dd6-209">Du behöver administratörsbehörighet för att använda SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94dd6-209">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="94dd6-210">Information om portalstart för lanseringar som skapas i PowerShell visas och kan hanteras i det nya startschemaverktyget för portal i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="94dd6-210">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="94dd6-211">Appkonfiguration och anslutning till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="94dd6-211">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="94dd6-212">[Ladda ned de senaste SharePoint Online Management Shell.](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="94dd6-212">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="94dd6-213">Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägga till eller ta bort program och avinstallerar "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="94dd6-213">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="94dd6-214">På sidan Download Center väljer du språk och klickar sedan på knappen Ladda ned.</span><span class="sxs-lookup"><span data-stu-id="94dd6-214">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="94dd6-215">Du uppmanas att välja mellan att ladda ned en x64- och x86-.msi fil.</span><span class="sxs-lookup"><span data-stu-id="94dd6-215">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="94dd6-216">Ladda ned x64-filen om du kör 64-bitarsversionen av Windows eller x86-filen om du kör 32-bitarsversionen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-216">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="94dd6-217">Om du inte vet vilken version av [operativsystemet Windows använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="94dd6-217">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="94dd6-218">När filen har laddats ned kör du den och följer anvisningarna i Installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="94dd6-218">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="94dd6-219">Anslut att SharePoint som [global administratör eller SharePoint administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94dd6-219">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="94dd6-220">Mer information finns i Komma [igång med SharePoint Online Management Shell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="94dd6-220">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="94dd6-221">Visa eventuella befintliga startinställningar för portalen</span><span class="sxs-lookup"><span data-stu-id="94dd6-221">View any existing portal launch setups</span></span>

<span data-ttu-id="94dd6-222">Så här ser du om det finns befintliga konfigurationer för portalstart:</span><span class="sxs-lookup"><span data-stu-id="94dd6-222">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="94dd6-223">Schemalägga en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="94dd6-223">Schedule a portal launch on the site</span></span>

<span data-ttu-id="94dd6-224">Antalet vågor som krävs beror på den förväntade startstorleken.</span><span class="sxs-lookup"><span data-stu-id="94dd6-224">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="94dd6-225">Färre än 10 000 användare: en omgång</span><span class="sxs-lookup"><span data-stu-id="94dd6-225">Less than 10k users: One wave</span></span>
- <span data-ttu-id="94dd6-226">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-226">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="94dd6-227">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="94dd6-227">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="94dd6-228">Fler än 100 000 användare: Fem vågor och kontakta ditt Microsoft-kontoteam</span><span class="sxs-lookup"><span data-stu-id="94dd6-228">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="94dd6-229">Steg för dubbelriktad omdirigering</span><span class="sxs-lookup"><span data-stu-id="94dd6-229">Steps for bidirectional redirection</span></span>

<span data-ttu-id="94dd6-230">Dubbelriktad omdirigering innebär att en ny modern onlineportal SharePoint lanseras och ersätter en befintlig SharePoint klassisk eller modern portal.</span><span class="sxs-lookup"><span data-stu-id="94dd6-230">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="94dd6-231">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-231">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="94dd6-232">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-232">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="94dd6-233">Vi stöder endast omdirigering mellan standardhemsidan på den gamla webbplatsen och standardhemsidan på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-233">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="94dd6-234">Om du har administratörer eller ägare som behöver åtkomst till de gamla och nya webbplatserna utan att omdirigeras, se till att de listas med `WaveOverrideUsers` parametern.</span><span class="sxs-lookup"><span data-stu-id="94dd6-234">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="94dd6-235">Så här migrerar du användare från SharePoint webbplats till en SharePoint webbplats på ett stegat sätt:</span><span class="sxs-lookup"><span data-stu-id="94dd6-235">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="94dd6-236">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-236">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="94dd6-237">Exempel:</span><span class="sxs-lookup"><span data-stu-id="94dd6-237">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="94dd6-238">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-238">Complete validation.</span></span> <span data-ttu-id="94dd6-239">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="94dd6-239">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="94dd6-240">Steg för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="94dd6-240">Steps for redirection to temporary page</span></span>

<span data-ttu-id="94dd6-241">Tillfällig sidomdirigering bör användas när det inte SharePoint en befintlig portal.</span><span class="sxs-lookup"><span data-stu-id="94dd6-241">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="94dd6-242">Användare dirigeras till en ny modern SharePoint Online-portal på ett enhetligt sätt.</span><span class="sxs-lookup"><span data-stu-id="94dd6-242">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="94dd6-243">Om en användare går i en omgång som inte har startats omdirigeras de till en tillfällig sida (alla URL-adresser).</span><span class="sxs-lookup"><span data-stu-id="94dd6-243">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="94dd6-244">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="94dd6-244">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="94dd6-245">Exempel:</span><span class="sxs-lookup"><span data-stu-id="94dd6-245">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="94dd6-246">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-246">Complete validation.</span></span> <span data-ttu-id="94dd6-247">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="94dd6-247">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="94dd6-248">Pausa eller starta om en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="94dd6-248">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="94dd6-249">Kör följande kommando för att pausa en pågående portalstart och tillfälligt förhindra att kommande omgångsförlopp uppstår:</span><span class="sxs-lookup"><span data-stu-id="94dd6-249">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="94dd6-250">Verifiera att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="94dd6-250">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="94dd6-251">Om du vill starta om en portalstart som har pausats kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="94dd6-251">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="94dd6-252">Kontrollera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="94dd6-252">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="94dd6-253">Ta bort en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="94dd6-253">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="94dd6-254">Kör följande kommando för att ta bort en portalstart som är schemalagd eller pågår för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="94dd6-254">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="94dd6-255">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="94dd6-255">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="94dd6-256">Mer information</span><span class="sxs-lookup"><span data-stu-id="94dd6-256">Learn more</span></span>

[<span data-ttu-id="94dd6-257">Planera lanseringsplanen för portalen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="94dd6-257">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="94dd6-258">Planera din kommunikationswebbplats</span><span class="sxs-lookup"><span data-stu-id="94dd6-258">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
