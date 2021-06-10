---
title: Använda objektcachen med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
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
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint server 2013 lokalt och i SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696727"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>Använda objektcachen med SharePoint Online

I den här artikeln förklaras skillnaden mellan att använda objektcachen i SharePoint server 2013 lokalt och i SharePoint Online.
  
Det finns betydande negativ inverkan med att lita på objektcachen i SharePoint Online-distribution. Beroende av objektcachen i SharePoint Online minskar tillförlitligheten på sidan. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>Hur objektcachen SharePoint Online SharePoint Server 2013 fungerar

När SharePoint server 2013 ligger lokalt har kunden privata frontend-webbservrar som fungerar som värd för objektcachen. Det innebär att cachen är dedikerad till en kund och begränsas bara av hur mycket minne som är tillgängligt och tilldelas till objektcachen. Eftersom endast en kund bearbetas i det lokala scenariot har frontend-webbservrarna vanligtvis användare som gör begäranden till samma webbplatser om och om igen. Det innebär att cachen snabbt blir full och förblir full av listfrågeresultat och SharePoint objekt som användarna begär regelbundet.
  
![Visar trafik och inläsning till lokala frontend-webbservrar](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
Därför kan inläsningstiden för sidan bli bättre andra gången en användare besöker en sida. När samma sida har läses in minst fyra gånger cachelagras sidan på alla frontend-webbservrar.
  
I SharePoint online finns det många fler servrar men också många fler webbplatser. Varje användare kan ansluta till en annan frontend-webbserver som inte har cachen ifylld. Eller så kanske cachen fylls i för en server, men nästa användare på den frontend-webbservern begär en sida från en annan webbplats. Eller, även om nästa användare begär samma sida som vid föregående besök, kan de belastningsutjämnas till en annan frontend-webbserver som inte har den sidan i cachen. I det sista fallet hjälper cachelagring inte användarna alls.
  
I följande bild representerar varje punkt en sida som en användare begär och där den cachelagras. Olika färger representerar olika kunder som delar på användningen av SaaS-infrastrukturen.
  
![Visar resultat för cachelagrade objekt i SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
Som du ser i diagrammet är chansen att en viss användare ska komma till en server med den cachelagrade versionen av sidan liten. På grund av det stora dataflödet och det faktum att servrarna delas mellan många webbplatser, varar cachen dessutom inte länge eftersom det bara finns så mycket utrymme för cachelagring.
  
Att förlita sig på att användarna får cachelagrade objekt är därför inte ett effektivt sätt att säkerställa kvaliteten på användarupplevelsen och sidinläsningstiderna i SharePoint Online.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>Om vi inte kan lita på objektcachen för att förbättra prestanda i SharePoint Online, vad ska vi använda i stället?

Eftersom du inte bör förlita dig på cachelagring i SharePoint Online, bör du utvärdera alternativa design metoder för SharePoint anpassningar som använder objektcachen. Det här innebär att använda metoder för prestandaproblem som inte förlitar sig på cachelagrade objekt för att kunna ge bra resultat för användare. Det här beskrivs i några av de andra artiklarna i den här serien och omfattar:
  
- [Navigeringsalternativ för SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Förgrening och sammanslagning i SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Fördröja inläsning av bilder och JavaScript i SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

