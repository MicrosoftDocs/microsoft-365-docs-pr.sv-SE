---
title: Konfigurera sökning för Microsoft 365 multi-geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Lär dig hur du konfigurerar sökning i en multi-geo-miljö. Endast vissa klienter, till exempel OneDrive för företag, kan returnera resultat i en multi-geo-miljö.
ms.openlocfilehash: e213e93cfbc967a723b4d27f4b36a83fe6687da9
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547158"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="37288-104">Konfigurera sökning för Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="37288-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="37288-105">I en multi-geo-miljö har varje Geo-plats ett eget Sök index och Sök Center.</span><span class="sxs-lookup"><span data-stu-id="37288-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="37288-106">När en användare söker är frågan fanned ut till alla index och resultaten som returneras kopplas.</span><span class="sxs-lookup"><span data-stu-id="37288-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="37288-107">En användare på en Geo-plats kan till exempel söka efter innehåll som lagras på en annan Geo-plats eller för innehåll på en SharePoint-webbplats som är begränsad till en annan Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="37288-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="37288-108">Om användaren har till gång till innehållet visas resultatet i sökningen.</span><span class="sxs-lookup"><span data-stu-id="37288-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="37288-109">Vilka Sök klienter fungerar i en multi-geo-miljö?</span><span class="sxs-lookup"><span data-stu-id="37288-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="37288-110">Dessa klienter kan returnera resultat från alla geo-platser:</span><span class="sxs-lookup"><span data-stu-id="37288-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="37288-111">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="37288-111">OneDrive for Business</span></span>
- <span data-ttu-id="37288-112">Delve</span><span class="sxs-lookup"><span data-stu-id="37288-112">Delve</span></span>
- <span data-ttu-id="37288-113">Start sidan för SharePoint</span><span class="sxs-lookup"><span data-stu-id="37288-113">The SharePoint home page</span></span>
- <span data-ttu-id="37288-114">Sök Center</span><span class="sxs-lookup"><span data-stu-id="37288-114">The Search Center</span></span>
- <span data-ttu-id="37288-115">Anpassade Sök program som använder SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="37288-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="37288-116">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="37288-116">OneDrive for Business</span></span>

<span data-ttu-id="37288-117">När multi-geo-miljön har kon figurer ATS får användare som söker i OneDrive resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="37288-118">Delve</span><span class="sxs-lookup"><span data-stu-id="37288-118">Delve</span></span>

<span data-ttu-id="37288-119">När multi-geo-miljön har ställts in får användare som söker i Delve resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="37288-120">Delve-feeden och profil kortet visar bara förhands granskningar av filer som lagras på Central platsen.</span><span class="sxs-lookup"><span data-stu-id="37288-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="37288-121">För filer som lagras på satellit platser visas ikonen för filtypen i stället.</span><span class="sxs-lookup"><span data-stu-id="37288-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="37288-122">Start sidan för SharePoint</span><span class="sxs-lookup"><span data-stu-id="37288-122">The SharePoint home page</span></span>

<span data-ttu-id="37288-123">Så fort multi-geo-miljön har kon figurer ATS ser användarna nyheter, senaste och följda webbplatser från flera geo platser på Start sidan för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="37288-123">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page.</span></span> <span data-ttu-id="37288-124">Om de använder sökrutan på Start sidan för SharePoint får de sammankopplade resultat från flera geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-124">If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="37288-125">Sök Center</span><span class="sxs-lookup"><span data-stu-id="37288-125">The Search Center</span></span>

