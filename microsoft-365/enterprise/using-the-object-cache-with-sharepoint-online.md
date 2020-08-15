---
title: Använda objektcachen med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint Server 2013 lokalt och SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696727"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="134ea-103">Använda objektcachen med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="134ea-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="134ea-104">I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint Server 2013 lokalt och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="134ea-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="134ea-105">Det finns betydande negativa konsekvenser för objekt-cachen i distributionen av SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="134ea-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="134ea-106">Alla beroenden för objekt-cachen i SharePoint Online minskar tillförlitligheten hos din sida.</span><span class="sxs-lookup"><span data-stu-id="134ea-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="134ea-107">Så fungerar SharePoint Online-och SharePoint Server 2013-objektcache</span><span class="sxs-lookup"><span data-stu-id="134ea-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="134ea-108">När SharePoint Server 2013 hanteras lokalt har kunden privata front webb servrar som är värdar för objektcachen.</span><span class="sxs-lookup"><span data-stu-id="134ea-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="134ea-109">Det innebär att cacheminnet bevaras till en kund och begränsas bara av hur mycket minne som är tillgängligt och tilldelat objektcachen.</span><span class="sxs-lookup"><span data-stu-id="134ea-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="134ea-110">Eftersom endast en kund betjänas i det lokala scenariot har front webb servrarna vanligt vis användare som skapar förfrågningar till samma webbplatser.</span><span class="sxs-lookup"><span data-stu-id="134ea-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="134ea-111">Det innebär att cacheminnet blir snabbt och återstår att använda i listan med frågeresultaten och SharePoint-objekt som användarna begär med jämna mellanrum.</span><span class="sxs-lookup"><span data-stu-id="134ea-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Visar trafik och läser in till lokala front webb servrar](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="134ea-113">Därför förbättras den andra gången en användare besöker en sida.</span><span class="sxs-lookup"><span data-stu-id="134ea-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="134ea-114">Efter minst fyra belastningar på samma sida lagras sidan på alla front webb servrar.</span><span class="sxs-lookup"><span data-stu-id="134ea-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="134ea-115">I SharePoint Online finns det däremot många fler servrar men också många fler webbplatser.</span><span class="sxs-lookup"><span data-stu-id="134ea-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="134ea-116">Varje användare kan ansluta till en annan front webb server utan cacheminnet.</span><span class="sxs-lookup"><span data-stu-id="134ea-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="134ea-117">Eller så fyller cacheminnet för en server, men nästa användare till front webb servern begär en sida från en annan webbplats.</span><span class="sxs-lookup"><span data-stu-id="134ea-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="134ea-118">Eller även om nästa användare begär samma sida som på ett tidigare besök är de belastningsutjämnade till en annan front webb server som inte har den sidan i cacheminnet.</span><span class="sxs-lookup"><span data-stu-id="134ea-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="134ea-119">I det här fallet hjälper cachelagring inte till användarna alls.</span><span class="sxs-lookup"><span data-stu-id="134ea-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="134ea-120">I bilden nedan representerar varje prick en sida som en användare begär och var den cachelagrade.</span><span class="sxs-lookup"><span data-stu-id="134ea-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="134ea-121">Olika färger är olika kunder som gör gemensam användning av SaaS infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="134ea-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Visar resultaten av cachelagring av objekt i SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="134ea-123">Som du ser i diagrammet är sannolikheten för att en viss användare ska kunna trycka på en server med den cachelagrade versionen av sidan slank.</span><span class="sxs-lookup"><span data-stu-id="134ea-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="134ea-124">På grund av det stora genomflödet och det faktum att servrarna delas mellan många platser är cacheminnet inte senaste länge eftersom det bara finns så mycket utrymme för cachelagring.</span><span class="sxs-lookup"><span data-stu-id="134ea-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="134ea-125">Av alla de här anledningarna är det inte ett effektivt sätt att förlita dig på användare att få cachelagrade objekt i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="134ea-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="134ea-126">Vad kan jag göra om det inte går att använda objektcachen för att förbättra prestanda i SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="134ea-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="134ea-127">Eftersom du inte kan använda cachelagring i SharePoint Online bör du utvärdera alternativa design metoder för SharePoint-anpassningar som använder objektcachen.</span><span class="sxs-lookup"><span data-stu-id="134ea-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="134ea-128">Detta innebär att du använder olika metoder för prestanda problem som inte förlitar sig på objektcache för att få bra resultat för användarna.</span><span class="sxs-lookup"><span data-stu-id="134ea-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="134ea-129">Detta beskrivs i några av de andra artiklarna i denna serie och inkluderar:</span><span class="sxs-lookup"><span data-stu-id="134ea-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="134ea-130">Navigerings alternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="134ea-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="134ea-131">För minskning och buntar i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="134ea-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="134ea-132">Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="134ea-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="134ea-133">Fördröj inläsning av bilder och Java Script i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="134ea-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

