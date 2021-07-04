---
title: SharePoint Gränser för moderna portalwebbplatser online
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
description: Läs mer om prestandarekommendationer för moderna webbplatser i SharePoint Online, till exempel att begränsa samtal till Sharepoint och externa slutpunkter.
ms.openlocfilehash: 2429869c5397e0260876ee5a765ea18ae3fc42a1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288881"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Gränser för moderna portalwebbplatser online

Den här artikeln innehåller prestandarekommendationer för moderna portalwebbplatser i SharePoint Online. Använd riktlinjerna i den här artikeln för att optimera webbplatsprestanda på moderna portaler och undvika vanliga prestandaproblem.

## <a name="performance-considerations-for-modern-portal-sites"></a>Prestandaöverväganden för moderna portalwebbplatser

När det gäller prestandaoptimering finns det några egenskaper som gör moderna portalwebbplatser unika. Den största skillnaden mellan samarbete och portalwebbplatser i SharePoint Online är skalning. Portalwebbplatser förväntas i allmänhet ha fler sidvyer för ett större antal användare än samarbetswebbplatser och innehåller troligtvis mer statiskt innehåll och färre redigerbara resurser. Arkitekturen för moderna webbplatser skiljer sig dessutom från klassiska webbplatser på så sätt att den mesta bearbetningen som ingår i renderingssidor och kör kod sker på klienten i stället för på servern.

Prestandaoptimeringen för moderna portalwebbplatser fokuserar främst på några övergripande mål:

- Minska den totala storleken på komponenterna på varje webbplatssida
- Inläsning av vanliga statiska filer, till exempel bilder, formatmallar och skript, som ska CDN
- Begränsa samtal till SharePoint och externa slutpunkter till endast det som behövs
- Undvik dubblettförfrågningar för samma innehåll

Många av riktlinjerna i den här artikeln fokuserar på att minimera och optimera samtal till SharePoint Online. Att göra återkommande samtal varje gång en sida läses in påverkar prestanda för användarna eftersom informationen hämtas från tjänsten varje gång även om den inte har ändrats. Därför kan förfrågningar till SharePoint kategoriseras som samtal som är gemensamma för alla användare eller samtal som krävs för varje enskild användare. Resultat från dessa två samtalskategorier bör cachelagras för att optimera användarupplevelsen.

>[!NOTE]
>Använd [Siddiagnostik för SharePoint för](./page-diagnostics-for-spo.md) att analysera specifika prestandamätvärden på sidor SharePoint onlinewebbplats.

## <a name="modern-portal-site-limits-and-recommendations"></a>Begränsningar och rekommendationer för moderna portalwebbplatser

|**Gräns**|**Högsta rekommenderade värde**|**Kommentarer**|
|:-----|:-----|:-----|:-----|
|Sidor och nyhetsobjekt  <br/> |5 000 per webbplats  <br/> |Vi rekommenderar att du begränsar antalet sidor och nyhetsobjekt på en modern portalwebbplats till under 5 000.  <br/> |
|Webbdelar på en sida  <br/> |20 per sida  <br/> |Vi rekommenderar att du använder 20 eller färre totala webbdelar per sida, inklusive både In-of-the-box Microsoft-webbdelar och anpassade webbdelar. <br/> Mer information finns i Optimera [webbdelsprestanda i SharePoint moderna webbplatssidor online.](modern-web-part-optimization.md)  <br/> |
|Dynamiska webbdelar på en sida  <br/> |4 per sida  <br/> |Dynamiska webbdelar som gör en eller flera frågor för SharePoint för att hämta senaste data bör vara begränsade till 4 per sida. _Webbdelen_ Nyheter är ett exempel på en dynamisk webbdel. <br/> Mer information finns i Optimera [webbdelsprestanda i SharePoint moderna webbplatssidor online.](modern-web-part-optimization.md)    <br/> |
|Säkerhetsgrupper  <br/> |20 per webbplats  <br/> |Antalet säkerhetsgrupper påverkar omfattningen av många frågor på moderna portalwebbplatser. Vi rekommenderar att du begränsar antalet säkerhetsgrupper till så liten uppsättning som möjligt, med högst 20 per webbplats.  <br/> |
|Objekt i webbplatsnavigering  <br/> |100 per webbplats  <br/> |Vi rekommenderar att du lägger till färre än 100 objekt i webbplatsnavigeringen och att du använder de inbaserade navigeringskontrollerna.  <br/> Mer information finns i Optimera [sidvikt i SharePoint moderna webbplatssidor online.](modern-page-weight-optimization.md) <br/> |
|Maximal bildstorlek  <br/> |300 kB per bild  <br/> |Vi rekommenderar att du begränsar storleken på bilderna till 300 eller mindre, och att du använder en CDN för bilder, formatmallar och skript. <br/>Mer information finns i [Optimera bilder i SharePoint sidor](modern-image-optimization.md) för moderna webbplatser online och Använda Office 365 Content Delivery Network [(CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)  <br/> |
|Användare med redigeringsrättigheter  <br/> |200 användare per webbplats  <br/> |SharePoint är optimerade för att visa och använda innehåll. Redigeringsbehörigheter på en portal bör vara begränsade till en begränsad grupp användare eftersom redigeringsbehörigheter laddar ned ytterligare kontroller och därför fungerar långsammare för dessa användare. Ett överflödigt antal användare med redigeringsbehörighet påverkar därför den övergripande upplevelsen. <br/> |
|Tredjeparts-iFrames  <br/> |2 per sida  <br/> |iFrames är oförutsägbara långsamt eftersom de läser in en separat extern sida med allt associerat innehåll, till exempel javascript, CSS och framework-element. Om du måste använda iFrames begränsar du antalet till 2 eller färre per sida.<br/> Mer information finns i Optimera [iFrames i SharePoint moderna och klassiska publiceringswebbplatssidor.](modern-iframe-optimization.md) <br/> |
|Samtal till UPA-tjänsten  <br/> |1 per användare per timme  <br/> |Vi rekommenderar att du inte _ringer per förfrågan_ till UPA-tjänsten (User Profile Application). [Microsoft Graph API och](/graph/call-api) [PageContext](/javascript/api/sp-page-context/pagecontext) kan användas för att söka efter användarinformation.  <br/> Om ett UPA-tjänstsamtal krävs kan du ringa ett samtal när det behövs och sedan cachelagra informationen för återanvändning i samma session. |
|Samtal till taxonomitjänsten  <br/> |5 per användare per timme  <br/> |Vi rekommenderar att du inte _ringer några samtal per_ begäran till taxonomitjänsten. Om taxonomitjänstanrop behövs cachelagrar du informationen för återanvändning i samma session. <br/> Mer information finns i Optimera [sidsamtal i SharePoint moderna och klassiska publiceringswebbplatssidor](modern-page-call-optimization.md)online. <br/> |

## <a name="related-topics"></a>Relaterade ämnen

[Skapa en webbportal för SharePoint fel](/sharepoint/portal-health)

[Justera SharePoint onlineprestanda](tune-sharepoint-online-performance.md)

[Justera Office 365 prestanda](tune-microsoft-365-performance.md)

[SharePoint Onlinebegränsningar](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Prestanda i den moderna SharePoint upplevelsen](/sharepoint/modern-experience-performance)

[Prestandavägledning för SharePoint Online-portaler](/sharepoint/dev/solution-guidance/portal-performance)
