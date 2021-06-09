---
title: Använda webbdel för innehållssökning i stället för webbdel för innehållsfråga för att förbättra prestanda SharePoint Online
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
description: Lär dig hur du kan öka prestanda genom att ersätta webbdelen för innehållsfråga med webbdelen för innehållssökning i SharePoint Server 2013 och SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694919"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="3e3db-103">Använda webbdel för innehållssökning i stället för webbdel för innehållsfråga för att förbättra prestanda SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3e3db-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="3e3db-104">I den här artikeln beskrivs hur du kan öka prestanda genom att ersätta webbdelen för innehållsfråga med webbdelen för innehållssökning i SharePoint Server 2013 och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3e3db-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="3e3db-105">En av de mest kraftfulla nya funktionerna i SharePoint Server 2013 och SharePoint Online är webbdel för innehållssökning (CSWP).</span><span class="sxs-lookup"><span data-stu-id="3e3db-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="3e3db-106">Den här webbdelen använder sökindexet för att snabbt hämta resultat som visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="3e3db-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="3e3db-107">Använd webbdelen Innehållssökning i stället för webbdel för innehållsfråga (CQWP) på dina sidor för att förbättra prestanda för användarna.</span><span class="sxs-lookup"><span data-stu-id="3e3db-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="3e3db-108">Genom att använda webbdel för innehållssökning i över en webbdel för innehållsfråga får du nästan alltid avsevärt bättre prestanda vid sidinläsning SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3e3db-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="3e3db-109">Det krävs lite ytterligare konfiguration för att få fram rätt fråga, men vinsterna är högre prestanda och nöjdare användare.</span><span class="sxs-lookup"><span data-stu-id="3e3db-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="3e3db-110">Jämförelse av de prestanda som ger dig när du använder webbdel för innehållssökning i stället för webbdel för innehållsfråga</span><span class="sxs-lookup"><span data-stu-id="3e3db-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="3e3db-111">Följande exempel visar de relativa prestandaförbättringar som du kan få när du använder en webbdel för innehållssökning i stället för en webbdel för innehållsfråga.</span><span class="sxs-lookup"><span data-stu-id="3e3db-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="3e3db-112">Effekterna blir mer uppenbara med en komplex webbplatsstruktur och mycket breda innehållsfrågor.</span><span class="sxs-lookup"><span data-stu-id="3e3db-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="3e3db-113">Den här exempelwebbplatsen har följande egenskaper:</span><span class="sxs-lookup"><span data-stu-id="3e3db-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="3e3db-114">Åtta nivåer med underwebbplatser.</span><span class="sxs-lookup"><span data-stu-id="3e3db-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="3e3db-115">Listor med den anpassade innehållstypen "frukt".</span><span class="sxs-lookup"><span data-stu-id="3e3db-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="3e3db-116">I webbdelen är innehållsfrågan bred, vilket returnerar alla objekt med innehållstypen "frukt".</span><span class="sxs-lookup"><span data-stu-id="3e3db-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="3e3db-117">I exemplet används bara 50 objekt på de 8 webbplatserna.</span><span class="sxs-lookup"><span data-stu-id="3e3db-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="3e3db-118">Effekterna blir ännu mer markanta för webbplatser med mer innehåll.</span><span class="sxs-lookup"><span data-stu-id="3e3db-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="3e3db-119">Här visas en skärmbild av resultaten från webbdelen för innehållsfråga.</span><span class="sxs-lookup"><span data-stu-id="3e3db-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Bild som visar webbdelens innehållsfråga](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="3e3db-121">I Internet Explorer använder du fliken **Nätverk** för F12-utvecklingsverktygen för att titta på informationen för svarshuvudet.</span><span class="sxs-lookup"><span data-stu-id="3e3db-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="3e3db-122">På följande skärmbild är värdet för **SPRequestDuration** för den här sidinläsningen 924 millisekunder.</span><span class="sxs-lookup"><span data-stu-id="3e3db-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Skärmbild som visar begärans varaktighet på 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="3e3db-124">**SPRequestDuration** anger mängden arbete som utförs på servern för att förbereda sidan.</span><span class="sxs-lookup"><span data-stu-id="3e3db-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="3e3db-125">Genom att byta webbdelar fråga mot innehåll genom sökning webbdelar avsevärt minskar tiden det tar att återge sidan.</span><span class="sxs-lookup"><span data-stu-id="3e3db-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="3e3db-126">Som jämförelse har en sida med en motsvarande webbdel för innehållssökning, som returnerar samma antal resultat, ett **SPRequestDuration-värde** på 106 millisekunder, som visas på skärmbilden:</span><span class="sxs-lookup"><span data-stu-id="3e3db-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Skärmbild som visar Begärans varaktighet på 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="3e3db-128">Lägga till en webbdel för innehållssökning i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3e3db-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="3e3db-129">Att lägga till en webbdel för innehållssökning liknar en vanlig webbdel för innehållsfråga.</span><span class="sxs-lookup"><span data-stu-id="3e3db-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="3e3db-130">Se avsnittet *"Lägga till en webbdel för innehållssökning"* i [Konfigurera en webbdel för innehållssökning i SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="3e3db-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="3e3db-131">Skapa rätt sökfråga för webbdelen Innehållssökning</span><span class="sxs-lookup"><span data-stu-id="3e3db-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="3e3db-132">När du har lagt till en webbdel för innehållssökning kan du förfina sökningen och returnera de objekt du vill ha.</span><span class="sxs-lookup"><span data-stu-id="3e3db-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="3e3db-133">Detaljerade anvisningar om hur du gör detta finns i avsnittet *"Visa* innehåll genom att konfigurera en avancerad fråga i en webbdel för innehållssökning" i Konfigurera en webbdel för innehållssökning [i SharePoint.](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)</span><span class="sxs-lookup"><span data-stu-id="3e3db-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="3e3db-134">Verktyg för att skapa och testa frågor</span><span class="sxs-lookup"><span data-stu-id="3e3db-134">Query building and testing tool</span></span>

<span data-ttu-id="3e3db-135">Ett verktyg för att skapa och testa komplexa frågor finns i [Sökfrågeverktyget på](https://sp2013searchtool.codeplex.com/) Codeplex.</span><span class="sxs-lookup"><span data-stu-id="3e3db-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

