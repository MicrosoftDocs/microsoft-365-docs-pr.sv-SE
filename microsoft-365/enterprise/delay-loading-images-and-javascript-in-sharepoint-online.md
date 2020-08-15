---
title: Fördröj inläsning av bilder och Java Script i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Lär dig hur du minskar inläsnings tiden för SharePoint Online-sidor genom att använda Java Script för att fördröja inläsning av bilder och icke-väsentliga Java Script
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694689"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="91cd7-103">Fördröj inläsning av bilder och Java Script i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="91cd7-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="91cd7-104">I den här artikeln beskrivs hur du kan minska inläsnings tiden för sidor i SharePoint Online genom att använda Java Script för att fördröja inläsning av bilder och även genom att vänta med att läsa in icke-väsentlig Java Script tills du har läst</span><span class="sxs-lookup"><span data-stu-id="91cd7-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="91cd7-105">Bilder kan påverka sid hastigheten på SharePoint Online negativt.</span><span class="sxs-lookup"><span data-stu-id="91cd7-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="91cd7-106">Som standard är de flesta moderna Internet webbläsare förhämtade bilder när du läser in en HTML-sida.</span><span class="sxs-lookup"><span data-stu-id="91cd7-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="91cd7-107">Det kan medföra att sidan blir onödigt långsamt för att laddas om bilderna inte visas på skärmen förrän användaren bläddrar nedåt.</span><span class="sxs-lookup"><span data-stu-id="91cd7-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="91cd7-108">Bilderna kan hindra webbläsaren från att läsa in den synliga delen av sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="91cd7-109">Du kan undvika problemet genom att använda Java Script för att hoppa över laddningen av bilderna först.</span><span class="sxs-lookup"><span data-stu-id="91cd7-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="91cd7-110">Dessutom kan du ladda ned icke-väsentliga JavaScript-tider på dina SharePoint-sidor.</span><span class="sxs-lookup"><span data-stu-id="91cd7-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="91cd7-111">I det här avsnittet beskrivs några metoder som du kan använda för att förbättra sid inläsnings tider med Java Script i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="91cd7-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="91cd7-112">Förbättra sid inläsnings tid genom att försena bild inläsning på SharePoint Online-sidor med hjälp av Java Script</span><span class="sxs-lookup"><span data-stu-id="91cd7-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="91cd7-113">Du kan använda Java Script för att förhindra att en webbläsare förhämtar bilder.</span><span class="sxs-lookup"><span data-stu-id="91cd7-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="91cd7-114">Detta påskyndar den övergripande dokument åter givningen.</span><span class="sxs-lookup"><span data-stu-id="91cd7-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="91cd7-115">För att göra det här tar du bort värdet på src-attributet från \<img\> taggen och ersätter det med sökvägen till en fil i ett dataattribut, till exempel: data-src.</span><span class="sxs-lookup"><span data-stu-id="91cd7-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="91cd7-116">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="91cd7-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="91cd7-117">Med den här metoden hämtas inte bilderna direkt av webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="91cd7-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="91cd7-118">Om bilden redan är i visnings området, säger Java Script till webbläsaren att hämta URL-adressen från dataattributet och infoga den som värde för attributet src.</span><span class="sxs-lookup"><span data-stu-id="91cd7-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="91cd7-119">Bilden läses in bara när användaren bläddrar och det kommer att visas.</span><span class="sxs-lookup"><span data-stu-id="91cd7-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="91cd7-120">För att det ska hända måste du använda Java Script.</span><span class="sxs-lookup"><span data-stu-id="91cd7-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="91cd7-121">I en textfil definierar du funktionen **isElementInViewport ()** för att kontrol lera om ett element finns i den del av webbläsaren som visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="91cd7-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="91cd7-122">Sedan använder du **isElementInViewport ()** i funktionen **loadItemsInView ()** .</span><span class="sxs-lookup"><span data-stu-id="91cd7-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="91cd7-123">Funktionen **loadItemsInView ()** läser in alla bilder som har ett värde för attributet data-src om de ingår i den webbläsare som visas för användaren.</span><span class="sxs-lookup"><span data-stu-id="91cd7-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="91cd7-124">Lägga till följande funktion i text filen:</span><span class="sxs-lookup"><span data-stu-id="91cd7-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="91cd7-125">Slutligen kan du ringa **loadItemsInView ()** inifrån **window. onscroll ()** enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="91cd7-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="91cd7-126">Då ser du till att alla bilder som finns i visnings området läses in eftersom användarna behöver dem, men inte före.</span><span class="sxs-lookup"><span data-stu-id="91cd7-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="91cd7-127">Lägg till följande i text filen:</span><span class="sxs-lookup"><span data-stu-id="91cd7-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="91cd7-128">För SharePoint Online måste du koppla följande funktion till rullnings händelsen i taggen #s4-arbetsyta \<div\> .</span><span class="sxs-lookup"><span data-stu-id="91cd7-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="91cd7-129">Detta beror på att fönster händelserna åsidosätts för att det ska vara öppet i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="91cd7-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="91cd7-130">Spara text filen som en JavaScript-fil med fil namns tillägget. js, till exempel delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="91cd7-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="91cd7-131">När du har skrivit delayLoadImages.js kan du lägga till innehållet i filen på en huvud sida i SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="91cd7-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="91cd7-132">Det gör du genom att lägga till en skript länk till sidhuvudet på huvud sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="91cd7-133">När det är på en huvud sida används Java Script på alla sidor på SharePoint Online-webbplatsen som använder den huvud sidans layout.</span><span class="sxs-lookup"><span data-stu-id="91cd7-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="91cd7-134">Om du bara tänker använda den här sidan på en sida på din webbplats kan du använda webb delen skript redigeraren för att bädda in JavaScript-filen på sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="91cd7-135">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="91cd7-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="91cd7-136">Så här: använda en huvud sida för en webbplats i SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="91cd7-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [<span data-ttu-id="91cd7-137">Så här skapar du en sidlayout i SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="91cd7-137">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="91cd7-138">Exempel: referera till JavaScript delayLoadImages.js-filen från en huvud sida i SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="91cd7-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="91cd7-139">För att det ska fungera måste du också referera till jQuery på huvud sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="91cd7-140">I följande exempel kan du se i den inledande sid inläsningen att det bara finns en bild som är laddad, men det finns flera mer på sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Skärm bild som visar en bild som lästs in på sidan](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="91cd7-142">På följande skärm bild visas resten av bilderna som laddas ned efter en rullning.</span><span class="sxs-lookup"><span data-stu-id="91cd7-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Skärm bild som visar flera inlästa bilder på sidan](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="91cd7-144">Försenad bild laddning med Java Script kan vara en effektiv metod för att öka prestandan. om den här metoden tillämpas på en offentlig webbplats kan sökmotorer inte heller crawla bilderna på samma sätt som de crawlar en vanligt bild.</span><span class="sxs-lookup"><span data-stu-id="91cd7-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="91cd7-145">Det här kan påverka rangordningarna för sökmotorer eftersom metadata på själva bilden inte är så bra förrän sidan laddas.</span><span class="sxs-lookup"><span data-stu-id="91cd7-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="91cd7-146">Sök robotar läser bara HTML-koden så att bilderna inte visas som innehåll på sidan.</span><span class="sxs-lookup"><span data-stu-id="91cd7-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="91cd7-147">Bilder är ett av de faktorer som används för att rangordna sidor i Sök resultat.</span><span class="sxs-lookup"><span data-stu-id="91cd7-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="91cd7-148">Ett sätt att kringgå det här är att använda inledande text för dina bilder.</span><span class="sxs-lookup"><span data-stu-id="91cd7-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="91cd7-149">GitHub kod exempel: injicera Java Script för att förbättra prestanda</span><span class="sxs-lookup"><span data-stu-id="91cd7-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="91cd7-150">Missa inte artikeln och kod exemplet på [Java Script injektion](https://go.microsoft.com/fwlink/p/?LinkId=524759) på GitHub.</span><span class="sxs-lookup"><span data-stu-id="91cd7-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="91cd7-151">Se även</span><span class="sxs-lookup"><span data-stu-id="91cd7-151">See also</span></span>

[<span data-ttu-id="91cd7-152">Webbläsare som stöds i Office 2013 och Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="91cd7-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="91cd7-153">Så här: använda en huvud sida för en webbplats i SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="91cd7-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[<span data-ttu-id="91cd7-154">Så här skapar du en sidlayout i SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="91cd7-154">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)
