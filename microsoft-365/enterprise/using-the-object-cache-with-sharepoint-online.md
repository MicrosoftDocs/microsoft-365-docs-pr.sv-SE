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
description: I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint server 2013 lokalt och i SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696727"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="7c432-103">Använda objektcachen med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c432-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="7c432-104">I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint server 2013 lokalt och i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7c432-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="7c432-105">Det finns betydande negativ inverkan med att lita på objektcachen i SharePoint Online-distribution.</span><span class="sxs-lookup"><span data-stu-id="7c432-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="7c432-106">Beroende av objektcachen i SharePoint Online minskar tillförlitligheten på sidan.</span><span class="sxs-lookup"><span data-stu-id="7c432-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="7c432-107">Hur objektcachen SharePoint Online SharePoint Server 2013 fungerar</span><span class="sxs-lookup"><span data-stu-id="7c432-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="7c432-108">När SharePoint server 2013 ligger lokalt har kunden privata frontend-webbservrar som fungerar som värd för objektcachen.</span><span class="sxs-lookup"><span data-stu-id="7c432-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="7c432-109">Det innebär att cachen är dedikerad till en kund och begränsas bara av hur mycket minne som är tillgängligt och tilldelas till objektcachen.</span><span class="sxs-lookup"><span data-stu-id="7c432-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="7c432-110">Eftersom endast en kund bearbetas i det lokala scenariot har frontend-webbservrarna vanligtvis användare som gör begäranden till samma webbplatser om och om igen.</span><span class="sxs-lookup"><span data-stu-id="7c432-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="7c432-111">Det innebär att cachen snabbt blir full och förblir full av listfrågeresultat och SharePoint objekt som användarna begär regelbundet.</span><span class="sxs-lookup"><span data-stu-id="7c432-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Visar trafik och inläsning till lokala frontend-webbservrar](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="7c432-113">Därför kan inläsningstiden för sidan bli bättre andra gången en användare besöker en sida.</span><span class="sxs-lookup"><span data-stu-id="7c432-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="7c432-114">När samma sida har läses in minst fyra gånger cachelagras sidan på alla frontend-webbservrar.</span><span class="sxs-lookup"><span data-stu-id="7c432-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="7c432-115">I SharePoint online finns det många fler servrar men också många fler webbplatser.</span><span class="sxs-lookup"><span data-stu-id="7c432-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="7c432-116">Varje användare kan ansluta till en annan frontend-webbserver som inte har cachen ifylld.</span><span class="sxs-lookup"><span data-stu-id="7c432-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="7c432-117">Eller så kanske cachen fylls i för en server, men nästa användare på den frontend-webbservern begär en sida från en annan webbplats.</span><span class="sxs-lookup"><span data-stu-id="7c432-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="7c432-118">Eller, även om nästa användare begär samma sida som vid föregående besök, kan de belastningsutjämnas till en annan frontend-webbserver som inte har den sidan i cachen.</span><span class="sxs-lookup"><span data-stu-id="7c432-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="7c432-119">I det sista fallet hjälper cachelagring inte användarna alls.</span><span class="sxs-lookup"><span data-stu-id="7c432-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="7c432-120">I följande bild representerar varje punkt en sida som en användare begär och där den cachelagras.</span><span class="sxs-lookup"><span data-stu-id="7c432-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="7c432-121">Olika färger representerar olika kunder som delar på användningen av SaaS-infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="7c432-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Visar resultat för cachelagrade objekt i SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="7c432-123">Som du ser i diagrammet är chansen att en viss användare ska komma till en server med den cachelagrade versionen av sidan liten.</span><span class="sxs-lookup"><span data-stu-id="7c432-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="7c432-124">På grund av det stora dataflödet och det faktum att servrarna delas mellan många webbplatser, varar cachen dessutom inte länge eftersom det bara finns så mycket utrymme för cachelagring.</span><span class="sxs-lookup"><span data-stu-id="7c432-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="7c432-125">Att förlita sig på att användarna får cachelagrade objekt är därför inte ett effektivt sätt att säkerställa kvaliteten på användarupplevelsen och sidinläsningstiderna i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7c432-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="7c432-126">Om vi inte kan lita på objektcachen för att förbättra prestanda i SharePoint Online, vad ska vi använda i stället?</span><span class="sxs-lookup"><span data-stu-id="7c432-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="7c432-127">Eftersom du inte bör förlita dig på cachelagring i SharePoint Online, bör du utvärdera alternativa design metoder för SharePoint anpassningar som använder objektcachen.</span><span class="sxs-lookup"><span data-stu-id="7c432-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="7c432-128">Det här innebär att använda metoder för prestandaproblem som inte förlitar sig på cachelagrade objekt för att kunna ge bra resultat för användare.</span><span class="sxs-lookup"><span data-stu-id="7c432-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="7c432-129">Det här beskrivs i några av de andra artiklarna i den här serien och omfattar:</span><span class="sxs-lookup"><span data-stu-id="7c432-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="7c432-130">Navigeringsalternativ för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c432-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="7c432-131">Förgrening och sammanslagning i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c432-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="7c432-132">Använda Office 365 Content Delivery Network (CDN) med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c432-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="7c432-133">Fördröja inläsning av bilder och JavaScript i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="7c432-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

