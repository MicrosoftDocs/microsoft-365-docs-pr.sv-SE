---
title: Användarupplevelse i en miljö med flera geografiska miljöer
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
description: Läs mer SharePoint, OneDrive och Exchange i en miljö med flera geografiska Microsoft 365.
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749581"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="d3ff3-103">Användarupplevelse i en miljö med flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="d3ff3-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="d3ff3-104">Det här ser dina användare i en OneDrive Multi-Geo konfiguration:</span><span class="sxs-lookup"><span data-stu-id="d3ff3-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="d3ff3-105">Exchange postlåda</span><span class="sxs-lookup"><span data-stu-id="d3ff3-105">Exchange mailbox</span></span>

<span data-ttu-id="d3ff3-106">En användares e Exchange postlåda etableras till den önskade dataplatsen och flyttas automatiskt om deras PDL ändras.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="d3ff3-107">Användare kan använda Outlook och Outlook på webben normalt utan att ändra användarupplevelsen i en geomiljö med flera webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="d3ff3-108">Navplatser</span><span class="sxs-lookup"><span data-stu-id="d3ff3-108">Hub sites</span></span>

<span data-ttu-id="d3ff3-109">SharePoint Navplatser förbättrar identifieringen och engagemanget med innehåll för anställda, samtidigt som en komplett och enhetlig representation av projekt, avdelningar eller regioner skapas.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="d3ff3-110">I flera geomiljöer kan webbplatser från satellitplatser enkelt kopplas till en navplats oavsett navplatsens geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="d3ff3-111">Användare kan söka och få resultat i hela navet genom en enda sökupplevelse, oavsett platsens geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="d3ff3-112">Microsoft 365 för appar</span><span class="sxs-lookup"><span data-stu-id="d3ff3-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="d3ff3-113">Startprogrammet är multi-geomedvetet och dirigerar varje panel till rätt geografisk plats för arbetsbelastningen.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="d3ff3-114">Med SharePoint och OneDrive-paneler pekar användaren på den plats som motsvarar användarens etablerade geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="d3ff3-115">Det innebär att användaren har ett OneDrive på den centrala platsen. Deras SharePoint-panel pekar dem på SP Home på den centrala platsen men gruppwebbplatsen etableras på den plats som motsvarar deras PDL.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="d3ff3-116">Office-program</span><span class="sxs-lookup"><span data-stu-id="d3ff3-116">Office applications</span></span>

<span data-ttu-id="d3ff3-117">Office program som Word, Excel och PowerPoint identifierar automatiskt rätt OneDrive för företag geoplats för varje användare när de loggar in.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="d3ff3-118">Användarna behöver inte ange den geospecifika URL-adressen för sina OneDrive eller SharePoint webbplatser.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="d3ff3-119">OneDrive för företag Synkroniseringsklient</span><span class="sxs-lookup"><span data-stu-id="d3ff3-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="d3ff3-120">Synkroniseringsklienten OneDrive för företag (version 17.3.6943.0625 och senare) identifierar automatiskt rätt OneDrive för företag geoplats för användaren.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="d3ff3-121">Stöd för synkroniseringsklienten omfattar möjligheten att synkronisera gruppbaserade webbplatser oavsett deras geografiska position.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-121">Sync client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="d3ff3-122">Observera att Groove synkroniseringsklienten inte stöds för multi-geo.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="d3ff3-123">OneDrive för företag plats</span><span class="sxs-lookup"><span data-stu-id="d3ff3-123">OneDrive for Business location</span></span>

<span data-ttu-id="d3ff3-124">Användarna får sina OneDrive för företag tillhandahållas på den dataplats de föredrar.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-124">Users will have their OneDrive for Business provisioned in their preferred data location.</span></span> <span data-ttu-id="d3ff3-125">Om en användare navigerar till en URL-adress för OneDrive som innehåller en felaktig geoplats (till exempel ett bokmärke från en tidigare geoplats) omdirigeras de automatiskt till OneDrive på lämplig geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-125">If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="d3ff3-126">OneDrive iOS och Android</span><span class="sxs-lookup"><span data-stu-id="d3ff3-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="d3ff3-127">I OneDrive iOS- och Android-mobilapparna visas dina OneDrive filer och filer som delas med dig oavsett var de befinner sig.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-127">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location.</span></span> <span data-ttu-id="d3ff3-128">Sök från OneDrive mobilappar visar relevanta resultat från alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-128">Search from the OneDrive mobile apps will show relevant results from all geo locations.</span></span> <span data-ttu-id="d3ff3-129">Ladda ned den senaste versionen av dessa appar.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-129">Please download the latest version of these apps.</span></span>

<span data-ttu-id="d3ff3-130">Mer information OneDrive Använda OneDrive [iOS och Använda OneDrive för Android.](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) [](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247)</span><span class="sxs-lookup"><span data-stu-id="d3ff3-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="d3ff3-131">OneDrive Mobilklient</span><span class="sxs-lookup"><span data-stu-id="d3ff3-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="d3ff3-132">The OneDrive Mobile Client is multi-geo aware and will display relevant content and results from all geo locations.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="d3ff3-133">Söka</span><span class="sxs-lookup"><span data-stu-id="d3ff3-133">Search</span></span>

