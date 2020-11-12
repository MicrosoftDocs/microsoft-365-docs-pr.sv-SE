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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999597"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="5b498-103">Starta portalen med hjälp av portalen starta Schemaläggaren</span><span class="sxs-lookup"><span data-stu-id="5b498-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="5b498-104">Du kan starta portalen med hjälp av portalen med att starta Schemaläggaren genom att först validera klient organisationens möjlighet att konfigurera en vågor för en ny portal.</span><span class="sxs-lookup"><span data-stu-id="5b498-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="5b498-105">Därefter kan administratören verifiera en omdirigering av förfrågningar, baserat på förekomsten av en användare i aktiva vågor.</span><span class="sxs-lookup"><span data-stu-id="5b498-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="5b498-106">Om du vill ha mer information om hur du startar en lyckad Portal följer du de grundläggande principerna, metoderna och rekommendationerna i [skapa, starta och underhålla en felfri Portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="5b498-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="5b498-107">Installations program</span><span class="sxs-lookup"><span data-stu-id="5b498-107">App setup</span></span>
1. <span data-ttu-id="5b498-108">Avinstallera om det finns en befintlig `Microsoft.Online.SharePoint.PowerShell` från datorn via kontroll panelen.</span><span class="sxs-lookup"><span data-stu-id="5b498-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="5b498-109">På PowerShell-pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="5b498-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="5b498-110">Ansluta till SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5b498-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="5b498-111">Öppna [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) i Windows.</span><span class="sxs-lookup"><span data-stu-id="5b498-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="5b498-112">Anslut till din klient organisation som administratör.</span><span class="sxs-lookup"><span data-stu-id="5b498-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="5b498-113">Ange lösen ordet när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="5b498-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="5b498-114">Kommando för att hämta en befintlig installation</span><span class="sxs-lookup"><span data-stu-id="5b498-114">Command to get an existing setup</span></span>

<span data-ttu-id="5b498-115">Så här visar du befintliga Portal start konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="5b498-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="5b498-116">Skicka `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="5b498-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="5b498-117">Skicka ytterligare en parameter `-DisplayFormat Raw` om du vill se Wave-samlingen formaterad som ett RAW-indataformat.</span><span class="sxs-lookup"><span data-stu-id="5b498-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="5b498-118">Kommandon för omdirigering till dubbelriktad</span><span class="sxs-lookup"><span data-stu-id="5b498-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="5b498-119">Så här migrerar du gamla webbplats användare till den nya webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="5b498-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="5b498-120">Skapa Portal lansera vågor.</span><span class="sxs-lookup"><span data-stu-id="5b498-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="5b498-121">Det här gäller endast i test fasen tidigt.</span><span class="sxs-lookup"><span data-stu-id="5b498-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="5b498-122">Om du vill testa effekten av ändringen omedelbart kontrollerar du att den första vågen `LaunchDateUtc` är inställd på dagens datum.</span><span class="sxs-lookup"><span data-stu-id="5b498-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="5b498-123">Om du inte anger den här flaggan får du ett fel meddelande.</span><span class="sxs-lookup"><span data-stu-id="5b498-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="5b498-124">Det här felet beror på att startas i en produktion på minst 7 dagar i förväg.</span><span class="sxs-lookup"><span data-stu-id="5b498-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="5b498-125">Slutför verifiering.</span><span class="sxs-lookup"><span data-stu-id="5b498-125">Complete validation.</span></span>
  - <span data-ttu-id="5b498-126">Det kan ta upp till fem minuter innan omdirigeringen slutför sin konfiguration via tjänsten, så vänta tills du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="5b498-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="5b498-127">Om du loggar in med användaren angiven som `WaveOverrideUsers` visas inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="5b498-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="5b498-128">Du bör hålla dig uppdaterad på den plats där du navigerade.</span><span class="sxs-lookup"><span data-stu-id="5b498-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="5b498-129">Logga in med en användare som är en del av *VISNINGS SG1*.</span><span class="sxs-lookup"><span data-stu-id="5b498-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="5b498-130">Gå till den gamla webbplatsen och omdirigera till den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="5b498-131">Navigera till den nya webbplatsen och du bör vara på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="5b498-132">Logga med användare i *visnings program SG2* och navigera till den gamla webbplatsen och håll kontakten med den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="5b498-133">Gå till den nya webbplatsen och omdirigera till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="5b498-134">Pausa Portal lansering.</span><span class="sxs-lookup"><span data-stu-id="5b498-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="5b498-135">Om du behöver pausa start vågor kan du pausa dem för "x" antal dagar.</span><span class="sxs-lookup"><span data-stu-id="5b498-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="5b498-136">`Status`Om du ställer in flaggan på paus förhindras alla kommande våg förlopp.</span><span class="sxs-lookup"><span data-stu-id="5b498-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="5b498-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="5b498-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="5b498-138">Detta bekräftar att alla användare omdirigeras till den gamla webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="5b498-139">Starta om portalen.</span><span class="sxs-lookup"><span data-stu-id="5b498-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="5b498-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="5b498-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="5b498-141">Kontrol lera att omdirigeringen nu har återställts.</span><span class="sxs-lookup"><span data-stu-id="5b498-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="5b498-142">Ta bort en portal start-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b498-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="5b498-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="5b498-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="5b498-144">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="5b498-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="5b498-145">Kommandon för omdirigering till tillfällig sida</span><span class="sxs-lookup"><span data-stu-id="5b498-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="5b498-146">Följ de här anvisningarna om du inte har någon föregående webbplats och vill utesluta användare som inte är i vågor från att landa på den nya Portal sidan.</span><span class="sxs-lookup"><span data-stu-id="5b498-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="5b498-147">Skapa en tillfällig sida på någon av webbplatserna:</span><span class="sxs-lookup"><span data-stu-id="5b498-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="5b498-148">Skapa en portal-starta Wave.</span><span class="sxs-lookup"><span data-stu-id="5b498-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="5b498-149">Slutför verifiering.</span><span class="sxs-lookup"><span data-stu-id="5b498-149">Complete validation.</span></span>

  - <span data-ttu-id="5b498-150">Vänta fem minuter innan du fortsätter eftersom det kan ta upp till fem minuter att slutföra åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5b498-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="5b498-151">Logga med den användare som är en del av *VISNINGS SG1* och:</span><span class="sxs-lookup"><span data-stu-id="5b498-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="5b498-152">Gå till den nya webbplatsen, så ska du vara på den nya webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="5b498-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="5b498-153">Gå till den tillfälliga sidan och se till att du är på Temp-sidan.</span><span class="sxs-lookup"><span data-stu-id="5b498-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="5b498-154">Logga med den användare som är en del av *VISNINGS SG2* och:</span><span class="sxs-lookup"><span data-stu-id="5b498-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="5b498-155">Gå till den nya webbplatsen och omdirigera till den tillfälliga sidan.</span><span class="sxs-lookup"><span data-stu-id="5b498-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="5b498-156">Gå till den tillfälliga sidan och se till att du är på Temp-sidan.</span><span class="sxs-lookup"><span data-stu-id="5b498-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="5b498-157">Ta bort en portal start-konfiguration.</span><span class="sxs-lookup"><span data-stu-id="5b498-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="5b498-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="5b498-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="5b498-159">Verifiera att ingen omdirigering sker för alla användare.</span><span class="sxs-lookup"><span data-stu-id="5b498-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="5b498-160">Mer information</span><span class="sxs-lookup"><span data-stu-id="5b498-160">Learn more</span></span>
[<span data-ttu-id="5b498-161">Planera hur portalen ska lanseras i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5b498-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)