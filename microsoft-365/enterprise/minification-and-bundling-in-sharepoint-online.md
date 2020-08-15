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
# <a name="minification-and-bundling-in-sharepoint-online"></a>För minskning och buntar i SharePoint Online

I den här artikeln beskrivs hur du använder för minskning-och bunt-teknik med Web Essentials för att minska antalet HTTP-begäranden och för att minska tiden det tar att ladda sidor i SharePoint Online.
  
När du anpassar din webbplats kan du lägga till ett stort antal extra filer på servern för att stödja anpassningen. Om du lägger till extra Java Script, CSS och bilder ökas antalet HTTP-begäranden till den server som i sin tur ökar den tid det tar att visa en webb sida. Om du har flera filer av samma typ kan du samla dessa filer för att kunna ladda ner dessa filer snabbare.
  
För Java Script-och CSS-filer kan du också använda en metod som heter för minskning, där du minskar storleken på filer genom att ta bort blank steg och andra tecken som inte behövs.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>För minskning och buntar Java Script och CSS-filer med webb grunderna

Du kan använda tredjepartsprogram som Web Essentials för att paketera CSS-och JavaScript-filer.
  
> [!IMPORTANT]
> Web Essentials är en tredje part, öppen källa, community-baserat projekt. Program varan är ett tillägg till Visual Studio 2012 och Visual Studio 2013 och stöds inte av Microsoft. Om du vill ladda ned Web Essentials går du till webbplatsen [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials har två typer av bunt:
  
- . paketera: för CSS-och JavaScript-filer
    
- . Sprite: för bilder (endast tillgängligt i Visual Studio 2013)
    
Du kan använda Web Essentials om du har en befintlig funktion med vissa märkes element som refereras till i en anpassad huvud sida, till exempel:
  
![Skärm bild av varumärkes elementet på en anpassad huvud sida](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Skapa en TE000127218 och ett CSS-paket i Web Essentials**
  
1. I Visual Studio, i lösnings Utforskaren, väljer du de filer som du vill ta med i paketet.
    
2. Högerklicka på de markerade filerna och välj sedan **Web Essentials** \> **create JavaScript-fil** på snabb menyn. Till exempel: 
    
    ![Skärm bild som visar meny alternativ i Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Visa resultatet av en bunts-och CSS-filer

När du skapar ett Java Script-och CSS-paket skapar Web Essentials en XML-fil som heter en recept fil som identifierar Java Script-och CSS-filer samt annan konfigurations information: 
  
![Skärm bild av JavaScript-och recept filen i CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Om flaggan flaggan är angiven till true i ett beskrivande recept måste filerna vara reducerade och sammanlänkade med varandra. Det innebär att nya, minified versioner av JavaScript-filerna skapades som du kan referera till på huvud sidan.
  
![Skärm bild av flaggan flaggan inställd på True](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
När du laddar en sida från din webbplats kan du använda utvecklingsverktygen från webbläsaren, till exempel Internet Explorer 11, för att se hur många förfrågningar som skickats till servern och hur lång tid varje fil tar att läsa in.
  
Följande bild är resultatet av inläsning av Java Script-och CSS-filer före för minskning.
  
![Skärm bild som visar 80 objekt som hämtas](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
När du har sammanställt CSS-och JavaScript-filer tillsammans tar antalet begär Anden som tagits bort till 74 och varje fil bara några gånger längre än de ursprungliga filerna att laddas ned individuellt:
  
![Skärm bild som visar 74 objekt som hämtas](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
När du är uppkopplad minskas filen med JavaScript-paketet markant från 815KB till 365KB:
  
![Skärm bild som visar minskad nedladdnings storlek](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Skapar bilder genom att skapa en bild Sprite

Precis som du använder för att paketera Java Script och CSS-filer kan du kombinera många små ikoner och andra vanliga bilder till ett större Sprite-ark och sedan använda CSS för att visa de enskilda bilderna. I stället för att hämta varje enskild bild hämtas Sprite-sidan av användarens webbläsare och cachelagrar den på den lokala datorn. Detta förbättrar prestanda i sid inläsningen genom att sänka antalet hämtningar och avrunda resor till webb servern.
  
 **Skapa en bild Sprite i Web Essentials**
  
1. I Visual Studio, i lösnings Utforskaren, väljer du de filer som du vill ta med i paketet.
    
2. Högerklicka på de markerade filerna och välj **Web Essentials** \> **Skapa bild Sprite** på snabb menyn. Till exempel: 
    
    ![Skärm bild som visar hur du skapar en bild Sprite](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Välj en plats där du vill spara Sprite-filen. Sprite-filen är en XML-fil som beskriver inställningarna och filerna i spriten. Här visas ett exempel på en sprite PNG-fil och dess motsvarande. Sprite-XML-fil.
    
    ![Skärm bild av en sprite-fil](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Skärm bild av XML-filen Sprite](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

