---
title: Optimera anpassade tillägg i SharePoint Online-sidor med moderna webbplatser
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
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
description: Lär dig hur du optimerar prestanda för anpassade tillägg i sidor med moderna webbplatser i SharePoint Online.
ms.openlocfilehash: 3f9474bcfa3266742d2e01af2f1df6eb5c0d017c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694712"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Optimera anpassade prestanda i SharePoint Online-sidor med moderna webbplatser

Den här artikeln hjälper dig att förstå hur anpassade tillägg påverkar uppskattad svars tid och hur du åtgärdar vanliga problem.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Använd verktyget för nätverksdiagnostik för SharePoint för att analysera anpassade tillägg

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om anpassade tillägg som överskrider bas linjens mått i **tilläggen påverkar laddnings tiden** och/eller **för många tillägg som används** i fönstret _diagnostiktest_ 

Möjliga resultat:

- **Åtgärd krävs** (röd): alla _anpassade_ tillägg som tar längre tid än **en** sekund att läsa in. Den totala inläsnings tiden som visas i test resultaten är uppdelad efter modul beläggning och initiering. Om det finns för många fil namns tillägg på en sida kan de påverka sid inläsnings tiden och det markeras om **sju** eller fler fil namns tillägg används på sidan.
- **Förbättrings möjligheter** (gult) om **fem** eller fler fil namns tillägg används kommer de att markeras i det här avsnittet som en varning tills sju eller fler används, vilka då markeras som åtgärd krävs.
- **Ingen åtgärd krävs** (grön): inget tillägg tar längre än en sekund att läsa in.

Om ett tillägg påverkar sid inläsnings tiden eller om det finns för många extsnions på sidan, visas resultatet i avsnittet för att kontrol lera att det är **åtgärdat** . Klicka på resultatet för att visa information om vilka tillägg som laddas långsamt eller för många tillägg har marker ATS. Framtida uppdateringar av diagnostikverktyget för SharePoint kan innehålla uppdateringar av analys regler, så se till att du alltid har den senaste versionen av verktyget.

![Tids resultat för sid inläsning](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

Informationen i resultatet inkluderar:

- **Namn och ID** visar identifierande information som kan hjälpa dig att hitta tillägget på sidan
- **Totalt** visar den totala tiden för tillägget att initiera och läsa in
- **Modul inläsning** visar den tid det tar att hämta och läsa in tillägget
- **Init** visar tids åtgången för att tillägget ska initieras

Den här informationen tillhandahålls för att utvecklare och utvecklare ska kunna felsöka problem. Denna information bör ges till din design-och utvecklings grupp.

## <a name="overview-of-extensions"></a>Översikt över tillägg

SPFx-tillägg (SharePoint Framework) kan användas för att utöka SharePoint-gränssnittet. Med SharePoint Framework-tillägg kan du anpassa fler aspekter av SharePoint-upplevelsen, inklusive aviserings områden, verktygsfält och listvyer.

Tilläggen kan ha dålig inverkan på en SharePoint-sidas prestanda eftersom den också tar processor-och nätverks resurser för att fungera.

Det finns fyra typer av tillägg:

- Med **Programanpassare** läggs skript till på sidan och du får till gång till välbekanta plats hållare för HTML-element och förlänger dem med anpassade åter givningar.
- **Fält anpassningar** ger ändrade vyer till data för fält i en lista.
- **Kommando uppsättningar** utökar kommando ytorna i SharePoint för att lägga till nya åtgärder och innehåller kod för klient sidan som du kan använda för att implementera beteenden.
- Alternativet för **sökning efter frågor (endast för hands version)** anropas precis innan Sök frågan körs.

## <a name="remediate-extension-performance-issues"></a>Åtgärda problem med tilläggets prestanda

Följ anvisningarna i det här avsnittet för att identifiera och åtgärda prestanda problem med tillägg som listas i **fil namns tilläggen påverkar sid inläsnings tiden** .

>[!NOTE]
>Programanpassare kan köras i tidigt skede under en sidas livs cykel och det kan påverka prestandan hos andra tillägg på sidan.

Gransknings resultaten i verktyget för sid Diagnostic visar två steg för att utföra ett tillägg för att identifiera den potentiella prestanda påverkan.

- **Modul belastning** är hur lång tid det tar att läsa in tillägget, som påverkas av storleken på ett tillägg, så det är en bra idé att bara bunta ihop nödvändiga bibliotek i tillägget och att välja ljusare bibliotek.
- **Init** är initierings tiden för tillägget och utöknings utvecklare bör överväga om tillägget gör onödigt arbete eller kör för många kommandon under initieringen.

Sid författare kan också använda gransknings resultatet för att kontrol lera om en sida har för många fil namns tillägg som för många fil namns tillägg påverkar sidans prestanda negativt.

- **Storlek och samband för tillägg**
  - Användning av Office 365 CDN krävs för optimal statisk resurs nedladdning. Offentliga CDN-ursprung är lämpligt för _JS/CSS-_ filer. Mer information om hur du använder Office 365 CDN finns i [använda office 365-leverans Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Åter användnings bara ramverk som _reagerar_ och _Fabric-import_ som ingår i SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Kontrol lera att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- **Data hämtning/cachning**
  - Om fil namns tillägget är beroende av extra Server samtal för att hämta data för visning kontrollerar du att dessa Server-API: er snabbt och/eller implementerar cachelagring på klient sidan (som att använda _localStorage_ eller _IndexDB_ för större uppsättningar).
  - Om det krävs flera samtal för att återge viktiga data bör du överväga att använda en server eller någon annan metod för att konsolidera förfrågningar till ett enda samtal.
  - Om vissa delar av data kräver ett långsammare API men inte är kritiska för inledande rendering kan du koppla ihop dessa med ett separat samtal som körs efter att kritiska data har Render ATS.
  - Om flera delar använder samma data kan du använda ett vanligt data lager för att undvika dubbletter.
- **Åter givnings tid**
  - Alla medie källor som bilder och videor bör begränsas till gränserna för behållaren, enheten och/eller nätverket för att undvika onödigt stora till gångar. Mer information om innehålls beroenden finns i [använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Undvik API-samtal som orsakar omflöde, komplexa CSS-regler eller komplexa animeringar. Mer information finns i [minimera bakströmningen](https://developers.google.com/speed/docs/insights/browser-reflow).
  - Undvik att använda inaktiva långa aktiviteter. I stället kan du dela tids krävande uppgifter i olika köer. Mer information finns i [optimera JavaScript-körning](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).
  - Reservera motsvarande utrymme för asynkron åter givning av media eller visuella element för att undvika överhoppade ramar och hackigt (kallas även _Jank_).
  - Om en viss webbläsare inte har stöd för en funktion som används i rendering kan du antingen använda en polyfyllning eller utesluta en beroende kod. Om funktionen inte är kritisk kan du ta bort resurser som händelse hanterare för att undvika minnes läckor.

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
