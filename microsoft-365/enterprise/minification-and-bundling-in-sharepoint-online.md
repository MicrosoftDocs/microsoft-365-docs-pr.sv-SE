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
# <a name="minification-and-bundling-in-sharepoint-online"></a>Förgrening och sammanslagning i SharePoint Online

I den här artikeln beskrivs hur du använder teknik förgrening och sammanslagning med Web Essentials för att minska antalet HTTP-begäranden och för att minska tiden det tar att läsa in sidor i SharePoint Online.
  
När du anpassar din webbplats kan det leda till att du lägger till ett stort antal extra filer till servern för att stödja anpassningen. När du lägger till extra JavaScript, CSS och bilder ökar antalet HTTP-begäranden till servern och det ökar i sin tur tiden det tar att visa en webbsida. Om du har flera filer av samma typ kan du samla dem i paket så att de kan laddas ned snabbare.
  
För JavaScript- och CSS-filer kan du också använda en metod som kallas för minskning, där du minskar den totala storleken på filer genom att ta bort blanksteg och andra tecken som inte behövs.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Förgrening och sammanslagning av JavaScript- och CSS-filer med Web Essentials

Du kan använda programvara från tredje part, till exempel Web Essentials, för att samla CSS- och JavaScript-filer.
  
> [!IMPORTANT]
> Web Essentials är ett community-baserat projekt från tredje part med öppen källkod. Programvaran är ett tillägg till Visual Studio 2012 och Visual Studio 2013 och stöds inte av Microsoft. Om du vill ladda ned Web Essentials kan du besöka webbplatsen på [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials erbjuder två typer av sammanslagning:
  
- .bundle: för CSS- och JavaScript-filer
    
- .sprite: för bilder (endast tillgängligt i Visual Studio 2013)
    
Du kan använda Web Essentials om du har en befintlig funktion med vissa varumärkeselement som refereras till på en anpassad huvudsida, till exempel:
  
![Skärmbild av märkeselement på anpassad huvudsida](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Skapa TE000127218- och CSS-paket i Web Essentials**
  
1. I Visual Studio i Solution Explorer väljer du de filer som du vill ta med i paketet.
    
2. Högerklicka på de markerade filerna och välj Web **Essentials Skapa** \> **JavaScript-paketfil** på snabbmenyn. Till exempel: 
    
    ![Skärmbild som visar menyalternativen för Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Visa resultat för sammanslagning av JavaScript- och CSS-filer

När du skapar ett JavaScript- och CSS-paket skapar Web Essentials en XML-fil som kallas receptfil som identifierar JavaScript- och CSS-filer samt annan konfigurationsinformation: 
  
![Skärmbild av JavaScript och CSS-receptfil](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Om flaggan för förmining dessutom är inställd på Sant i sammanslagningsreceptet förminskas filerna samtidigt som de samlas. Det innebär att nya, minrifierade versioner av JavaScript-filerna har skapats som du kan referera till på huvudsidan.
  
![Skärmbild av flaggan för förmining inställd på sant](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
När du läser in en sida från din webbplats kan du använda utvecklingsverktygen i webbläsaren, till exempel Internet Explorer 11, för att se antalet förfrågningar som skickas till servern och hur lång tid det tog för varje fil att läsas in.
  
Följande bild visar resultatet av inläsning av JavaScript- och CSS-filer innan förgreningen.
  
![Skärmbild som visar 80 objekt som hämtas](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Efter sammanslagningen av CSS- och JavaScript-filerna minskade antalet begäran till 74 och det tog bara något längre tid att ladda ned varje fil individuellt än de ursprungliga filerna:
  
![Skärmbild som visar 74 objekt som hämtas](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Efter sammanslagningen minskar JavaScript-paketfilen avsevärt från 815 KB till 365 KB:
  
![Skärmbild som visar reducerad nedladdningsstorlek](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Sammanslagning av bilder genom att skapa en bild-sprite

På ungefär samma sätt som när du slår samman JavaScript- och CSS-filer kan du samla flera små ikoner och andra vanliga bilder i en större sprite och sedan visa de enskilda bilderna med CSS. I stället för att varje enskild bild laddas ned laddas hela sprite-arket ned en gång i användarens webbläsare och cachelagras på den lokala datorn. Det förbättrar prestanda för sidinläsning genom att antalet nedladdningar och resor till webbservern klipps ned.
  
 **Skapa en bild-sprite i Web Essentials**
  
1. I Visual Studio i Solution Explorer väljer du de filer som du vill ta med i paketet.
    
2. Högerklicka på de markerade filerna och välj **Web Essentials** \> **Skapa bild-sprite** på snabbmenyn. Till exempel: 
    
    ![Skärmbild som visar hur du skapar en bild-sprite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Välj en plats där sprite-filen ska sparas. .sprite-filen är en XML-fil som beskriver inställningarna och filerna i sprite-filen. På följande bilder visas ett exempel på en PNG-spritefil och den motsvarande XML-filen .sprite.
    
    ![Skärmbild av en sprite-fil](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Skärmbild av sprite-XML-fil](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

