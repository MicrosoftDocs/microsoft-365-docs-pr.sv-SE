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
ms.openlocfilehash: a0ba40849b47af93f45bcc9c77f2ba6d8f715dc5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229557"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="7495a-103">Starta portalen med hjälp SharePoint- eller portalstartschemaläggeren</span><span class="sxs-lookup"><span data-stu-id="7495a-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="7495a-104">En portal är en SharePoint-kommunikationswebbplats i intranätet med hög trafik – en webbplats med allt från 10 000 till över 100 000 användare under några veckor.</span><span class="sxs-lookup"><span data-stu-id="7495a-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="7495a-105">Använd portalstartschemaläggren för att starta portalen för att se till att användarna får en smidigare visningsupplevelse när de använder den nya SharePoint portalen.</span><span class="sxs-lookup"><span data-stu-id="7495a-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="7495a-106">Med portalstartschemaläggeren får du hjälp med att fasa in lanseringen genom att samla användare i vågor och hantera URL-omdirigeringar för den nya portalen.</span><span class="sxs-lookup"><span data-stu-id="7495a-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="7495a-107">Under lanseringen av varje omgång kan du samla in feedback från användare, övervaka portalens prestanda och pausa lanseringen för att lösa problem innan du fortsätter med nästa omgång.</span><span class="sxs-lookup"><span data-stu-id="7495a-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="7495a-108">Läs mer om hur du [planerar en portalstart i SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out).</span><span class="sxs-lookup"><span data-stu-id="7495a-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out).</span></span>

