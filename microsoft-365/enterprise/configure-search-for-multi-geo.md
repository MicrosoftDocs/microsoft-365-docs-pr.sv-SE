---
title: Konfigurera sökning efter Microsoft 365 Multi-Geo
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
description: Lär dig hur du konfigurerar sökning i en miljö med flera geoer. Endast vissa klienter, till exempel OneDrive, kan returnera resultat i en geomiljö med flera funktioner.
ms.openlocfilehash: dfc9e3dd986132810f363ba47ba18eae45666fc7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362276"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="915b3-104">Konfigurera sökning efter Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="915b3-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="915b3-105">I en geomiljö med flera platser har varje geoplats ett eget sökindex och ett sökcenter.</span><span class="sxs-lookup"><span data-stu-id="915b3-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="915b3-106">När en användare söker visas frågan i alla index och de returnerade resultaten sammanfogas.</span><span class="sxs-lookup"><span data-stu-id="915b3-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="915b3-107">En användare på en geoplats kan till exempel söka efter innehåll som lagrats på en annan geoplats eller efter innehåll på en SharePoint-webbplats som är begränsad till en annan geoplats.</span><span class="sxs-lookup"><span data-stu-id="915b3-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="915b3-108">Om användaren har åtkomst till innehållet visas resultatet i sökningen.</span><span class="sxs-lookup"><span data-stu-id="915b3-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="915b3-109">Vilka sökklienter fungerar i en geomiljö med flera sökklienter?</span><span class="sxs-lookup"><span data-stu-id="915b3-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="915b3-110">Dessa klienter kan returnera resultat från alla geoplatser:</span><span class="sxs-lookup"><span data-stu-id="915b3-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="915b3-111">OneDrive</span><span class="sxs-lookup"><span data-stu-id="915b3-111">OneDrive</span></span>
- <span data-ttu-id="915b3-112">Delve</span><span class="sxs-lookup"><span data-stu-id="915b3-112">Delve</span></span>
- <span data-ttu-id="915b3-113">Sidan SharePoint startsida</span><span class="sxs-lookup"><span data-stu-id="915b3-113">The SharePoint home page</span></span>
- <span data-ttu-id="915b3-114">Sökcenter</span><span class="sxs-lookup"><span data-stu-id="915b3-114">The Search Center</span></span>
- <span data-ttu-id="915b3-115">Anpassade sökprogram som använder SharePoint Search API</span><span class="sxs-lookup"><span data-stu-id="915b3-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive"></a><span data-ttu-id="915b3-116">OneDrive</span><span class="sxs-lookup"><span data-stu-id="915b3-116">OneDrive</span></span>

<span data-ttu-id="915b3-117">Så snart multigeomiljön har ställts in kan användare som söker i OneDrive få resultat från alla geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="915b3-118">Delve</span><span class="sxs-lookup"><span data-stu-id="915b3-118">Delve</span></span>

<span data-ttu-id="915b3-119">Så snart multigeomiljön har ställts in kan användare som söker i Delve få resultat från alla geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="915b3-120">I Delve och profilkortet visas bara förhandsgranskningar av filer som lagras på den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="915b3-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="915b3-121">För filer som lagras på satellitplatser visas ikonen för filtypen i stället.</span><span class="sxs-lookup"><span data-stu-id="915b3-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="915b3-122">Sidan SharePoint startsida</span><span class="sxs-lookup"><span data-stu-id="915b3-122">The SharePoint home page</span></span>

<span data-ttu-id="915b3-123">Så snart multi geomiljön har SharePoint kan användarna se nyheter, senaste och följda webbplatser från flera geografiska platser på SharePoint startsida.</span><span class="sxs-lookup"><span data-stu-id="915b3-123">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page.</span></span> <span data-ttu-id="915b3-124">Om de använder sökrutan på SharePoint startsida får de kopplade resultat från flera geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-124">If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="915b3-125">Sökcenter</span><span class="sxs-lookup"><span data-stu-id="915b3-125">The Search Center</span></span>

