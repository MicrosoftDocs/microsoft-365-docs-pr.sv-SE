---
title: Navigerings alternativ för SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: Den här artikeln beskriver navigerings alternativ webbplatser med SharePoint-publicering aktiverat i SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696688"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="99af9-103">Navigerings alternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99af9-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="99af9-104">Den här artikeln beskriver navigerings alternativ webbplatser med SharePoint-publicering aktiverat i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="99af9-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="99af9-105">Valet och konfigurationen av navigeringen påverkar markant prestanda och skalbarhet för webbplatser i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="99af9-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="99af9-106">Mallen för publicerings webbplatsen för SharePoint bör bara användas om den är nödvändig för en centraliserad Portal och publicerings funktionen bör endast aktive ras på specifika webbplatser och bara när det är absolut obligatoriskt som kan påverka prestanda när den används felaktigt.</span><span class="sxs-lookup"><span data-stu-id="99af9-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="99af9-107">Om du använder moderna navigerings alternativ för SharePoint, till exempel menyn megapixlar, navigerings navigering eller navigering, gäller inte den här artikeln för din webbplats.</span><span class="sxs-lookup"><span data-stu-id="99af9-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="99af9-108">Moderna SharePoint-webbplatserna har en mer förplattad Webbplatshierarki och en nav-och-eker-modell.</span><span class="sxs-lookup"><span data-stu-id="99af9-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="99af9-109">Detta gör att många scenarier kan uppfyllas som inte kräver användning av SharePoint-publiceringen.</span><span class="sxs-lookup"><span data-stu-id="99af9-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="99af9-110">Översikt över navigerings alternativ</span><span class="sxs-lookup"><span data-stu-id="99af9-110">Overview of navigation options</span></span>