<span data-ttu-id="d3ff3-134">Varje geoplats har ett eget sökindex och sökcenter.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-134">Each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="d3ff3-135">När en användare söker skickas frågan till alla geografiska platser och de returnerade resultaten sammanfogas och rangordnas så att användaren får enhetliga resultat.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-135">When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results.</span></span> <span data-ttu-id="d3ff3-136">Användare får resultat från alla geoplatser oavsett var de befinner sig.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-136">Users get results from all geo locations regardless of their own geo location.</span></span> <span data-ttu-id="d3ff3-137">Mer [information finns i OneDrive för företag för](configure-search-for-multi-geo.md) sökning med multi-geo.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-137">See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="d3ff3-138">Följande sökklienter stöds:</span><span class="sxs-lookup"><span data-stu-id="d3ff3-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="d3ff3-139">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="d3ff3-139">OneDrive for Business</span></span>

-   <span data-ttu-id="d3ff3-140">Delve</span><span class="sxs-lookup"><span data-stu-id="d3ff3-140">Delve</span></span>

-   <span data-ttu-id="d3ff3-141">SharePoint Home</span><span class="sxs-lookup"><span data-stu-id="d3ff3-141">SharePoint Home</span></span>

-   <span data-ttu-id="d3ff3-142">Sökcenter</span><span class="sxs-lookup"><span data-stu-id="d3ff3-142">The Search Center</span></span>

-   <span data-ttu-id="d3ff3-143">Anpassade sökprogram som använder SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="d3ff3-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="d3ff3-144">SharePoint Home</span><span class="sxs-lookup"><span data-stu-id="d3ff3-144">SharePoint Home</span></span> 

<span data-ttu-id="d3ff3-145">I SharePoint Multi-Geo ditt SharePoint ligger hemma på den plats där användaren finns enligt användarens OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="d3ff3-146">Exempel: Om användaren har en OneDrive på en europeisk satellitplats återges deras SharePoint från Europa.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="d3ff3-147">SharePoint innehåller allt innehåll som är relevant för användaren, oavsett dess geografiska position.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="d3ff3-148">**Webbplatser du följer, nyheter från webbplatser, senaste webbplatser, vanliga webbplatser och föreslagna webbplatser**</span><span class="sxs-lookup"><span data-stu-id="d3ff3-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="d3ff3-149">Alla dessa komponenter visas för användaren oavsett den geoplats där innehållet finns, så länge användaren har behörighet till innehållet.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="d3ff3-150">**Länkar till funktioner**</span><span class="sxs-lookup"><span data-stu-id="d3ff3-150">**Features Links**</span></span>

<span data-ttu-id="d3ff3-151">Administratörer kan konfigurera aktuella länkar i SharePoint efter behov för varje geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="d3ff3-152">Det gör att administratören kan använda länkarna som är lämpliga för användare i regionen i SP Home för varje region.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="d3ff3-153">SharePoint Mobilklient</span><span class="sxs-lookup"><span data-stu-id="d3ff3-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="d3ff3-154">The SharePoint Mobile Client is multi-geo aware and will display relevant content and results from all geo locations.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="d3ff3-155">Delning</span><span class="sxs-lookup"><span data-stu-id="d3ff3-155">Sharing</span></span>

<span data-ttu-id="d3ff3-156">I väljaren för personer visas alla användare oavsett var de befinner sig.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="d3ff3-157">Det gör att en användare kan dela med en annan användare i samma geo eller på någon annan av klientorganisationens geoplatser.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="d3ff3-158">Innehåll från olika geografiska platser visas  i vyn Delas med mig i användarens OneDrive för företag och kan nås med single Sign-On-upplevelse oavsett vilken geoplats den finns på.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="d3ff3-159">Teams Upplevelse</span><span class="sxs-lookup"><span data-stu-id="d3ff3-159">Teams Experience</span></span>

<span data-ttu-id="d3ff3-160">Teams är multi-geomedveten.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="d3ff3-161">OneDrive filer och senast visade filer visas oavsett användarens geografiska position.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="d3ff3-162">@ omnämnanden fungerar med användare från alla geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="d3ff3-163">Användarprofiler</span><span class="sxs-lookup"><span data-stu-id="d3ff3-163">User profiles</span></span>

<span data-ttu-id="d3ff3-164">Användarprofilinformation kan lagras på användarens geoplats.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-164">User profile information is mastered in the user's geo location.</span></span> <span data-ttu-id="d3ff3-165">När du väljer en användare dirigeras du till lämplig geoplats för användaren, där du ser den fullständiga profilinformationen.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-165">When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="d3ff3-166">Om Delve är inaktiverat visas det klassiska profilupplevelsen i SharePoint, som inte är multigeografiska.</span><span class="sxs-lookup"><span data-stu-id="d3ff3-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


