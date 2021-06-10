---
title: Optimera anpassade tillägg i SharePoint moderna webbplatssidor online
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
description: Lär dig att optimera prestandan för anpassade tillägg i SharePoint moderna webbplatssidor online.
ms.openlocfilehash: 05d9b9cd9ad70630169595dc42080c718b39dbc8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923069"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Optimera anpassade tilläggsprestanda i SharePoint moderna webbplatssidor online

Den här artikeln hjälper dig att förstå hur anpassade tillägg påverkar användarfördröjning och hur du åtgärdar vanliga problem.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Använd siddiagnostikverktyget för SharePoint för att analysera anpassade tillägg

Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Verktyget innehåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer SharePoint siddiagnostikverktyget går du till Använda [verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint systemsida.

När du analyserar en sida på en SharePoint-webbplats med verktyget Siddiagnostik för SharePoint kan du  se information om anpassade tillägg  som överskrider baslinjemåttet i tilläggen påverkar inläsningstiden och/eller resultatet för för många tillägg som används i fönstret Diagnostiktest  

Möjliga resultat är:

- **Obs!** Krävs (röd): Alla _anpassade_ tillägg som tar längre tid **än en** sekund att läsa in. Den totala inläsningstiden som visas i testresultaten delas upp efter modulbelastning och init. Om det finns för många tillägg på en sida kan inläsningstiden påverkas. Det markeras om **sju** eller fler tillägg används på sidan.
- **Förbättrings** möjligheter (gult) Om fem eller fler tillägg används markeras de i det här avsnittet som en varning tills sju eller fler används som sedan markeras som Uppmärksamhet krävs. 
- **Ingen åtgärd krävs** (grön): Inget tillägg tar längre tid än en sekund att läsa in.

Om ett tillägg påverkar inläsningstiden eller om det finns för många  tillägg på sidan visas resultatet i avsnittet Åtgärder krävs i resultatet. Klicka på resultatet för att se information om vilket tillägg som läses in långsamt eller för många tillägg har markerats. Framtida uppdateringar av siddiagnostik för SharePoint kan innehålla uppdateringar av analysregler, så se till att du alltid har den senaste versionen av verktyget.

![Inläsningstid för sida](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

Information som är tillgänglig i resultatet omfattar:

- **Namn och ID** visar identifieringsinformation som kan hjälpa dig att hitta tillägget på sidan
- **Summa** visar den totala tiden för inläsning och initiering av modulen för tillägget. Det är den totala relativa tid som tillägget tar för att köras på sidan, från början till slutet.
- **Modulladdning** visar den tid det tar att ladda ned, utvärdera och läsa in tilläggen JavaScript- och CSS-filer. Sedan startas Init-processen.
- **Init** visar hur lång tid det tog för tillägget att initiera data.
    Det är ett asynkront samtal och inittid är beräkningen av tid för funktionen onInit när den returnerade lovat har lösts.

Den här informationen finns med för att hjälpa designers och utvecklare att felsöka problem. Den här informationen bör ges till din design- och utvecklingsteam.

## <a name="overview-of-extensions"></a>Översikt över tillägg

SharePoint Framework (SPFx) Tillägg kan användas för att utöka SharePoint användarupplevelsen. Med SharePoint Framework Tillägg kan du anpassa fler aspekter av SharePoint, till exempel meddelandeområden, verktygsfält och listdatavyer.

Tillägg kan påverka prestandan för en sida i SharePoint eftersom det också kräver processor- och nätverksresurser för att göra det arbete som krävs.

Det finns fyra typer av tillägg:

- **Application Customizers** lägger till skript på sidan och öppnar välkända platshållare för HTML-element och utökar dem med anpassade återgivningar.
- **Med Fältanpassare** får du ändrade vyer för data för fält i en lista.
- **Kommandouppsättningar** utökar SharePoint kommandoytor för att lägga till nya åtgärder och ger klientkod som du kan använda för att implementera beteenden.
- **Sökfrågemoderare (endast förhandsgranskning)** anropas precis innan sökfrågan körs.

## <a name="remediate-extension-performance-issues"></a>Åtgärda prestandaproblem med tillägg

Följ instruktionerna i det här avsnittet för att identifiera och åtgärda prestandaproblem med tillägg som listas i Tillägg påverkar inläsningstiden **för** sidor.

>[!NOTE]
>Programanpassare kan utföras i ett tidigt skede av en sidas livscykel och det kan påverka prestandan för andra tillägg på sidan.

Granskningsresultatet i Siddiagnostikverktyget visar två steg av kör ett tillägg för att hjälpa till att identifiera potentiell prestanda påverkan.

- **Modulens** inläsning är hur lång tid det tar att läsa in tillägget, vilket påverkas av storleken på ett tillägg, så det är en bra idé att bara bunta ihop nödvändiga bibliotek i tillägget och även välja ljusare bibliotek.
- **Init** är initieringstiden för tillägget och utvecklare av tillägg bör överväga om tillägget utför onödigt arbete eller kör för många kommandon under initieringssteget.

Sidförfattare kan också använda granskningsresultatet för att se om en sida har för många tillägg eftersom för många tillägg påverkar en sidas prestanda negativt.

- **Förlängningsstorlek och beroenden**
  - Användning av Office 365 CDN krävs för optimal nedladdning av statiska resurser. Offentliga CDN ursprung är bättre för _js/css-filer._ Mer information om hur du använder Office 365 CDN finns i [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Återanvänd ramverk som _React och_ _fabric-import_ som ingår i SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework](/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Kontrollera att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- **Hämta/cachelagra data**
  - Om tillägget förlitar sig på extra serveranrop för att hämta data för visning ska du se till att de server-API:erna är snabba och/eller implementera cachelagring på klientsidan (till exempel att använda _lokalLagring_ eller _IndexDB_ för större uppsättningar).
  - Om flera anrop krävs för att återge viktiga data kan det vara bra att batcha på servern eller andra metoder för att konsolidera förfrågningar till ett enda samtal.
  - Om vissa dataelement kräver ett långsammare API, men inte är kritiska för den första renderingen, kan du avkoda dessa till ett separat anrop som körs när viktiga data har återgets.
  - Om flera delar använder samma data använder du ett vanligt datalager för att undvika dubbletter.
- **Renderingstid**
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