<span data-ttu-id="99af9-111">Konfiguration av navigerings leverantör kan påverka prestanda avsevärt för hela webbplatsen och det är viktigt att tänka på att välja en navigations leverantör och en konfiguration som kan anpassas efter kraven på en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="99af9-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="99af9-112">Det finns två avsluts bara navigerings leverantörer och anpassade navigerings implementeringar.</span><span class="sxs-lookup"><span data-stu-id="99af9-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="99af9-113">Det första alternativet, [**strukturell navigering**](#using-structural-navigation-in-sharepoint-online), är det rekommenderade navigerings alternativet i SharePoint Online för klassiska SharePoint-webbplatser **om du aktiverar cachelagring av strukturell navigering för webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="99af9-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="99af9-114">Den här navigerings leverantören visar navigerings alternativen under den aktuella webbplatsen, och även på den aktuella webbplatsen och dess objekt.</span><span class="sxs-lookup"><span data-stu-id="99af9-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="99af9-115">Det ger ytterligare funktioner som säkerhets trimning och uppräkning av webbplats strukturer.</span><span class="sxs-lookup"><span data-stu-id="99af9-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="99af9-116">Om cachelagring är inaktiverat påverkar detta prestanda och skalbarhet negativt och kan komma att begränsas.</span><span class="sxs-lookup"><span data-stu-id="99af9-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="99af9-117">Det andra alternativet, [**hanterad navigering (metadata)**](#using-managed-navigation-and-metadata-in-sharepoint-online), representerar navigerings objekt med en term uppsättning för hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="99af9-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="99af9-118">Vi rekommenderar att säkerhets trimning är inaktiverat om det inte behövs.</span><span class="sxs-lookup"><span data-stu-id="99af9-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="99af9-119">Säkerhets trimning är aktiverat som standard för den här navigerings leverantören; många webbplatser kräver emellertid inte att säkerhets trimning används eftersom navigerings element ofta är konsekventa för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99af9-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="99af9-120">Den rekommenderade konfigurationen för att inaktivera säkerhets optimering kräver inte att den här navigerings leverantören räknar upp webbplats strukturen och är mycket skalbar med acceptabel prestanda.</span><span class="sxs-lookup"><span data-stu-id="99af9-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="99af9-121">Utöver de navigerings leverantörer som inte är i kartongen har många kunder lyckats implementera alternativa anpassade navigerings implementeringar.</span><span class="sxs-lookup"><span data-stu-id="99af9-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="99af9-122">Se [Sök drivna klient skript](#using-search-driven-client-side-scripting) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="99af9-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="99af9-123">För-och nack delar av navigerings alternativ i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99af9-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="99af9-124">I följande tabell sammanfattas de olika alternativen för för-och nack delar.</span><span class="sxs-lookup"><span data-stu-id="99af9-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="99af9-125">Strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="99af9-125">Structural navigation</span></span>  |<span data-ttu-id="99af9-126">Hanterad navigering</span><span class="sxs-lookup"><span data-stu-id="99af9-126">Managed navigation</span></span>  |<span data-ttu-id="99af9-127">Sök drivna navigering</span><span class="sxs-lookup"><span data-stu-id="99af9-127">Search-driven navigation</span></span>  |<span data-ttu-id="99af9-128">Anpassad navigerings leverantör</span><span class="sxs-lookup"><span data-stu-id="99af9-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="99af9-129">Tekniker</span><span class="sxs-lookup"><span data-stu-id="99af9-129">Pros:</span></span><br/><br/><span data-ttu-id="99af9-130">Lätt att underhålla</span><span class="sxs-lookup"><span data-stu-id="99af9-130">Easy to maintain</span></span><br/><span data-ttu-id="99af9-131">Säkerhetstrimmer</span><span class="sxs-lookup"><span data-stu-id="99af9-131">Security trimmed</span></span><br/><span data-ttu-id="99af9-132">Uppdateringar sker automatiskt inom 24 timmar när innehållet ändras</span><span class="sxs-lookup"><span data-stu-id="99af9-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="99af9-133">Tekniker</span><span class="sxs-lookup"><span data-stu-id="99af9-133">Pros:</span></span><br/><br/><span data-ttu-id="99af9-134">Lätt att underhålla</span><span class="sxs-lookup"><span data-stu-id="99af9-134">Easy to maintain</span></span><br/>|<span data-ttu-id="99af9-135">Tekniker</span><span class="sxs-lookup"><span data-stu-id="99af9-135">Pros:</span></span><br/><br/><span data-ttu-id="99af9-136">Säkerhetstrimmer</span><span class="sxs-lookup"><span data-stu-id="99af9-136">Security trimmed</span></span><br/><span data-ttu-id="99af9-137">Automatisk uppdatering när webbplatser läggs till</span><span class="sxs-lookup"><span data-stu-id="99af9-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="99af9-138">Snabb inläsnings tid och lokalt cachelagrad navigerings struktur</span><span class="sxs-lookup"><span data-stu-id="99af9-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="99af9-139">Tekniker</span><span class="sxs-lookup"><span data-stu-id="99af9-139">Pros:</span></span><br/><br/><span data-ttu-id="99af9-140">Det finns fler tillgängliga alternativ</span><span class="sxs-lookup"><span data-stu-id="99af9-140">Wider choice of options available</span></span><br/><span data-ttu-id="99af9-141">Snabb laddning när cachelagring används korrekt</span><span class="sxs-lookup"><span data-stu-id="99af9-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="99af9-142">Många alternativ fungerar bra med sidlayouten</span><span class="sxs-lookup"><span data-stu-id="99af9-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="99af9-143">Nack</span><span class="sxs-lookup"><span data-stu-id="99af9-143">Cons:</span></span><br/><br/><span data-ttu-id="99af9-144">**Påverkar prestanda om cachelagring är inaktiverat**</span><span class="sxs-lookup"><span data-stu-id="99af9-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="99af9-145">Föremål för begränsning</span><span class="sxs-lookup"><span data-stu-id="99af9-145">Subject to throttling</span></span><br/>|<span data-ttu-id="99af9-146">Nack</span><span class="sxs-lookup"><span data-stu-id="99af9-146">Cons:</span></span><br/><br/><span data-ttu-id="99af9-147">Uppdateras inte automatiskt för att spegla webbplats strukturen</span><span class="sxs-lookup"><span data-stu-id="99af9-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="99af9-148">**Påverkar prestanda om säkerhets trimning är aktiverat** eller när navigerings strukturen är komplex</span><span class="sxs-lookup"><span data-stu-id="99af9-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="99af9-149">Nack</span><span class="sxs-lookup"><span data-stu-id="99af9-149">Cons:</span></span><br/><br/><span data-ttu-id="99af9-150">Ingen möjlighet att enkelt ordna webbplatser</span><span class="sxs-lookup"><span data-stu-id="99af9-150">No ability to easily order sites</span></span><br/><span data-ttu-id="99af9-151">Kräver anpassning av huvud sidan (tekniska kunskaper krävs)</span><span class="sxs-lookup"><span data-stu-id="99af9-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="99af9-152">Nack</span><span class="sxs-lookup"><span data-stu-id="99af9-152">Cons:</span></span><br/><br/><span data-ttu-id="99af9-153">Anpassad utveckling krävs</span><span class="sxs-lookup"><span data-stu-id="99af9-153">Custom development is required</span></span><br/><span data-ttu-id="99af9-154">Extern data källa/cache lagras, t. ex.</span><span class="sxs-lookup"><span data-stu-id="99af9-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="99af9-155">Det lämpligaste alternativet för webbplatsen beror på dina webbplats krav och din tekniska funktion.</span><span class="sxs-lookup"><span data-stu-id="99af9-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="99af9-156">Om du vill använda en lättanvänd navigerings leverantör som uppdateras automatiskt när innehållet ändras, är strukturell navigering [med cachelagring aktiverat](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) ett bra alternativ.</span><span class="sxs-lookup"><span data-stu-id="99af9-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="99af9-157">Genom att använda samma princip som moderna SharePoint-webbplatser genom att förenkla den övergripande webbplatsens struktur till en Flatter, icke hierarkisk struktur förbättras prestanda och enklare att flytta till moderna SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="99af9-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="99af9-158">Vad det innebär är att i stället för att ha en samlad webbplats samling med hundratals webbplatser (under webbplatser), är en bättre metod att få många webbplats samlingar med mycket få under webbplatser (under webbplatser).</span><span class="sxs-lookup"><span data-stu-id="99af9-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="99af9-159">Analysera navigerings prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99af9-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="99af9-160">[Verktyget för nätverksdiagnostik för SharePoint](https://aka.ms/perftool) är ett webb läsar tillägg för webbläsarna Microsoft Edge och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor.</span><span class="sxs-lookup"><span data-stu-id="99af9-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="99af9-161">Det här verktyget fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.</span><span class="sxs-lookup"><span data-stu-id="99af9-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="99af9-162">Verktyget genererar en rapport för varje sida som visar hur sidan fungerar mot en fördefinierad uppsättning regler och visar detaljerad information när resultaten för ett test ligger utanför bas linjen.</span><span class="sxs-lookup"><span data-stu-id="99af9-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="99af9-163">SharePoint Online-administratörer och designer kan använda verktyget för att felsöka prestanda problem för att säkerställa att nya sidor optimeras före publiceringen.</span><span class="sxs-lookup"><span data-stu-id="99af9-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="99af9-164">**SPRequestDuration** är i synnerhet den tid det tar för SharePoint att bearbeta sidan.</span><span class="sxs-lookup"><span data-stu-id="99af9-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="99af9-165">Omfattande navigering (till exempel sidor i navigering), komplexa webbplatserna och andra inställningar för konfiguration och topologi kan avsevärt bidra till längre varaktigheter.</span><span class="sxs-lookup"><span data-stu-id="99af9-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="99af9-166">Använda strukturell navigering i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99af9-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="99af9-167">Det här är den här navigerings navigeringen som används som standard och är den enklaste lösningen.</span><span class="sxs-lookup"><span data-stu-id="99af9-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="99af9-168">Ingen anpassning behövs och en icke-teknisk användare kan också enkelt lägga till objekt, dölja objekt och hantera navigeringen från inställnings sidan.</span><span class="sxs-lookup"><span data-stu-id="99af9-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="99af9-169">Vi rekommenderar att du [aktiverar cachelagring](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), annars är det dyrt att kompromissa.</span><span class="sxs-lookup"><span data-stu-id="99af9-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="99af9-170">Så här implementerar du cachelagring av strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="99af9-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="99af9-171">Under **Site Settings**  >  **Look and Feel**  >  **navigerings**-och känsla kan du kontrol lera om strukturell navigering är markerat för antingen global navigering eller aktuell navigering.</span><span class="sxs-lookup"><span data-stu-id="99af9-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="99af9-172">Att välja **Visa sidor** påverkar prestanda negativt.</span><span class="sxs-lookup"><span data-stu-id="99af9-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Strukturell navigering med Visa under webbplatser markerade](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="99af9-174">Cachelagring kan aktive ras eller avaktiveras på webbplats samlings nivå och på webbplats nivå och är aktiverat för båda som standard.</span><span class="sxs-lookup"><span data-stu-id="99af9-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="99af9-175">Aktivera på webbplats samlings nivå genom **att gå till**webbplats samlingens webbplats samlings  >  **Site Collection Administration**  >  **navigering**och markera kryss rutan för att **Aktivera cachelagring**.</span><span class="sxs-lookup"><span data-stu-id="99af9-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Aktivera cachelagring på webbplats nivå](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="99af9-177">Om du vill aktivera på webbplats nivå **Site Settings**  >  markerar du kryss rutan för **att aktivera cachelagring**under**navigering**för webbplats inställningar.</span><span class="sxs-lookup"><span data-stu-id="99af9-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Aktivera cachelagring på webbplats nivå](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="99af9-179">Använda hanterad navigering och metadata i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99af9-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="99af9-180">Hanterad navigering är ett annat icke-skrivskyddat alternativ som du kan använda för att återskapa de flesta av samma funktioner som strukturell navigering.</span><span class="sxs-lookup"><span data-stu-id="99af9-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="99af9-181">Hanterade metadata kan konfigureras för att få säkerhets trimning aktive rad eller inaktive rad.</span><span class="sxs-lookup"><span data-stu-id="99af9-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="99af9-182">När du har konfigurerat med säkerhets trimning inaktive rad är hanterad navigering ganska effektiv när du läser in alla navigations länkar med ett konstant antal Server samtal.</span><span class="sxs-lookup"><span data-stu-id="99af9-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="99af9-183">Genom att aktivera säkerhets putsning kan du göra en del av prestanda fördelarna med hanterad navigering.</span><span class="sxs-lookup"><span data-stu-id="99af9-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="99af9-184">Om du behöver aktivera säkerhets trimning rekommenderar vi att du:</span><span class="sxs-lookup"><span data-stu-id="99af9-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="99af9-185">Uppdatera alla egna webb adress länkar till enkla länkar</span><span class="sxs-lookup"><span data-stu-id="99af9-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="99af9-186">Lägga till begärda säkerhetstrimmade noder som egna URL: er</span><span class="sxs-lookup"><span data-stu-id="99af9-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="99af9-187">Begränsa antalet navigerings objekt till högst 100 och högst 3 nivåer djupt</span><span class="sxs-lookup"><span data-stu-id="99af9-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="99af9-188">Många webbplatser kräver inte säkerhetstrimning eftersom navigerings strukturen ofta är konsekvent för alla användare på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="99af9-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="99af9-189">Om säkerhets trimning är inaktiverat och en länk läggs till för navigering som inte alla användare har åtkomst till, kommer länken ändå att visas men kommer att leda till ett meddelande om nekad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="99af9-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="99af9-190">Det finns ingen risk för oavsiktlig åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="99af9-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="99af9-191">Implementera hanterad navigering och resultaten</span><span class="sxs-lookup"><span data-stu-id="99af9-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="99af9-192">Det finns flera artiklar om docs.microsoft.com information om hanterad navigering.</span><span class="sxs-lookup"><span data-stu-id="99af9-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="99af9-193">Se [Översikt över hanterad navigering i SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span><span class="sxs-lookup"><span data-stu-id="99af9-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="99af9-194">För att implementera hanterad navigering kan du ange villkor med URL: er som motsvarar webbplatsens navigerings struktur.</span><span class="sxs-lookup"><span data-stu-id="99af9-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="99af9-195">Hanterad navigering kan till och med ses manuellt för att ersätta strukturell navigering i många fall.</span><span class="sxs-lookup"><span data-stu-id="99af9-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="99af9-196">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="99af9-196">For example:</span></span>

![Webbplats struktur för SharePoint Online](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="99af9-198">)</span><span class="sxs-lookup"><span data-stu-id="99af9-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="99af9-199">Använda Sök drivna klient skript</span><span class="sxs-lookup"><span data-stu-id="99af9-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="99af9-200">En vanlig klass med anpassade navigerings implementeringar omfattar klient åter givnings mönster som lagrar en lokal cache med navigeringsnoder.</span><span class="sxs-lookup"><span data-stu-id="99af9-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="99af9-201">Dessa navigerings leverantörer har många viktiga fördelar:</span><span class="sxs-lookup"><span data-stu-id="99af9-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="99af9-202">De fungerar i allmänhet bra med sid design.</span><span class="sxs-lookup"><span data-stu-id="99af9-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="99af9-203">De är oerhört skalbara och utförda eftersom de kan återges utan resurs kostnad (och uppdateras i bakgrunden efter en tids gräns).</span><span class="sxs-lookup"><span data-stu-id="99af9-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="99af9-204">Dessa navigerings leverantörer kan hämta navigerings data med olika strategier, från enkla statiska konfigurationer till olika dynamiska data leverantörer.</span><span class="sxs-lookup"><span data-stu-id="99af9-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="99af9-205">Ett exempel på en DataProvider är att använda en **sökstyrd navigering**som gör det enklare att räkna upp navigeringsnoder och hantera säkerhets optimering.</span><span class="sxs-lookup"><span data-stu-id="99af9-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="99af9-206">Det finns andra populära alternativ för att bygga **anpassade navigerings leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="99af9-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="99af9-207">För mer information om hur du skapar en anpassad navigerings leverantör kan du läsa mer i [navigerings lösningarna för SharePoint online-portaler](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) .</span><span class="sxs-lookup"><span data-stu-id="99af9-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="99af9-208">Med Sök kan du använda de index som är inbyggda i bakgrunden med kontinuerlig crawlning.</span><span class="sxs-lookup"><span data-stu-id="99af9-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="99af9-209">Sök resultaten hämtas från Sök indexet och resultaten blir säkerhetstrimmade.</span><span class="sxs-lookup"><span data-stu-id="99af9-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="99af9-210">Detta är vanligt vis snabbare än ej obligatoriska navigations leverantörer när säkerhets trimning krävs.</span><span class="sxs-lookup"><span data-stu-id="99af9-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="99af9-211">Genom att använda Sök funktionen för strukturell navigering, särskilt om du har en komplex webbplats struktur, blir det betydligt snabbare att läsa upp sidan.</span><span class="sxs-lookup"><span data-stu-id="99af9-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="99af9-212">Den största fördelen med detta via hanterad navigering är att du har nytta av säkerhets trimning.</span><span class="sxs-lookup"><span data-stu-id="99af9-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="99af9-213">Den här metoden handlar om att skapa en anpassad huvud sida och ersätta den avslutande navigerings koden med anpassade HTML.</span><span class="sxs-lookup"><span data-stu-id="99af9-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="99af9-214">Följ den här proceduren som beskrivs i följande exempel för att ersätta navigerings koden i filen `seattle.html` .</span><span class="sxs-lookup"><span data-stu-id="99af9-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="99af9-215">I det här exemplet öppnar du `seattle.html` filen och ersätter hela elementet `id="DeltaTopNavigation"` med anpassad HTML-kod.</span><span class="sxs-lookup"><span data-stu-id="99af9-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="99af9-216">Exempel: ersätta den föråldrade navigerings koden på en huvud sida</span><span class="sxs-lookup"><span data-stu-id="99af9-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="99af9-217">Gå till sidan webbplats inställningar.</span><span class="sxs-lookup"><span data-stu-id="99af9-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="99af9-218">Öppna huvud sid galleriet genom att klicka på **huvud sidor**.</span><span class="sxs-lookup"><span data-stu-id="99af9-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="99af9-219">Härifrån kan du navigera i biblioteket och ladda ned filen `seattle.master` .</span><span class="sxs-lookup"><span data-stu-id="99af9-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="99af9-220">Redigera koden med en text redigerare och ta bort kod blocket i följande skärm bild.</span><span class="sxs-lookup"><span data-stu-id="99af9-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Ta bort det kodblock som visas](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="99af9-222">Ta bort koden mellan `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` taggarna och och ersätt den med följande kod avsnitt:</span><span class="sxs-lookup"><span data-stu-id="99af9-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="99af9-223">Ersätt URL-adressen i början av bildens fäst punkt med en länk till en inläsnings bild i webbplats samlingen.</span><span class="sxs-lookup"><span data-stu-id="99af9-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="99af9-224">När du har gjort ändringarna byter du namn på filen och överför den sedan till galleriet för huvud sidor.</span><span class="sxs-lookup"><span data-stu-id="99af9-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="99af9-225">Då skapas en ny huvud fil.</span><span class="sxs-lookup"><span data-stu-id="99af9-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="99af9-226">Den här HTML-koden är den bas märkning som kommer att fyllas i med Sök resultaten från JavaScript-koden.</span><span class="sxs-lookup"><span data-stu-id="99af9-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="99af9-227">Du måste redigera koden för att ändra värdet för Variansens rot = "URL-adress för webbplats samling" enligt följande kod utdrag:</span><span class="sxs-lookup"><span data-stu-id="99af9-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="99af9-228">Resultatet tilldelas till själv. Arrays-matrisen och en hierarki är inbyggd av objekten genom att linq.js tilldelar utdata till en matris själv. hierarki.</span><span class="sxs-lookup"><span data-stu-id="99af9-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="99af9-229">Den här matrisen är det objekt som är bundet till HTML.</span><span class="sxs-lookup"><span data-stu-id="99af9-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="99af9-230">Det här görs i funktionen toggleView () genom att skicka det Self-objektet till funktionen ko. applyBinding ().</span><span class="sxs-lookup"><span data-stu-id="99af9-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="99af9-231">Då blir hierarki-matrisen bunden till följande HTML:</span><span class="sxs-lookup"><span data-stu-id="99af9-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="99af9-232">Händelse hanterarna för `mouseenter` och `mouseexit` läggs till i navigering på översta nivån för att hantera de nedrullningsbara menyn under webbplatser som görs i `addEventsToElements()` funktionen.</span><span class="sxs-lookup"><span data-stu-id="99af9-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="99af9-233">I vårt komplexa navigerings exempel visas en ny sid belastning utan lokal cachelagring för att visa hur lång tid det tog för servern att få ett liknande resultat som den hanterade navigeringen.</span><span class="sxs-lookup"><span data-stu-id="99af9-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="99af9-234">Om JavaScript-filen...</span><span class="sxs-lookup"><span data-stu-id="99af9-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="99af9-235">Om du använder anpassat Java Script kontrollerar du att offentlig CDN är aktiverat och att filen är på en CDN-plats.</span><span class="sxs-lookup"><span data-stu-id="99af9-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="99af9-236">Hela JavaScript-filen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="99af9-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="99af9-237">Om du vill summera koden ovan i `jQuery $(document).ready` funktionen är en `viewModel object` skapad och sedan `loadNavigationNodes()` funktionen för det objektet.</span><span class="sxs-lookup"><span data-stu-id="99af9-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="99af9-238">Med den här funktionen laddas antingen den tidigare skapade navigerings hierarkin i den lokala HTML5-lagringen i klient webbläsaren eller så anropas funktionen `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="99af9-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="99af9-239">`QueryRemoteInterface()` skapar en begäran med `getRequest()` funktionen med den frågeparameter som definierats tidigare i skriptet och returnerar sedan data från servern.</span><span class="sxs-lookup"><span data-stu-id="99af9-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="99af9-240">Dessa data är i stort sett en matris med alla webbplatser i webbplats samlingen som representerar data överförings objekt med olika egenskaper.</span><span class="sxs-lookup"><span data-stu-id="99af9-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="99af9-241">Dessa data parsas sedan till de tidigare definierade `SPO.Models.NavigationNode` objekten som används `Knockout.js` för att skapa observerbara egenskaper för data bindning till den HTML-kod som vi definierade tidigare.</span><span class="sxs-lookup"><span data-stu-id="99af9-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="99af9-242">Objekten placeras i en resultat mat ris.</span><span class="sxs-lookup"><span data-stu-id="99af9-242">The objects are then put into a results array.</span></span> <span data-ttu-id="99af9-243">Den här matrisen tolkas i JSON med blockering och lagras i den lokala webbläsarens lagrings utrymme för bättre prestanda på framtida sid inläsningar.</span><span class="sxs-lookup"><span data-stu-id="99af9-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="99af9-244">Fördelar med den här metoden</span><span class="sxs-lookup"><span data-stu-id="99af9-244">Benefits of this approach</span></span>

<span data-ttu-id="99af9-245">En stor fördel med [den här metoden](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) är att med hjälp av HTML5 lokal lagring sparas navigeringen lokalt för användaren nästa gång de läser in sidan.</span><span class="sxs-lookup"><span data-stu-id="99af9-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="99af9-246">Vi får viktiga förbättringar av prestandan genom att använda Sök-API: t för strukturell navigering. men det tar lite teknisk möjlighet att köra och anpassa den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="99af9-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="99af9-247">I [exemplet med implementeringen](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)ordnas webbplatserna på samma sätt som i den nedrullningsbara strukturell navigeringen. alfabetisk ordning.</span><span class="sxs-lookup"><span data-stu-id="99af9-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="99af9-248">Om du vill avvika från den här ordningen blir det mer komplicerat att utveckla och underhålla.</span><span class="sxs-lookup"><span data-stu-id="99af9-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="99af9-249">Dessutom kräver den här metoden att du avviker från huvud sidorna som stöds.</span><span class="sxs-lookup"><span data-stu-id="99af9-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="99af9-250">Om den anpassade huvud sidan inte är underordnad missar webbplatsen uppdateringar och förbättringar som Microsoft gör till huvud sidorna.</span><span class="sxs-lookup"><span data-stu-id="99af9-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="99af9-251">[Koden ovan](#about-the-javascript-file) har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="99af9-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="99af9-252">jQuery https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="99af9-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="99af9-253">KnockoutJS https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="99af9-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="99af9-254">Linq.js- https://linqjs.codeplex.com/ eller github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="99af9-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="99af9-255">Den aktuella versionen av LinqJS innehåller inte den ByHierarchy-metod som används i ovanstående kod och delar navigerings koden.</span><span class="sxs-lookup"><span data-stu-id="99af9-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="99af9-256">Lös det genom att lägga till följande metod i Linq.js-filen före raden `Flatten: function ()` .</span><span class="sxs-lookup"><span data-stu-id="99af9-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="99af9-257">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="99af9-257">Related topics</span></span>

[<span data-ttu-id="99af9-258">Översikt över hanterad navigering i SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="99af9-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="99af9-259">Cachelagring och prestanda för strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="99af9-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
