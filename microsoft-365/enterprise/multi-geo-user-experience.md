---
title: Användar upplevelse i en multi-geo-miljö
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Läs mer om användar upplevelsen för SharePoint, OneDrive och Exchange i en multi-geo-miljö för Microsoft 365.
ms.openlocfilehash: c94fc5569a5444ca6361712f57460cf0c977b18e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694479"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="9ba32-103">Användar upplevelse i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="9ba32-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="9ba32-104">Så här ser användarna i en konfiguration med OneDrive multi-geo:</span><span class="sxs-lookup"><span data-stu-id="9ba32-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="9ba32-105">Exchange-postlåda</span><span class="sxs-lookup"><span data-stu-id="9ba32-105">Exchange mailbox</span></span>

<span data-ttu-id="9ba32-106">En användares Exchange-postlåda etableras till deras önskade data plats och flyttas automatiskt om den ändras.</span><span class="sxs-lookup"><span data-stu-id="9ba32-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="9ba32-107">Användare kan använda Outlook och Outlook på webben normalt utan någon ändring i användar miljön i en multi-geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="9ba32-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="9ba32-108">NAV webbplatser</span><span class="sxs-lookup"><span data-stu-id="9ba32-108">Hub sites</span></span>

<span data-ttu-id="9ba32-109">SharePoint Hub-webbplatser förbättrar identifieringen och åtagandet med innehållet för de anställda, samtidigt som du skapar en komplett och konsekvent presentation av projekt, avdelningar eller regioner.</span><span class="sxs-lookup"><span data-stu-id="9ba32-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="9ba32-110">I en multi-geo-miljö kan webbplatser från satellit platser enkelt kopplas till en nav webbplats oavsett dess geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="9ba32-111">Användare kan söka efter och få resultat över navet genom en enda Sök funktion, oavsett webbplatsernas Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="9ba32-112">Start ikon för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9ba32-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="9ba32-113">Start programmet är multi-geo-känsligt och dirigerar varje bricka till en lämplig Geo-plats för arbets belastningen.</span><span class="sxs-lookup"><span data-stu-id="9ba32-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="9ba32-114">SharePoint-och OneDrive-paneler kommer att peka användaren på platsen som motsvarar användarens provisioed Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="9ba32-115">Det innebär att användaren har en OneDrive i den centrala platsen, att deras SharePoint-panel pekar på SP Home på Central platsen, men deras grupp webbplats etableras på den plats som motsvarar deras PDL.</span><span class="sxs-lookup"><span data-stu-id="9ba32-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="9ba32-116">Office-program</span><span class="sxs-lookup"><span data-stu-id="9ba32-116">Office applications</span></span>

<span data-ttu-id="9ba32-117">Office-program som Word, Excel och PowerPoint identifierar automatiskt den korrekta OneDrive för företag-geo-platsen för varje användare när de loggar in.</span><span class="sxs-lookup"><span data-stu-id="9ba32-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="9ba32-118">Användare behöver inte ange den geo-specifika URL-adressen för sina OneDrive-eller SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="9ba32-119">Synkroniseringsklient för OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="9ba32-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="9ba32-120">Synkroniseringsklienten för OneDrive för företag (version 17.3.6943.0625 och senare) identifierar automatiskt rätt OneDrive för företag Geo-plats för användaren.</span><span class="sxs-lookup"><span data-stu-id="9ba32-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="9ba32-121">Stöd för Synch client inkluderar möjligheten att synkronisera grupperade webbplatser oavsett deras Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-121">Synch client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="9ba32-122">Observera att synkroniseringsklienten för Groove inte stöds för multi-geo.</span><span class="sxs-lookup"><span data-stu-id="9ba32-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="9ba32-123">OneDrive för företag-plats</span><span class="sxs-lookup"><span data-stu-id="9ba32-123">OneDrive for Business location</span></span>

<span data-ttu-id="9ba32-124">Användare kommer att få sin OneDrive för företag-etablerad på sin data plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-124">Users will have their OneDrive for Business provisioned in their preferred data location.</span></span> <span data-ttu-id="9ba32-125">Om en användare navigerar till en OneDrive-URL som innehåller en felaktig Geo-plats (till exempel ett bok märke från en tidigare Geo-plats) omdirigeras de automatiskt till OneDrive på lämplig Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="9ba32-126">OneDrive iOS och Android</span><span class="sxs-lookup"><span data-stu-id="9ba32-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="9ba32-127">I OneDrive iOS-och Android-mobilappar visas dina OneDrive-filer och filer som delas med dig oavsett var de befinner sig.</span><span class="sxs-lookup"><span data-stu-id="9ba32-127">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location.</span></span> <span data-ttu-id="9ba32-128">Sökning i OneDrive-mobilappen visar relevanta resultat från alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-128">Search from the OneDrive mobile apps will show relevant results from all geo locations.</span></span> <span data-ttu-id="9ba32-129">Ladda ner den senaste versionen av dessa program.</span><span class="sxs-lookup"><span data-stu-id="9ba32-129">Please download the latest version of these apps.</span></span>

<span data-ttu-id="9ba32-130">Mer information finns i använda [OneDrive för iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) och [använda OneDrive för Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) .</span><span class="sxs-lookup"><span data-stu-id="9ba32-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="9ba32-131">OneDrive-mobilapp</span><span class="sxs-lookup"><span data-stu-id="9ba32-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="9ba32-132">OneDrive-mobilappen är en geo medveten och visar relevant innehåll och resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="9ba32-133">Sökmotor</span><span class="sxs-lookup"><span data-stu-id="9ba32-133">Search</span></span>

