---
title: Optimera webbdelsprestanda i moderna webbplatssidor i SharePoint Online
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
description: Lär dig hur du använder siddiagnostik för att optimera prestanda för webbdelar på moderna webbplatssidor i SharePoint Online.
ms.openlocfilehash: ca1b9328ad71fdd4a3f3c6c6be47eaa3993d4fc7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287155"
---
# <a name="optimize-web-part-performance-in-sharepoint-online-modern-site-pages"></a>Optimera webbdelsprestanda i moderna webbplatssidor i SharePoint Online

Moderna webbplatssidor i SharePoint Online innehåller webbdelar som kan bidra till den övergripande sidinläsningstiden. Den här artikeln hjälper dig att förstå hur du avgör hur webbdelar i dina sidor påverkar användarens uppfattas fördröjning och hur du åtgärdar vanliga problem.

>[!NOTE]
>Mer information om prestanda i moderna SharePoint Online-portaler finns [i Prestanda i det moderna SharePoint-programmet.](https://docs.microsoft.com/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts"></a>Använda verktyget Siddiagnostik för SharePoint för att analysera webbdelar

Verktyget Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge (och Chrome-webbläsare som analyserar både modern portal för SharePoint Online och https://www.microsoft.com/edge) klassiska publiceringswebbplatssidor. Verktyget tillhandahåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer om verktyget Siddiagnostik för SharePoint går du [till Använda verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.

När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint kan du  se information om webbdelar som  överskrider baslinjemåttet i webbdelarna påverkar sidinläsningstidens resultat i fönstret Diagnostiktest.

Möjliga resultat är:

- **Obs!** (röd): _Alla_ anpassade webbdelen som visas i visningsområdet (den del av sidan som visas på skärmen som läses in först) tar längre tid än **två** sekunder att läsa in. Anpassade _webbdelar_ utanför visningsområdet som tar längre tid än **fyra** sekunder att läsa in. Total inläsningstid visas i testresultat och delas upp efter inläsning i modulen, lat inläsning, init och återgivning.
- **Förbättringsmöjligheter** (gult): Objekt som kan påverka sidinläsningstiden visas i det här avsnittet och bör granskas och övervakas. Det kan inkludera Microsoft-webbdelar (OOTB). Resultat för alla Microsoft-webbdelar som visas i det här avsnittet rapporteras automatiskt till Microsoft, så **ingen åtgärd krävs.** Du bör bara logga ett support ärende för undersökning om  du har mycket långsam prestanda på sidan och alla Microsoft-webbdelar på sidan visas i resultatet i avsnittet för **förbättringsmöjligheter.** Observera att en kommande uppdatering av siddiagnostik för SharePoint-verktyget ytterligare delar upp resultaten baserat på den specifika konfigurationen av Microsoft-webbdelen.
- **Ingen åtgärd krävs** (grön): Ingen webbdel tar längre tid än **två sekunder** att returnera data.

Om **webbdelarna** påverkar sidinläsningstidens resultat  visas  i antingen avsnittet om obligatoriska åtgärder eller förbättringsmöjligheter i resultatet klickar du på resultatet för att se information om vilka webbdelar som läses in långsamt. Framtida uppdateringar av verktyget Siddiagnostik för SharePoint kan innehålla uppdateringar av analysregler, så se till att du alltid har den senaste versionen av verktyget.

![Resultat för verktyget Siddiagnostik](../media/modern-portal-optimization/pagediag-web-part.png)

Information som är tillgänglig i resultatet är:

- **Skapad** av visar om webbdelen är anpassad eller Microsoft OOTB.
- **Namn och ID** visar identifierande information som kan hjälpa dig att hitta webbdelen på sidan.
- **Totalt** visar den totala tiden för webbdelen att läsa in, initiera och återge webbdelen. Det är den totala relativa tid som webbdelen tar för att återge på sidan, från början till slutet.
- **Modulladdning** visar tiden det tar att ladda ned, utvärdera och läsa in tilläggen JavaScript- och CSS-filer. Sedan startas Init-processen.
- **I Lat** lata belastning visas tiden för uppskjuten inläsning av webbdelar som inte visas i huvudavsnittet på sidan. Det finns vissa villkor där det finns för många webbdelar för att återges och de finns i kö för att återges för att minimera inläsningstiden för sidan.
- **Init** visar hur lång tid det tar för webbdelen att initiera data.
    Det är ett asynkront anrop och inittid är beräkningen av tid för onInit-funktionen när den returnerade lovat har lösts.
- **Återgivningen** visar tiden det tar att återge användargränssnittet (användargränssnittet) när inläsningen av modulen och Init har slutförts.
    Det är JavaScript-körningstiden att sätta fast DOM-versionen i dokumentet (sidan).
    Rendering av asynkrona resurser, till exempel bilder, kan ta ytterligare tid att slutföra.

Den här informationen tillhandahålls för att hjälpa designers och utvecklare att felsöka problem. Den här informationen ska ges till din design- och utvecklingsgrupp.

## <a name="remediate-web-part-performance-issues"></a>Åtgärda prestandaproblem för webbdel

Följ instruktionerna i det här avsnittet för att identifiera och åtgärda prestandaproblem med webbdelar som listas i webbdelarna påverkar **sidinläsningstidens** resultat.

Det finns tre kategorier av möjliga orsaker till dålig prestanda för webbdel. Använd informationen nedan för att avgöra vilka problem som gäller för ditt scenario och åtgärda dem.

- Skriptstorlek och beroenden för webbdel
  - Optimera det första skriptet som återger huvudlinjescenariot endast _för visningsläge._
  - Flytta mindre vanliga scenarier och redigeringslägeskod (som egenskapsfönstret) för att separera delar med hjälp av _import(-satsen)._
  - Granska beroenden för filen _package.jsför_ att ta bort all avliden kod helt. Flytta test-/build-beroenden till devDependencies.
  - Du måste använda Office 365 CDN för optimal nedladdning av statiska resurser. Offentliga CDN-ursprung är bättre för _js/css-filer._ Mer information om hur du använder Office 365 CDN finns i Använda [Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Återanvänd ramverk som _React_ och _Fabric-import_ som kommer som en del av SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework.](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
  - Se till att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- Hämtning/cachelagring av data
  - Om webbdelen är beroende av extra serveranrop för att hämta data för visning ska du se till att de server-API:erna är snabba och/eller implementera cachelagring på klientsidan (t.ex. använda _localStorage_ eller _IndexedDB_ för större uppsättningar).
  - Om flera anrop krävs för att återge viktiga data kan du överväga att batcha på servern eller andra metoder för att konsolidera förfrågningar till ett enda samtal.
  - Alternativt, om vissa dataelement kräver ett långsammare API, men inte är viktiga för den första renderingen, kan du avkoda dessa till ett separat anrop som körs när viktiga data har återges.
  - Om flera delar använder samma data bör du använda ett vanligt datalager för att undvika dubbletter av samtal.
- Renderingstid
  - Alla mediekällor som bilder och videor bör ha en storlek som begränsar behållaren, enheten och/eller nätverket för att undvika att ladda ned onödiga stora tillgångar. Mer information om innehållsberoenden finns i Använda [Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Undvik API-anrop som leder till flödesschema, komplexa CSS-regler eller komplicerade animeringar. Mer information finns i [Minimera webbläsarens flödesomformning.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Undvik att använda kedjeaktiviteter som körs länge. Dela i stället upp långa aktiviteter i separata köer. Mer information finns i Optimera [körning av JavaScript.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reservera motsvarande utrymme för asynkron rendering av media eller visuella element för att undvika överhoppade ramar och hackar (kallas även _jank)._
  - Om en viss webbläsare inte har stöd för en funktion som används för rendering kan du antingen läsa in en polyfyllfunktion eller utesluta löpande beroende kod. Om funktionen inte är kritisk kasserar du resurser som händelsehanterare för att undvika minnesläckor.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna sidinläsningstiden i analysresultaten. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstidsresultat för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd olika faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden för sidorna några gånger före och efter ändringarna för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i det moderna SharePoint-programmet](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
