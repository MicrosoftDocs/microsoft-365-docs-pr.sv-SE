---
title: Optimera anpassade tillägg på moderna webbplatssidor i SharePoint Online
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
description: Lär dig hur du optimerar prestanda för anpassade tillägg på moderna webbplatssidor i SharePoint Online.
ms.openlocfilehash: 92d328c64c89a1a01bbcd50fb7ad04affdf69af8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287203"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Optimera anpassade tillägg i moderna webbplatssidor i SharePoint Online

Den här artikeln hjälper dig att förstå hur anpassade tillägg påverkar användarens uppfattas svarstid och hur du åtgärdar vanliga problem.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Använd verktyget Siddiagnostik för SharePoint för att analysera anpassade tillägg

Verktyget Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge (och Chrome-webbläsare som analyserar både modern portal för SharePoint Online och https://www.microsoft.com/edge) klassiska publiceringswebbplatssidor. Verktyget tillhandahåller en rapport för varje analyserad sida som visar hur sidan fungerar mot en definierad uppsättning prestandavillkor. Om du vill installera och lära dig mer om verktyget Siddiagnostik för SharePoint går du [till Använda verktyget Siddiagnostik för SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Verktyget Siddiagnostik fungerar bara för SharePoint Online och kan inte användas på en SharePoint-systemsida.

När du analyserar en SharePoint-webbplatssida med verktyget Siddiagnostik för SharePoint kan du  se information om anpassade tillägg  som överskrider baslinjemåttet i tilläggen påverkar inläsningstiden och/eller resultatet för för många tillägg som används i fönstret Diagnostiktest  

Möjliga resultat är:

- **Åtgärder krävs** (röd): Alla _anpassade tillägg_ som tar längre tid **än en** sekund att läsa in. Den totala inläsningstiden som visas i testresultaten delas in efter modulbelastning och init. Om det finns för många tillägg på en sida kan de påverka inläsningstiden och det markeras om **sju** eller fler tillägg används på sidan.
- **Förbättringsmöjligheter** (gul) **Om** fem eller fler tillägg används markeras de i det här avsnittet som en varning tills sju eller fler används, och sedan markeras som Åtgärder krävs.
- **Ingen åtgärd krävs** (grön): Inget tillägg tar längre tid än en sekund att läsa in.

Om ett tillägg påverkar sidinläsningstiden eller om det finns för många  tillägg på sidan visas resultatet i den obligatoriska delen av resultatet. Klicka på resultatet om du vill se information om vilket tillägg som läses in långsamt eller för många tillägg har markerats. Framtida uppdateringar av verktyget Siddiagnostik för SharePoint kan innehålla uppdateringar av analysregler, så se till att du alltid har den senaste versionen av verktyget.

![Inläsningstidsresultat för sida](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

Information som är tillgänglig i resultatet är:

- **Namn och ID** visar identifierande information som kan hjälpa dig att hitta tillägget på sidan
- **Summan** visar total tid för tillägget för inläsning och initialisering av modulen. Det är den totala relativa tid som det tar att köra tillägget på sidan, från början till slutet.
- **Modulladdning** visar tiden det tar att ladda ned, utvärdera och läsa in tilläggen JavaScript- och CSS-filer. Sedan startas Init-processen.
- **Init** visar hur lång tid det tar för tillägget att initiera data.
    Det är ett asynkront anrop och inittid är beräkningen av tid för onInit-funktionen när den returnerade lovat har lösts.

Den här informationen tillhandahålls för att hjälpa designers och utvecklare att felsöka problem. Den här informationen bör tillhandahållas till din design- och utvecklingsgrupp.

## <a name="overview-of-extensions"></a>Översikt över tillägg

SharePoint Framework-tillägg (SPFx) kan användas för att utöka användarupplevelsen för SharePoint. Med SharePoint Framework-tillägg kan du anpassa SharePoint-upplevelsen på ett mer övergripande sätt, inklusive meddelandeområden, verktygsfält och listdatavyer.

Tillägg kan ha ett dåligt inflytande över prestandan för en SharePoint-sida eftersom det också tar PROCESSOR- och nätverksresurser att göra obligatoriskt arbete.

Det finns fyra typer av tillägg:

- **Application Customizers** lägger till skript på sidan och öppnar välkända platshållare för HTML-element och utökar dem med anpassade renderingar.
- **Med Fältanpassare** får du ändrade vyer för data för fält i en lista.
- **Kommandouppsättningar** utökar SharePoint-kommandoytorna för att lägga till nya åtgärder och tillhandahåller klientkod som du kan använda för att implementera beteenden.
- **Ändring av sökfråga (endast förhandsgranskning)** anropas precis innan sökfrågan körs.

## <a name="remediate-extension-performance-issues"></a>Åtgärda prestandaproblem med tillägg

Följ instruktionerna i det här avsnittet för att identifiera och åtgärda prestandaproblem med tillägg som listas i tillägg som **påverkar sidinläsningstidens** resultat.

>[!NOTE]
>Programanpassare kan köras i ett tidigt skede under en sidas livscykel och det kan påverka prestandan för andra tillägg på sidan.

Granskningsresultatet i siddiagnostikverktyget visar två steg i körningen av ett tillägg för att hjälpa till att identifiera den potentiella prestanda påverkan.

- **Modulens** inläsning är hur lång tid det tar att läsa in tillägget, vilket påverkas av storleken på ett tillägg, så det är en bra idé att bara samla de bibliotek som behövs i tillägget och att även välja ljusare bibliotek.
- **Init** is the initialization time of the extension and extension developers should consider whether the extension is doing unnecessary work or executing too many commands during the initializing stage.

Sidförfattare kan också använda granskningsresultatet för att se om en sida har för många tillägg eftersom för många tillägg negativt påverkar prestandan för en sida.

- **Filstorlek och beroenden**
  - Du måste använda Office 365 CDN för optimal nedladdning av statiska resurser. Offentliga CDN-ursprung är bättre för _js/css-filer._ Mer information om hur du använder Office 365 CDN finns i Använda [Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Återanvänd ramverk som _React_ och _Fabric-import_ som kommer som en del av SharePoint Framework (SPFx). Mer information finns i [Översikt över SharePoint Framework.](https://docs.microsoft.com/sharepoint/dev/spfx/sharepoint-framework-overview)
  - Se till att du använder den senaste versionen av SharePoint Framework och uppgradera till nya versioner när de blir tillgängliga.
- **Hämtning/cachelagring av data**
  - Om tillägget förlitar sig på extra serveranrop för att hämta data för visning ska du se till att de server-API:erna är snabba och/eller implementera cachelagring på klientsidan (t.ex. använda _localStorage_ eller _IndexDB_ för större uppsättningar).
  - Om flera anrop krävs för att återge viktiga data kan du överväga att batcha på servern eller andra metoder för att konsolidera förfrågningar till ett enda samtal.
  - Alternativt, om vissa dataelement kräver ett långsammare API, men inte är viktiga för den första renderingen, kan du avkoda dessa till ett separat anrop som körs när viktiga data har återges.
  - Om flera delar använder samma data bör du använda ett vanligt datalager för att undvika dubbletter av samtal.
- **Renderingstid**
  - Alla mediekällor som bilder och videor bör ha en storlek som begränsar behållaren, enheten och/eller nätverket för att undvika att ladda ned onödiga stora tillgångar. Mer information om innehållsberoenden finns i Använda [Office 365 Content Delivery Network (CDN) med SharePoint Online.](use-microsoft-365-cdn-with-spo.md)
  - Undvik API-anrop som leder till flödesschema, komplexa CSS-regler eller komplicerade animeringar. Mer information finns i [Minimera webbläsarens flödesomformning.](https://developers.google.com/speed/docs/insights/browser-reflow)
  - Undvik att använda kedjeaktiviteter som körs länge. Dela i stället upp långa aktiviteter i separata köer. Mer information finns i Optimera [körning av JavaScript.](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution)
  - Reservera motsvarande utrymme för asynkron rendering av media eller visuella element för att undvika överhoppade ramar och hackar (kallas även _jank)._
  - Om en viss webbläsare inte har stöd för en funktion som används för rendering kan du antingen läsa in en polyfyllfunktion eller exkludera att köra beroende kod. Om funktionen inte är kritisk kasserar du resurser som händelsehanterare för att undvika minnesläckor.

Innan du gör sidändringar för att åtgärda prestandaproblem bör du anteckna sidinläsningstiden i analysresultaten. Kör verktyget igen efter ändringen för att se om det nya resultatet ligger inom baslinjestandarden och kontrollera inläsningstiden för den nya sidan för att se om det finns en förbättring.

![Inläsningstidsresultat för sida](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Sidinläsningstiden kan variera beroende på en mängd olika faktorer, till exempel nätverksbelastning, tid på dagen och andra tillfälliga villkor. Du bör testa inläsningstiden för sidor några gånger före och efter du gör ändringar för att beräkna medelvärdet för resultatet.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i det moderna SharePoint-programmet](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