<span data-ttu-id="7495a-109">**Det finns två typer av omdirigeringar:**</span><span class="sxs-lookup"><span data-stu-id="7495a-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="7495a-110">**Dubbelriktad**: starta en ny modern SharePoint att ersätta en befintlig klassisk SharePoint eller modern portal</span><span class="sxs-lookup"><span data-stu-id="7495a-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="7495a-111">**Omdirigera till en tillfällig sida**: starta en ny modern SharePoint portal utan befintlig SharePoint portal</span><span class="sxs-lookup"><span data-stu-id="7495a-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="7495a-112">Webbplatsbehörigheter måste ställas in separat från vågor som en del av lanseringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="7495a-113">Om du till exempel släpper en organisationsomfattande portal kan du ange behörigheter till "Alla utom externa användare" och sedan dela upp användarna i vågor med hjälp av säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="7495a-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="7495a-114">Att lägga till en säkerhetsgrupp i en omgång ger inte säkerhetsgruppen åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7495a-115">Den här funktionen kommer att vara åtkomlig från **panelen Inställningar** på startsidan för SharePoint-kommunikationswebbplatser för kunder med riktad version från och med maj 2021 och blir tillgänglig för alla kunder senast i juli 2021</span><span class="sxs-lookup"><span data-stu-id="7495a-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="7495a-116">PowerShell-versionen av det här verktyget är tillgänglig i dag</span><span class="sxs-lookup"><span data-stu-id="7495a-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="7495a-117">Den här funktionen kan endast användas på moderna SharePoint kommunikationswebbplatser</span><span class="sxs-lookup"><span data-stu-id="7495a-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="7495a-118">Du måste ha behörigheten webbplatsägare för webbplatsen för att anpassa och schemalägga lanseringen av en portal</span><span class="sxs-lookup"><span data-stu-id="7495a-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="7495a-119">Lanseringar måste schemaläggas minst sju dagar i förväg och varje omgång kan pågå i en till sju dagar</span><span class="sxs-lookup"><span data-stu-id="7495a-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="7495a-120">Antalet vågor som krävs bestäms automatiskt av det förväntade antalet användare</span><span class="sxs-lookup"><span data-stu-id="7495a-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="7495a-121">Innan du schemalägger en portalstart [måste SharePoint för](https://aka.ms/perftool) att kontrollera att startsidan på webbplatsen är felfri</span><span class="sxs-lookup"><span data-stu-id="7495a-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="7495a-122">I slutet av lanseringen kommer alla användare med behörighet till webbplatsen att kunna komma åt den nya webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7495a-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="7495a-123">Om din organisation använder [Viva Connections](/SharePoint/viva-connections)kan användarna se organisationens ikon i appfältet i Microsoft Teams, men när ikonen väljs kan användarna inte komma åt portalen förrän deras omgång har startats</span><span class="sxs-lookup"><span data-stu-id="7495a-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="7495a-124">Den här funktionen är inte tillgänglig för Office 365 Germany, Office 365 som drivs av 21Vianet (Kina) eller i Microsoft 365 för myndigheter i USA</span><span class="sxs-lookup"><span data-stu-id="7495a-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="7495a-125">Förstå skillnaderna mellan alternativen för portalstartschemaläggare:</span><span class="sxs-lookup"><span data-stu-id="7495a-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="7495a-126">Tidigare kunde portalstarter bara schemaläggas via SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7495a-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="7495a-127">Nu har du två alternativ som hjälper dig att schemalägga och hantera portalens lansering.</span><span class="sxs-lookup"><span data-stu-id="7495a-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="7495a-128">Lär dig mer om de viktigaste skillnaderna mellan båda verktygen:</span><span class="sxs-lookup"><span data-stu-id="7495a-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="7495a-129">**SharePoint PowerShell-version:**</span><span class="sxs-lookup"><span data-stu-id="7495a-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="7495a-130">Administratörsautentiseringsuppgifter krävs [för att använda SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="7495a-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="7495a-131">Minimikravet för en våg</span><span class="sxs-lookup"><span data-stu-id="7495a-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="7495a-132">Schemalägg lanseringen baserat på UTC-tidszon (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="7495a-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="7495a-133">**I produktversion:**</span><span class="sxs-lookup"><span data-stu-id="7495a-133">**In-product version:**</span></span>

- <span data-ttu-id="7495a-134">Autentiseringsuppgifter för webbplatsägare krävs</span><span class="sxs-lookup"><span data-stu-id="7495a-134">Site owner credentials are required</span></span>
- <span data-ttu-id="7495a-135">Minimikravet för två vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="7495a-136">Schemalägga lanseringen baserat på portalens lokala tidszon enligt de nationella inställningarna</span><span class="sxs-lookup"><span data-stu-id="7495a-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="7495a-137">Komma igång med portalstartschemaläggeren</span><span class="sxs-lookup"><span data-stu-id="7495a-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="7495a-138">Innan du använder schemaläggaren [](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) för portalen ska du lägga till  alla användare som behöver åtkomst till den här webbplatsen via Webbplatsbehörigheter som webbplatsägare, Webbplatsmedlem eller Besökare.</span><span class="sxs-lookup"><span data-stu-id="7495a-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="7495a-139">Börja sedan schemalägga portalens lansering genom att öppna portalstartschemaläggningen på ett av två sätt:</span><span class="sxs-lookup"><span data-stu-id="7495a-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="7495a-140">**Alternativ 1:** De första gånger som du redigerar och publicerar om ändringar på startsidan – eller upp till startsidan version 3.0 – uppmanas du att använda schemaläggningsverktyget för portalstart.</span><span class="sxs-lookup"><span data-stu-id="7495a-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="7495a-141">Välj **Schemalägg lansering** för att gå framåt med schemaläggning.</span><span class="sxs-lookup"><span data-stu-id="7495a-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="7495a-142">Eller välj **Publicera om** för att publicera om sidredigeringarna utan att schemalägga lanseringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![Bild av uppmaningen att använda portalstartschemaläggeren när du publicerar om startsidan](../media/portal-launch-republish-2.png)

   <span data-ttu-id="7495a-144">**Alternativ 2:** Du kan när som helst gå till startsidan för SharePoint-kommunikationswebbplatsen, välja **Inställningar** och sedan Schemalägga lanseringen av webbplatsen för att schemalägga portalens lansering. </span><span class="sxs-lookup"><span data-stu-id="7495a-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![Bild av Inställningar med Schemalägg en webbplatslansering markerat](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="7495a-146">Bekräfta sedan portalens hälsoresultat och gör förbättringar i portalen om det **behövs** med hjälp av siddiagnostik för [SharePoint](https://aka.ms/perftool) tills portalen får ett hälsoresultat.</span><span class="sxs-lookup"><span data-stu-id="7495a-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="7495a-147">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7495a-147">Then, select **Next**.</span></span>

   ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="7495a-149">Du kan inte redigera webbplatsens namn och beskrivning från portalstartschemaläggaren och i stället  ändra den genom att **välja Inställningar** och sedan Webbplatsinformation på startsidan.</span><span class="sxs-lookup"><span data-stu-id="7495a-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="7495a-150">Välj **antalet förväntade användare** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="7495a-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="7495a-151">I den här bilden visas det antal användare som troligen behöver åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="7495a-152">Uppstartsschemat för portalen bestämmer automatiskt det bästa antalet vågor beroende på vilka användare som förväntas göra så här:</span><span class="sxs-lookup"><span data-stu-id="7495a-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="7495a-153">Mindre än 10 000 användare: två vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="7495a-154">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="7495a-155">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="7495a-156">Fler än 100 000 användare: Fem vågor och kontakta microsoft via stegen som anges i Starta portalen med över 100 000 användare.</span><span class="sxs-lookup"><span data-stu-id="7495a-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="7495a-157">Fastställ sedan vilken **typ av omdirigering som** behövs:</span><span class="sxs-lookup"><span data-stu-id="7495a-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="7495a-158">Alternativ 1: Skicka användare till en **befintlig SharePoint -sida (dubbelriktad)** – Använd det här alternativet när du startar en ny modern SharePoint-portal för att ersätta en SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="7495a-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="7495a-159">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="7495a-160">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="7495a-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7495a-161">När du använder dubbelriktat alternativ måste den person som schemalägger lanseringen också ha webbplatsägaresbehörighet till den andra SharePoint portalen.</span><span class="sxs-lookup"><span data-stu-id="7495a-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="7495a-162">**Alternativ 2:** Skicka användare till en automatiskt genererad tillfällig sida (tillfällig sidomdirigering) – Använd en tillfällig sidomdirigering när det inte finns någon SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="7495a-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="7495a-163">Användare dirigeras till en ny modern SharePoint-portal och om en användare befinner sig i en omgång som inte har startats omdirigeras de till en tillfällig sida.</span><span class="sxs-lookup"><span data-stu-id="7495a-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="7495a-164">**Alternativ 3: Skicka användare** till en extern sida – Ge en extern URL till en tillfällig landningssida tills användaromgången lanseras.</span><span class="sxs-lookup"><span data-stu-id="7495a-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="7495a-165">Dela upp åhörarna i vågor.</span><span class="sxs-lookup"><span data-stu-id="7495a-165">Break up your audience into waves.</span></span> <span data-ttu-id="7495a-166">Addera upp till 20 säkerhetsgrupper per omgång.</span><span class="sxs-lookup"><span data-stu-id="7495a-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="7495a-167">Omgångsinformation kan redigeras till lanseringen av varje omgång.</span><span class="sxs-lookup"><span data-stu-id="7495a-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="7495a-168">Varje omgång kan pågå minst en dag (24 timmar) och som mest sju dagar.</span><span class="sxs-lookup"><span data-stu-id="7495a-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="7495a-169">Det gör SharePoint och den tekniska miljön en möjlighet att anpassa sig till och skala till det stora antalet webbplatsanvändare.</span><span class="sxs-lookup"><span data-stu-id="7495a-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="7495a-170">När du schemalägger en start via användargränssnittet baseras tidszonen på webbplatsens nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="7495a-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="7495a-171">Startschemat för portalen används automatiskt i minst två omgångar.</span><span class="sxs-lookup"><span data-stu-id="7495a-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="7495a-172">Men PowerShell-versionen av det här verktyget ger möjlighet till 1 omgång.</span><span class="sxs-lookup"><span data-stu-id="7495a-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="7495a-173">Microsoft 365-grupper stöds inte av den här versionen av portalstartschemaläggaren.</span><span class="sxs-lookup"><span data-stu-id="7495a-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="7495a-174">Bestäm vilka som behöver visa webbplatsen direkt och ange sin information i fältet **Användare undantas från vågor.**</span><span class="sxs-lookup"><span data-stu-id="7495a-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="7495a-175">Dessa användare utesluts från vågor och omdirigeras inte före, under eller efter lanseringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7495a-176">Upp till 50 distinkta användare eller säkerhetsgrupper max kan användas under hela lanseringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-176">Up to 50 distinct users or security groups max can be used for the entire launch.</span></span> <span data-ttu-id="7495a-177">Varje start är oberoende av varandra, så om du schemalägger en lansering på en annan portal kan du använda upp till 50 användare/säkerhetsgrupper för den lanseringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-177">Each launch is independent of each other, so if you schedule a launch on another portal, then you could use up to 50 users/security groups for that launch.</span></span> <span data-ttu-id="7495a-178">Dessutom kan du använda upp till 20 distinkta användare eller säkerhetsgrupper per omgång.</span><span class="sxs-lookup"><span data-stu-id="7495a-178">Additionally, you can use up to 20 distinct users or security groups per wave.</span></span> 

><span data-ttu-id="7495a-179">Schemaläggaren för portalstart har stöd för säkerhetsgrupper och e-postaktiverade säkerhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="7495a-179">The portal launch scheduler supports security groups and mail enabled security groups.</span></span> 


8. <span data-ttu-id="7495a-180">Bekräfta portalstartinformationen och välj **Schemalägg**.</span><span class="sxs-lookup"><span data-stu-id="7495a-180">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="7495a-181">När lanseringen har schemalagts måste ändringar på startsidan för SharePoint-portalen få ett felfritt diagnostikresultat innan portalstarten återupptas.</span><span class="sxs-lookup"><span data-stu-id="7495a-181">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="7495a-182">Starta en portal med fler än 100 000 användare</span><span class="sxs-lookup"><span data-stu-id="7495a-182">Launch a portal with over 100k users</span></span>

<span data-ttu-id="7495a-183">Om du planerar att starta en portal med över 100 000 användare kan du skicka en supportbegäran enligt anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="7495a-183">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="7495a-184">Se till att inkludera all information som efterfrågas.</span><span class="sxs-lookup"><span data-stu-id="7495a-184">Make sure to include all the requested information.</span></span>

<span data-ttu-id="7495a-185">**Gör så här:**</span><span class="sxs-lookup"><span data-stu-id="7495a-185">**Follow these steps:**</span></span>

1. <span data-ttu-id="7495a-186">Gå till <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="7495a-186">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="7495a-187">Se till att du använder den nya förhandsversionen av administrationscentret</span><span class="sxs-lookup"><span data-stu-id="7495a-187">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="7495a-188">I det vänstra navigeringsfönstret väljer du **Support** och sedan **Ny tjänstbegäran**</span><span class="sxs-lookup"><span data-stu-id="7495a-188">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="7495a-189">Detta aktiverar fönstret **Behöver du hjälp?** till höger på skärmen.</span><span class="sxs-lookup"><span data-stu-id="7495a-189">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="7495a-190">Ange **"Starta e-SharePoint** med 100 000 användare" för Kort beskrivning av problemet</span><span class="sxs-lookup"><span data-stu-id="7495a-190">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="7495a-191">Välj sedan **Kontakta support**</span><span class="sxs-lookup"><span data-stu-id="7495a-191">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="7495a-192">Under **Beskrivning** anger du "Starta SharePoint portal med 100 000 användare"</span><span class="sxs-lookup"><span data-stu-id="7495a-192">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="7495a-193">Fyll i resten av informationen och välj **sedan Kontakta mig**</span><span class="sxs-lookup"><span data-stu-id="7495a-193">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="7495a-194">När biljetten har skapats bör du ange följande information för supportagenten:</span><span class="sxs-lookup"><span data-stu-id="7495a-194">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="7495a-195">URL:er för portalen</span><span class="sxs-lookup"><span data-stu-id="7495a-195">Portal URL's</span></span>
   - <span data-ttu-id="7495a-196">Antal användare som förväntat</span><span class="sxs-lookup"><span data-stu-id="7495a-196">Number of users expected</span></span>
   - <span data-ttu-id="7495a-197">Beräknat startschema</span><span class="sxs-lookup"><span data-stu-id="7495a-197">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="7495a-198">Göra ändringar i en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="7495a-198">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="7495a-199">Information om lanseringen kan redigeras för varje omgång fram till datumet för vågens lansering.</span><span class="sxs-lookup"><span data-stu-id="7495a-199">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="7495a-200">Om du vill redigera informationen om portalstart går **du Inställningar** väljer **Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="7495a-200">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="7495a-201">Välj sedan **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="7495a-201">Then, select **Edit**.</span></span>
3. <span data-ttu-id="7495a-202">När du är klar med redigeringarna väljer du **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="7495a-202">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="7495a-203">Ta bort en schemalagd portalstart</span><span class="sxs-lookup"><span data-stu-id="7495a-203">Delete a scheduled portal launch</span></span>

<span data-ttu-id="7495a-204">Startar schemalagda med hjälp av schemaläggningsverktyget för portalstart kan avbrytas eller tas bort när som helst även om vissa vågor redan har startats.</span><span class="sxs-lookup"><span data-stu-id="7495a-204">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="7495a-205">Om du vill avbryta portalens lansering går du till **Inställningar** **Schemalägg webbplatsstart.**</span><span class="sxs-lookup"><span data-stu-id="7495a-205">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="7495a-206">Välj sedan Ta **bort** och när du ser meddelandet nedan väljer du Ta **bort** igen.</span><span class="sxs-lookup"><span data-stu-id="7495a-206">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![Bild av schemaläggningsverktyget för portalstart](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="7495a-208">Använda PowerShell-portalens startschemaläggare</span><span class="sxs-lookup"><span data-stu-id="7495a-208">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="7495a-209">Startschemaverktyget SharePoint Portal var ursprungligen endast tillgängligt via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) och kommer att fortsätta stödjas via PowerShell för kunder som föredrar den här metoden.</span><span class="sxs-lookup"><span data-stu-id="7495a-209">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="7495a-210">Samma anteckningar i början av den här artikeln gäller båda versionerna av portalstartschemaläggeren.</span><span class="sxs-lookup"><span data-stu-id="7495a-210">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="7495a-211">Du behöver administratörsbehörighet för att använda SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7495a-211">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="7495a-212">Information om portalstart för lanseringar som skapas i PowerShell visas och kan hanteras i det nya startschemaverktyget för portal i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7495a-212">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="7495a-213">Appkonfiguration och anslutning till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7495a-213">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="7495a-214">[Ladda ned de senaste SharePoint Online Management Shell.](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="7495a-214">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="7495a-215">Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägga till eller ta bort program och avinstallerar "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="7495a-215">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="7495a-216">På sidan Download Center väljer du språk och klickar sedan på knappen Ladda ned.</span><span class="sxs-lookup"><span data-stu-id="7495a-216">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="7495a-217">Du uppmanas att välja mellan att ladda ned en x64- och x86-.msi fil.</span><span class="sxs-lookup"><span data-stu-id="7495a-217">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="7495a-218">Ladda ned x64-filen om du kör 64-bitarsversionen av Windows eller x86-filen om du kör 32-bitarsversionen.</span><span class="sxs-lookup"><span data-stu-id="7495a-218">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="7495a-219">Om du inte vet vilken version av [operativsystemet Windows använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="7495a-219">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="7495a-220">När filen har laddats ned kör du den och följer anvisningarna i Installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="7495a-220">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="7495a-221">Anslut att SharePoint som [global administratör eller SharePoint administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7495a-221">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="7495a-222">Mer information finns i Komma [igång med SharePoint Online Management Shell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="7495a-222">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="7495a-223">Visa eventuella befintliga startinställningar för portalen</span><span class="sxs-lookup"><span data-stu-id="7495a-223">View any existing portal launch setups</span></span>

<span data-ttu-id="7495a-224">Så här ser du om det finns befintliga konfigurationer för portalstart:</span><span class="sxs-lookup"><span data-stu-id="7495a-224">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="7495a-225">Schemalägga en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7495a-225">Schedule a portal launch on the site</span></span>

<span data-ttu-id="7495a-226">Antalet vågor som krävs beror på den förväntade startstorleken.</span><span class="sxs-lookup"><span data-stu-id="7495a-226">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="7495a-227">Färre än 10 000 användare: en omgång</span><span class="sxs-lookup"><span data-stu-id="7495a-227">Less than 10k users: One wave</span></span>
- <span data-ttu-id="7495a-228">10k-till-30k-användare: Tre vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-228">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="7495a-229">30k+ till 100 000 användare: Fem vågor</span><span class="sxs-lookup"><span data-stu-id="7495a-229">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="7495a-230">Fler än 100 000 användare: Fem vågor och kontakta ditt Microsoft-kontoteam</span><span class="sxs-lookup"><span data-stu-id="7495a-230">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="7495a-231">Steg för dubbelriktad omdirigering</span><span class="sxs-lookup"><span data-stu-id="7495a-231">Steps for bidirectional redirection</span></span>

<span data-ttu-id="7495a-232">Dubbelriktad omdirigering innebär att en ny modern onlineportal SharePoint lanseras och ersätter en befintlig SharePoint klassisk eller modern portal.</span><span class="sxs-lookup"><span data-stu-id="7495a-232">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="7495a-233">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-233">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="7495a-234">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="7495a-234">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="7495a-235">Vi stöder endast omdirigering mellan standardhemsidan på den gamla webbplatsen och standardhemsidan på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-235">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="7495a-236">Om du har administratörer eller ägare som behöver åtkomst till de gamla och nya webbplatserna utan att omdirigeras, se till att de listas med `WaveOverrideUsers` parametern.</span><span class="sxs-lookup"><span data-stu-id="7495a-236">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="7495a-237">Så här migrerar du användare från SharePoint webbplats till en SharePoint webbplats på ett stegat sätt:</span><span class="sxs-lookup"><span data-stu-id="7495a-237">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="7495a-238">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="7495a-238">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="7495a-239">Exempel:</span><span class="sxs-lookup"><span data-stu-id="7495a-239">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="7495a-240">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-240">Complete validation.</span></span> <span data-ttu-id="7495a-241">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7495a-241">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="7495a-242">Steg för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="7495a-242">Steps for redirection to temporary page</span></span>

<span data-ttu-id="7495a-243">Tillfällig sidomdirigering bör användas när det inte SharePoint en befintlig portal.</span><span class="sxs-lookup"><span data-stu-id="7495a-243">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="7495a-244">Användare dirigeras till en ny modern SharePoint Online-portal på ett enhetligt sätt.</span><span class="sxs-lookup"><span data-stu-id="7495a-244">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="7495a-245">Om en användare går i en omgång som inte har startats omdirigeras de till en tillfällig sida (alla URL-adresser).</span><span class="sxs-lookup"><span data-stu-id="7495a-245">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="7495a-246">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="7495a-246">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="7495a-247">Exempel:</span><span class="sxs-lookup"><span data-stu-id="7495a-247">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="7495a-248">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="7495a-248">Complete validation.</span></span> <span data-ttu-id="7495a-249">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7495a-249">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="7495a-250">Pausa eller starta om en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7495a-250">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="7495a-251">Kör följande kommando för att pausa en pågående portalstart och tillfälligt förhindra att kommande omgångsförlopp uppstår:</span><span class="sxs-lookup"><span data-stu-id="7495a-251">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="7495a-252">Verifiera att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7495a-252">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="7495a-253">Om du vill starta om en portalstart som har pausats kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="7495a-253">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="7495a-254">Kontrollera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="7495a-254">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="7495a-255">Ta bort en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7495a-255">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="7495a-256">Kör följande kommando för att ta bort en portalstart som är schemalagd eller pågår för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="7495a-256">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="7495a-257">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="7495a-257">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="7495a-258">Mer information</span><span class="sxs-lookup"><span data-stu-id="7495a-258">Learn more</span></span>

[<span data-ttu-id="7495a-259">Planera lanseringsplanen för portalen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7495a-259">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="7495a-260">Planera din kommunikationswebbplats</span><span class="sxs-lookup"><span data-stu-id="7495a-260">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
