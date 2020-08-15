---
title: Begränsningar för SharePoint Online moderna Portal webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: Lär dig mer om prestanda rekommendationer för moderna webbplatser i SharePoint Online, till exempel begränsa samtal till SharePoint-och externa slut punkter.
ms.openlocfilehash: 2afca20183bef8c8f6dda9bdc35a44e5153ef07c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694772"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>Begränsningar för SharePoint Online moderna Portal webbplatser

Den här artikeln innehåller prestanda rekommendationer för moderna Portal webbplatser i SharePoint Online. Använd rikt linjerna i den här artikeln för att optimera prestanda för moderna Portal webbplatser och undvika vanliga prestanda problem.

## <a name="performance-considerations-for-modern-portal-sites"></a>Prestanda överväganden för moderna Portal webbplatser

Från synpunkt av prestanda optimering finns det några egenskaper som gör moderna Portal webbplatser unika. Huvud skillnaden mellan samarbete och Portal webbplatser i SharePoint Online är skala. Portal webbplatser förväntas normalt sett fler sidvyer till ett större antal användare än samarbets webbplatser, och det kan förmodligen finnas mer statiskt innehåll och färre redigerbara resurser. Dessutom är arkitekturen för moderna webbplatser annorlunda jämfört med de klassiska webbplatserna i det mesta av bearbetningen för att återge sidor och körning av kod ska placeras på klienten och inte på servern.

Prestanda optimering för moderna Portal webbplatser är främst inriktad på några övergripande mål:

- Minska den totala storleken på komponenterna på varje webbplats sida
- Avlasta värd av vanliga statiska filer som bilder, formatmallar och skript till CDN
- Begränsa bara samtal till SharePoint och externa slut punkter till vad som behövs
- Undvik dubbletter av samma innehåll

Många av rikt linjerna i den här artikeln fokuserar på att minimera och optimera samtal till SharePoint Online. Om du gör upprepade samtal varje gång en sida laddas påverkas prestanda för användarna eftersom informationen hämtas från tjänsten varje gång även om den inte har ändrats. Det innebär att förfrågningar till SharePoint kan kategoriseras antingen som samtal som är vanliga för alla användare eller samtal som behövs för varje enskild användare. Resultat från dessa två samtals kategorier bör cachelagras för att optimera användar upplevelsen.

>[!NOTE]
>Använd [verktyget för nätverksdiagnostik för SharePoint](https://aka.ms/perftool) som en utgångs punkt för att analysera specifika prestanda mått på webbplats sidorna för SharePoint Online.

## <a name="modern-portal-site-limits-and-recommendations"></a>Moderna Portal webbplats begränsningar och rekommendationer

|**Sten**|**Maximalt Rekommenderat värde**|**Kommentarer**|
|:-----|:-----|:-----|:-----|
|Sidor och nyhets objekt  <br/> |5 000 per webbplats  <br/> |Vi rekommenderar att du begränsar antalet sidor och nyhets objekt på en modern Portal webbplats till under 5 000.  <br/> |
|Webb delar på en sida  <br/> |20 per sida  <br/> |Vi rekommenderar att du använder 20 eller färre webb delar per sida, inklusive både från-programmet och anpassade webb delar. <br/> Mer information finns i [optimera webb dels prestanda i sidor för moderna webbplatser i SharePoint Online](modern-web-part-optimization.md).  <br/> |
|Dynamiska webb delar på en sida  <br/> |4 per sida  <br/> |Dynamiska webb delar som gör en eller flera frågor till SharePoint för att hämta senaste data ska begränsas till 4 per sida. Webb delen _Nyheter_ är ett exempel på en dynamisk webbdel. <br/> Mer information finns i [optimera webb dels prestanda i sidor för moderna webbplatser i SharePoint Online](modern-web-part-optimization.md).    <br/> |
|Säkerhetsgrupper  <br/> |20 per webbplats  <br/> |Antalet säkerhets grupper påverkar skalan för många frågor i moderna Portal webbplatser. Vi rekommenderar att du begränsar antalet säkerhets grupper till så litet som möjligt, med maximalt 20 per webbplats.  <br/> |
|Objekt i webbplats navigering  <br/> |100 per webbplats  <br/> |Vi rekommenderar att du lägger till färre än 100 objekt i webbplatsens navigering och att du använder navigerings kontrollerna utanför lådan.  <br/> Mer information finns i [optimera sid tjock leken i sidor för moderna webbplatser i SharePoint Online](modern-page-weight-optimization.md). <br/> |
|Maximal bild storlek  <br/> |300 kB per bild  <br/> |Vi rekommenderar att du begränsar storleken på bilder till 300kb eller mindre och använder en CDN för att hantera bilder, formatmallar och skript. <br/>Mer information finns i [optimera bilder i SharePoint Online-sidor med moderna webbplatser](modern-image-optimization.md) och [använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).  <br/> |
|Användare med redigerings rättigheter  <br/> |200-användare per webbplats  <br/> |SharePoint Portal-webbplatser är optimerade för att visa och konsumera innehåll. Redigera behörigheter för en portal ska begränsas till en begränsad grupp användare eftersom redigera behörigheter hämtar ytterligare kontroller och kommer därför att få långsammare för dessa användare. Ett stort antal användare med redigerings behörigheter påverkar därför den övergripande upplevelsen. <br/> |
|Tredjeparts-iFrames  <br/> |2 per sida  <br/> |iFrames är oförutsägbara långsamt eftersom de laddar en separat extern sida inklusive allt tillhör ande innehåll som Java Script, CSS och Ramverks element. Om du måste använda iFrames kan du begränsa deras tal till 2 eller färre per sida.<br/> Mer information finns i [optimera iframes i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser](modern-iframe-optimization.md). <br/> |
|Samtal till UPA-tjänsten  <br/> |1 per användare per timme  <br/> |Vi rekommenderar att du ringer inga samtal _per begäran_ till UPA-tjänsten (program vara för användar profil). API-och [PageContext](https://docs.microsoft.com/javascript/api/sp-page-context/pagecontext?view=sp-typescript-latest) i [Microsoft Graph](https://docs.microsoft.com/graph/call-api) kan användas för att fråga efter användar information.  <br/> Om ett samtal till UPA är nödvändigt ringer du ett samtal när det behövs och cachelagrar sedan informationen för åter användning i samma session. |
|Samtal till taxonomi tjänsten  <br/> |5 per användare per timme  <br/> |Vi rekommenderar att du ringer inga samtal _per begäran_ till taxonomi tjänsten. Om det behövs taxonomielement kan du lagra informationen för åter användning under samma session. <br/> Mer information finns i [optimera sid samtal i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser](modern-page-call-optimization.md). <br/> |

## <a name="related-topics"></a>Relaterade ämnen

[Skapa en felfri SharePoint-Portal](https://docs.microsoft.com/sharepoint/portal-health)

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[SharePoint Online-begränsningar](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Prestanda vägledning för SharePoint online-portaler](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-performance)
