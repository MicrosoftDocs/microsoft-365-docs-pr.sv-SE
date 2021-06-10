---
title: Fördröja inläsning av bilder och JavaScript i SharePoint Online
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
description: Lär dig hur du kan minska inläsningstiden för SharePoint onlinesidor genom att använda JavaScript för att fördröja inläsningen av bilder och javascript som inte behövs.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919170"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Fördröja inläsning av bilder och JavaScript i SharePoint Online

I den här artikeln beskrivs hur du kan minska inläsningstiden för SharePoint Online-sidor genom att använda JavaScript för att fördröja inläsningen av bilder och även genom att vänta med att läsa in Icke-viktiga JavaScript tills sidan har lästs in.
  
Bilder kan påverka inläsningshastigheten för sidor i SharePoint Online. Som standard hämtar de flesta moderna webbläsare bilder i förväg när de läser in en HTML-sida. Det kan leda till att sidan tar onödigt lång tid att läsa in om bilderna inte visas på skärmen förrän användaren rullar nedåt. Bilderna kan blockera webbläsaren från att läsa in den synliga delen av sidan. Du kan komma runt det här problemet genom att använda JavaScript för att hoppa över inläsningen av bilder först. Inläsning av JavaScript som inte behövs kan också leda till långsamma nedladdningstider på SharePoint sidor. I det här avsnittet beskrivs några metoder du kan använda för att förbättra sidinläsningstiderna med JavaScript SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Förbättra sidladdningstiderna genom att fördröja inläsningen av bilder SharePoint onlinesidor med JavaScript

Du kan använda JavaScript för att förhindra att en webbläsare hämtar bilder i förväg. Det gör att den övergripande dokumentåtergivningen går snabbare. Om du vill göra det här tar du bort värdet för src-attributet från taggen och ersätter det med sökvägen till en fil i ett \<img\> dataattribut, till exempel: data-src. Till exempel:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Med den här metoden laddar webbläsaren inte ned bilderna direkt. Om bilden redan finns i visningsområdet talar JavaScript om för webbläsaren att hämta URL-adressen från dataattributet och infoga den som värde för src-attributet. Bilden läses bara in när användaren rullar och den kommer in i visningsläge.
  
Om du vill göra allt detta måste du använda JavaScript.
  
Definiera funktionen **isElementInViewport()** i en textfil för att kontrollera om ett element finns i den del av webbläsaren som är synlig för användaren.
  
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

Använd sedan **isElementInViewport()** i funktionen **loadItemsInView().** Funktionen **loadItemsInView()** laddar alla bilder som har ett värde för attributet data-src, om de finns i den del av webbläsaren som är synlig för användaren. Lägg till följande funktion i textfilen:
  
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

Anropa slutligen **loadItemsInView()** inifrån **window.onscroll()** enligt följande exempel. Detta garanterar att alla bilder som finns i visningsområdet laddas när användaren behöver dem, men inte tidigare. Lägg till följande i textfilen:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

För SharePoint Online måste du koppla följande funktion till rullningshändelsen på \<div\> #s4-workspace-taggen. Det beror på att fönsterhändelserna åsidosätts för att säkerställa att menyfliksområdet förblir kopplat till början av sidan.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Spara textfilen som en JavaScript-fil med filnamnstillägget .js till exempel delayLoadImages.js.
  
När du är klar med delayLoadImages.js kan du lägga till innehållet i filen på en huvudsida i SharePoint Online. Det gör du genom att lägga till en skriptlänk i sidhuvudet på huvudsidan. När JavaScript-koderna finns på en huvudsida används de på alla sidor i SharePoint Online-webbplatsen där huvuds sidlayouten används. Om du bara tänker använda det på en sida på webbplatsen kan du använda skriptredigeringswebbdelen till att bädda in JavaScript-skriptet på sidan. Mer information finns i följande avsnitt:
  
- [Så här gör du för att: Använda en huvudsida för en webbplats SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [Så här gör du för att: Skapa en sidlayout SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Exempel: Referera till JavaScript-delayLoadImages.js från en huvudsida i SharePoint Online
  
För att det här ska fungera måste du också referera till jQuery på huvudsidan. I följande exempel kan du se att i den första sidinläsningen finns det bara en bild inläst, men det finns flera bilder på sidan.
  
![Skärmbild som visar en bild som lästs in på sidan](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
På följande skärmbild visas resten av bilderna som laddas ned när de rullas in i vyn.
  
![Skärmbild med flera bilder laddade på sidan](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Att fördröja bildläsningen med hjälp av JavaScript kan vara en effektiv teknik för att öka prestandan. Men om tekniken används på en offentlig webbplats kan sökmotorer inte crawla bilder på samma sätt som de skulle crawla bilder som skapats regelbundet. Det kan påverka rangordningen på sökmotorer eftersom metadata på själva bilden inte verkligen finns där förrän sidan läses in. Sökmotor crawlare läser bara HTML-koden och ser därför inte bilderna som innehåll på sidan. Bilder är en av de faktorer som används för att rangordna sidor i sökresultat. Ett sätt att komma runt det här problemet är att använda introduktionstext för bilder.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHub kodexempel: Mata in JavaScript för att förbättra prestanda

Missa inte artikeln och kodexeskriptet på [JavaScript-rutor](https://go.microsoft.com/fwlink/p/?LinkId=524759) som visas på GitHub.
  
## <a name="see-also"></a>Se även

[Webbläsare som stöds i Office 2013 och Microsoft 365-appar för företag](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Så här gör du för att: Använda en huvudsida för en webbplats SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[Så här gör du för att: Skapa en sidlayout SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)