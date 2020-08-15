---
title: Bild optimering för klassiska SharePoint Online-webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
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
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Lär dig hur du använder åter givningar och Sprite för att förbättra bild prestanda på dina klassiska SharePoint Online-publicerings webbplatser.
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694559"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Bild optimering för klassiska SharePoint Online-webbplatser

Laddnings hastigheten för en webb sida beror på den sammanlagda storleken på alla komponenter som behövs för att återge sidan, inklusive bilder, HTML, Java Script och CSS. Bilder är ett bra sätt att göra din webbplats mer tilltalande men storleken på dem påverkar prestanda. Genom att optimera bilder med komprimering och storleks ändring och använda spritor kan du förskjuta effekterna av mycket stora bilder. Med hjälp av bild åter givningar i SharePoint kan du ladda upp en enda stor bild och Visa delar av bilden så att den kan återanvändas i stället för att läsas in igen.

>[!NOTE]
>Det här avsnittet gäller för SharePoint Online Classic för publicerings webbplatser, inte moderna Portal webbplatser. Information om bild optimering i SharePoint Online moderna Portal webbplatser finns i [optimera bilder i SharePoint Online moderna Portal-sidor](modern-image-optimization.md).
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Använda spritor för att påskynda bild inläsningen

|||
|:-----|:-----|
| En bild Sprite innehåller många mindre bilder. Med CSS kan du välja en del av den sammansatta bilden som ska visas på en viss del av sidan med absolut placering. Du flyttar bara en bild runt sidan i stället för att läsa in flera bilder och göra en liten del av bilden synlig i ett litet fönster där den del av bilden som krävs visas för slutanvändaren. SharePoint Online använder sprites för att visa de olika ikonerna i Sprite-spcommon.png.  <br/>  Vad finns här:  <br/>  Bild komprimering  <br/>  Bild optimering  <br/>  Bild åter givningar för SharePoint  <br/> |![Skärm bild av spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Det här kan öka prestandan eftersom du bara laddar ned en bild i stället för flera och sedan cache och återanvändar den bilden. Även om bilden inte är cachelagrad, med en enda bild i stället för flera bilder, minskar den här metoden det totala antalet HTTP-begäranden till servern som minskar sid inläsnings tiden. Det här är egentligen en form av bildfiler. Det här är en mycket praktisk teknik om bilderna inte ändras väldigt ofta, till exempel ikoner, som visas i exemplet ovan. Du kan använda [webb grunderna](https://vswebessentials.com/), en tredje part, öppen källa och ett community-baserat projekt för att enkelt uppnå detta i Microsoft Visual Studio. Mer information finns i [för minskning och buntar i SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=708698).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Använda bild komprimering och optimering för att öka sid inläsningen

Bild komprimering och-optimering är att minska fil storleken på de bilder du använder på webbplatsen. De bästa teknikerna för att minska storleken på en bild är ofta att ändra storlek på bilden till de maximala mått som den visas på webbplatsen. Det finns ingen betydelse för att en bild ska visas större än. Det är ett snabbt och enkelt sätt att se till att bilder har rätt mått genom att använda en bild redigerare för att minska storleken på sidan.
  
När bilderna har rätt storlek är nästa steg att optimera komprimeringen av de här bilderna. Det finns olika verktyg för komprimering och optimering, inklusive foto galleriet och verktyg från tredje part. Den främsta komprimeringen är att minska fil storleken så mycket som möjligt utan att förlora discernible kvalitet för slutanvändarna. Kontrol lera att du testar dina komprimerade filer på en högkvalitativ skärm så att de ser bra ut.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Snabba på sidan Ladda ner med hjälp av bild åter givningar i SharePoint

Bild åter givningar är en funktion i SharePoint Online där du kan använda olika versioner av bilder baserat på fördefinierade bild dimensioner. Det är särskilt viktigt när det finns ett användardefinierat bild innehåll eller om bildens dimensioner, till exempel bredd och höjd, är fasta efter CSS på webbplatsen. Även om en bild är åtgärdad efter CSS laddas den fullständiga upplösnings bilden ändå. I det här fallet kan fil storleken minskas med hjälp av bild åter givningar.
  
> [!NOTE]
> Åter givningar är bara tillgängliga för SharePoint när publicering är aktiverat. Du kan aktivera publicering under inställningar \> webbplats inställningar \> Hantera webbplats funktioner \> SharePoint Server-publicering. Alternativet visas inte på annat sätt.
  
Bild åter givningen ändrar storlek på det här alternativet genom att ta den minsta mått du definierar, antingen bredd eller höjd, och sedan ändra storlek på bilden så att den andra dimensionen automatiskt ändrar storlek på det låsta bredd-breddförhållandet. Som standard beskärs bilden från mitten av de återstående måtten. Om du till exempel definierar en rendering av 100px bred och 50px hög och den ursprungliga bilden är 1000px bred och 800px hög kommer den att ändras så att 800px-dimensionen är 50px och 1000px-dimensionen (nu 62.5 px) beskärs från mitten av bilden.
  
Stegen är relativt enkla men för bilder för att använda åter givningarna måste renderingarna vara på SharePoint-webbplatsen innan du lägger till bilderna. Dessutom måste du också ha SharePoint Server Publishing-infrastrukturen (webbplats samlings nivå) och SharePoint Server-publicering (webbplats nivå) aktiverat.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Lägga till en bild åter givning för att snabba på sid inläsningen
  
1. Kontrol lera att användar kontot som utför den här proceduren har minst behörigheten design för webbplats samlingens översta nivå och att webbplatsen publiceras på en webb sida.

2. Gå till webbplatsen på den högsta nivån i en webbläsare.

3. Välj ikonen **Inställningar** .

4. I avsnittet **utseende** på sidan **webbplats inställningar** ser du de inbyggda bild åter givningarna.

    Du kan använda slut av kartongerna eller välja **bild åter givningar** för att skapa en ny.

    ![Skärmdump av bild åter givning](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. På sidan **bild åter givningar** väljer du **Lägg till nytt objekt**.

    ![Skärm bild av Lägg till nytt objekt](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Ange ett namn för åter givningen i rutan **namn** på sidan **ny bild åter givning** .

7. I text rutorna **Bredd** och **höjd** anger du bredd och höjd i bild punkter för åter givningen och väljer sedan **Spara**.

    ![Skärm bild av bild åter givnings namnet](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Anpassad beskärning med bild åter givningar

Som standard skapas en bild åter givning från bildens mitt. Du kan justera bild åter givningen för enskilda bilder genom att beskära den del av bilden som du vill använda. Du kan beskära bilderna på individuell basis per åter givning. Att beskära bilderna går snabbare att läsa in sidan med hjälp av SharePoint-BLOB-cachen för att skapa en version av bilden för varje åter givning. Detta gör att Server belastningen minskar eftersom bilden endast är storleks änd rad en gång och att den är klar att fungera för slutanvändare flera gånger. Mer information om hur du beskär en bild åter givning finns i [beskära en bild åter givning](https://go.microsoft.com/fwlink/p/?LinkId=525626).
  

