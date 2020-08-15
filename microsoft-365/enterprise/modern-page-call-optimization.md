---
title: Optimera sid samtal i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du optimerar sidor för en modern och klassisk publicerings webbplats i SharePoint Online genom att begränsa antalet samtal till SharePoint Online-tjänstens slut punkter.
ms.openlocfilehash: b3c41dfe308f1546887f28cf0e8fbe9ab4dc2761
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694907"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>Optimera sid samtal i SharePoint Online-sidor med moderna och klassisk publicerings webbplatser

Både moderna och klassiska SharePoint Online-webbplatser innehåller länkar som läser in data från (eller ringer till) SharePoint-funktioner och CDN. Det fler samtal som görs av en sida, desto längre tid tar det att läsa in sidan. Detta kallas **slutanvändarens uppskattade svars tid** eller **EUPL**.

Den här artikeln hjälper dig att förstå hur du tar reda på hur många samtal som kommer till externa slut punkter från dina sidor för en modern och en klassisk publicerings webbplats och hur du kan begränsa deras effekt på slutanvändarens uppskattade svars tid.

>[!NOTE]
>Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a>Analysera samtal med Page Diagnostics för SharePoint

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du se information om externa samtal i resultatet **till SharePoint** i fönstret _diagnostiktest_ . Raden kommer att synas i grönt om webbplats sidan innehåller färre än bas linjens antal samtal och rött om sidan överskrider original numret. Original Plans numret skiljer sig från de moderna och klassiska sidorna eftersom webb sidor använder HTTP 1.1 och moderna sidor använder HTTP 2.0:

- Moderna webbplats sidor ska innehålla högst **25** samtal
- Klassiska publicerings sidor ska innehålla högst **6** samtal

Möjliga resultat:

- **Åtgärd krävs** (röd): Sidan överskrider bas linjens antal samtal
- **Ingen åtgärd krävs** (grön): Sidan innehåller färre än bas linje numret för samtal

Om **begäran till SharePoint** -resultatet visas i avsnittet **åtgärdat krävs** kan du klicka på resultatet för att få information, inklusive det totala antalet samtal på sidan och en lista med URL-adresser.

![Förfrågningar till SharePoint-resultat](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a>Åtgärda prestanda problem relaterade till för många samtal på en sida

Om en sida innehåller för många samtal kan du använda listan med URL-adresser i **förfrågningar till SharePoint** -resultat för att avgöra om det finns upprepade samtal, samtal som ska registreras eller samtal som returnerar data som ska cachelagras.

Med **grupp rest-samtal** kan du minska prestanda. Mer information om hur du grupperar API-samtal finns i [göra batch-begäranden med resten av API: erna](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

Om du **använder ett cacheminne** för att lagra resultaten av ett API-samtal kan du förbättra prestandan hos en varm förfrågan genom att låta klienten använda cachelagrade data i stället för att ringa ytterligare ett samtal för varje efterföljande sid laddning. Det finns flera sätt att närma den här lösningen beroende på affärs kraven. Vanligt vis om data kommer att vara desamma för alla användare, är det lämpligt att använda mellannivå caching-tjänsten, till exempel att [ _Azure Redis_ cache](https://azure.microsoft.com/services/cache/) är ett bra alternativ för att avsevärt minska API-trafik mot en webbplats, eftersom användarna kan begära data från cache-tjänsten i stället för direkt från SPO. De enda SPO-samtal som krävs är att uppdatera mellanskiktets cache. Om data kommer att ändras för enskilda användare kanske det är bäst att implementera ett klient-Side-cacheminne, till exempel LocalStorage eller till och med en cookie. Detta minskar antalet samtals volymer genom att eliminera efterföljande begär Anden som görs av samma användare under cachens varaktighet, men det är mindre effektivt än en särskild cache-tjänst. Med PnP kan du använda LocalStorage med lite extra utveckling som krävs.

Innan du gör sid ändringar för att åtgärda prestanda problem ska du anteckna sid inläsnings tiden i analys resultaten. Kör verktyget igen efter ändringen för att se om det nya resultatet är inom bas linje standarden och kontrol lera den nya sid inläsnings tiden för att se om det gjorts en förbättring.

![Tids resultat för sid inläsning](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sid inläsnings tiden kan variera beroende på en mängd olika faktorer, till exempel nätverks belastning, tidpunkt och andra tillfälliga förhållanden. Testa sid inläsnings tid ett par gånger innan och efter det att du har gjort ändringar för att få hjälp med medelvärdet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Nätverk för innehålls leverans](content-delivery-networks.md)

[Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
