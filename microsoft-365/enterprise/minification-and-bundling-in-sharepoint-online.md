---
title: Förgrening och sammanslagning i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
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
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Lär dig hur du använder teknik för lägre användning och sammanslagning med Web Essentials för att minska HTTP-begäranden och den tid det tar att läsa in sidor i SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694357"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="a680c-103">Förgrening och sammanslagning i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a680c-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="a680c-104">I den här artikeln beskrivs hur du använder teknik förgrening och sammanslagning med Web Essentials för att minska antalet HTTP-begäranden och för att minska tiden det tar att läsa in sidor i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a680c-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="a680c-105">När du anpassar din webbplats kan det leda till att du lägger till ett stort antal extra filer till servern för att stödja anpassningen.</span><span class="sxs-lookup"><span data-stu-id="a680c-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="a680c-106">När du lägger till extra JavaScript, CSS och bilder ökar antalet HTTP-begäranden till servern och det ökar i sin tur tiden det tar att visa en webbsida.</span><span class="sxs-lookup"><span data-stu-id="a680c-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="a680c-107">Om du har flera filer av samma typ kan du samla dem i paket så att de kan laddas ned snabbare.</span><span class="sxs-lookup"><span data-stu-id="a680c-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="a680c-108">För JavaScript- och CSS-filer kan du också använda en metod som kallas för minskning, där du minskar den totala storleken på filer genom att ta bort blanksteg och andra tecken som inte behövs.</span><span class="sxs-lookup"><span data-stu-id="a680c-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="a680c-109">Förgrening och sammanslagning av JavaScript- och CSS-filer med Web Essentials</span><span class="sxs-lookup"><span data-stu-id="a680c-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="a680c-110">Du kan använda programvara från tredje part, till exempel Web Essentials, för att samla CSS- och JavaScript-filer.</span><span class="sxs-lookup"><span data-stu-id="a680c-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a680c-111">Web Essentials är ett community-baserat projekt från tredje part med öppen källkod.</span><span class="sxs-lookup"><span data-stu-id="a680c-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="a680c-112">Programvaran är ett tillägg till Visual Studio 2012 och Visual Studio 2013 och stöds inte av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a680c-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="a680c-113">Om du vill ladda ned Web Essentials kan du besöka webbplatsen på [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="a680c-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="a680c-114">Web Essentials erbjuder två typer av sammanslagning:</span><span class="sxs-lookup"><span data-stu-id="a680c-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="a680c-115">.bundle: för CSS- och JavaScript-filer</span><span class="sxs-lookup"><span data-stu-id="a680c-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="a680c-116">.sprite: för bilder (endast tillgängligt i Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="a680c-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="a680c-117">Du kan använda Web Essentials om du har en befintlig funktion med vissa varumärkeselement som refereras till på en anpassad huvudsida, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a680c-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Skärmbild av märkeselement på anpassad huvudsida](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="a680c-119">**Skapa TE000127218- och CSS-paket i Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="a680c-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="a680c-120">I Visual Studio i Solution Explorer väljer du de filer som du vill ta med i paketet.</span><span class="sxs-lookup"><span data-stu-id="a680c-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="a680c-121">Högerklicka på de markerade filerna och välj Web **Essentials Skapa** \> **JavaScript-paketfil** på snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="a680c-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="a680c-122">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="a680c-122">For example:</span></span> 
    
    ![Skärmbild som visar menyalternativen för Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="a680c-124">Visa resultat för sammanslagning av JavaScript- och CSS-filer</span><span class="sxs-lookup"><span data-stu-id="a680c-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="a680c-125">När du skapar ett JavaScript- och CSS-paket skapar Web Essentials en XML-fil som kallas receptfil som identifierar JavaScript- och CSS-filer samt annan konfigurationsinformation:</span><span class="sxs-lookup"><span data-stu-id="a680c-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Skärmbild av JavaScript och CSS-receptfil](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="a680c-127">Om flaggan för förmining dessutom är inställd på Sant i sammanslagningsreceptet förminskas filerna samtidigt som de samlas.</span><span class="sxs-lookup"><span data-stu-id="a680c-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="a680c-128">Det innebär att nya, minrifierade versioner av JavaScript-filerna har skapats som du kan referera till på huvudsidan.</span><span class="sxs-lookup"><span data-stu-id="a680c-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Skärmbild av flaggan för förmining inställd på sant](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="a680c-130">När du läser in en sida från din webbplats kan du använda utvecklingsverktygen i webbläsaren, till exempel Internet Explorer 11, för att se antalet förfrågningar som skickas till servern och hur lång tid det tog för varje fil att läsas in.</span><span class="sxs-lookup"><span data-stu-id="a680c-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="a680c-131">Följande bild visar resultatet av inläsning av JavaScript- och CSS-filer innan förgreningen.</span><span class="sxs-lookup"><span data-stu-id="a680c-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Skärmbild som visar 80 objekt som hämtas](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="a680c-133">Efter sammanslagningen av CSS- och JavaScript-filerna minskade antalet begäran till 74 och det tog bara något längre tid att ladda ned varje fil individuellt än de ursprungliga filerna:</span><span class="sxs-lookup"><span data-stu-id="a680c-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Skärmbild som visar 74 objekt som hämtas](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="a680c-135">Efter sammanslagningen minskar JavaScript-paketfilen avsevärt från 815 KB till 365 KB:</span><span class="sxs-lookup"><span data-stu-id="a680c-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Skärmbild som visar reducerad nedladdningsstorlek](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="a680c-137">Sammanslagning av bilder genom att skapa en bild-sprite</span><span class="sxs-lookup"><span data-stu-id="a680c-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="a680c-138">På ungefär samma sätt som när du slår samman JavaScript- och CSS-filer kan du samla flera små ikoner och andra vanliga bilder i en större sprite och sedan visa de enskilda bilderna med CSS.</span><span class="sxs-lookup"><span data-stu-id="a680c-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="a680c-139">I stället för att varje enskild bild laddas ned laddas hela sprite-arket ned en gång i användarens webbläsare och cachelagras på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="a680c-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="a680c-140">Det förbättrar prestanda för sidinläsning genom att antalet nedladdningar och resor till webbservern klipps ned.</span><span class="sxs-lookup"><span data-stu-id="a680c-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="a680c-141">**Skapa en bild-sprite i Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="a680c-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="a680c-142">I Visual Studio i Solution Explorer väljer du de filer som du vill ta med i paketet.</span><span class="sxs-lookup"><span data-stu-id="a680c-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="a680c-143">Högerklicka på de markerade filerna och välj **Web Essentials** \> **Skapa bild-sprite** på snabbmenyn.</span><span class="sxs-lookup"><span data-stu-id="a680c-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="a680c-144">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="a680c-144">For example:</span></span> 
    
    ![Skärmbild som visar hur du skapar en bild-sprite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="a680c-146">Välj en plats där sprite-filen ska sparas.</span><span class="sxs-lookup"><span data-stu-id="a680c-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="a680c-147">.sprite-filen är en XML-fil som beskriver inställningarna och filerna i sprite-filen.</span><span class="sxs-lookup"><span data-stu-id="a680c-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="a680c-148">På följande bilder visas ett exempel på en PNG-spritefil och den motsvarande XML-filen .sprite.</span><span class="sxs-lookup"><span data-stu-id="a680c-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Skärmbild av en sprite-fil](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Skärmbild av sprite-XML-fil](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