<span data-ttu-id="37288-126">När multi-geo-miljön har ställts in fortsätter varje Sök Center att bara visa resultat från sin egen Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="37288-126">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location.</span></span> <span data-ttu-id="37288-127">Administratörer måste [ändra inställningarna för varje Sök Center](#_Set_up_a_1) för att få resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-127">Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations.</span></span> <span data-ttu-id="37288-128">Därefter får användare som söker i Sök centret resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-128">Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="37288-129">Anpassade Sök program</span><span class="sxs-lookup"><span data-stu-id="37288-129">Custom search applications</span></span>

<span data-ttu-id="37288-130">Som vanligt kan anpassade Sök program interagera med Sök indexen med hjälp av de befintliga SharePoint-sökningens REST-API: er.</span><span class="sxs-lookup"><span data-stu-id="37288-130">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs.</span></span> <span data-ttu-id="37288-131">För att få resultat från alla, eller vissa geo platser, måste programmet [anropa API: t och inkludera de nya multi-geo-frågeparametrarna](#_Get_custom_search) i begäran.</span><span class="sxs-lookup"><span data-stu-id="37288-131">To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request.</span></span> <span data-ttu-id="37288-132">Då utlöses en fläkt från frågan till alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="37288-132">This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="37288-133">Vad är skillnaden mellan sökning i en multi-geo-miljö?</span><span class="sxs-lookup"><span data-stu-id="37288-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="37288-134">Vissa Sök funktioner du kanske känner till, fungerar annorlunda i en multi-geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="37288-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37288-135"><strong>Funktion</strong></span><span class="sxs-lookup"><span data-stu-id="37288-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="37288-136"><strong>Så fungerar det</strong></span><span class="sxs-lookup"><span data-stu-id="37288-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="37288-137"><strong>Lösning</strong></span><span class="sxs-lookup"><span data-stu-id="37288-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-138">Framhävda resultat</span><span class="sxs-lookup"><span data-stu-id="37288-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="37288-139">Du kan skapa Frågeregler med framhävda resultat på olika nivåer: för hela klient organisationen, för en webbplats samling eller för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="37288-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="37288-140">I en multi-geo-miljö definierar du framhävda resultat på klient organisations nivå för att marknadsföra resultaten till Sök Center på alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="37288-141">Om du bara vill framhäva resultaten i Sök centret som finns på Geo-platsen för webbplats samlingen eller webbplatsen definierar du de framhävda resultaten på webbplats samlingen eller webbplats nivån.</span><span class="sxs-lookup"><span data-stu-id="37288-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="37288-142">Dessa resultat marknadsförs inte på andra geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="37288-143">Om du inte behöver olika framhävda resultat per Geo-plats, till exempel olika regler för resor, rekommenderar vi att du definierar framhävda resultat på klient organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="37288-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-144">Sök förfiningar</span><span class="sxs-lookup"><span data-stu-id="37288-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="37288-145">Sök returnerar förfiningar från alla geo-platser hos en klient organisation och aggregerar dem.</span><span class="sxs-lookup"><span data-stu-id="37288-145">Search returns refiners from all the geo locations of a tenant and then aggregates them.</span></span> <span data-ttu-id="37288-146">Aggregation är ett bra sätt, vilket innebär att förfiningen kanske inte är 100% korrekt.</span><span class="sxs-lookup"><span data-stu-id="37288-146">The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate.</span></span> <span data-ttu-id="37288-147">För de flesta Sök-drivna scenarier är denna noggrannhet tillräckligt.</span><span class="sxs-lookup"><span data-stu-id="37288-147">For most search-driven scenarios, this accuracy is sufficient.</span></span> 
</td>
<td align="left"><span data-ttu-id="37288-148">För Sök drivna program som är beroende av att förfining är klart kan du fråga varje Geo-plats oberoende.</span><span class="sxs-lookup"><span data-stu-id="37288-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="37288-149">Multi-geo-sökning stöder inte dynamisk upphållning för numeriska förfiningar.</span><span class="sxs-lookup"><span data-stu-id="37288-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="37288-150">Använd <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">parametern "Discretize"</a> för numeriska förfiningar.</span><span class="sxs-lookup"><span data-stu-id="37288-150">Use the <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-151">Dokument-ID</span><span class="sxs-lookup"><span data-stu-id="37288-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="37288-152">Om du utvecklar ett Sök drivna program som är beroende av dokument-ID: na kan du observera att dokument-ID i en multi-geo-miljö inte är unika för geo platser, de är unika per Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="37288-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="37288-153">Vi har lagt till en kolumn som identifierar geo platsen.</span><span class="sxs-lookup"><span data-stu-id="37288-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="37288-154">Använd den här kolumnen för att uppnå unika.</span><span class="sxs-lookup"><span data-stu-id="37288-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="37288-155">Denna kolumn kallas "GeoLocationSource".</span><span class="sxs-lookup"><span data-stu-id="37288-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-156">Antal resultat</span><span class="sxs-lookup"><span data-stu-id="37288-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="37288-157">Sök Resultat sidan visar sammanslagna resultat från geo platser, men det går inte att bläddra bortom 500-resultaten.</span><span class="sxs-lookup"><span data-stu-id="37288-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-158">HYBRIDS ökning</span><span class="sxs-lookup"><span data-stu-id="37288-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="37288-159">I en hybrid SharePoint-miljö med <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">moln HYBRIDS ökning</a>läggs lokalt innehåll till i Microsoft 365-indexet för den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="37288-159">In a hybrid SharePoint environment with <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="37288-160">Vad stöds inte för sökning i en multi-geo-miljö?</span><span class="sxs-lookup"><span data-stu-id="37288-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="37288-161">Vissa av de Sök funktioner du kanske är van vid, stöds inte i en multi-geo-miljö.</span><span class="sxs-lookup"><span data-stu-id="37288-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37288-162"><strong>Sök funktion</strong></span><span class="sxs-lookup"><span data-stu-id="37288-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="37288-163"><strong>Fotnot</strong></span><span class="sxs-lookup"><span data-stu-id="37288-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-164">Endast app-only</span><span class="sxs-lookup"><span data-stu-id="37288-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="37288-165">Endast app-inloggningsautentisering (privilegie rad åtkomst från tjänster) stöds inte i multi-geo-sökning.</span><span class="sxs-lookup"><span data-stu-id="37288-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-166">Gästanvändare</span><span class="sxs-lookup"><span data-stu-id="37288-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="37288-167">Gäst användare får bara resultat från den Geo-plats som de söker från.</span><span class="sxs-lookup"><span data-stu-id="37288-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="37288-168">Hur fungerar sökning i en multi-geo-miljö?</span><span class="sxs-lookup"><span data-stu-id="37288-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="37288-169">Alla Sök klienter använder de befintliga SharePoint-sökningens REST-API: er för att interagera med Sök indexen.</span><span class="sxs-lookup"><span data-stu-id="37288-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Diagram som visar hur resten av API för SharePoint-sökning interagerar med Sök indexen](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="37288-171">En Sök klient anropar Sök öknings slut punkten med Frågeparametern EnableMultiGeoSearch = True.</span><span class="sxs-lookup"><span data-stu-id="37288-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="37288-172">Frågan skickas till alla geo-platser i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="37288-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="37288-173">Sök Resultat från varje Geo-plats slås samman och rangordnas.</span><span class="sxs-lookup"><span data-stu-id="37288-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="37288-174">Klienten får enhetliga Sök resultat.</span><span class="sxs-lookup"><span data-stu-id="37288-174">The client gets unified search results.</span></span>

<span data-ttu-id="37288-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Observera att vi inte sammanfogar Sök resultaten förrän vi har fått resultat från alla geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="37288-176">Det innebär att multi-geo-sökningar har ytterligare fördröjning jämfört med sökningar i en miljö med bara en Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="37288-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="37288-177">Hämta ett Sök Center för att visa resultat från alla geo platser</span><span class="sxs-lookup"><span data-stu-id="37288-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="37288-178">Varje Sök Center innehåller flera lodräta och du måste ställa in varje lodrätt.</span><span class="sxs-lookup"><span data-stu-id="37288-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="37288-179">Kontrol lera att du utför de här stegen med ett konto som har behörighet att redigera Sök Resultat sidan och webb delen Sök resultat.</span><span class="sxs-lookup"><span data-stu-id="37288-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="37288-180">Gå till sidan med Sök resultat (se [listan](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) med Sök Resultat sidor)</span><span class="sxs-lookup"><span data-stu-id="37288-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="37288-181">Markera kryss rutan lodrätt och klicka på **Inställningar** kugg hjul i det övre högra hörnet och klicka sedan på **Redigera sida**.</span><span class="sxs-lookup"><span data-stu-id="37288-181">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**.</span></span> <span data-ttu-id="37288-182">Sidan Sök Resultat öppnas i redigerings läge.</span><span class="sxs-lookup"><span data-stu-id="37288-182">The search results page opens in Edit mode.</span></span>

   ![Redigera sid val i inställningar](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="37288-184">I webb delen Sök Resultat flyttar du pekaren till det övre högra hörnet av webb delen, klickar på pilen och sedan på **Redigera webbdel** på menyn.</span><span class="sxs-lookup"><span data-stu-id="37288-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="37288-185">Verktygs fönstret för webb delen Sök Resultat öppnas under menyfliksområdet längst upp till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="37288-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Redigera webb dels val](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="37288-187">I verktygs fönstret webbdel, i avsnittet **Inställningar** , under **resultat kontroll inställningar**väljer du **Visa multi-geo Results** för att få webb delen Sök Resultat för att visa resultat från alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="37288-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="37288-188">Klicka på **OK** för att spara ändringen och stänga verktygs fönstret för webb delen.</span><span class="sxs-lookup"><span data-stu-id="37288-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="37288-189">Kontrol lera dina ändringar i webb delen Sök resultat genom att klicka på **checka** in på fliken sida i huvud menyn.</span><span class="sxs-lookup"><span data-stu-id="37288-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="37288-190">Publicera ändringarna med länken i anteckningen högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="37288-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="37288-191">Få anpassade Sök program för att visa resultat från alla eller vissa geo-platser</span><span class="sxs-lookup"><span data-stu-id="37288-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="37288-192">Anpassade Sök program får resultat från alla eller vissa geo platser genom att ange frågeparametrar med begäran till den REST-API för SharePoint-sökning.</span><span class="sxs-lookup"><span data-stu-id="37288-192">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API.</span></span><span data-ttu-id="37288-193">Beroende på frågeparametrarna är frågan fanned ut till alla geo platser eller till vissa geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-193"> Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations.</span></span> <span data-ttu-id="37288-194">Om du till exempel bara behöver fråga en delmängd geo platser för att hitta relevant information kan du bara kontrol lera fläkten till dessa.</span><span class="sxs-lookup"><span data-stu-id="37288-194">For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these.</span></span> <span data-ttu-id="37288-195">Om begäran lyckas returneras svars data i SharePoint Search REST API.</span><span class="sxs-lookup"><span data-stu-id="37288-195">If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="37288-196">Krav</span><span class="sxs-lookup"><span data-stu-id="37288-196">Requirement</span></span>

<span data-ttu-id="37288-197">För varje Geo-plats måste du se till att alla användare i organisationen har fått behörighets nivån **läsa** för rot webbplatsen (till exempel contoso**APAC**. SharePoint.com/och contoso**EU**. SharePoint.com/).</span><span class="sxs-lookup"><span data-stu-id="37288-197">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso**APAC**.sharepoint.com/ and contoso**EU**.sharepoint.com/).</span></span> <span data-ttu-id="37288-198">[Läs mer om behörigheter](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="37288-198">[Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="37288-199">Frågeparametrar</span><span class="sxs-lookup"><span data-stu-id="37288-199">Query parameters</span></span>

<span data-ttu-id="37288-200">EnableMultiGeoSearch-det här är ett booleskt värde som anger om frågan ska fanned till indexen för andra geo platser i multi-geo-klienten.</span><span class="sxs-lookup"><span data-stu-id="37288-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="37288-201">Ange att det ska vara **Sant** för att det ska vara. **falskt** för att inte framhäva frågan.</span><span class="sxs-lookup"><span data-stu-id="37288-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="37288-202">Om du inte tar med den här parametern är standardvärdet **falskt**, förutom när du skapar ett REST API-samtal på en webbplats där mallen Enterprise Search Center används, i det här fallet är standardvärdet **Sant**.</span><span class="sxs-lookup"><span data-stu-id="37288-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="37288-203">Om du använder en parameter i en miljö som inte är multi-geo ignoreras parametern.</span><span class="sxs-lookup"><span data-stu-id="37288-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="37288-204">ClientType-det här är en sträng.</span><span class="sxs-lookup"><span data-stu-id="37288-204">ClientType - This is a string.</span></span> <span data-ttu-id="37288-205">Ange ett unikt klient namn för varje sökprogram.</span><span class="sxs-lookup"><span data-stu-id="37288-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="37288-206">Om du inte tar med den här parametern fanned inte frågan ut till andra geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="37288-207">MultiGeoSearchConfiguration – det här är en valfri lista över vilka geo-platser i multi-geo-klient organisationen som kan utnyttja frågan på när **EnableMultiGeoSearch** är **Sant**.</span><span class="sxs-lookup"><span data-stu-id="37288-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="37288-208">Om du inte tar med den här parametern, eller lämnar den tom, fanned frågan ut till alla geo-platser.</span><span class="sxs-lookup"><span data-stu-id="37288-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="37288-209">För varje Geo-plats anger du följande objekt i JSON-format:</span><span class="sxs-lookup"><span data-stu-id="37288-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37288-210">Objekt</span><span class="sxs-lookup"><span data-stu-id="37288-210">Item</span></span></th>
<th align="left"><span data-ttu-id="37288-211">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="37288-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="37288-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="37288-213">Geo platsen, till exempel.</span><span class="sxs-lookup"><span data-stu-id="37288-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-214">Änd</span><span class="sxs-lookup"><span data-stu-id="37288-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="37288-215">Slut punkten för att ansluta till till exempel https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="37288-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-216">Käll</span><span class="sxs-lookup"><span data-stu-id="37288-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="37288-217">GUID för resultat källan, till exempel B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="37288-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="37288-218">Om du utelämnar DataLocation eller slut punkter, eller om en DataLocation har dubblerats Miss lyckas begäran.</span><span class="sxs-lookup"><span data-stu-id="37288-218">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails.</span></span> <span data-ttu-id="37288-219">[Du kan få information om slut punkten för en innehavares geo platser genom att använda Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="37288-219">[You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="37288-220">Svars data</span><span class="sxs-lookup"><span data-stu-id="37288-220">Response data</span></span>

<span data-ttu-id="37288-221">MultiGeoSearchStatus – det här är en egenskap som SharePoint Search API returnerar som svar på en begäran.</span><span class="sxs-lookup"><span data-stu-id="37288-221">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request.</span></span> <span data-ttu-id="37288-222">Värdet för egenskapen är en sträng och ger följande information om resultaten som returneras av SharePoint Search API:</span><span class="sxs-lookup"><span data-stu-id="37288-222">The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37288-223">Value</span><span class="sxs-lookup"><span data-stu-id="37288-223">Value</span></span></th>
<th align="left"><span data-ttu-id="37288-224">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="37288-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-225">Fullständiga</span><span class="sxs-lookup"><span data-stu-id="37288-225">Full</span></span></td>
<td align="left"><span data-ttu-id="37288-226">Fullständiga resultat från <strong>alla</strong> geo-platser.</span><span class="sxs-lookup"><span data-stu-id="37288-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="37288-227">Partiell</span><span class="sxs-lookup"><span data-stu-id="37288-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="37288-228">Delar av resultat från en eller flera geo platser.</span><span class="sxs-lookup"><span data-stu-id="37288-228">Partial results from one or more geo locations.</span></span> <span data-ttu-id="37288-229">Resultaten är ofullständiga på grund av ett tillfälligt fel.</span><span class="sxs-lookup"><span data-stu-id="37288-229">The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="37288-230">Fråga med REST-tjänsten</span><span class="sxs-lookup"><span data-stu-id="37288-230">Query using the REST service</span></span>

<span data-ttu-id="37288-231">Med en GET-begäran anger du frågeparametrarna i URL: en.</span><span class="sxs-lookup"><span data-stu-id="37288-231">With a GET request, you specify the query parameters in the URL.</span></span> <span data-ttu-id="37288-232">Med en POST-begäran skickar du frågeparametrarna i bröd texten i JSON-format (Java Script Object Notation).</span><span class="sxs-lookup"><span data-stu-id="37288-232">With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="37288-233">Begärandehuvuden</span><span class="sxs-lookup"><span data-stu-id="37288-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="37288-234">Namn</span><span class="sxs-lookup"><span data-stu-id="37288-234">Name</span></span></th>
<th align="left"><span data-ttu-id="37288-235">Värde</span><span class="sxs-lookup"><span data-stu-id="37288-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="37288-236">Innehålls typ</span><span class="sxs-lookup"><span data-stu-id="37288-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="37288-237">Application/JSON; OData = verbose</span><span class="sxs-lookup"><span data-stu-id="37288-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="37288-238">TA en fanned på **alla** geo platser</span><span class="sxs-lookup"><span data-stu-id="37288-238">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="37288-239">https:// \<tenant\> / \_ API/sökning/fråga? querytext = ' SharePoint ' &Properties = ' EnableMultiGeoSearch: true ' &ClientType = ' mitt \_ klient \_ -ID '</span><span class="sxs-lookup"><span data-stu-id="37288-239">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="37288-240">Exempel på GET-begäran för att utnyttja **vissa** geo platser</span><span class="sxs-lookup"><span data-stu-id="37288-240">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="37288-241">https:// \<tenant\> / \_ API/Sök/fråga? querytext = ' site ' &ClientType = ' my_client_id ' &egenskaper = ' EnableMultiGeoSearch: true, MultiGeoSearchConfiguration: [{DataLocation \\ : "," \\ slut punkt \\ : "https \\ ://contosoNAM.SharePoint.com" \\ , SourceId \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {DataLocation \\ : "kan" \\ ; slut punkt \\ : "https \\ ://contosoCAN.SharePoint-DF.com"}] "</span><span class="sxs-lookup"><span data-stu-id="37288-241">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="37288-242">Kommatecken och kolon i listan med geo-platser för egenskapen MultiGeoSearchConfiguration föregås av det **omvända snedstrecket** .</span><span class="sxs-lookup"><span data-stu-id="37288-242">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="37288-243">Det beror på att GET-begäranden använder kolon för att avgränsa egenskaper och kommatecken för att skilja mellan egenskaper.</span><span class="sxs-lookup"><span data-stu-id="37288-243">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="37288-244">Utan omvänt snedstreck som escape-tecken tolkas egenskapen MultiGeoSearchConfiguration som felaktig.</span><span class="sxs-lookup"><span data-stu-id="37288-244">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="37288-245">Exempel på inlägg som fanned ut till **alla** geo-platser</span><span class="sxs-lookup"><span data-stu-id="37288-245">Sample POST request that's fanned out to **all** geo locations</span></span>

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="37288-246">Exempel på inlägg som fanned ut till **vissa** geo platser</span><span class="sxs-lookup"><span data-stu-id="37288-246">Sample POST request that's fanned out to **some** geo locations</span></span>

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="37288-247">Fråga med CSOM</span><span class="sxs-lookup"><span data-stu-id="37288-247">Query using CSOM</span></span>

<span data-ttu-id="37288-248">Här är ett exempel på en CSOM fråga som fanned på **alla** geo platser:</span><span class="sxs-lookup"><span data-stu-id="37288-248">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```
