---
title: Använda webb delen för innehålls sökning i stället för webb delen innehålls fråga för att förbättra prestanda i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Lär dig att öka prestandan genom att ersätta webb delen innehålls fråga med webb delen innehålls sökning i SharePoint Server 2013 och SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694919"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="0b5ac-103">Använda webb delen för innehålls sökning i stället för webb delen innehålls fråga för att förbättra prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0b5ac-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="0b5ac-104">I den här artikeln beskrivs hur du ökar prestandan genom att ersätta webb delen innehålls fråga med webb delen innehålls sökning i SharePoint Server 2013 och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="0b5ac-105">En av de mest kraftfulla funktionerna i SharePoint Server 2013 och SharePoint Online är webb delen innehålls sökning (INNEHÅLLS sökning).</span><span class="sxs-lookup"><span data-stu-id="0b5ac-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="0b5ac-106">Den här webb delen använder Sök indexet för att snabbt hämta resultat som visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="0b5ac-107">Använd webb delen innehålls sökning i stället för webb delen innehålls fråga (INNEHÅLLS fråga) på dina sidor för att förbättra datorns prestanda.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="0b5ac-108">Om du använder en webbdel för innehålls sökning via en webbdel för innehålls fråga kommer nästan alltid att få betydligt bättre prestanda i sid belastning på SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="0b5ac-109">Det finns lite extra konfiguration för att få rätt fråga, men fördelarna är bättre prestanda och presenten glädjer användare.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="0b5ac-110">Jämför prestanda ökningen du får genom att använda webb delen för innehålls sökning i stället för webb delen innehålls fråga</span><span class="sxs-lookup"><span data-stu-id="0b5ac-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="0b5ac-111">I följande exempel visas de relativa prestanda vinster du kan få när du använder en webbdel för innehålls sökning i stället för en webbdel för innehålls fråga.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="0b5ac-112">Effekterna är mer uppenbara med en komplex webbplats struktur och mycket breda innehålls frågor.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="0b5ac-113">Den här exempel webbplatsen har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="0b5ac-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="0b5ac-114">8 nivåer av under webbplatser.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="0b5ac-115">Listor med den anpassade innehålls typen "frukt".</span><span class="sxs-lookup"><span data-stu-id="0b5ac-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="0b5ac-116">I webb delen är innehålls frågan brett och returnerar alla objekt med innehålls typen "frukt".</span><span class="sxs-lookup"><span data-stu-id="0b5ac-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="0b5ac-117">I exemplet används endast 50-objekt på åtta webbplatser.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="0b5ac-118">Effekterna blir ännu mer uttalade för webbplatser med mer innehåll.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="0b5ac-119">Här visas en skärm bild av resultatet av webb delen för innehålls fråga.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Bild som visar innehålls fråga för webbdel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="0b5ac-121">I Internet Explorer går du till fliken **nätverk** i F12-utvecklingsverktygen för att se informationen för svars huvudet.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="0b5ac-122">I följande skärmdump är värdet för **SPRequestDuration** för den här sidans laddning 924 millisekunder.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Skärm bild som visar begärande-varaktighet för 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="0b5ac-124">**SPRequestDuration** anger hur mycket arbete som utförs på servern för att förbereda sidan.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="0b5ac-125">Om du byter innehåll efter webb delar från en fråga med innehåll efter Sök webb delar drastiskt minskar den tid det tar att rendera sidan.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="0b5ac-126">En sida med en motsvarande webb delen för innehålls sökning, som returnerar samma antal resultat, har ett **SPRequestDuration** -värde på 106 millisekunder som visas i den här skärm bilden:</span><span class="sxs-lookup"><span data-stu-id="0b5ac-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Skärm bild som visar varaktigheten för en aktivitet med 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="0b5ac-128">Lägga till en webbdel för innehålls sökning i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0b5ac-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="0b5ac-129">Att lägga till en webbdel för innehålls sökning liknar en vanlig innehålls fråga.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="0b5ac-130">Se avsnittet  *"lägga till en webbdel för innehålls sökning"*  i [Konfigurera en webbdel för innehålls sökning i SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="0b5ac-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="0b5ac-131">Skapa rätt Sök fråga för webb delen innehålls sökning</span><span class="sxs-lookup"><span data-stu-id="0b5ac-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="0b5ac-132">När du har lagt till en webbdel för innehålls sökning kan du förfina sökningen och returnera de objekt du vill.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="0b5ac-133">Detaljerade anvisningar om hur du gör detta finns i avsnittet  *"Visa innehåll genom att konfigurera en avancerad fråga i en webbdel för innehålls sökning"*  i [Konfigurera en webbdel för innehålls sökning i SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="0b5ac-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="0b5ac-134">Verktyg för att skapa frågor</span><span class="sxs-lookup"><span data-stu-id="0b5ac-134">Query building and testing tool</span></span>

<span data-ttu-id="0b5ac-135">Ett verktyg för att skapa och testa komplexa frågor finns i [verktyget för Sök frågor](https://sp2013searchtool.codeplex.com/) på Codeplex.</span><span class="sxs-lookup"><span data-stu-id="0b5ac-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