<span data-ttu-id="915b3-126">Efter att multigeomiljön har ställts in fortsätter varje sökcenter bara att visa resultat från sin egen geoplats.</span><span class="sxs-lookup"><span data-stu-id="915b3-126">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location.</span></span> <span data-ttu-id="915b3-127">Administratörer måste [ändra inställningarna för varje sökcenter för](#_Set_up_a_1) att få resultat från alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-127">Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations.</span></span> <span data-ttu-id="915b3-128">Därefter får användare som söker i sökcentret resultat från alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-128">Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="915b3-129">Anpassade sökprogram</span><span class="sxs-lookup"><span data-stu-id="915b3-129">Custom search applications</span></span>

<span data-ttu-id="915b3-130">Som vanligt interagerar anpassade sökprogram med sökindex genom att använda de befintliga SharePoint REST-API:er.</span><span class="sxs-lookup"><span data-stu-id="915b3-130">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs.</span></span> <span data-ttu-id="915b3-131">Om du vill få resultat från alla, eller vissa geoplatser, måste programmet anropa API:t och inkludera de nya parametrarna för [multi-geofråga](#_Get_custom_search) i begäran.</span><span class="sxs-lookup"><span data-stu-id="915b3-131">To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request.</span></span> <span data-ttu-id="915b3-132">Det här utlöser en fan av frågan på alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-132">This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="915b3-133">Vad är så annorlunda med sökning i en geomiljö med flera platser?</span><span class="sxs-lookup"><span data-stu-id="915b3-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="915b3-134">Vissa sökfunktioner som du kanske är van vid fungerar annorlunda i en geomiljö med flera platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="915b3-135">Funktion</span><span class="sxs-lookup"><span data-stu-id="915b3-135">Feature</span></span></th>
<th align="left"><span data-ttu-id="915b3-136">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="915b3-136">How it works</span></span></th>
<th align="left"><span data-ttu-id="915b3-137">Lösning</span><span class="sxs-lookup"><span data-stu-id="915b3-137">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-138">Framhävda resultat</span><span class="sxs-lookup"><span data-stu-id="915b3-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="915b3-139">Du kan skapa frågeregler med framhävda resultat på olika nivåer: för hela klientorganisationen, för en webbplatssamling eller för en webbplats.</span><span class="sxs-lookup"><span data-stu-id="915b3-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="915b3-140">Definiera framhävda resultat på innehavarnivå i en geomiljö så att sökresultatet framhävs till sökcentren på alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="915b3-141">Om du bara vill lyfta fram resultat i Sökcenter som finns på den geografiska platsen för webbplatssamlingen eller webbplatsen definierar du framhävda resultat på webbplatssamlingen eller webbplatsnivån.</span><span class="sxs-lookup"><span data-stu-id="915b3-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="915b3-142">Dessa resultat framhävs inte på andra geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="915b3-143">Om du inte behöver olika framhävda resultat per geoplats, till exempel olika regler för resor, rekommenderar vi att du definierar framhävda resultat på innehavarnivå.</span><span class="sxs-lookup"><span data-stu-id="915b3-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-144">Sök förfining</span><span class="sxs-lookup"><span data-stu-id="915b3-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="915b3-145">Sökningen returnerar förfiningar från alla geoplatser för en klientorganisation och aggregerar dem sedan.</span><span class="sxs-lookup"><span data-stu-id="915b3-145">Search returns refiners from all the geo locations of a tenant and then aggregates them.</span></span> <span data-ttu-id="915b3-146">Aggregeringen är en bästa ansträngning, vilket innebär att förfiningen kanske inte är 100 % korrekt.</span><span class="sxs-lookup"><span data-stu-id="915b3-146">The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate.</span></span> <span data-ttu-id="915b3-147">För de flesta sökdrivna scenarier är den här precisionen tillräcklig.</span><span class="sxs-lookup"><span data-stu-id="915b3-147">For most search-driven scenarios, this accuracy is sufficient.</span></span> 
</td>
<td align="left"><span data-ttu-id="915b3-148">För sökdrivna program som är beroende av förfiningens fullständighet bör du köra frågor för varje geoplats oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="915b3-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="915b3-149">Geosökning med flera har inte stöd för dynamisk bucketing för numeriska förfining.</span><span class="sxs-lookup"><span data-stu-id="915b3-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="915b3-150">Använd <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">parametern "Diskretize" för numeriska</a> förfining.</span><span class="sxs-lookup"><span data-stu-id="915b3-150">Use the <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-151">Dokument-IDs</span><span class="sxs-lookup"><span data-stu-id="915b3-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="915b3-152">Om du utvecklar ett sökdrivna program som är beroende av dokument-ID:t är dokument-ID:t i en geomiljö inte unika för flera geografiska platser, utan unika per geoplats.</span><span class="sxs-lookup"><span data-stu-id="915b3-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="915b3-153">Vi har lagt till en kolumn som identifierar geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="915b3-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="915b3-154">Använd den här kolumnen för att uppnå unikhet.</span><span class="sxs-lookup"><span data-stu-id="915b3-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="915b3-155">Den här kolumnen heter "GeoLocationSource".</span><span class="sxs-lookup"><span data-stu-id="915b3-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-156">Antal resultat</span><span class="sxs-lookup"><span data-stu-id="915b3-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="915b3-157">Sökresultatsidan visar kombinerade resultat från geoplatserna, men det går inte att ha mer än 500 resultat.</span><span class="sxs-lookup"><span data-stu-id="915b3-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-158">Hybridsökning</span><span class="sxs-lookup"><span data-stu-id="915b3-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="915b3-159">I en SharePoint miljö med <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint"></a>molnhybridsökning läggs lokalt innehåll till i Microsoft 365 för den centrala platsen.</span><span class="sxs-lookup"><span data-stu-id="915b3-159">In a hybrid SharePoint environment with <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="915b3-160">Vad stöds inte för sökning i en miljö med flera geoer?</span><span class="sxs-lookup"><span data-stu-id="915b3-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="915b3-161">Vissa av de sökfunktioner du kanske är van vid stöds inte i en miljö med flera geofunktioner.</span><span class="sxs-lookup"><span data-stu-id="915b3-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="915b3-162">Sökfunktion</span><span class="sxs-lookup"><span data-stu-id="915b3-162">Search feature</span></span></th>
<th align="left"><span data-ttu-id="915b3-163">Obs!</span><span class="sxs-lookup"><span data-stu-id="915b3-163">Note</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-164">Endast appautentisering</span><span class="sxs-lookup"><span data-stu-id="915b3-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="915b3-165">Endast programautentisering (behörighet från tjänster) stöds inte i Multi-Geo-sökning.</span><span class="sxs-lookup"><span data-stu-id="915b3-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-166">Gäster</span><span class="sxs-lookup"><span data-stu-id="915b3-166">Guests</span></span></td>
<td align="left"><span data-ttu-id="915b3-167">Gäster får bara resultat från den geoplats de söker från.</span><span class="sxs-lookup"><span data-stu-id="915b3-167">Guests only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="915b3-168">Hur fungerar sökning i en geomiljö med flera sökverktyg?</span><span class="sxs-lookup"><span data-stu-id="915b3-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="915b3-169">Alla sökklienter använder befintliga REST-API:SharePoint för sökning för att interagera med sökindexen.</span><span class="sxs-lookup"><span data-stu-id="915b3-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Diagram som visar SharePoint REST-API:er för sökning interagerar med sökindexen](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="915b3-171">En sökklient anropar SÖK REST-slutpunkten med frågeegenskapen EnableMultiGeoSearch= true.</span><span class="sxs-lookup"><span data-stu-id="915b3-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="915b3-172">Frågan skickas till alla geoplatser i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="915b3-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="915b3-173">Sökresultat från varje geoplats sammanfogas och rangordnas.</span><span class="sxs-lookup"><span data-stu-id="915b3-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="915b3-174">Klienten får enhetliga sökresultat.</span><span class="sxs-lookup"><span data-stu-id="915b3-174">The client gets unified search results.</span></span>

<span data-ttu-id="915b3-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Observera att vi inte slår samman sökresultaten förrän vi har fått resultat från alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="915b3-176">Det innebär att flera geosökningar har ytterligare fördröjning jämfört med sökningar i en miljö med bara en geoplats.</span><span class="sxs-lookup"><span data-stu-id="915b3-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="915b3-177">Hämta ett sökcenter för att visa resultat från alla geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="915b3-178">Varje sökcenter har flera lodräta och du måste konfigurera varje lodrätt individuellt.</span><span class="sxs-lookup"><span data-stu-id="915b3-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="915b3-179">Se till att du utför de här stegen med ett konto som har behörighet att redigera sökresultatsidan och webbdelen Sökresultat.</span><span class="sxs-lookup"><span data-stu-id="915b3-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="915b3-180">Gå till sidan med sökresultat (se [listan över](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) sökresultatsidor)</span><span class="sxs-lookup"><span data-stu-id="915b3-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="915b3-181">Markera den lodräta för att konfigurera, **Inställningar** kugghjulsikonen i det övre högra hörnet och klicka sedan på **Redigera sida.**</span><span class="sxs-lookup"><span data-stu-id="915b3-181">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**.</span></span> <span data-ttu-id="915b3-182">Sidan med sökresultat öppnas i redigeringsläge.</span><span class="sxs-lookup"><span data-stu-id="915b3-182">The search results page opens in Edit mode.</span></span>

   ![Redigera sidmarkering i Inställningar](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="915b3-184">I webbdelen Sökresultat flyttar du pekaren till det övre högra hörnet av webbdelen, klickar på pilen och klickar sedan på Redigera **webbdel** på menyn.</span><span class="sxs-lookup"><span data-stu-id="915b3-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="915b3-185">Verktygsfönstret för webbdelen Sökresultat öppnas under menyfliksområdet längst upp till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="915b3-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Redigera webbdelsval](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="915b3-187">I verktygsfönstret Webbdel, i **avsnittet Inställningar,** **under** Inställningar för resultatkontroll väljer du Visa **multi georesultat** för att få webbdelen Sökresultat för att visa resultat från alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="915b3-188">Klicka **på OK** för att spara ändringen och stänga verktygsfönstret Webbdel.</span><span class="sxs-lookup"><span data-stu-id="915b3-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="915b3-189">Kontrollera ändringarna i webbdelen Sökresultat genom att klicka **på Checka in** på fliken Sida i huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="915b3-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="915b3-190">Publicera ändringarna med hjälp av länken som finns i anteckningen högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="915b3-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="915b3-191">Hämta anpassade sökprogram för att visa resultat från alla eller vissa geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="915b3-192">Anpassade sökprogram får resultat från alla, eller vissa, geoplatser genom att ange frågeparametrar med begäran till SharePoint REST API.</span><span class="sxs-lookup"><span data-stu-id="915b3-192">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API.</span></span> <span data-ttu-id="915b3-193">Beroende på frågeparametrarna är frågan borta från alla geoplatser eller till vissa geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-193">Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations.</span></span> <span data-ttu-id="915b3-194">Om du till exempel bara behöver söka efter relevant information på en delmängd av geoplatserna kan du hålla koll på endast dessa.</span><span class="sxs-lookup"><span data-stu-id="915b3-194">For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these.</span></span> <span data-ttu-id="915b3-195">Om begäran lyckas returnerar SharePoint REST API svarsdata.</span><span class="sxs-lookup"><span data-stu-id="915b3-195">If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="915b3-196">Krav</span><span class="sxs-lookup"><span data-stu-id="915b3-196">Requirement</span></span>

<span data-ttu-id="915b3-197">För varje geoplats måste du säkerställa att alla användare  i organisationen har beviljats läsbehörighetsnivå för rotwebbplatsen (till exempel contoso **APAC**.sharepoint.com/ och contoso **EU**.sharepoint.com/).</span><span class="sxs-lookup"><span data-stu-id="915b3-197">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/).</span></span> <span data-ttu-id="915b3-198">[Läs mer om behörigheter.](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848)</span><span class="sxs-lookup"><span data-stu-id="915b3-198">[Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="915b3-199">Frågeparametrar</span><span class="sxs-lookup"><span data-stu-id="915b3-199">Query parameters</span></span>

<span data-ttu-id="915b3-200">EnableMultiGeoSearch – Det här är ett booleskt värde som anger om frågan ska rensas mot index för andra geoplatser för den geoklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="915b3-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="915b3-201">Sätt det på **sant** för att skapa en bra fråga; **false** to not fan out the query.</span><span class="sxs-lookup"><span data-stu-id="915b3-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="915b3-202">Om du inte tar med den här parametern är standardvärdet falskt **,** förutom när du ringer ett REST API-anrop mot en webbplats som använder sökcentermallen för företag, är standardvärdet **sant.**</span><span class="sxs-lookup"><span data-stu-id="915b3-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="915b3-203">Om du använder parametern i en miljö som inte innehåller flera geovärden ignoreras parametern.</span><span class="sxs-lookup"><span data-stu-id="915b3-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="915b3-204">ClientType – det här är en sträng.</span><span class="sxs-lookup"><span data-stu-id="915b3-204">ClientType - This is a string.</span></span> <span data-ttu-id="915b3-205">Ange ett unikt klientnamn för varje sökprogram.</span><span class="sxs-lookup"><span data-stu-id="915b3-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="915b3-206">Om du inte tar med den här parametern är frågan inte borta från andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="915b3-207">MultiGeoSearchConfiguration – Det här är en valfri lista över vilka geoplatser i multi-geoklientorganisationen som du kan ta frågan till när **EnableMultiGeoSearch** är **sant.**</span><span class="sxs-lookup"><span data-stu-id="915b3-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="915b3-208">Om du inte tar med den här parametern eller lämnar den tom kommer frågan att visas för alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="915b3-209">För varje geoplats anger du följande objekt i JSON-format:</span><span class="sxs-lookup"><span data-stu-id="915b3-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="915b3-210">Objekt</span><span class="sxs-lookup"><span data-stu-id="915b3-210">Item</span></span></th>
<th align="left"><span data-ttu-id="915b3-211">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="915b3-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="915b3-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="915b3-213">Geoplatsen, till exempel NAM.</span><span class="sxs-lookup"><span data-stu-id="915b3-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="915b3-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="915b3-215">Slutpunkten som du vill ansluta till, till exempel https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="915b3-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="915b3-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="915b3-217">GUID för resultatkällan, till exempel B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="915b3-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="915b3-218">Om du utelämnar DataLocation eller EndPoint, eller om en DataLocation dupliceras, misslyckas begäran.</span><span class="sxs-lookup"><span data-stu-id="915b3-218">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails.</span></span> <span data-ttu-id="915b3-219">[Du kan få information om slutpunkten för en klientorganisations geografiska platser med hjälp av Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="915b3-219">[You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="915b3-220">Svarsdata</span><span class="sxs-lookup"><span data-stu-id="915b3-220">Response data</span></span>

<span data-ttu-id="915b3-221">MultiGeoSearchStatus – Det här är en egenskap som SharePoint sök-API returnerar som svar på en begäran.</span><span class="sxs-lookup"><span data-stu-id="915b3-221">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request.</span></span> <span data-ttu-id="915b3-222">Värdet för egenskapen är en sträng och ger följande information om de resultat som sök-API:t SharePoint returnerar:</span><span class="sxs-lookup"><span data-stu-id="915b3-222">The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="915b3-223">Värde</span><span class="sxs-lookup"><span data-stu-id="915b3-223">Value</span></span></th>
<th align="left"><span data-ttu-id="915b3-224">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="915b3-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-225">Fullständig</span><span class="sxs-lookup"><span data-stu-id="915b3-225">Full</span></span></td>
<td align="left"><span data-ttu-id="915b3-226">Fullständiga resultat <strong>från</strong> alla geoplatser.</span><span class="sxs-lookup"><span data-stu-id="915b3-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="915b3-227">Delvis</span><span class="sxs-lookup"><span data-stu-id="915b3-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="915b3-228">Ofullständiga resultat från en eller flera geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="915b3-228">Partial results from one or more geo locations.</span></span> <span data-ttu-id="915b3-229">Resultatet är ofullständigt på grund av ett tillfälligt fel.</span><span class="sxs-lookup"><span data-stu-id="915b3-229">The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="915b3-230">Fråga med REST-tjänsten</span><span class="sxs-lookup"><span data-stu-id="915b3-230">Query using the REST service</span></span>

<span data-ttu-id="915b3-231">Med en HÄMTA-begäran anger du frågeparametrar i URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="915b3-231">With a GET request, you specify the query parameters in the URL.</span></span> <span data-ttu-id="915b3-232">Med en POST-begäran skickar du frågeparametrarna i brödtexten i JavaScript Object Notation-formatet (JSON).</span><span class="sxs-lookup"><span data-stu-id="915b3-232">With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="915b3-233">Frågerubriker</span><span class="sxs-lookup"><span data-stu-id="915b3-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="915b3-234">Namn</span><span class="sxs-lookup"><span data-stu-id="915b3-234">Name</span></span></th>
<th align="left"><span data-ttu-id="915b3-235">Värde</span><span class="sxs-lookup"><span data-stu-id="915b3-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="915b3-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="915b3-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="915b3-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="915b3-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="915b3-238">Exempel på HÄMTA-begäran som är **bortskad från alla** geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-238">Sample GET request that's fanned out to **all** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'
```

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="915b3-239">Exempel på HÄMTA begäran att ta del **av en** del geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-239">Sample GET request to fan out to **some** geo locations</span></span>

```http
https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'
```

> [!NOTE]
> <span data-ttu-id="915b3-240">Kommatecken och kolon i listan över geografiska platser för egenskapen MultiGeoSearchConfiguration föregås av **omstöpen** snedstreck.</span><span class="sxs-lookup"><span data-stu-id="915b3-240">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="915b3-241">Det beror på att HÄMTA-begäranden använder kolon för att separera egenskaper och kommatecken för att separera egenskapsargument.</span><span class="sxs-lookup"><span data-stu-id="915b3-241">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="915b3-242">Utan om baksnedstrecket som ett escape-tecken tolkas egenskapen MultiGeoSearchConfiguration felaktigt.</span><span class="sxs-lookup"><span data-stu-id="915b3-242">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="915b3-243">Exempel på EFTER-begäran som är **bortskad från alla** geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-243">Sample POST request that's fanned out to **all** geo locations</span></span>

```http
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

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="915b3-244">Exempel på INLÄGG-begäran som är **bortskad från vissa** geografiska platser</span><span class="sxs-lookup"><span data-stu-id="915b3-244">Sample POST request that's fanned out to **some** geo locations</span></span>

```http
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

### <a name="query-using-csom"></a><span data-ttu-id="915b3-245">Fråga med CSOM</span><span class="sxs-lookup"><span data-stu-id="915b3-245">Query using CSOM</span></span>

<span data-ttu-id="915b3-246">Här är ett exempel på en CSOM-fråga som är borta **från alla** geoplatser:</span><span class="sxs-lookup"><span data-stu-id="915b3-246">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```CSOM
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery.Properties["EnableMultiGeoSearch"] = true;
```
