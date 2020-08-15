---
title: Optimera webb dels prestanda i sidor i SharePoint Online
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Lär dig hur du använder Nätverksdiagnostik för att optimera prestanda för webb delar i SharePoint Online-moderna webbplats sidor.
ms.openlocfilehash: 7dcfcbfe033ef5f4257cc9688b61aca3227ade8b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694608"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>Optimera webb dels prestanda i sidor i SharePoint Online

Moderna webbplats sidor för SharePoint Online innehåller webb delar som kan bidra till den totala sid inläsnings tiden. Den här artikeln hjälper dig att förstå hur webb delar på sidor påverkar uppskattad svars tid och hur du åtgärdar vanliga problem.

>[!NOTE]
>Mer information om prestanda i SharePoint Online-moderna portaler finns i [prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance).

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Använda verktyget för nätverksdiagnostik för SharePoint för att analysera webb delar

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Verktyget visar en rapport för varje sida som visar hur sidan fungerar mot en viss uppsättning prestanda villkor. Om du vill installera och läsa mer om verktyget för nätverksdiagnostik för SharePoint kan du gå till [använda diagnostikverktyget för SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Verktyget för nätverksdiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

När du analyserar en SharePoint-webbplats med Page Diagnostics för SharePoint-verktyget kan du Visa information om vilka webb delar som överskrider bas linjen i **webb delarna som påverkar sid inläsnings tiden** i fönstret _diagnostiktest_ .

Möjliga resultat:

- **Åtgärd krävs** (röd): en _anpassad_ webbdel som visas i visnings området (skärm synlig del av sidan som laddas först) och som tar längre tid än **två** sekunder att läsa in. _Anpassade_ webb delar utanför det område som tar längre tid än **fyra** sekunder att läsa in. Total inläsnings tid visas i test resultat och är uppdelat per modul laddas, Lazy load, init and rendering.
- **Förbättrings möjligheter** (gula): objekt som kan påverka sid inläsnings tid visas i det här avsnittet och bör granskas och övervakas. Det kan innehålla "från lådan" (OOTB) webb delar. Resultaten för de Microsoft-webbdelar som visas i det här avsnittet rapporteras automatiskt till Microsoft, så **Ingen åtgärd krävs**. Du bör bara logga ett support ärende för att få en undersökning om du har mycket långsam prestanda på sidan och **alla Microsoft webb delar** på sidan visas i avsnittet **förbättrings möjligheter** . Observera att om du uppdaterar en framtida diagnostik för SharePoint-verktyg kommer resultaten att brytas efter den specifika konfigurationen för Microsoft-webbdelen.
- **Ingen åtgärd krävs** (grön): ingen webbdel tar längre tid än **två** sekunder att returnera data.

Om **webb delarna påverkar tiden för sid inläsnings tid** som visas i avsnittet **Obs!** eller **förbättrings möjligheter** i resultatet klickar du på resultatet för att visa information om vilka webb delar som laddas långsamt. Framtida uppdateringar av diagnostikverktyget för SharePoint kan innehålla uppdateringar av analys regler, så se till att du alltid har den senaste versionen av verktyget.

![Resultat för verktyget Nätverksdiagnostik](../media/modern-portal-optimization/pagediag-web-part.png)

Informationen i resultatet inkluderar:

- **Gjort av** visar om webb delen är anpassad eller Microsoft OOTB
- **Namn och ID** visar identifierande information som kan hjälpa dig att hitta webb delen på sidan
- **Totalt** visar den totala tiden för webb delen som ska läsas in
- **Modul beläggning** visar hur lång tid det tar att hämta och ladda webb dels komponenter
- **Lazy load** visar tiden för uppskjutning av webb delar som inte visas i huvud avsnittet på sidan
- **Init** visar den tid det tar för webb dels initiering
- **Rendera** visar den tid det tar för webb delen att hämta och återge resultat

Den här informationen tillhandahålls för att utvecklare och utvecklare ska kunna felsöka problem. Denna information bör ges till din design-och utvecklings grupp.

## <a name="remediate-web-part-performance-issues"></a>Åtgärda problem med webb dels prestanda

Följ anvisningarna i det här avsnittet om du vill identifiera och åtgärda prestanda problem med webb delar som listas i **webb delarna påverkar sid inläsnings tid** .

Det finns tre möjliga orsaker till dåligt webb dels prestanda. Använd informationen nedan för att avgöra vilka problem som gäller för ditt scenario och åtgärda dem.

- Skript storlek och samband för webb delar
  - Optimera det första skriptet som visar Mainline-scenariot för _endast visnings läge_.
  - Flytta de mindre vanliga scenarierna och redigerings läges koden (som egenskaps fönstret) till olika segment med hjälp av _import ()_ -instruktionen.
  - Ta bort alla döda koder fullständigt genom att granska sambanden för _package.js_ . Flytta alla test/skapa bara samband till devDependencies.
  - Användning av Office 365 CDN krävs för optimal statisk resurs nedladdning. Offentliga CDN-ursprung är lämpligt för _JS/CSS-_ filer. Mer information om hur du använder Office 365 CDN finns i [använda office 365-leverans Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Åter användnings bara ramverk som _reagerar_ och _Fabric-import_ som ingår i SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Kontrol lera att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- Data hämtning/cachning
  - Om webb delen är beroende av extra Server samtal för att hämta data för visning kontrollerar du att dessa Server-API: er snabbt och/eller implementerar cachelagring på klient sidan (till exempel genom att använda _localStorage_ eller _IndexDB_ för större uppsättningar).
  - Om det krävs flera samtal för att återge viktiga data bör du överväga att använda en server eller någon annan metod för att konsolidera förfrågningar till ett enda samtal.
  - Om vissa delar av data kräver ett långsammare API men inte är kritiska för inledande rendering kan du koppla ihop dessa med ett separat samtal som körs efter att kritiska data har Render ATS.
  - Om flera delar använder samma data kan du använda ett vanligt data lager för att undvika dubbletter.
- Åter givnings tid
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