<span data-ttu-id="9ba32-134">Varje Geo-plats har ett eget Sök index och Sök Center.</span><span class="sxs-lookup"><span data-stu-id="9ba32-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="9ba32-135">När en användare söker skickas frågan till alla geo-platser, och de returnerade resultaten kopplas och rangordnas sedan så att användaren får enhetliga resultat.</span><span class="sxs-lookup"><span data-stu-id="9ba32-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="9ba32-136">Användare får resultat från alla geo platser oavsett deras egna Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="9ba32-137">Se [Konfigurera sökning i OneDrive för företag multi-geo](configure-search-for-multi-geo.md) för specifika nyheter.</span><span class="sxs-lookup"><span data-stu-id="9ba32-137">See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="9ba32-138">Följande Sök klienter stöds:</span><span class="sxs-lookup"><span data-stu-id="9ba32-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="9ba32-139">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="9ba32-139">OneDrive for Business</span></span>

-   <span data-ttu-id="9ba32-140">Delve</span><span class="sxs-lookup"><span data-stu-id="9ba32-140">Delve</span></span>

-   <span data-ttu-id="9ba32-141">Start sidan för SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ba32-141">SharePoint Home</span></span>

-   <span data-ttu-id="9ba32-142">Sök Center</span><span class="sxs-lookup"><span data-stu-id="9ba32-142">The Search Center</span></span>

-   <span data-ttu-id="9ba32-143">Anpassade Sök program som använder SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="9ba32-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="9ba32-144">Start sidan för SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ba32-144">SharePoint Home</span></span> 

<span data-ttu-id="9ba32-145">I SharePoint multi-geo är SharePoint-hem platsen placerad på den plats där användaren finns som den definieras av OneDrive för företag-platsen.</span><span class="sxs-lookup"><span data-stu-id="9ba32-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="9ba32-146">Till exempel: om användaren har OneDrive-värd på en europeisk satellit plats kommer deras SharePoint-hem att renderas från Europa.</span><span class="sxs-lookup"><span data-stu-id="9ba32-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="9ba32-147">SharePoint Home inkluderar allt innehåll som är relevant för användaren oavsett dess geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="9ba32-148">**Följda webbplatser, nyheter från webbplatser, senaste webbplatser, vanliga webbplatser och föreslagna webbplatser**</span><span class="sxs-lookup"><span data-stu-id="9ba32-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="9ba32-149">Alla de här komponenterna visas för användaren oavsett vilken Geo-plats som innehållet hanteras på, så länge användaren har behörighet till innehåll.</span><span class="sxs-lookup"><span data-stu-id="9ba32-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="9ba32-150">**Funktions länkar**</span><span class="sxs-lookup"><span data-stu-id="9ba32-150">**Features Links**</span></span>

<span data-ttu-id="9ba32-151">Administratörer kan konfigurera aktuella länkar i SharePoint Home efter behov till varje Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="9ba32-152">På så sätt kan administratören i SP hem för varje region de länkar som är lämpliga för användarna i regionen.</span><span class="sxs-lookup"><span data-stu-id="9ba32-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="9ba32-153">SharePoint Mobile-klient</span><span class="sxs-lookup"><span data-stu-id="9ba32-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="9ba32-154">SharePoint Mobile-klienten är en geo medveten och visar relevant innehåll och resultat från alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="9ba32-155">Delning</span><span class="sxs-lookup"><span data-stu-id="9ba32-155">Sharing</span></span>

<span data-ttu-id="9ba32-156">Person väljaren visar alla användare oavsett deras Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="9ba32-157">Det gör det möjligt för en användare att dela med sig av sina geo-eller andra användares geo-platser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="9ba32-158">Innehåll från olika geo-platser visas i vyn **delas med mig** i användarens OneDrive för företag och kan nås med enkel inloggnings upplevelse oavsett vilken Geo-plats den finns i.</span><span class="sxs-lookup"><span data-stu-id="9ba32-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="9ba32-159">Teams Experience</span><span class="sxs-lookup"><span data-stu-id="9ba32-159">Teams Experience</span></span>

<span data-ttu-id="9ba32-160">Teams är multi-geo-känsligt.</span><span class="sxs-lookup"><span data-stu-id="9ba32-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="9ba32-161">OneDrive-filer och nyligen visade filer visas oavsett användarens Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="9ba32-162">@ omnämnanden fungerar tillsammans med användare från alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="9ba32-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="9ba32-163">Användar profiler</span><span class="sxs-lookup"><span data-stu-id="9ba32-163">User profiles</span></span>

<span data-ttu-id="9ba32-164">Användar profil informationen hanteras i användarens Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="9ba32-164">User profile information is mastered in the user's geo location.</span></span> <span data-ttu-id="9ba32-165">När du väljer en användare omdirigeras du till en lämplig Geo-plats för användaren, där du kan se deras fullständiga profil uppgifter.</span><span class="sxs-lookup"><span data-stu-id="9ba32-165">When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="9ba32-166">Om Delve är inaktiverat visas den klassiska profil upplevelsen i SharePoint, som inte är särskilt kompatibel.</span><span class="sxs-lookup"><span data-stu-id="9ba32-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


