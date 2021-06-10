---
title: Använda verktyget Siddiagnostik för SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Använd Siddiagnostik för SharePoint för att analysera SharePoint modern portal och klassiska publiceringssidor online mot en fördefinierad uppsättning prestandavillkor.
ms.openlocfilehash: b55e5c04f56bac4e6313284de60753d1beaaaed1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921636"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Använda siddiagnostik för SharePoint verktyg

I den här artikeln beskrivs hur du använder siddiagnostikverktyget för **SharePoint för** att analysera moderna och klassiska webbplatssidor i SharePoint Online mot en fördefinierad uppsättning prestandavillkor.

Siddiagnostik för SharePoint installeras för:

- **Microsoft Edge** [(Edge-tillägg)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(Chrome-tillägg)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>Version **2.0.0** och senare har stöd för moderna sidor utöver klassiska webbplatssidor. Om du är osäker på vilken version av verktyget  du använder kan du verifiera din version genom att välja länken Om eller ellipsen (...). **Uppdatera alltid till den senaste versionen** när du använder verktyget.

Siddiagnostik för SharePoint är ett webbläsartillägg för nya Microsoft Edge ( och Chrome-webbläsare som analyserar både moderna SharePoint Online-portalen och klassiska https://www.microsoft.com/edge) publiceringswebbplatssidor. Det här verktyget fungerar bara SharePoint Online och kan inte användas på SharePoint systemsida.

Verktyget genererar en rapport för varje analyserad sida som visar hur sidan fungerar mot en fördefinierad uppsättning regler och visar detaljerad information när resultaten för ett test faller utanför baslinjevärdet. SharePoint Onlineadministratörer och designers kan använda verktyget för att felsöka prestandaproblem och se till att nya sidor optimeras innan du publicerar.

Verktyget Siddiagnostik är utformat för att analysera SharePoint endast webbplatssidor, inte systemsidor som *allitems.aspx* eller *sharepoint.aspx.* Om du försöker köra verktyget på en systemsida eller någon annan sida än sidan på webbplatsen får du ett felmeddelande som anger att verktyget inte kan köras för den typen av sida.

> [!div class="mx-imgBorder"]
> ![Måste köras på en SharePoint sida](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Det här är inte ett fel i verktyget eftersom det inte finns något värde i att utvärdera bibliotek eller systemsidor. Gå till en SharePoint webbplatssida för att använda verktyget. Om det här felet inträffar SharePoint på en annan sida kontrollerar du på huvudsidan att SharePoint bort metataggarna inte har tagits bort.

Ge feedback om verktyget genom att välja ellipsen i det övre högra hörnet av verktyget och sedan välja [Ge feedback.](https://go.microsoft.com/fwlink/?linkid=874109)

> [!div class="mx-imgBorder"]
> ![Lämna feedback](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Installera verktyget Siddiagnostik för SharePoint siddiagnostik

Installationsproceduren i det här avsnittet fungerar för både Chrome och Microsoft Edge webbläsare.

> [!IMPORTANT]
> Microsoft läser inte data- eller sidinnehåll som analyseras av siddiagnostikverktyget för SharePoint och vi samlar inte in någon personlig information, webbplats eller nedladdningsinformation. Det enda identifierbara information som loggas på Microsoft med verktyget är klientorganisationens namn, antalet regler som har misslyckats och datum och tid då verktyget körts. Den här informationen används av Microsoft för att bättre förstå moderna portal- och publiceringstrender för webbplatsanvändning och vanliga prestandaproblem.

1. Installera Siddiagnostik för SharePoint för ett **Microsoft Edge** [(Edge-tillägg) eller](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) **Chrome** [(Chrome-tillägg).](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi) Läs igenom användarsekretesspolicyn som finns på beskrivningssidan i Store. När du lägger till verktyget i webbläsaren visas följande behörighetsmeddelande.

    > [!div class="mx-imgBorder"]
    > ![Tilläggsbehörigheter](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Det här meddelandet finns eftersom en sida kan innehålla innehåll från platser utanför SharePoint beroende på webbdelarna och anpassningarna på sidan. Det innebär att verktyget läser förfrågningar och svar när du klickar på startknappen och bara för den aktiva SharePoint där verktyget körs. Den här informationen lagras lokalt i webbläsaren och är tillgänglig via knappen Exportera till **JSON** eller Exportera till **HAR** på fliken Nätverksspårning för verktyget. Informationen skickas inte till eller lagras av  **Microsoft.** (Verktyget respekterar Microsofts sekretesspolicy som finns [här](https://go.microsoft.com/fwlink/p/?linkid=857875).)

    Behörigheten _Hantera dina nedladdningar_ omfattar användningen av verktygets Export till **JSON-funktioner.** Följ företagets egna riktlinjer för sekretess innan du delar JSON-filen utanför organisationen, eftersom resultatet innehåller URL:er och som kan klassificeras som personligt identifierbar information.
1. Om du vill använda verktyget i Inkognito- eller InPrivate-läge följer du instruktionerna för webbläsaren:
    1. I Microsoft Edge går du till **Tillägg** eller skriver _edge://extensions_ i URL-fältet och **väljer Information** för tillägget. I tilläggsinställningarna markerar du kryssrutan för **Tillåt i InPrivate.**
    1. I Chrome går du till **Tillägg** eller skriver _chrome://extensions_ i URL-fältet och **väljer Information** för tillägget. I tilläggsinställningarna väljer du skjutreglaget för **tillåt i Inkognito**.
1. Gå till SharePoint webbplatssidan SharePoint Online som du vill granska. Vi har tillåtit "fördröjd inläsning" av objekt på sidor. Därför stoppas inte verktyget automatiskt (det här är av designsidan för att passa alla scenarier med sidinläsning). Om du vill stoppa samlingen väljer du **Stoppa**. Kontrollera att sidinläsningen har slutförts innan du stoppar datainsamlingen, annars visas bara en delspårning.
1. Klicka på tilläggets verktygsfältsknapp ![Siddiagnostik för SharePoint logotyp](../media/page-diagnostics-for-spo/pagediag-icon32.png) för att läsa in verktyget så visas följande popup-fönster för tillägg:

    ![Popup-verktyg för siddiagnostik](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Välj **Börja samla** in data för analys.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Det här visas i verktyget Siddiagnostik för SharePoint diagnostikverktyg

1. Klicka på ellipsen (...) i det övre högra hörnet av verktyget för att hitta följande länkar:
   1. Länken **Ytterligare resurser** innehåller allmän vägledning och information om verktyget, inklusive en länk tillbaka till den här artikeln.
   1. Länken **Ge feedback** innehåller en länk till webbplatsen SharePoint _Samarbetswebbplatser och User Voice-samarbete._
   1. Länken **Om** innehåller den installerade versionen av verktyget och en direkt länk till verktygets meddelande från tredje part.  
1. **Korrelations-ID, SPRequestDuration, URL:erLatency,** Sidinläsningstid och **URL-information** är information och kan användas för några syften. 

    > [!div class="mx-imgBorder"]
    > ![Information om siddiagnostik](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** är ett viktigt element när de arbetar med Microsoft Support eftersom det gör att de kan samla in ytterligare diagnostikdata för den specifika sidan.
   - **SPRequestDuration** är den tid det tar SharePoint att bearbeta sidan. Strukturell navigering, stora bilder, många API-anrop kan alla bidra till längre varaktighet.
   - **SPIISLatency** är tiden i millisekunder som SharePoint inläsningen av sidan online. Det här värdet omfattar inte hur lång tid det tar för webbprogrammet att svara.
   - **Sidinläsningstid** är den totala tiden som registrerats av sidan från tiden för begäran till den tidpunkt då svaret togs emot och återges i webbläsaren. Det här värdet påverkas av en mängd faktorer, till exempel nätverkets svarstid, datorns prestanda och den tid det tar för webbläsaren att läsa in sidan.
   - **Sid-URL** :en (Uniform Resource Locator) är webbadressen till den aktuella sidan.

1. På [**fliken Diagnostiktester**](#how-to-use-the-diagnostic-tests-tab) visas analysresultatet i tre kategorier. **Ingen åtgärd krävs**, **förbättringsmöjligheter** och **uppmärksamhet krävs.** Varje testresultat representeras av ett objekt i någon av följande kategorier enligt beskrivningen i följande tabell:

    |Kategori  |Färg  |Beskrivning  |
    |---------|---------|---------|
    |**Åtgärder krävs** |Röd |Testresultatet ligger utanför baslinjevärdet och påverkar sidprestandan. Följ reparationsvägledning.|
    |**Förbättringsmöjligheter** |Gul |Testresultatet ligger utanför baslinjevärdet och kan bidra till prestandaproblem. Testspecifika villkor kan gälla.|
    |**Ingen åtgärd krävs** |Grön |Testresultatet faller inom testets baslinjevärde.|

    > [!div class="mx-imgBorder"]
    > ![Siddiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. En [**flik för nätverksspårning**](#how-to-use-the-network-trace-tab-and-how-to-export-a-har-file) innehåller information om förfrågningar om sid byggen och svar.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Så här använder du fliken Diagnostiktest

När du analyserar en SharePoint modern portalsida eller en klassisk publiceringswebbplatssida med verktyget Siddiagnostik för SharePoint analyseras resultaten med fördefinierade regler som jämför resultaten med baslinjevärden och visas på fliken Diagnostiktest.  Regler för vissa tester kan använda olika baslinjevärden för moderna portalen och klassiska publiceringswebbplatser beroende på hur specifika prestandaegenskaper skiljer sig åt mellan dem.

Testresultat som visas  i  kategorierna Förbättringsmöjligheter eller Åtgärder som krävs anger områden som ska granskas mot rekommenderade metoder och kan väljas för att visa ytterligare information om resultatet. Information om varje objekt innehåller _en Läs mer-länk_ som tar dig direkt till rätt vägledning för testet. Testresultat som visas i kategorin **Ingen åtgärd krävs anger** att den relevanta regeln efterlevs och att ingen ytterligare information visas när den väljs.

Informationen på fliken Diagnostiktest visar inte hur du utformar sidor, men faktorer som kan påverka sidprestandan framhävs. Vissa sidfunktioner och sidanpassningar har en ofrånkomlig inverkan på sidprestandan och bör granskas för att risken för åtgärder eller utelämnande från sidan är avsevärd.

Röda eller gula resultat kan också ange webbdelar som uppdaterar data för ofta. Till exempel uppdateras inte företagsnyheter varannan gång, men anpassade webbdelar är ofta byggda för att hämta de senaste nyheterna varannan gång i stället för att implementera cachelagringselement som kan förbättra användarupplevelsen. Kom ihåg när du tar med webbdelar på en sida som det ofta finns enkla sätt att minska deras prestanda genom att utvärdera värdet på varje tillgänglig parameter för att säkerställa att den konfigureras på rätt sätt för sitt avsedda syfte.

>[!NOTE]
>Klassiska gruppwebbplatser som inte har publiceringsfunktionen aktiverad kan inte använda CDN. När du kör verktyget på dessa webbplatser CDN testet misslyckas och kan ignoreras, men alla återstående tester är tillämpliga. De ytterligare funktionerna i SharePoint kan öka inläsningstider för sidor, så den bör inte aktiveras bara för att CDN funktioner.

>[!IMPORTANT]
>Testregler läggs till och uppdateras regelbundet, så mer information om aktuella regler och specifik information om testresultaten finns i den senaste versionen av verktyget. Du kan verifiera versionen genom att hantera dina tillägg och tillägget anger om det finns en uppdatering tillgänglig.

## <a name="how-to-use-the-network-trace-tab-and-how-to-export-a-har-file"></a>Så här använder du fliken Nätverksspårning och hur du exporterar en HAR-fil

På **fliken Nätverksspårning** finns detaljerad information om både förfrågningar om att skapa sidan och de svar som tas emot från SharePoint.

1. **Leta efter inläsningstider för objekt som är flaggade som röda**. Varje begäran och svar är färgkodade för att indikera dess inverkan på sidans övergripande prestanda med följande svarstidsmått:
    - Grön: \< 500 ms
    - Gul: 500–1 000 ms
    - Röd: \> 1 000 ms

    > [!div class="mx-imgBorder"]
    > ![Nätverksspårning](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    I bilden ovan gäller det röda objektet standardsidan. Det visas alltid rött om sidan inte läses in \< på 1 000 ms (mindre än 1 sekund).

2. **Testa inläsningstider för objekt.** I vissa fall finns det ingen tids- eller färgindikator eftersom objekten redan har cachelagrats i webbläsaren. Om du vill testa det här korrekt öppnar du sidan, rensar webbläsarens cache och klickar sedan på **Starta** eftersom det gör att det blir en "kall" sidinläsning och en verklig reflektion av den första sidinläsningen. Det bör sedan jämföras med den "varma" sidinläsningen eftersom den också gör det möjligt att avgöra vilka objekt som cachelagras på sidan.

3. **Dela relevant information med andra som kan hjälpa dig att undersöka problem.** Om du vill dela information som finns i verktyget med dina utvecklare eller en teknisk supportperson rekommenderar vi att du använder Aktivera export till **HTTP-arkiv (HAR).** 

   > [!div class="mx-imgBorder"]
   > ![Aktivera export till HAR](../media/page-diagnostics-for-spo/pagediag-submithar.png)

Det bör aktiveras innan du klickar på Start, vilket sedan aktiverar felsökningsläge i webbläsaren. Det genererar en HTTP-arkivfil (HAR) som sedan kan nås via fliken "Nätverksspårning". Klicka på "Exportera till HAR" så laddas filen ned till datorn och du kan sedan dela den i enlighet med detta. Filen kan öppnas i en mängd olika felsökningsverktyg, som F12 Developer Tools och Fiddler.

> [!div class="mx-imgBorder"]
> ![Nätverksspårning](../media/page-diagnostics-for-spo/pagediag-networktracehar.png)

> [!IMPORTANT]
> Resultaten innehåller URL:er och kan klassificeras som personligt identifierbar information. Se till att följa organisationens riktlinjer innan du distribuerar den informationen.

## <a name="engaging-with-microsoft-support"></a>Arbeta med Microsoft Support

Vi har inkluderat en **funktion på Microsoft Support-nivå** som endast ska användas när du arbetar direkt med ett supportfall. Användning av den här funktionen ger inga fördelar när den används utan teamengagemang, och kan göra att sidan presterar betydligt långsammare. Det finns ingen ytterligare information när du använder den här funktionen i verktyget eftersom ytterligare information läggs till i loggning i tjänsten.

Ingen ändring visas förutom att du får ett meddelande om att du har aktiverat det och att sidprestandan kommer att försämras avsevärt med 2–3 gånger långsammare prestanda trots att den är aktiverad. Den är bara relevant för den specifika sidan och den aktiva sessionen. Av den anledningen bör det bara användas sparsamt och vid aktivt samarbete.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Så här aktiverar du funktionen Microsoft Support-nivå

1. Öppna verktyget Siddiagnostik för SharePoint diagnostikverktyg.
2. Tryck på **ALT-Skift-L på tangentbordet.** Då visas kryssrutan **Aktivera supportloggning.**
3. Markera kryssrutan och klicka sedan på Starta för **att** läsa in sidan igen och generera utförlig loggning.

   > [!div class="mx-imgBorder"]
   > ![Supportalternativ aktiverat](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Observera CorrelationID (visas överst i verktyget) och ge det till din supportrepresentant så att de kan samla in ytterligare information om diagnostiksessionen.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint onlineprestanda](tune-sharepoint-online-performance.md)

[Justera Office 365 prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint upplevelsen](/sharepoint/modern-experience-performance)

[Nätverk för innehållsleverans](content-delivery-networks.md)

[Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)