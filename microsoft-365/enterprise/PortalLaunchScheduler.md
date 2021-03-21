---
title: Starta portalen med hjälp av Portal Launch Scheduler
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
description: I den här artikeln beskrivs hur du kan starta portalen med hjälp av Portal Launch Scheduler
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926148"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="d6e54-103">Starta portalen med hjälp av Portal Launch Scheduler</span><span class="sxs-lookup"><span data-stu-id="d6e54-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="d6e54-104">En portal är en SharePoint-webbplats i ditt intranät som har många användare som använder innehåll på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="d6e54-105">Att lansera portalen i vågor är en viktig del av att se till att användarna får en smidig och fungerande upplevelse av att komma åt en ny SharePoint Online-portal.</span><span class="sxs-lookup"><span data-stu-id="d6e54-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="d6e54-106">Att starta i vågor är ett viktigt sätt att distribuera portalen, enligt beskrivningen i Planera lanseringen av portalen [i SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d6e54-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="d6e54-107">Portal Launch Scheduler har utformats för att hjälpa dig att följa en fas-/fas-utrullningsmetod genom att hantera omdirigeringarna för den nya portalen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="d6e54-108">Under varje vågor kan du samla in feedback från användare och övervaka prestanda under varje distributionsvåg.</span><span class="sxs-lookup"><span data-stu-id="d6e54-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="d6e54-109">Detta har fördelen med att långsamt introducera portalen, vilket ger dig möjlighet att pausa och lösa problem innan du fortsätter med nästa omgång, och i slutänden säkerställa en positiv upplevelse för dina användare.</span><span class="sxs-lookup"><span data-stu-id="d6e54-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="d6e54-110">Det finns två typer av omdirigering:</span><span class="sxs-lookup"><span data-stu-id="d6e54-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="d6e54-111">dubbelriktad: starta en ny modern SharePoint Online-portal för att ersätta en befintlig klassisk eller modern SharePoint-portal</span><span class="sxs-lookup"><span data-stu-id="d6e54-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="d6e54-112">Tillfällig sidomdirigering: starta en ny modern SharePoint Online-portal utan en befintlig SharePoint-portal</span><span class="sxs-lookup"><span data-stu-id="d6e54-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="d6e54-113">Schemaläggaren för portalstart är endast tillgänglig för att starta moderna SharePoint Online-portaler (dvs. kommunikationswebbplatser).</span><span class="sxs-lookup"><span data-stu-id="d6e54-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="d6e54-114">Lanseringar måste schemaläggas minst 7 dagar i förväg.</span><span class="sxs-lookup"><span data-stu-id="d6e54-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="d6e54-115">Antalet vågor som krävs bestäms av det förväntade antalet användare.</span><span class="sxs-lookup"><span data-stu-id="d6e54-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="d6e54-116">Innan du schemalägger en portalstart måste verktyget Siddiagnostik för [SharePoint](./page-diagnostics-for-spo.md) köras för att kontrollera att startsidan på portalen är felfri.</span><span class="sxs-lookup"><span data-stu-id="d6e54-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="d6e54-117">I slutet av portalens start kan alla användare med behörighet till webbplatsen få åtkomst till den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="d6e54-118">Om du vill ha mer information om hur du startar en lyckad portal följer du de grundläggande principerna, metoderna och rekommendationerna i Skapa, starta och [underhålla en felfri portal.](/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="d6e54-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="d6e54-119">Den här funktionen är inte tillgänglig för Office 365 Germany-, Office 365-abonnemang som drivs av 21Vianet (Kina) eller Microsoft 365 för amerikanska myndigheter.</span><span class="sxs-lookup"><span data-stu-id="d6e54-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="d6e54-120">Appkonfiguration och anslutning till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d6e54-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="d6e54-121">[Ladda ned den senaste versionen av SharePoint Online Management Shell.](https://go.microsoft.com/fwlink/p/?LinkId=255251)</span><span class="sxs-lookup"><span data-stu-id="d6e54-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d6e54-122">Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägga till eller ta bort program och avinstallerar "SharePoint Online Management Shell".</span><span class="sxs-lookup"><span data-stu-id="d6e54-122">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="d6e54-123">På sidan Download Center väljer du språk och klickar sedan på knappen Ladda ned.</span><span class="sxs-lookup"><span data-stu-id="d6e54-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="d6e54-124">Du uppmanas att välja mellan att ladda ned en x64- och x86-MSI-fil.</span><span class="sxs-lookup"><span data-stu-id="d6e54-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="d6e54-125">Ladda ned x64-filen om du kör 64-bitarsversionen av Windows eller x86-filen om du kör 32-bitarsversionen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="d6e54-126">Om du inte vet, se Vilken [version av Windows-operativsystemet använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="d6e54-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="d6e54-127">När filen har laddats ned kör du den och följer anvisningarna i Installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="d6e54-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="d6e54-128">Anslut till SharePoint som [global administratör eller SharePoint-administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6e54-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="d6e54-129">Mer information finns i Komma [igång med SharePoint Online Management Shell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="d6e54-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="d6e54-130">Visa eventuella befintliga startinställningar för portalen</span><span class="sxs-lookup"><span data-stu-id="d6e54-130">View any existing portal launch setups</span></span>

<span data-ttu-id="d6e54-131">Så här ser du om det finns befintliga konfigurationer för portalstart:</span><span class="sxs-lookup"><span data-stu-id="d6e54-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="d6e54-132">Schemalägga en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="d6e54-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="d6e54-133">Antalet vågor som krävs beror på den förväntade startstorleken.</span><span class="sxs-lookup"><span data-stu-id="d6e54-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="d6e54-134">Mindre än 10 000 användare: 1 omgång</span><span class="sxs-lookup"><span data-stu-id="d6e54-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="d6e54-135">10k-till-30k-användare: 3 vågor</span><span class="sxs-lookup"><span data-stu-id="d6e54-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="d6e54-136">30k+ till 100 000 användare: 5 vågor</span><span class="sxs-lookup"><span data-stu-id="d6e54-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="d6e54-137">Fler än 100 000 användare: 5 vågor och kontakta ditt Microsoft-kontoteam</span><span class="sxs-lookup"><span data-stu-id="d6e54-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="d6e54-138">Steg för dubbelriktad omdirigering</span><span class="sxs-lookup"><span data-stu-id="d6e54-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="d6e54-139">Dubbelriktad omdirigering innebär att en ny modern SharePoint Online-portal lanseras så att en befintlig klassisk eller modern SharePoint-portal ersätts.</span><span class="sxs-lookup"><span data-stu-id="d6e54-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="d6e54-140">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="d6e54-141">Användare i en icke-lanserad omgång som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla webbplatsen tills deras omgång startar.</span><span class="sxs-lookup"><span data-stu-id="d6e54-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="d6e54-142">Vi stöder endast omdirigering mellan standardhemsidan på den gamla webbplatsen och standardhemsidan på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="d6e54-143">Om du har administratörer eller ägare som behöver åtkomst till de gamla och nya webbplatserna utan att omdirigeras, se till att de listas med `WaveOverrideUsers` parametern.</span><span class="sxs-lookup"><span data-stu-id="d6e54-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="d6e54-144">Så här migrerar du användare från en befintlig SharePoint-webbplats till en ny SharePoint-webbplats på ett stegat sätt:</span><span class="sxs-lookup"><span data-stu-id="d6e54-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="d6e54-145">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="d6e54-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="d6e54-146">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d6e54-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="d6e54-147">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-147">Complete validation.</span></span> <span data-ttu-id="d6e54-148">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6e54-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="d6e54-149">Steg för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="d6e54-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="d6e54-150">Tillfällig sidomdirigering bör användas när det inte finns någon befintlig SharePoint-portal.</span><span class="sxs-lookup"><span data-stu-id="d6e54-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="d6e54-151">Användare dirigeras till en ny modern SharePoint Online-portal på ett enhetligt sätt.</span><span class="sxs-lookup"><span data-stu-id="d6e54-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="d6e54-152">Om en användare går i en omgång som inte har startats omdirigeras de till en tillfällig sida (alla URL-adresser).</span><span class="sxs-lookup"><span data-stu-id="d6e54-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="d6e54-153">Kör följande kommando för att ange portalstartsvågar.</span><span class="sxs-lookup"><span data-stu-id="d6e54-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="d6e54-154">Exempel:</span><span class="sxs-lookup"><span data-stu-id="d6e54-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="d6e54-155">Bekräfta verifieringen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-155">Complete validation.</span></span> <span data-ttu-id="d6e54-156">Det kan ta 5–10 minuter innan omdirigeringen slutförs i hela tjänsten.</span><span class="sxs-lookup"><span data-stu-id="d6e54-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="d6e54-157">Pausa eller starta om en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="d6e54-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="d6e54-158">Kör följande kommando för att pausa en pågående portalstart och tillfälligt förhindra att kommande omgångsförlopp uppstår:</span><span class="sxs-lookup"><span data-stu-id="d6e54-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="d6e54-159">Verifiera att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d6e54-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="d6e54-160">Om du vill starta om en portalstart som har pausats kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="d6e54-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="d6e54-161">Kontrollera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="d6e54-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="d6e54-162">Ta bort en portalstart på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="d6e54-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="d6e54-163">Kör följande kommando för att ta bort en portalstart som är schemalagd eller pågår för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="d6e54-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="d6e54-164">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d6e54-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d6e54-165">Mer information</span><span class="sxs-lookup"><span data-stu-id="d6e54-165">Learn more</span></span>
[<span data-ttu-id="d6e54-166">Planera lanseringsplanen för portalen i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d6e54-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)