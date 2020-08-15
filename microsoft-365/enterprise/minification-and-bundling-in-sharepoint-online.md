---
title: För minskning och buntar i SharePoint Online
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
description: Lär dig hur du använder för minskning-och bunt-teknik med Web Essentials för att minska HTTP-begäranden och hur lång tid det tar att ladda sidor i SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694357"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="66b05-103">För minskning och buntar i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="66b05-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="66b05-104">I den här artikeln beskrivs hur du använder för minskning-och bunt-teknik med Web Essentials för att minska antalet HTTP-begäranden och för att minska tiden det tar att ladda sidor i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="66b05-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="66b05-105">När du anpassar din webbplats kan du lägga till ett stort antal extra filer på servern för att stödja anpassningen.</span><span class="sxs-lookup"><span data-stu-id="66b05-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="66b05-106">Om du lägger till extra Java Script, CSS och bilder ökas antalet HTTP-begäranden till den server som i sin tur ökar den tid det tar att visa en webb sida.</span><span class="sxs-lookup"><span data-stu-id="66b05-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="66b05-107">Om du har flera filer av samma typ kan du samla dessa filer för att kunna ladda ner dessa filer snabbare.</span><span class="sxs-lookup"><span data-stu-id="66b05-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="66b05-108">För Java Script-och CSS-filer kan du också använda en metod som heter för minskning, där du minskar storleken på filer genom att ta bort blank steg och andra tecken som inte behövs.</span><span class="sxs-lookup"><span data-stu-id="66b05-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="66b05-109">För minskning och buntar Java Script och CSS-filer med webb grunderna</span><span class="sxs-lookup"><span data-stu-id="66b05-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="66b05-110">Du kan använda tredjepartsprogram som Web Essentials för att paketera CSS-och JavaScript-filer.</span><span class="sxs-lookup"><span data-stu-id="66b05-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66b05-111">Web Essentials är en tredje part, öppen källa, community-baserat projekt.</span><span class="sxs-lookup"><span data-stu-id="66b05-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="66b05-112">Program varan är ett tillägg till Visual Studio 2012 och Visual Studio 2013 och stöds inte av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66b05-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="66b05-113">Om du vill ladda ned Web Essentials går du till webbplatsen [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="66b05-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="66b05-114">Web Essentials har två typer av bunt:</span><span class="sxs-lookup"><span data-stu-id="66b05-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="66b05-115">. paketera: för CSS-och JavaScript-filer</span><span class="sxs-lookup"><span data-stu-id="66b05-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="66b05-116">. Sprite: för bilder (endast tillgängligt i Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="66b05-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="66b05-117">Du kan använda Web Essentials om du har en befintlig funktion med vissa märkes element som refereras till i en anpassad huvud sida, till exempel:</span><span class="sxs-lookup"><span data-stu-id="66b05-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Skärm bild av varumärkes elementet på en anpassad huvud sida](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="66b05-119">**Skapa en TE000127218 och ett CSS-paket i Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="66b05-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="66b05-120">I Visual Studio, i lösnings Utforskaren, väljer du de filer som du vill ta med i paketet.</span><span class="sxs-lookup"><span data-stu-id="66b05-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="66b05-121">Högerklicka på de markerade filerna och välj sedan **Web Essentials** \> **create JavaScript-fil** på snabb menyn.</span><span class="sxs-lookup"><span data-stu-id="66b05-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="66b05-122">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="66b05-122">For example:</span></span> 
    
    ![Skärm bild som visar meny alternativ i Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="66b05-124">Visa resultatet av en bunts-och CSS-filer</span><span class="sxs-lookup"><span data-stu-id="66b05-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="66b05-125">När du skapar ett Java Script-och CSS-paket skapar Web Essentials en XML-fil som heter en recept fil som identifierar Java Script-och CSS-filer samt annan konfigurations information:</span><span class="sxs-lookup"><span data-stu-id="66b05-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Skärm bild av JavaScript-och recept filen i CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="66b05-127">Om flaggan flaggan är angiven till true i ett beskrivande recept måste filerna vara reducerade och sammanlänkade med varandra.</span><span class="sxs-lookup"><span data-stu-id="66b05-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="66b05-128">Det innebär att nya, minified versioner av JavaScript-filerna skapades som du kan referera till på huvud sidan.</span><span class="sxs-lookup"><span data-stu-id="66b05-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Skärm bild av flaggan flaggan inställd på True](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="66b05-130">När du laddar en sida från din webbplats kan du använda utvecklingsverktygen från webbläsaren, till exempel Internet Explorer 11, för att se hur många förfrågningar som skickats till servern och hur lång tid varje fil tar att läsa in.</span><span class="sxs-lookup"><span data-stu-id="66b05-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="66b05-131">Följande bild är resultatet av inläsning av Java Script-och CSS-filer före för minskning.</span><span class="sxs-lookup"><span data-stu-id="66b05-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Skärm bild som visar 80 objekt som hämtas](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="66b05-133">När du har sammanställt CSS-och JavaScript-filer tillsammans tar antalet begär Anden som tagits bort till 74 och varje fil bara några gånger längre än de ursprungliga filerna att laddas ned individuellt:</span><span class="sxs-lookup"><span data-stu-id="66b05-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Skärm bild som visar 74 objekt som hämtas](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="66b05-135">När du är uppkopplad minskas filen med JavaScript-paketet markant från 815KB till 365KB:</span><span class="sxs-lookup"><span data-stu-id="66b05-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Skärm bild som visar minskad nedladdnings storlek](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="66b05-137">Skapar bilder genom att skapa en bild Sprite</span><span class="sxs-lookup"><span data-stu-id="66b05-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="66b05-138">Precis som du använder för att paketera Java Script och CSS-filer kan du kombinera många små ikoner och andra vanliga bilder till ett större Sprite-ark och sedan använda CSS för att visa de enskilda bilderna.</span><span class="sxs-lookup"><span data-stu-id="66b05-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="66b05-139">I stället för att hämta varje enskild bild hämtas Sprite-sidan av användarens webbläsare och cachelagrar den på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="66b05-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="66b05-140">Detta förbättrar prestanda i sid inläsningen genom att sänka antalet hämtningar och avrunda resor till webb servern.</span><span class="sxs-lookup"><span data-stu-id="66b05-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="66b05-141">**Skapa en bild Sprite i Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="66b05-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="66b05-142">I Visual Studio, i lösnings Utforskaren, väljer du de filer som du vill ta med i paketet.</span><span class="sxs-lookup"><span data-stu-id="66b05-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="66b05-143">Högerklicka på de markerade filerna och välj **Web Essentials** \> **Skapa bild Sprite** på snabb menyn.</span><span class="sxs-lookup"><span data-stu-id="66b05-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="66b05-144">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="66b05-144">For example:</span></span> 
    
    ![Skärm bild som visar hur du skapar en bild Sprite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="66b05-146">Välj en plats där du vill spara Sprite-filen.</span><span class="sxs-lookup"><span data-stu-id="66b05-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="66b05-147">Sprite-filen är en XML-fil som beskriver inställningarna och filerna i spriten.</span><span class="sxs-lookup"><span data-stu-id="66b05-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="66b05-148">Här visas ett exempel på en sprite PNG-fil och dess motsvarande. Sprite-XML-fil.</span><span class="sxs-lookup"><span data-stu-id="66b05-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Skärm bild av en sprite-fil](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Skärm bild av XML-filen Sprite](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

