---
title: Diagnosticera prestanda problem med SharePoint Online
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
description: Den här artikeln visar hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklingsverktyg för Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694548"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="a48df-103">Diagnosticera prestanda problem med SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a48df-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="a48df-104">Den här artikeln visar hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklingsverktyg för Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a48df-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="a48df-105">Det finns tre olika sätt att identifiera att en sida på en SharePoint Online-webbplats har ett prestanda problem med anpassningarna.</span><span class="sxs-lookup"><span data-stu-id="a48df-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="a48df-106">Nätverks övervakaren i F12-verktygsfältet</span><span class="sxs-lookup"><span data-stu-id="a48df-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="a48df-107">Jämförelse med en icke-anpassad original plan</span><span class="sxs-lookup"><span data-stu-id="a48df-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="a48df-108">Mått för svars rubriker i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a48df-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="a48df-109">I det här avsnittet beskrivs hur du använder dessa metoder för att diagnosticera prestanda problem.</span><span class="sxs-lookup"><span data-stu-id="a48df-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="a48df-110">När du har tagit reda på orsaken till problemet kan du jobba mot en lösning med hjälp av artiklarna om att förbättra SharePoint-prestandan som du kan hitta på https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="a48df-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="a48df-111">Använda F12-verktygsfältet för att diagnosticera prestanda i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a48df-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="a48df-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a48df-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="a48df-113">I den här artikeln används Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="a48df-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="a48df-114">Versioner av F12-utvecklingsverktygen i andra webbläsare har liknande funktioner, men de kan se lite annorlunda ut.</span><span class="sxs-lookup"><span data-stu-id="a48df-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="a48df-115">Information om F12-utvecklingsverktygen finns i:</span><span class="sxs-lookup"><span data-stu-id="a48df-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="a48df-116">Nyheter i F12-verktyg</span><span class="sxs-lookup"><span data-stu-id="a48df-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="a48df-117">Använda verktygen för att F12-utvecklare</span><span class="sxs-lookup"><span data-stu-id="a48df-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="a48df-118">Öppna utvecklingsverktygen genom att trycka på **F12** och sedan klicka på WiFi-ikonen:</span><span class="sxs-lookup"><span data-stu-id="a48df-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Skärm bild av ikonen för att F12-utvecklingsverktygen](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="a48df-120">På fliken **nätverk** trycker du på den gröna uppspelnings knappen för att läsa in en sida.</span><span class="sxs-lookup"><span data-stu-id="a48df-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="a48df-121">Verktyget returnerar alla filer som webbläsaren begär för att få den sida du bad om.</span><span class="sxs-lookup"><span data-stu-id="a48df-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="a48df-122">På följande bild visas en sådan lista.</span><span class="sxs-lookup"><span data-stu-id="a48df-122">The following screen shot shows one such list.</span></span>
  
