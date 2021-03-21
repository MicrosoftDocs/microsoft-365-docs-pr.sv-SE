---
title: Navigeringsalternativ för SharePoint Online
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
description: I den här artikeln beskrivs webbplatser med navigeringsalternativ där SharePoint-publicering är aktiverat i SharePoint Online.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923630"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="68db6-103">Navigeringsalternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68db6-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="68db6-104">I den här artikeln beskrivs webbplatser med navigeringsalternativ där SharePoint-publicering är aktiverat i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68db6-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="68db6-105">Valet och konfigurationen av navigeringen påverkar avsevärt prestanda och skalbarheten för webbplatser i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68db6-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="68db6-106">SharePoint-publiceringswebbplatsmallen bör endast användas om det behövs för en centraliserad portal, och publiceringsfunktionen ska endast aktiveras på vissa webbplatser och endast om det är absolut nödvändigt eftersom den kan påverka prestandan när den används felaktigt.</span><span class="sxs-lookup"><span data-stu-id="68db6-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="68db6-107">Om du använder moderna SharePoint-navigeringsalternativ som mega-meny, kaskadnavigering eller navnavigering gäller den här artikeln inte för din webbplats.</span><span class="sxs-lookup"><span data-stu-id="68db6-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="68db6-108">Moderna SharePoint-webbplatsarkitekturer utnyttjar en mer platt webbplatshierarki och en hub-and-ekmodell.</span><span class="sxs-lookup"><span data-stu-id="68db6-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="68db6-109">Detta möjliggör många scenarier som inte kräver användning av SharePoint-publiceringsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="68db6-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="68db6-110">Översikt över navigeringsalternativ</span><span class="sxs-lookup"><span data-stu-id="68db6-110">Overview of navigation options</span></span>

