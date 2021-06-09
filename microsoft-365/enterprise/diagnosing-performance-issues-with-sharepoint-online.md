---
title: Diagnostisering av prestandaproblem med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
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
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: I den här artikeln visar vi hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklarverktygen i Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927618"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="98a08-103">Diagnostisering av prestandaproblem med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98a08-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="98a08-104">I den här artikeln visar vi hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklarverktygen i Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="98a08-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="98a08-105">Det finns tre olika sätt att identifiera att en sida på en SharePoint Online-webbplats har prestandaproblem med anpassningarna.</span><span class="sxs-lookup"><span data-stu-id="98a08-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="98a08-106">F12-verktygsfältets nätverksskärm</span><span class="sxs-lookup"><span data-stu-id="98a08-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="98a08-107">Jämförelse med en icke-anpassad originalplan</span><span class="sxs-lookup"><span data-stu-id="98a08-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="98a08-108">SharePoint Mått för onlinesvarshuvud</span><span class="sxs-lookup"><span data-stu-id="98a08-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="98a08-109">I det här avsnittet beskrivs hur du använder var och en av de här metoderna för att diagnostisera prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="98a08-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="98a08-110">När du har hittat orsaken till problemet kan du arbeta mot en lösning med hjälp av artiklarna om hur du SharePoint prestanda som du hittar på https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="98a08-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="98a08-111">Använda F12-verktygsfältet för att diagnostisera prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98a08-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="98a08-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="98a08-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="98a08-113">I den här artikeln använder vi Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="98a08-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="98a08-114">Versioner av F12-utvecklarverktygen i andra webbläsare har liknande funktioner, men de kan se lite annorlunda ut.</span><span class="sxs-lookup"><span data-stu-id="98a08-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="98a08-115">Mer information om F12-utvecklingsverktygen finns i:</span><span class="sxs-lookup"><span data-stu-id="98a08-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="98a08-116">[Vad är nytt i F12-verktygen](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="98a08-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="98a08-117">[Använda F12-utvecklingsverktygen](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="98a08-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="98a08-118">Du visar utvecklingsverktygen genom att trycka **på F12** och sedan klicka Wi-Fi ikonen:</span><span class="sxs-lookup"><span data-stu-id="98a08-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Skärmbild av WiFi-ikonen för F12-utvecklarverktyg](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="98a08-120">På fliken **Nätverk** trycker du på den gröna uppspelningsknappen för att läsa in en sida.</span><span class="sxs-lookup"><span data-stu-id="98a08-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="98a08-121">Verktyget returnerar alla filer som webbläsaren begär för att få den sida du efterfrågar.</span><span class="sxs-lookup"><span data-stu-id="98a08-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="98a08-122">Följande skärmbild visar en sådan lista.</span><span class="sxs-lookup"><span data-stu-id="98a08-122">The following screen shot shows one such list.</span></span>
  
![Skärmbild av listan med filer som returnerades med en sidbegäran.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="98a08-124">På höger sida kan du även se nedladdningstiderna för filerna, som på skärmbilden.</span><span class="sxs-lookup"><span data-stu-id="98a08-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagram som visar den tid det tar att läsa in begärda sidor SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="98a08-126">Det ger dig en visualisering av hur lång tid det tog att läsa in filen.</span><span class="sxs-lookup"><span data-stu-id="98a08-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="98a08-127">Den gröna linjen visar när sidan är klar att återges i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="98a08-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="98a08-128">Det ger dig en snabb översikt över de olika filer som kan vara orsaken till långsam sidin läses in på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="98a08-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="98a08-129">Konfigurera en icke-anpassad originalplan för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="98a08-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="98a08-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="98a08-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="98a08-131">Det bästa sättet att ta reda på var webbplatsen fungerar bäst är att konfigurera en förinställt webbplatssamling i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="98a08-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="98a08-132">På så sätt kan du jämföra olika aspekter av webbplatsen med vad du skulle få utan anpassning på sidan.</span><span class="sxs-lookup"><span data-stu-id="98a08-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="98a08-133">Startsidan OneDrive för företag ett bra exempel på en separat webbplatssamling som inte har några anpassningar.</span><span class="sxs-lookup"><span data-stu-id="98a08-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="98a08-134">Visa SharePoint i svarshuvuden</span><span class="sxs-lookup"><span data-stu-id="98a08-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="98a08-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="98a08-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="98a08-136">I SharePoint Online kan du komma åt den information som skickas tillbaka till webbläsaren i svarshuvudet för varje fil.</span><span class="sxs-lookup"><span data-stu-id="98a08-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="98a08-137">Det mest användbara värdet för diagnostisering av prestandaproblem är **SPRequestDuration,** som visar den tid som begäran tog på servern för att bearbetas.</span><span class="sxs-lookup"><span data-stu-id="98a08-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="98a08-138">Det kan hjälpa dig att avgöra om begäran är mycket tung och resurskrävande.</span><span class="sxs-lookup"><span data-stu-id="98a08-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="98a08-139">Det här är den bästa insikt du har i hur mycket arbete servern utför för att servera sidan.</span><span class="sxs-lookup"><span data-stu-id="98a08-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="98a08-140">Så här visar SharePoint i svarshuvuden</span><span class="sxs-lookup"><span data-stu-id="98a08-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="98a08-141">Kontrollera att du har F12-verktygen installerade.</span><span class="sxs-lookup"><span data-stu-id="98a08-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="98a08-142">Mer information om hur du laddar ned och installerar dessa verktyg finns [i Vad är nytt i F12-verktygen.](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="98a08-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="98a08-143">I F12-verktygen på fliken Nätverk **trycker du på** den gröna uppspelningsknappen för att läsa in en sida.</span><span class="sxs-lookup"><span data-stu-id="98a08-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="98a08-144">Klicka på en av .aspx-filerna som returneras av verktyget och klicka sedan på **INFORMATION.**</span><span class="sxs-lookup"><span data-stu-id="98a08-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Visar information om svarshuvudet](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="98a08-146">Klicka **på Svarshuvuden**.</span><span class="sxs-lookup"><span data-stu-id="98a08-146">Click **Response headers**.</span></span>

    ![Diagram som visar URL-adressen för svarshuvudet](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="98a08-148">Vad orsakar prestandaproblem i SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="98a08-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="98a08-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="98a08-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="98a08-150">I artikeln [Navigeringsalternativ](navigation-options-for-sharepoint-online.md) för SharePoint Online visas ett exempel på hur SPRequestDuration-värdet används för att fastställa att den komplicerade strukturella navigeringen ledde till att sidan tog lång tid att bearbeta på servern.</span><span class="sxs-lookup"><span data-stu-id="98a08-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="98a08-151">Genom att ta ett värde för en baslinjewebbplats (utan anpassning) kan du avgöra om det tar lång tid att läsa in en viss fil.</span><span class="sxs-lookup"><span data-stu-id="98a08-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="98a08-152">Det exempel som används [i Navigeringsalternativ för SharePoint Online](navigation-options-for-sharepoint-online.md) är den viktigaste .aspx-filen.</span><span class="sxs-lookup"><span data-stu-id="98a08-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="98a08-153">Den filen innehåller de flesta ASP.NET kod som körs för sidinläsningen.</span><span class="sxs-lookup"><span data-stu-id="98a08-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="98a08-154">Beroende på vilken webbplatsmall du använder kan det vara start.aspx, home.aspx, default.aspx eller ett annat namn om du anpassar startsidan.</span><span class="sxs-lookup"><span data-stu-id="98a08-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="98a08-155">Om det här talet är betydligt högre än baslinjewebbplatsens är det en god indikation på att något komplicerat pågår på sidan som orsakar prestandaproblemen.</span><span class="sxs-lookup"><span data-stu-id="98a08-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="98a08-156">När du har identifierat att ett problem gäller specifikt för din webbplats är det rekommenderade sättet att ta reda på vad som orsakar dåliga prestanda att ta bort alla möjliga orsaker, som sidanpassning, och sedan lägga till dem en och en på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="98a08-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="98a08-157">När du har tagit bort tillräckligt många anpassningar för att sidan ska gå bra kan du lägga tillbaka specifika anpassningar en och en.</span><span class="sxs-lookup"><span data-stu-id="98a08-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="98a08-158">Om du till exempel har en mycket komplex navigering kan du försöka ändra navigeringen så att underwebbplatser inte visas, och sedan kontrollera utvecklarverktygen för att se om det gör någon skillnad.</span><span class="sxs-lookup"><span data-stu-id="98a08-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="98a08-159">Om du har en stor mängd innehållsupprullningar kan du ta bort dem från sidan och se om det förbättrar saker.</span><span class="sxs-lookup"><span data-stu-id="98a08-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="98a08-160">Om du tar bort alla möjliga orsaker och lägger till dem i en i taget kan du enkelt identifiera vilka funktioner som är det största problemet och sedan arbeta mot en lösning.</span><span class="sxs-lookup"><span data-stu-id="98a08-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>