![Skärm bild av listan med filer som returnerats med en sidbegäran.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="a48df-124">Du kan också se nedladdnings tiderna för filerna till höger som visas i den här skärm bilden.</span><span class="sxs-lookup"><span data-stu-id="a48df-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagram som visar hur lång tid det tar att läsa in begärda sidor från SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="a48df-126">Då får du en bild av hur lång tid det tagit att läsa in filen.</span><span class="sxs-lookup"><span data-stu-id="a48df-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="a48df-127">Den gröna linjen representerar när sidan är klar att renderas av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="a48df-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="a48df-128">Det här kan ge dig en snabb översikt över de olika filerna som kan orsaka långsam sid läsning på din webbplats.</span><span class="sxs-lookup"><span data-stu-id="a48df-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="a48df-129">Konfigurera en icke-anpassad original plan för SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a48df-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="a48df-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a48df-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="a48df-131">Det bästa sättet att kontrol lera webbplatsens prestanda svaga punkter är att konfigurera en helt annan webbplats samling i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a48df-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="a48df-132">På det sättet kan du jämföra alla olika aspekter av din webbplats med vad du skulle få utan att anpassa på sidan.</span><span class="sxs-lookup"><span data-stu-id="a48df-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="a48df-133">Start sidan för OneDrive för företag är ett bra exempel på en separat webbplats samling som sannolikt inte har några anpassningar.</span><span class="sxs-lookup"><span data-stu-id="a48df-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="a48df-134">Visa information om SharePoint-svarshuvuden</span><span class="sxs-lookup"><span data-stu-id="a48df-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="a48df-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a48df-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="a48df-136">I SharePoint Online kan du komma åt den information som skickas tillbaka till webbläsaren i svars huvudet för varje fil.</span><span class="sxs-lookup"><span data-stu-id="a48df-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="a48df-137">Det mest användbara värdet för diagnostisering av prestanda problem är **SPRequestDuration**, som visar hur lång tid det tog för servern att behandlas.</span><span class="sxs-lookup"><span data-stu-id="a48df-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="a48df-138">Det här kan hjälpa till att avgöra om begäran är mycket tungt och krävande för resurserna.</span><span class="sxs-lookup"><span data-stu-id="a48df-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="a48df-139">Det här är det bästa med hur mycket arbete som servern utför för att betjäna sidan.</span><span class="sxs-lookup"><span data-stu-id="a48df-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="a48df-140">Visa information om SharePoint-svarshuvuden</span><span class="sxs-lookup"><span data-stu-id="a48df-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="a48df-141">Kontrol lera att du har F12-verktygen installerat.</span><span class="sxs-lookup"><span data-stu-id="a48df-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="a48df-142">Mer information om hur du laddar ned och installerar de här verktygen finns i [Nyheter i F12-verktyg](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span><span class="sxs-lookup"><span data-stu-id="a48df-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="a48df-143">I F12-verktyg trycker du på den gröna uppspelnings knappen på fliken **nätverk** för att läsa in en sida.</span><span class="sxs-lookup"><span data-stu-id="a48df-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="a48df-144">Klicka på en av. aspx-filerna som returneras av verktyget och klicka sedan på **information**.</span><span class="sxs-lookup"><span data-stu-id="a48df-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Visar information om svars huvudet](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="a48df-146">Klicka på **svarshuvuden**.</span><span class="sxs-lookup"><span data-stu-id="a48df-146">Click **Response headers**.</span></span>

    ![Diagram som visar URL-adressen för svars huvudet](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="a48df-148">Vad orsakar prestanda problem i SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="a48df-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="a48df-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a48df-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="a48df-150">I artikel [navigerings alternativen för SharePoint Online](navigation-options-for-sharepoint-online.md) visas ett exempel på hur du kan använda SPRequestDuration-värdet för att fastställa att den komplexa strukturell navigeringen gjorde att sidan är lång tid att bearbeta på servern.</span><span class="sxs-lookup"><span data-stu-id="a48df-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="a48df-151">Genom att ta ett värde för en original webbplats (utan anpassning) kan du avgöra om en viss fil tar lång tid att läsa in.</span><span class="sxs-lookup"><span data-stu-id="a48df-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="a48df-152">Exemplet som används i [navigerings alternativ för SharePoint Online](navigation-options-for-sharepoint-online.md) är main. aspx-filen.</span><span class="sxs-lookup"><span data-stu-id="a48df-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="a48df-153">Filen innehåller de flesta ASP.NET-koder som körs för sid inläsningen.</span><span class="sxs-lookup"><span data-stu-id="a48df-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="a48df-154">Beroende på vilken webbplatsmall du använder kan du starta. aspx, Home. aspx, default. aspx eller ett annat namn om du anpassar start sidan.</span><span class="sxs-lookup"><span data-stu-id="a48df-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="a48df-155">Om det här numret är betydligt högre än din original plats är det lämpligt att ange att det finns något komplicerat på sidan som orsakar prestanda problem.</span><span class="sxs-lookup"><span data-stu-id="a48df-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="a48df-156">När du har identifierat att det finns ett problem som är specifikt för din webbplats, rekommenderar vi att du tar reda på vad som orsakar dålig prestanda genom att eliminera alla möjliga orsaker, till exempel sid anpassningar, och sedan lägga till dem på en och samma plats.</span><span class="sxs-lookup"><span data-stu-id="a48df-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="a48df-157">När du har tagit bort tillräckligt många anpassningar som sidan fungerar kan du lägga till ytterligare anpassningar en och en.</span><span class="sxs-lookup"><span data-stu-id="a48df-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="a48df-158">Om du till exempel har en mycket komplicerad navigering kan du ändra navigeringen till att inte Visa under webbplatser och sedan kontrol lera utvecklingsverktygen för att se om det gör något.</span><span class="sxs-lookup"><span data-stu-id="a48df-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="a48df-159">Om du har en stor mängd innehåll kan du försöka med att ta bort dem från sidan och se om det här förbättrar saker.</span><span class="sxs-lookup"><span data-stu-id="a48df-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="a48df-160">Om du tar bort alla möjliga orsaker och lägger till dem på en gång, kan du enkelt se vilka funktioner som är det största problemet och sedan arbeta med en lösning.</span><span class="sxs-lookup"><span data-stu-id="a48df-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
