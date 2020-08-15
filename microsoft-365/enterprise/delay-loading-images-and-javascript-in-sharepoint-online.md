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
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Fördröj inläsning av bilder och Java Script i SharePoint Online

I den här artikeln beskrivs hur du kan minska inläsnings tiden för sidor i SharePoint Online genom att använda Java Script för att fördröja inläsning av bilder och även genom att vänta med att läsa in icke-väsentlig Java Script tills du har läst
  
Bilder kan påverka sid hastigheten på SharePoint Online negativt. Som standard är de flesta moderna Internet webbläsare förhämtade bilder när du läser in en HTML-sida. Det kan medföra att sidan blir onödigt långsamt för att laddas om bilderna inte visas på skärmen förrän användaren bläddrar nedåt. Bilderna kan hindra webbläsaren från att läsa in den synliga delen av sidan. Du kan undvika problemet genom att använda Java Script för att hoppa över laddningen av bilderna först. Dessutom kan du ladda ned icke-väsentliga JavaScript-tider på dina SharePoint-sidor. I det här avsnittet beskrivs några metoder som du kan använda för att förbättra sid inläsnings tider med Java Script i SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Förbättra sid inläsnings tid genom att försena bild inläsning på SharePoint Online-sidor med hjälp av Java Script

Du kan använda Java Script för att förhindra att en webbläsare förhämtar bilder. Detta påskyndar den övergripande dokument åter givningen. För att göra det här tar du bort värdet på src-attributet från \<img\> taggen och ersätter det med sökvägen till en fil i ett dataattribut, till exempel: data-src. Till exempel:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Med den här metoden hämtas inte bilderna direkt av webbläsaren. Om bilden redan är i visnings området, säger Java Script till webbläsaren att hämta URL-adressen från dataattributet och infoga den som värde för attributet src. Bilden läses in bara när användaren bläddrar och det kommer att visas.
  
För att det ska hända måste du använda Java Script.
  
I en textfil definierar du funktionen **isElementInViewport ()** för att kontrol lera om ett element finns i den del av webbläsaren som visas för användaren.
  
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

Sedan använder du **isElementInViewport ()** i funktionen **loadItemsInView ()** . Funktionen **loadItemsInView ()** läser in alla bilder som har ett värde för attributet data-src om de ingår i den webbläsare som visas för användaren. Lägga till följande funktion i text filen:
  
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

Slutligen kan du ringa **loadItemsInView ()** inifrån **window. onscroll ()** enligt följande exempel. Då ser du till att alla bilder som finns i visnings området läses in eftersom användarna behöver dem, men inte före. Lägg till följande i text filen:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

För SharePoint Online måste du koppla följande funktion till rullnings händelsen i taggen #s4-arbetsyta \<div\> . Detta beror på att fönster händelserna åsidosätts för att det ska vara öppet i menyfliksområdet.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Spara text filen som en JavaScript-fil med fil namns tillägget. js, till exempel delayLoadImages.js.
  
När du har skrivit delayLoadImages.js kan du lägga till innehållet i filen på en huvud sida i SharePoint Online. Det gör du genom att lägga till en skript länk till sidhuvudet på huvud sidan. När det är på en huvud sida används Java Script på alla sidor på SharePoint Online-webbplatsen som använder den huvud sidans layout. Om du bara tänker använda den här sidan på en sida på din webbplats kan du använda webb delen skript redigeraren för att bädda in JavaScript-filen på sidan. Mer information finns i följande avsnitt:
  
- [Så här: använda en huvud sida för en webbplats i SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [Så här skapar du en sidlayout i SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Exempel: referera till JavaScript delayLoadImages.js-filen från en huvud sida i SharePoint Online
  
För att det ska fungera måste du också referera till jQuery på huvud sidan. I följande exempel kan du se i den inledande sid inläsningen att det bara finns en bild som är laddad, men det finns flera mer på sidan.
  
![Skärm bild som visar en bild som lästs in på sidan](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
På följande skärm bild visas resten av bilderna som laddas ned efter en rullning.
  
![Skärm bild som visar flera inlästa bilder på sidan](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Försenad bild laddning med Java Script kan vara en effektiv metod för att öka prestandan. om den här metoden tillämpas på en offentlig webbplats kan sökmotorer inte heller crawla bilderna på samma sätt som de crawlar en vanligt bild. Det här kan påverka rangordningarna för sökmotorer eftersom metadata på själva bilden inte är så bra förrän sidan laddas. Sök robotar läser bara HTML-koden så att bilderna inte visas som innehåll på sidan. Bilder är ett av de faktorer som används för att rangordna sidor i Sök resultat. Ett sätt att kringgå det här är att använda inledande text för dina bilder.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHub kod exempel: injicera Java Script för att förbättra prestanda

Missa inte artikeln och kod exemplet på [Java Script injektion](https://go.microsoft.com/fwlink/p/?LinkId=524759) på GitHub.
  
## <a name="see-also"></a>Se även

[Webbläsare som stöds i Office 2013 och Microsoft 365-appar för företag](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Så här: använda en huvud sida för en webbplats i SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[Så här skapar du en sidlayout i SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)