<span data-ttu-id="68db6-111">Konfiguration av navigeringsleverantör kan avsevärt påverka prestandan för hela webbplatsen, och noggrant måste beaktas för att välja en navigeringsleverantör och konfiguration som skalar effektivt för kraven på en SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="68db6-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="68db6-112">Det finns två in-of-box navigeringsleverantörer, samt anpassade implementeringar av navigering.</span><span class="sxs-lookup"><span data-stu-id="68db6-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="68db6-113">Det första alternativet, [**Strukturell navigering,**](#using-structural-navigation-in-sharepoint-online)är det rekommenderade navigeringsalternativet i SharePoint Online för klassiska Sharepoint-webbplatser, om du aktiverar cachelagring av strukturell navigering **för din webbplats.**</span><span class="sxs-lookup"><span data-stu-id="68db6-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="68db6-114">Den här navigeringsleverantören visar navigeringsobjekten nedanför den aktuella webbplatsen och, om du vill, den aktuella webbplatsen och dess objekt på samma plats.</span><span class="sxs-lookup"><span data-stu-id="68db6-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="68db6-115">Den innehåller ytterligare funktioner, till exempel säkerhets trimning och uppräkning av webbplatsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="68db6-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="68db6-116">Om cachelagring är inaktiverat påverkar det här prestanda och skalbarhet negativt och kan påverkas av begränsning.</span><span class="sxs-lookup"><span data-stu-id="68db6-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="68db6-117">Det andra alternativet, [**Hanterad (metadata)-navigering**](#using-managed-navigation-and-metadata-in-sharepoint-online), motsvarar navigeringsobjekt med hjälp av en termuppsättning med hanterade metadata.</span><span class="sxs-lookup"><span data-stu-id="68db6-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="68db6-118">Vi rekommenderar att säkerhets trimningen är inaktiverad om det inte krävs.</span><span class="sxs-lookup"><span data-stu-id="68db6-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="68db6-119">Säkerhets trimning är aktiverat som en inställning som är säker som standard för den här navigeringsleverantören. Men många webbplatser kräver inte säkerhets trimning eftersom navigeringselement ofta är konsekventa för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="68db6-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="68db6-120">Med den rekommenderade konfigurationen för att inaktivera säkerhets trimning behöver den här navigeringsleverantören inte räkna upp webbplatsstrukturen och är mycket skalbar med acceptabel prestanda.</span><span class="sxs-lookup"><span data-stu-id="68db6-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="68db6-121">Många kunder har implementerat alternativa anpassade navigeringsimplementeringar utöver de in alltid använda navigeringsleverantörerna.</span><span class="sxs-lookup"><span data-stu-id="68db6-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="68db6-122">Läs [Sökdrivna skript på klientsidan i](#using-search-driven-client-side-scripting) den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="68db6-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="68db6-123">Fördelar och nackdelar med navigeringsalternativ i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68db6-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="68db6-124">I följande tabell sammanfattas fördelar och nackdelar med varje alternativ.</span><span class="sxs-lookup"><span data-stu-id="68db6-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="68db6-125">Strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="68db6-125">Structural navigation</span></span>  |<span data-ttu-id="68db6-126">Hanterad navigering</span><span class="sxs-lookup"><span data-stu-id="68db6-126">Managed navigation</span></span>  |<span data-ttu-id="68db6-127">Sökdriven navigering</span><span class="sxs-lookup"><span data-stu-id="68db6-127">Search-driven navigation</span></span>  |<span data-ttu-id="68db6-128">Anpassad navigeringsleverantör</span><span class="sxs-lookup"><span data-stu-id="68db6-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="68db6-129">Fördelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-129">Pros:</span></span><br/><br/><span data-ttu-id="68db6-130">Enkel att underhålla</span><span class="sxs-lookup"><span data-stu-id="68db6-130">Easy to maintain</span></span><br/><span data-ttu-id="68db6-131">Säkerhets trimning</span><span class="sxs-lookup"><span data-stu-id="68db6-131">Security trimmed</span></span><br/><span data-ttu-id="68db6-132">Uppdateras automatiskt inom 24 timmar när innehållet ändras</span><span class="sxs-lookup"><span data-stu-id="68db6-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="68db6-133">Fördelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-133">Pros:</span></span><br/><br/><span data-ttu-id="68db6-134">Enkel att underhålla</span><span class="sxs-lookup"><span data-stu-id="68db6-134">Easy to maintain</span></span><br/>|<span data-ttu-id="68db6-135">Fördelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-135">Pros:</span></span><br/><br/><span data-ttu-id="68db6-136">Säkerhets trimning</span><span class="sxs-lookup"><span data-stu-id="68db6-136">Security trimmed</span></span><br/><span data-ttu-id="68db6-137">Uppdateras automatiskt när webbplatser läggs till</span><span class="sxs-lookup"><span data-stu-id="68db6-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="68db6-138">Snabb inläsningstid och lokalt cachelagrad navigeringsstruktur</span><span class="sxs-lookup"><span data-stu-id="68db6-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="68db6-139">Fördelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-139">Pros:</span></span><br/><br/><span data-ttu-id="68db6-140">Fler alternativ</span><span class="sxs-lookup"><span data-stu-id="68db6-140">Wider choice of options available</span></span><br/><span data-ttu-id="68db6-141">Snabb inläsning vid cachelagring används korrekt</span><span class="sxs-lookup"><span data-stu-id="68db6-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="68db6-142">Många alternativ fungerar bra med dynamisk siddesign</span><span class="sxs-lookup"><span data-stu-id="68db6-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="68db6-143">Nackdelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-143">Cons:</span></span><br/><br/><span data-ttu-id="68db6-144">**Påverkar prestanda om cachelagring är inaktiverat**</span><span class="sxs-lookup"><span data-stu-id="68db6-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="68db6-145">Begränsningen gäller</span><span class="sxs-lookup"><span data-stu-id="68db6-145">Subject to throttling</span></span><br/>|<span data-ttu-id="68db6-146">Nackdelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-146">Cons:</span></span><br/><br/><span data-ttu-id="68db6-147">Uppdateras inte automatiskt för att återspegla webbplatsstrukturen</span><span class="sxs-lookup"><span data-stu-id="68db6-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="68db6-148">**Påverkar prestanda om säkerhets trimning är aktiverat eller** när navigeringsstrukturen är komplex</span><span class="sxs-lookup"><span data-stu-id="68db6-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="68db6-149">Nackdelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-149">Cons:</span></span><br/><br/><span data-ttu-id="68db6-150">Ingen möjlighet att enkelt ordna webbplatser</span><span class="sxs-lookup"><span data-stu-id="68db6-150">No ability to easily order sites</span></span><br/><span data-ttu-id="68db6-151">Kräver anpassning av huvudsidan (tekniska färdigheter krävs)</span><span class="sxs-lookup"><span data-stu-id="68db6-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="68db6-152">Nackdelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-152">Cons:</span></span><br/><br/><span data-ttu-id="68db6-153">Anpassad utveckling krävs</span><span class="sxs-lookup"><span data-stu-id="68db6-153">Custom development is required</span></span><br/><span data-ttu-id="68db6-154">Extern datakälla/cachelagring behövs, t.ex. Azure</span><span class="sxs-lookup"><span data-stu-id="68db6-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="68db6-155">Vilket alternativ som passar bäst för din webbplats beror på dina webbplatskrav och din tekniska kapacitet.</span><span class="sxs-lookup"><span data-stu-id="68db6-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="68db6-156">Om du vill ha en lättkonfigurerad navigeringsleverantör som uppdateras [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) automatiskt när innehåll ändras är strukturell navigering med cachelagring aktiverad ett bra alternativ.</span><span class="sxs-lookup"><span data-stu-id="68db6-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="68db6-157">Genom att tillämpa samma princip som moderna SharePoint-webbplatser genom att förenkla den övergripande webbplatsstrukturen till en snackande, icke-hierarkisk struktur förbättras prestanda och det blir enklare att flytta till moderna SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="68db6-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="68db6-158">Det innebär att i stället för att ha en enda webbplatssamling med hundratals webbplatser (underwebbplatser) är det bättre att ha många webbplatssamlingar med väldigt få underwebbplatser (underwebbplatser).</span><span class="sxs-lookup"><span data-stu-id="68db6-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="68db6-159">Analysera navigeringsprestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68db6-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="68db6-160">Verktyget [Siddiagnostik för SharePoint är](./page-diagnostics-for-spo.md) ett webbläsartillägg för webbläsarna Microsoft Edge och Chrome som analyserar både moderna portaler och klassiska publiceringswebbplatssidor i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68db6-160">The [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="68db6-161">Det här verktyget fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.</span><span class="sxs-lookup"><span data-stu-id="68db6-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="68db6-162">Verktyget genererar en rapport för varje analyserad sida som visar hur sidan fungerar mot en fördefinierad uppsättning regler och visar detaljerad information när resultaten för ett test faller utanför baslinjevärdet.</span><span class="sxs-lookup"><span data-stu-id="68db6-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="68db6-163">SharePoint Online-administratörer och -designers kan använda verktyget för att felsöka prestandaproblem och se till att nya sidor är optimerade innan du publicerar.</span><span class="sxs-lookup"><span data-stu-id="68db6-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="68db6-164">**SPRequestDuration** är i synnerhet den tid det tar för SharePoint att bearbeta sidan.</span><span class="sxs-lookup"><span data-stu-id="68db6-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="68db6-165">Tung navigering (t.ex. sidor i navigering), komplexa webbplatshierarkier och andra konfigurations- och topologialternativ kan avsevärt bidra till längre varaktighet.</span><span class="sxs-lookup"><span data-stu-id="68db6-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="68db6-166">Använda strukturell navigering i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68db6-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="68db6-167">Det här är den inklarade navigeringen som används som standard och är den enklaste lösningen.</span><span class="sxs-lookup"><span data-stu-id="68db6-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="68db6-168">Det krävs ingen anpassning och en icke-teknisk användare kan också enkelt lägga till objekt, dölja objekt och hantera navigeringen från inställningssidan.</span><span class="sxs-lookup"><span data-stu-id="68db6-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="68db6-169">Vi rekommenderar [att du aktiverar cachelagring,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)annars finns det en dyr prestandaförseing.</span><span class="sxs-lookup"><span data-stu-id="68db6-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="68db6-170">Implementera cachelagring av strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="68db6-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="68db6-171">Under **Utseende och känsla** för  >  **webbplatsinställningar**  >  **kan** du verifiera om strukturell navigering har markerats för antingen global navigering eller aktuell navigering.</span><span class="sxs-lookup"><span data-stu-id="68db6-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="68db6-172">Om **du väljer Visa** sidor påverkas prestandan negativt.</span><span class="sxs-lookup"><span data-stu-id="68db6-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Strukturell navigering med Visa underwebbplatser markerat](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="68db6-174">Cachelagring kan aktiveras eller inaktiveras på webbplatssamlingsnivå och på webbplatsnivå, och är aktiverat för båda som standard.</span><span class="sxs-lookup"><span data-stu-id="68db6-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="68db6-175">Aktivera på webbplatssamlingsnivå genom att **markera** kryssrutan Aktivera cachelagring under Webbplatsinställningar för webbplatssamlingens administration av  >    >   **webbplatssamlingsnavigering.**</span><span class="sxs-lookup"><span data-stu-id="68db6-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Aktivera cachelagring på webbplatsnivå](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="68db6-177">Om du vill aktivera på webbplatsnivå går **du till Navigering**  >  **i** Webbplatsinställningar och markerar kryssrutan **Aktivera cachelagring.**</span><span class="sxs-lookup"><span data-stu-id="68db6-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Aktivera cachelagring på webbplatsnivå](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="68db6-179">Använda hanterad navigering och metadata i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="68db6-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="68db6-180">Hanterad navigering är ett annat intr dess alternativ som du kan använda för att återskapa de flesta av funktionerna i strukturell navigering.</span><span class="sxs-lookup"><span data-stu-id="68db6-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="68db6-181">Hanterade metadata kan konfigureras så att säkerhets trimning är aktiverat eller inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="68db6-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="68db6-182">När den hanterade navigeringen konfigureras med inaktiverad säkerhets trimning är den ganska effektiv eftersom alla navigeringslänkar läses in med ett konstant antal serversamtal.</span><span class="sxs-lookup"><span data-stu-id="68db6-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="68db6-183">Aktivering av säkerhets trimning negerar emellertid vissa av prestandafördelarna för hanterad navigering.</span><span class="sxs-lookup"><span data-stu-id="68db6-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="68db6-184">Om du behöver aktivera säkerhets trimning rekommenderar vi att du gör följande:</span><span class="sxs-lookup"><span data-stu-id="68db6-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="68db6-185">Uppdatera alla användarvänliga URL-länkar till enkla länkar</span><span class="sxs-lookup"><span data-stu-id="68db6-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="68db6-186">Lägga till obligatoriska säkerhets trimningsnoder som användarvänliga URL:er</span><span class="sxs-lookup"><span data-stu-id="68db6-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="68db6-187">Begränsa antalet navigeringsobjekt till högst 100 och högst 3 nivåer</span><span class="sxs-lookup"><span data-stu-id="68db6-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="68db6-188">Många webbplatser kräver inte säkerhets trimning eftersom navigeringsstrukturen ofta är konsekvent för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="68db6-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="68db6-189">Om säkerhets trimning är inaktiverat och en länk läggs till i navigering som inte alla användare har åtkomst till visas länken fortfarande, men det leder till ett meddelande om nekad åtkomst.</span><span class="sxs-lookup"><span data-stu-id="68db6-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="68db6-190">Det finns ingen risk för oavsiktlig åtkomst till innehållet.</span><span class="sxs-lookup"><span data-stu-id="68db6-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="68db6-191">Så här implementerar du hanterad navigering och resultaten</span><span class="sxs-lookup"><span data-stu-id="68db6-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="68db6-192">Det finns flera artiklar docs.microsoft.com information om hanterad navigering.</span><span class="sxs-lookup"><span data-stu-id="68db6-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="68db6-193">Se till exempel Översikt [över hanterad navigering i SharePoint Server.](/sharepoint/administration/overview-of-managed-navigation)</span><span class="sxs-lookup"><span data-stu-id="68db6-193">For example, see [Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="68db6-194">Om du vill implementera hanterad navigering kan du konfigurera termer med URL:er som motsvarar webbplatsens navigeringsstruktur.</span><span class="sxs-lookup"><span data-stu-id="68db6-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="68db6-195">Hanterad navigering kan även väljas manuellt för att ersätta strukturell navigering i många fall.</span><span class="sxs-lookup"><span data-stu-id="68db6-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="68db6-196">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="68db6-196">For example:</span></span>

![SharePoint Online-webbplatsstruktur](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="68db6-198">)</span><span class="sxs-lookup"><span data-stu-id="68db6-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="68db6-199">Använda sökdrivna skript på klientsidan</span><span class="sxs-lookup"><span data-stu-id="68db6-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="68db6-200">En vanlig klass av anpassad navigeringsimplementering är att klientutgivna designmönster lagras i en lokal cache med navigeringsnoder.</span><span class="sxs-lookup"><span data-stu-id="68db6-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="68db6-201">De här navigeringsleverantörerna har några viktiga fördelar:</span><span class="sxs-lookup"><span data-stu-id="68db6-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="68db6-202">De fungerar oftast bra med siddesigner som svarar på dem.</span><span class="sxs-lookup"><span data-stu-id="68db6-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="68db6-203">De är extremt skalbara och performant eftersom de kan återges utan resurskostnad (och uppdateras i bakgrunden efter en timeout).</span><span class="sxs-lookup"><span data-stu-id="68db6-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="68db6-204">Dessa navigeringsleverantörer kan hämta navigeringsdata med olika strategier, allt från enkla statiska konfigurationer till olika dynamiska dataleverantörer.</span><span class="sxs-lookup"><span data-stu-id="68db6-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="68db6-205">Ett exempel på en dataleverantör är att använda en sökdriven **navigering**, som gör det möjligt att räkna upp navigeringsnoder och hantera säkerhetsoptimering effektivt.</span><span class="sxs-lookup"><span data-stu-id="68db6-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="68db6-206">Det finns andra populära alternativ för att skapa **anpassade navigeringsleverantörer.**</span><span class="sxs-lookup"><span data-stu-id="68db6-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="68db6-207">Mer information [om hur du skapar en anpassad navigeringsleverantör finns](/sharepoint/dev/solution-guidance/portal-navigation) i Navigeringslösningar för SharePoint Online-portaler.</span><span class="sxs-lookup"><span data-stu-id="68db6-207">Please review [Navigation solutions for SharePoint Online portals](/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="68db6-208">Med sökning kan du utnyttja de index som byggs upp i bakgrunden med kontinuerlig crawlning.</span><span class="sxs-lookup"><span data-stu-id="68db6-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="68db6-209">Sökresultaten hämtas från sökindexet och resultaten är säkerhets trimade.</span><span class="sxs-lookup"><span data-stu-id="68db6-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="68db6-210">Det här är oftast snabbare än de inringade navigeringsleverantörerna när du behöver säkerhets trimning.</span><span class="sxs-lookup"><span data-stu-id="68db6-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="68db6-211">Genom att använda sökning för strukturell navigering går det avsevärt snabbare att läsa in sidor, särskilt om du har en komplex webbplatsstruktur.</span><span class="sxs-lookup"><span data-stu-id="68db6-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="68db6-212">Den största fördelen med det här framför hanterad navigering är att du kan använda säkerhets trimning.</span><span class="sxs-lookup"><span data-stu-id="68db6-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="68db6-213">Den här metoden innebär att skapa en anpassad huvudsida och ersätta den inringade navigeringskoden med anpassad HTML-kod.</span><span class="sxs-lookup"><span data-stu-id="68db6-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="68db6-214">Följ den här proceduren som beskrivs i följande exempel för att ersätta navigeringskoden i filen `seattle.html` .</span><span class="sxs-lookup"><span data-stu-id="68db6-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="68db6-215">I det här exemplet öppnar du filen `seattle.html` och ersätter hela elementet `id="DeltaTopNavigation"` med anpassad HTML-kod.</span><span class="sxs-lookup"><span data-stu-id="68db6-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="68db6-216">Exempel: Ersätt den intr. navigeringskoden på en huvudsida</span><span class="sxs-lookup"><span data-stu-id="68db6-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="68db6-217">Gå till sidan Webbplatsinställningar.</span><span class="sxs-lookup"><span data-stu-id="68db6-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="68db6-218">Öppna galleriet för huvudsidor genom att klicka **på Huvudsidor.**</span><span class="sxs-lookup"><span data-stu-id="68db6-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="68db6-219">Härifrån kan du navigera i biblioteket och ladda ned filen `seattle.master` .</span><span class="sxs-lookup"><span data-stu-id="68db6-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="68db6-220">Redigera koden med en textredigerare och ta bort kodblocket i följande skärmbild.</span><span class="sxs-lookup"><span data-stu-id="68db6-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Ta bort kodblocket som visas](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="68db6-222">Ta bort koden mellan `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` taggarna och och ersätt den med följande kodstycke:</span><span class="sxs-lookup"><span data-stu-id="68db6-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

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
6. <span data-ttu-id="68db6-223">Ersätt URL:en i anchor-taggen för inläsningsbilden i början med en länk till en inläsningsbild i din webbplatssamling.</span><span class="sxs-lookup"><span data-stu-id="68db6-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="68db6-224">När du har gjort ändringarna byter du namn på filen och laddar sedan upp den till galleriet för huvudsidor.</span><span class="sxs-lookup"><span data-stu-id="68db6-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="68db6-225">Då skapas en ny .master-fil.</span><span class="sxs-lookup"><span data-stu-id="68db6-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="68db6-226">Den här HTML-koden är den grundläggande kod som används för sökresultaten som returneras från JavaScript-koden.</span><span class="sxs-lookup"><span data-stu-id="68db6-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="68db6-227">Du behöver redigera koden för att ändra värdet för var root = "site collection URL" enligt följande kodstycke:</span><span class="sxs-lookup"><span data-stu-id="68db6-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="68db6-228">Resultaten tilldelas till self.nodes-matrisen och en hierarki byggs upp av objekten linq.js tilldelar utdata till en matris-self.hierarchy.</span><span class="sxs-lookup"><span data-stu-id="68db6-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="68db6-229">Den här matrisen är det objekt som är bundet till HTML-koden.</span><span class="sxs-lookup"><span data-stu-id="68db6-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="68db6-230">Detta görs i funktionen toggleView() genom att skicka self-objektet till funktionen ko.applyBinding().</span><span class="sxs-lookup"><span data-stu-id="68db6-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="68db6-231">Hierarkimatrisen binds sedan till följande HTML-kod:</span><span class="sxs-lookup"><span data-stu-id="68db6-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="68db6-232">Händelsehanterare för och läggs till i navigeringen på den översta nivån för att hantera listmenyerna på underwebbplatsen som `mouseenter` `mouseexit` utförs i `addEventsToElements()` funktionen.</span><span class="sxs-lookup"><span data-stu-id="68db6-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="68db6-233">I exemplet med komplex navigering visar en ny inläsning av sidor utan lokal cachelagring att tiden som används på servern har klippts ned från utgångspunkten för strukturell navigering till att få ett liknande resultat som den hanterade navigeringen.</span><span class="sxs-lookup"><span data-stu-id="68db6-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="68db6-234">Om JavaScript-filen...</span><span class="sxs-lookup"><span data-stu-id="68db6-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="68db6-235">Om du använder anpassat JavaScript ser du till att public CDN är aktiverat och att filen finns på en CDN-plats.</span><span class="sxs-lookup"><span data-stu-id="68db6-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="68db6-236">Hela JavaScript-filen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="68db6-236">The entire JavaScript file is as follows:</span></span>

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

<span data-ttu-id="68db6-237">För att sammanfatta koden som visas ovan i funktionen skapas en och sedan anropas `jQuery $(document).ready` `viewModel object` funktionen för det `loadNavigationNodes()` objektet.</span><span class="sxs-lookup"><span data-stu-id="68db6-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="68db6-238">Med den här funktionen läses antingen den tidigare skapade navigeringshierarkin som lagras i den lokala HTML5-lagringen i klientwebbläsaren in eller så anropas funktionen `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="68db6-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="68db6-239">`QueryRemoteInterface()` skapar en begäran med hjälp av `getRequest()` funktionen med frågeparametern som definierats tidigare i skriptet och returnerar sedan data från servern.</span><span class="sxs-lookup"><span data-stu-id="68db6-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="68db6-240">Dessa data är i princip en matris av alla webbplatser i webbplatssamlingen som representeras som dataöverföringsobjekt med olika egenskaper.</span><span class="sxs-lookup"><span data-stu-id="68db6-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="68db6-241">Dessa data analyseras sedan i de tidigare definierade objekten som använder för att skapa observerbara egenskaper som används genom att data binder värdena till HTML-koden som `SPO.Models.NavigationNode` `Knockout.js` vi definierade tidigare.</span><span class="sxs-lookup"><span data-stu-id="68db6-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="68db6-242">Objekten läggs sedan in i en resultatmatris.</span><span class="sxs-lookup"><span data-stu-id="68db6-242">The objects are then put into a results array.</span></span> <span data-ttu-id="68db6-243">Den här matrisen analyseras till JSON med Knockout och lagras i den lokala webbläsarlagringen för bättre prestanda vid framtida sidinläsningar.</span><span class="sxs-lookup"><span data-stu-id="68db6-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="68db6-244">Fördelar med den här metoden</span><span class="sxs-lookup"><span data-stu-id="68db6-244">Benefits of this approach</span></span>

<span data-ttu-id="68db6-245">En av de största [fördelarna med den](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) här metoden är att navigeringen, genom lokal HTML5-lagring, lagras lokalt för användaren nästa gång han/hon läser in sidan.</span><span class="sxs-lookup"><span data-stu-id="68db6-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="68db6-246">Vi får stora prestandaförbättringar när vi använder sök-API:t för strukturell navigering. Det krävs emellertid viss teknisk kapacitet för att köra och anpassa den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="68db6-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="68db6-247">I [den här](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)exempelimplementering är webbplatserna ordnade på samma sätt som den inbeställda strukturella navigeringen. alfabetisk ordning.</span><span class="sxs-lookup"><span data-stu-id="68db6-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="68db6-248">Om du avviker från den här ordningen skulle det vara mer komplicerat att utveckla och underhålla.</span><span class="sxs-lookup"><span data-stu-id="68db6-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="68db6-249">Den här metoden kräver också att du avviker från huvudsidorna som stöds.</span><span class="sxs-lookup"><span data-stu-id="68db6-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="68db6-250">Om den anpassade huvudsidan inte underhålls går din webbplats miste om uppdateringar och förbättringar som Microsoft gör av huvudsidorna.</span><span class="sxs-lookup"><span data-stu-id="68db6-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="68db6-251">Koden [ovan](#about-the-javascript-file) har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="68db6-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="68db6-252">jQuery - https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="68db6-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="68db6-253">KnockoutJS - https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="68db6-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="68db6-254">Linq.js – https://linqjs.codeplex.com/ eller github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="68db6-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="68db6-255">Den aktuella versionen av LinqJS innehåller inte metoden ByHierar method som används i koden ovan och kommer att bryta navigeringskoden.</span><span class="sxs-lookup"><span data-stu-id="68db6-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="68db6-256">Lös det genom att lägga till följande metod i Linq.js filen före raden `Flatten: function ()` .</span><span class="sxs-lookup"><span data-stu-id="68db6-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

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
  
## <a name="related-topics"></a><span data-ttu-id="68db6-257">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="68db6-257">Related topics</span></span>

[<span data-ttu-id="68db6-258">Översikt över hanterad navigering i SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="68db6-258">Overview of managed navigation in SharePoint Server</span></span>](/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="68db6-259">Cachelagring och prestanda för strukturell navigering</span><span class="sxs-lookup"><span data-stu-id="68db6-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)