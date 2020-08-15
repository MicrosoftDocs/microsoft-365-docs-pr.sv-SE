---
title: Använda webb delen för innehålls sökning i stället för webb delen innehålls fråga för att förbättra prestanda i SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Lär dig att öka prestandan genom att ersätta webb delen innehålls fråga med webb delen innehålls sökning i SharePoint Server 2013 och SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694919"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Använda webb delen för innehålls sökning i stället för webb delen innehålls fråga för att förbättra prestanda i SharePoint Online

I den här artikeln beskrivs hur du ökar prestandan genom att ersätta webb delen innehålls fråga med webb delen innehålls sökning i SharePoint Server 2013 och SharePoint Online.
  
En av de mest kraftfulla funktionerna i SharePoint Server 2013 och SharePoint Online är webb delen innehålls sökning (INNEHÅLLS sökning). Den här webb delen använder Sök indexet för att snabbt hämta resultat som visas för användaren. Använd webb delen innehålls sökning i stället för webb delen innehålls fråga (INNEHÅLLS fråga) på dina sidor för att förbättra datorns prestanda.
  
Om du använder en webbdel för innehålls sökning via en webbdel för innehålls fråga kommer nästan alltid att få betydligt bättre prestanda i sid belastning på SharePoint Online. Det finns lite extra konfiguration för att få rätt fråga, men fördelarna är bättre prestanda och presenten glädjer användare.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Jämför prestanda ökningen du får genom att använda webb delen för innehålls sökning i stället för webb delen innehålls fråga

I följande exempel visas de relativa prestanda vinster du kan få när du använder en webbdel för innehålls sökning i stället för en webbdel för innehålls fråga. Effekterna är mer uppenbara med en komplex webbplats struktur och mycket breda innehålls frågor.
  
Den här exempel webbplatsen har följande egenskaper:
  
- 8 nivåer av under webbplatser.
    
- Listor med den anpassade innehålls typen "frukt".
    
- I webb delen är innehålls frågan brett och returnerar alla objekt med innehålls typen "frukt".
    
- I exemplet används endast 50-objekt på åtta webbplatser. Effekterna blir ännu mer uttalade för webbplatser med mer innehåll.
    
Här visas en skärm bild av resultatet av webb delen för innehålls fråga.
  
![Bild som visar innehålls fråga för webbdel](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
I Internet Explorer går du till fliken **nätverk** i F12-utvecklingsverktygen för att se informationen för svars huvudet. I följande skärmdump är värdet för **SPRequestDuration** för den här sidans laddning 924 millisekunder. 
  
![Skärm bild som visar begärande-varaktighet för 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** anger hur mycket arbete som utförs på servern för att förbereda sidan. Om du byter innehåll efter webb delar från en fråga med innehåll efter Sök webb delar drastiskt minskar den tid det tar att rendera sidan. En sida med en motsvarande webb delen för innehålls sökning, som returnerar samma antal resultat, har ett **SPRequestDuration** -värde på 106 millisekunder som visas i den här skärm bilden: 
  
![Skärm bild som visar varaktigheten för en aktivitet med 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Lägga till en webbdel för innehålls sökning i SharePoint Online

Att lägga till en webbdel för innehålls sökning liknar en vanlig innehålls fråga. Se avsnittet  *"lägga till en webbdel för innehålls sökning"*  i [Konfigurera en webbdel för innehålls sökning i SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>Skapa rätt Sök fråga för webb delen innehålls sökning

När du har lagt till en webbdel för innehålls sökning kan du förfina sökningen och returnera de objekt du vill. Detaljerade anvisningar om hur du gör detta finns i avsnittet  *"Visa innehåll genom att konfigurera en avancerad fråga i en webbdel för innehålls sökning"*  i [Konfigurera en webbdel för innehålls sökning i SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="query-building-and-testing-tool"></a>Verktyg för att skapa frågor

Ett verktyg för att skapa och testa komplexa frågor finns i [verktyget för Sök frågor](https://sp2013searchtool.codeplex.com/) på Codeplex. 
  

