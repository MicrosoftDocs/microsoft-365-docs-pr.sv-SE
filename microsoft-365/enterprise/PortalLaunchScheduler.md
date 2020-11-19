---
title: Starta portalen med hjälp av portalen starta Schemaläggaren
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
description: I den här artikeln beskrivs hur du kan starta portalen med hjälp av portalen starta Schemaläggaren
ms.openlocfilehash: e5e5850fa7e74f3e3b342e9bb28d17f65b491664
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356673"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="3f827-103">Starta portalen med hjälp av portalen starta Schemaläggaren</span><span class="sxs-lookup"><span data-stu-id="3f827-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="3f827-104">En portal är en SharePoint-webbplats på ditt intranät som har ett stort antal webbplats läsare som använder innehåll på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3f827-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="3f827-105">Att starta din portal i vågor är en viktig del av att säkerställa att användarna har en smidig och snabb åtkomst till en ny SharePoint Online-Portal.</span><span class="sxs-lookup"><span data-stu-id="3f827-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="3f827-106">Att starta i vågor är ett viktigt sätt att samla in din portal, enligt vad som beskrivs i [Planera hur portalen ska lanseras](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3f827-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="3f827-107">Med portalen kan du använda Schemaläggaren för att hjälpa dig att följa en nedrullningsbar våg med nedrullnings bara genom att hantera omdirigeringarna för den nya portalen.</span><span class="sxs-lookup"><span data-stu-id="3f827-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="3f827-108">Under varje vågor kan du samla in feedback och övervaka prestanda under varje enskild installation.</span><span class="sxs-lookup"><span data-stu-id="3f827-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="3f827-109">Det här är fördelen med att vi tar en långsam introduktion till portalen, vilket ger dig möjligheten att pausa och lösa problem innan du fortsätter med nästa våg, och slutligen säkerställa en positiv upplevelse för dina användare.</span><span class="sxs-lookup"><span data-stu-id="3f827-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="3f827-110">Det finns två typer av omdirigering:</span><span class="sxs-lookup"><span data-stu-id="3f827-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="3f827-111">dubbelriktad: starta en ny modern SharePoint Online-Portal för att ersätta en befintlig SharePoint-klassiskt eller modern Portal</span><span class="sxs-lookup"><span data-stu-id="3f827-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="3f827-112">omdirigering av tillfälliga sidor: starta en ny modern SharePoint Online-Portal utan befintlig SharePoint-Portal</span><span class="sxs-lookup"><span data-stu-id="3f827-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="3f827-113">Du kan bara använda Schemaläggaren för att starta moderna SharePoint online-portaler (till exempel kommunikations webbplatser).</span><span class="sxs-lookup"><span data-stu-id="3f827-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="3f827-114">Lanseringar måste schemaläggas minst 7 dagar i förväg.</span><span class="sxs-lookup"><span data-stu-id="3f827-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="3f827-115">Antalet vågor som behövs bestäms av det förväntade antalet användare.</span><span class="sxs-lookup"><span data-stu-id="3f827-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="3f827-116">Innan du schemalägger en portal start måste du köra [verktyget kör diagnostik för SharePoint](https://aka.ms/perftool) för att kontrol lera att start sidan på portalen är felfri.</span><span class="sxs-lookup"><span data-stu-id="3f827-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="3f827-117">I slutet av Portal start kommer alla användare som har behörighet till webbplatsen att få åtkomst till den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3f827-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="3f827-118">Om du vill ha mer information om hur du startar en lyckad Portal följer du de grundläggande principerna, metoderna och rekommendationerna i [skapa, lansera och underhålla en felfri Portal](https://docs.microsoft.com/sharepoint/portal-health).</span><span class="sxs-lookup"><span data-stu-id="3f827-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="3f827-119">Den här funktionen är inte tillgänglig för Office 365 Germany, Office 365 drivs av 21Vianet (Kina) eller Microsoft 365 amerikansk myndighets plan.</span><span class="sxs-lookup"><span data-stu-id="3f827-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="3f827-120">Program inställningar och ansluta till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3f827-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="3f827-121">[Ladda ner den senaste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="3f827-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3f827-122">Om du har installerat en tidigare version av SharePoint Online Management Shell går du till Lägg till eller ta bort program och avinstallerar SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f827-122">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="3f827-123">På sidan Download Center väljer du ditt språk och klickar sedan på knappen Ladda ned.</span><span class="sxs-lookup"><span data-stu-id="3f827-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="3f827-124">Du uppmanas att välja mellan att ladda ner en x64-och x86. msi-fil.</span><span class="sxs-lookup"><span data-stu-id="3f827-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="3f827-125">Ladda ner x64-filen om du kör 64-bitars versionen av Windows eller x86-filen om du kör 32-bitars versionen.</span><span class="sxs-lookup"><span data-stu-id="3f827-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="3f827-126">Om du inte vet kan du läsa [vilken version av operativ systemet Windows använder jag?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="3f827-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="3f827-127">När fil hämtningen är klar kör du den och följer anvisningarna i installations guiden.</span><span class="sxs-lookup"><span data-stu-id="3f827-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="3f827-128">Anslut till SharePoint som [Global administratör eller SharePoint-administratör](/sharepoint/sharepoint-admin-role) i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f827-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="3f827-129">Mer information finns i [komma igång med SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3f827-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="3f827-130">Visa befintliga Portal Start Inställningar</span><span class="sxs-lookup"><span data-stu-id="3f827-130">View any existing portal launch setups</span></span>

<span data-ttu-id="3f827-131">Så här ser du om det finns befintliga konfigurationer för Portal start:</span><span class="sxs-lookup"><span data-stu-id="3f827-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="3f827-132">Schemalägga en portal lansering på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="3f827-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="3f827-133">Antalet vågor är beroende av den förväntade start storleken.</span><span class="sxs-lookup"><span data-stu-id="3f827-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="3f827-134">Mindre än 10 000 användare: 1 våg</span><span class="sxs-lookup"><span data-stu-id="3f827-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="3f827-135">10 k till 30k användare: 3 vågor</span><span class="sxs-lookup"><span data-stu-id="3f827-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="3f827-136">30k + till 100K användare: 5 vågor</span><span class="sxs-lookup"><span data-stu-id="3f827-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="3f827-137">Fler än 100K användare: 5 vågor och kontakta ditt Microsoft-gruppteam</span><span class="sxs-lookup"><span data-stu-id="3f827-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="3f827-138">Steg för att utföra dubbelriktad omdirigering</span><span class="sxs-lookup"><span data-stu-id="3f827-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="3f827-139">Med dubbelriktad omdirigering kan du starta en ny modern SharePoint Online-Portal för att ersätta en befintlig SharePoint-klassiskt eller modern Portal.</span><span class="sxs-lookup"><span data-stu-id="3f827-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="3f827-140">Användare i aktiva vågor omdirigeras till den nya webbplatsen oavsett om de navigerar till den gamla eller nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3f827-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="3f827-141">Användare i en icke-lanserad våg som försöker komma åt den nya webbplatsen omdirigeras tillbaka till den gamla platsen tills dess att de har startats.</span><span class="sxs-lookup"><span data-stu-id="3f827-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="3f827-142">Om du har administratörer eller ägare som behöver komma åt de gamla och nya platserna utan att behöva omdirigeras kontrollerar du att de visas med hjälp av `WaveOverrideUsers` parametern.</span><span class="sxs-lookup"><span data-stu-id="3f827-142">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="3f827-143">Vi stöder bara omdirigering mellan standard start sidan på den gamla webbplatsen och standard start sidan på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3f827-143">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="3f827-144">Så här migrerar du användare från en befintlig SharePoint-webbplats till en ny SharePoint-webbplats:</span><span class="sxs-lookup"><span data-stu-id="3f827-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="3f827-145">Kör följande kommando för att ange hur portalen ska lanseras.</span><span class="sxs-lookup"><span data-stu-id="3f827-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="3f827-146">Exempel:</span><span class="sxs-lookup"><span data-stu-id="3f827-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3f827-147">Slutför verifiering.</span><span class="sxs-lookup"><span data-stu-id="3f827-147">Complete validation.</span></span> <span data-ttu-id="3f827-148">Det kan ta 5-10 minuter för omdirigeringen att slutföra sin konfiguration via tjänsten.</span><span class="sxs-lookup"><span data-stu-id="3f827-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="3f827-149">Steg för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="3f827-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="3f827-150">Omdirigering av tillfälliga sidor ska användas när det inte finns någon befintlig SharePoint-Portal.</span><span class="sxs-lookup"><span data-stu-id="3f827-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="3f827-151">Användare dirigeras till en ny modern SharePoint Online-Portal på ett stadium sätt.</span><span class="sxs-lookup"><span data-stu-id="3f827-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="3f827-152">Om en användare har en Wave-åtgärd som inte har startats kommer de att omdirigeras till en tillfällig sida (valfri URL).</span><span class="sxs-lookup"><span data-stu-id="3f827-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="3f827-153">Kör följande kommando för att ange hur portalen ska lanseras.</span><span class="sxs-lookup"><span data-stu-id="3f827-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="3f827-154">Exempel:</span><span class="sxs-lookup"><span data-stu-id="3f827-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3f827-155">Slutför verifiering.</span><span class="sxs-lookup"><span data-stu-id="3f827-155">Complete validation.</span></span> <span data-ttu-id="3f827-156">Det kan ta 5-10 minuter för omdirigeringen att slutföra sin konfiguration via tjänsten.</span><span class="sxs-lookup"><span data-stu-id="3f827-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="3f827-157">Pausa eller starta om en portal lansering på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="3f827-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="3f827-158">Om du vill pausa en pågående Portal start och tillfälligt förhindra att kommande våg förlopp inträffar kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="3f827-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="3f827-159">Verifiera att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="3f827-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="3f827-160">Om du vill starta om en portal lansering som har pausats kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="3f827-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="3f827-161">Kontrol lera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="3f827-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="3f827-162">Ta bort en portal lansering på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="3f827-162">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="3f827-163">Skapa en portal-starta Wave.</span><span class="sxs-lookup"><span data-stu-id="3f827-163">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="3f827-164">Kör följande kommando för att ta bort en portal som är schemalagd eller pågående för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="3f827-164">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="3f827-165">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="3f827-165">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="3f827-166">Mer information</span><span class="sxs-lookup"><span data-stu-id="3f827-166">Learn more</span></span>
[<span data-ttu-id="3f827-167">Planera hur portalen ska lanseras i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3f827-167">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
