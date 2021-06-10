---
title: Optimera webbdelsprestanda i SharePoint webbsidor med modern webbplats online
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
description: Lär dig hur du använder Siddiagnostik för att optimera prestanda för webbdelar i SharePoint moderna webbplatssidor online.
ms.openlocfilehash: 2a72ecd8bc1f6dee4166809f72ce5f9bce422dc9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929066"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>Optimera webbdelsprestanda i SharePoint webbsidor med modern webbplats online

SharePoint Moderna webbplatssidor online innehåller webbdelar som kan bidra till sidinläsningen. Den här artikeln hjälper dig att förstå hur webbdelar på sidorna påverkar användarens uppfattas fördröjning och hur du åtgärdar vanliga problem.

>[!NOTE]
>Mer information om prestanda i SharePoint moderna portaler finns i [Prestanda i det moderna SharePoint upplevelse.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Använd siddiagnostikverktyget för SharePoint för att analysera webbdelar

Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.

När du analyserar en sida på en SharePoint-webbplats med verktyget Siddiagnostik för SharePoint kan du  se information om webbdelar som  överskrider baslinjemåttet i webbdelarna påverkar inläsningstiden för sidor i fönstret Diagnostiktest.

Möjliga resultat är:

- **Obs!** Obligatoriskt  (rött): Alla anpassade webbdel som visas i visningsområdet (den del av sidan som läses in först) som tar längre tid än **två** sekunder att läsa in. Anpassade _webbdelar_ utanför visningsområdet som tar längre tid än **fyra sekunder** att läsa in. Den totala inläsningstiden visas i testresultat och delas upp efter modulbelastning, lat inläsning, init och återgivning.
- **Förbättringsmöjligheter** (gult): Objekt som kan påverka sidinläsningstiden visas i det här avsnittet och bör granskas och övervakas. Det här kan inkludera Microsoft-webbdelar (out of the box) (OOTB). Resultat för alla Microsoft-webbdelar som visas i det här avsnittet rapporteras automatiskt till Microsoft, så **ingen åtgärd krävs.** Du bör bara logga ett support ärende för undersökning om  du upplever mycket långsam prestanda på sidan och alla Microsoft-webbdelar på sidan visas i resultatet i avsnittet **Förbättringsmöjligheter.** Observera att en kommande siddiagnostik för SharePoint kommer att fortsätta dela upp resultaten baserat på den specifika konfigurationen av Microsoft-webbdelen.
- **Ingen åtgärd krävs** (grön): Ingen webbdel tar längre tid än **två sekunder** att returnera data.

Om **webbdelarna** påverkar inläsningstiden för sidan  visas  i avsnittet Affärsmöjligheter för uppmärksamhet eller Förbättring av affärsmöjligheter i resultatet klickar du på resultatet för att se information om vilka webbdelar som läses in långsamt. Framtida uppdateringar av siddiagnostik för SharePoint kan innehålla uppdateringar av analysregler, så se till att du alltid har den senaste versionen av verktyget.

![Resultat av verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-web-part.png)

Information som är tillgänglig i resultatet omfattar:

- **Skapad** av visar om webbdelen är anpassad eller Microsoft OOTB.
- **Namn och ID** visar identifieringsinformation som kan hjälpa dig att hitta webbdelen på sidan.
- **Summa** visar den totala tiden för inläsning, initiering och återgivning av webbdelen. Det är den totala relativa tid som webbdelen tar för att återge på sidan, från början till slutet.
- **Modulladdning** visar den tid det tar att ladda ned, utvärdera och läsa in tilläggen JavaScript- och CSS-filer. Sedan startas Init-processen.
- **I Lazy Load** visas tiden för uppskjuten inläsning av webbdelar som inte visas i huvudavsnittet på sidan. Det finns vissa villkor där det finns för många webbdelar för att återges och de är i kö för att återges för att minimera inläsningstiden för sidan.
- **Init** visar hur lång tid det tar för webbdelen att initiera data.
    Det är ett asynkront samtal och inittid är beräkningen av tid för funktionen onInit när den returnerade lovat har lösts.
- **Återgivningen** visar tiden det tar att återge användargränssnittet (användargränssnittet) när modulläsningen och Init har slutförts.
    Det är JavaScript-körningstiden för att installera DOM i dokumentet (sidan).
    Återgivning av asynkrona resurser, till exempel bilder, kan ta ytterligare tid att slutföra.

Den här informationen finns med för att hjälpa designers och utvecklare att felsöka problem. Den här informationen bör ges till din design- och utvecklingsteam.

## <a name="remediate-web-part-performance-issues"></a>Åtgärda prestandaproblem för webbdel

Följ instruktionerna i det här avsnittet för att identifiera och åtgärda prestandaproblem med webbdelar som listas i webbdelarna **påverkar inläsningstiden för** sidor.

Det finns tre kategorier av möjliga orsaker till dålig prestanda för webbdel. Använd informationen nedan för att avgöra vilka problem som gäller för ditt scenario och åtgärda dem.

- Webbdelsskriptstorlek och beroenden
  - Optimera det första skriptet som återger huvudlinjescenariot endast _för visningsläge._
  - Flytta mindre vanliga scenarier och redigeringslägeskod (som egenskapsfönstret) för att dela upp delar med hjälp av _import()-satsen._
  - Granska beroenden för filen _package.jsför_ att ta bort all avliden kod helt. Flytta test-/build-beroenden till devDependencies.
  - Användning av Office 365 CDN krävs för optimal nedladdning av statiska resurser. Offentliga CDN ursprung är bättre för _js/css-filer._ Mer information om hur du använder Office 365 CDN finns i [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Återanvänd ramverk som _React och_ _fabric-import_ som ingår i SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework](/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Kontrollera att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- Hämta/cachelagra data
  - Om webbdelen förlitar sig på extra serveranrop för att hämta data för visning ska du se till att de server-API:erna är snabba och/eller implementera cachelagring på klientsidan (till exempel att använda _lokalLagring_ eller _IndexedDB_ för större uppsättningar).
  - Om flera anrop krävs för att återge viktiga data kan det vara bra att batcha på servern eller andra metoder för att konsolidera förfrågningar till ett enda samtal.
  - Om vissa dataelement kräver ett långsammare API, men inte är kritiska för den första renderingen, kan du avkoda dessa till ett separat anrop som körs när viktiga data har återgets.
  - Om flera delar använder samma data använder du ett vanligt datalager för att undvika dubbletter.
- Renderingstid
  - Alla mediekällor, till exempel bilder och videoklipp, bör ha en storlek som är lika stor som behållaren, enheten och/eller nätverket för att undvika nedladdning av onödiga stora tillgångar. Mer information om innehållsberoenden finns i Använda Office 365 Content Delivery Network [(CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Undvik API-anrop som leder till flödesfördrång, komplexa CSS-regler eller komplicerade animeringar. Mer information finns i [Minimera webbläsarens flödesomformning.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Undvik att använda kedjeaktiviteter som körs länge. I stället kan du dela upp långvariga uppgifter i separata köer. Mer information finns i Optimera [körning av JavaScript.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reservera motsvarande utrymme för asynkron rendering av media eller visuella element för att undvika överhoppade ramar och hackar (kallas även _jank_).
  - Om en viss webbläsare inte har stöd för en funktion som används för rendering kan du antingen läsa in en polyfyll eller exkludera att köra beroende kod. Om funktionen inte är kritisk kasserar du resurser som händelsehanterare för att undvika minnesläckor.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna inläsningstiden för sidan i analysresultatet. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstid för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint onlineprestanda](tune-sharepoint-online-performance.md)

[Justera Office 365 prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint upplevelsen](/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)