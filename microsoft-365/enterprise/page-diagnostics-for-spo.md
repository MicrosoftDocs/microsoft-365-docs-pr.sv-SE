---
title: Använda verktyget för nätverksdiagnostik för SharePoint Online
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
description: Använd verktyget för nätverksdiagnostik för SharePoint för att analysera SharePoint Online-moderna portaler och klassiska publicerings sidor mot en förutbestämd uppsättning prestanda villkor.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696711"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>Använda verktyget för nätverksdiagnostik för SharePoint

I den här artikeln beskrivs hur du använder **verktyget för nätverksdiagnostik för SharePoint** för att analysera sidor för moderna och klassiska SharePoint Online-webbplatser mot en förutbestämd uppsättning prestanda villkor.

Verktyget för nätverksdiagnostik för SharePoint kan installeras för:

- **Microsoft Edge** [(Edge-tillägg)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome** [(Chrome-tillägg)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>Version **2.0.0** och senare innehåller stöd för moderna sidor, utöver klassiska webbplats sidor. Om du är osäker på vilken version av verktyget du använder kan du välja **om** -länken eller ellipsen (...) för att verifiera din version. **Uppdatera alltid till den senaste versionen** när du använder verktyget.

Verktyget för nätverksdiagnostik för SharePoint är ett webb läsar tillägg för de nya Microsoft Edge- https://www.microsoft.com/edge) webbläsarna (och Chrome som analyserar både SharePoint Online moderna Portal och klassisk publicerings webbplats sidor. Det här verktyget fungerar bara för SharePoint Online och kan inte användas på en SharePoint-Systemsida.

Verktyget genererar en rapport för varje sida som visar hur sidan fungerar mot en fördefinierad uppsättning regler och visar detaljerad information när resultaten för ett test ligger utanför bas linjen. SharePoint Online-administratörer och designer kan använda verktyget för att felsöka prestanda problem och för att säkerställa att nya sidor optimeras före publiceringen.

Verktyget för nätverksdiagnostik används bara för att analysera sidor i SharePoint-webbplatsen, inte på system sidor som *AllItems. aspx* eller *SharePoint. aspx*. Om du försöker köra verktyget på en system sida eller någon annan sida utanför webbplatsen får du ett fel meddelande om att det inte går att köra verktyget för den typen av sida.

![Måste köras på en SharePoint-sida](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

Det här är inte ett fel i verktyget eftersom det inte finns något värde för att utvärdera bibliotek eller system sidor. Navigera till en SharePoint-webbplats för att använda verktyget. Om felet uppstår på en SharePoint-sida kontrollerar du huvud sidan för att se till att SharePoint-metataggarna inte har tagits bort.

Om du vill lämna feedback om verktyget väljer du ellipsen i det övre högra hörnet i verktyget och väljer sedan [ge feedback](https://go.microsoft.com/fwlink/?linkid=874109).

![Ge feedback](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>Installera verktyget för nätverksdiagnostik för SharePoint

Installations proceduren i det här avsnittet fungerar både för webbläsarna Chrome och Microsoft Edge.

> [!IMPORTANT]
> Microsoft läser inte data-eller sid innehåll som analyseras av verktyget för nätverksdiagnostik för SharePoint, och ingen personlig information, webbplats eller nedladdnings information. Den enda identifierbara informationen som är inloggad i Microsoft av verktyget är klient organisationens namn, antalet regler som misslyckats och det datum och den tid då verktyget kördes. Den här informationen används av Microsoft för att bättre förstå moderna Portal-och publicerings webbplats användnings trender och vanliga prestanda problem.

1. Installera verktyget för sid diagnos för SharePoint för **Microsoft Edge** [(Edge Extension)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) eller **Chrome** [(Chrome)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi). Läs igenom användar integritets policyn på sidan beskrivning i butiken. När du lägger till verktyget i webbläsaren visas följande behörigheter.

    ![Behörigheter för tillägg](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    Det här meddelandet beror på att en sida kan innehålla innehåll från platser utanför SharePoint, beroende på webb delarna och anpassningarna på sidan. Det innebär att verktyget läser förfrågningarna och svaren när du klickar på Start-knappen och endast för den aktiva SharePoint-flik där verktyget körs. Den här informationen sparas lokalt av webbläsaren och kan nås via knappen **Exportera till JSON** eller **Exportera till** på verktygets flik för _nätverks spårning_ . **informationen skickas inte till eller sparas av Microsoft.** (Verktyget respekterar Microsofts integritets policy som är tillgänglig [här](https://go.microsoft.com/fwlink/p/?linkid=857875).)

    _Hantera dina nedladdnings_ behörigheter omfattar användning av verktygets **export till JSON** -funktion. Följ företagets egna integritets rikt linjer innan du delar JSON-filen utanför organisationen, eftersom resultatet innehåller URL-adresser och som kan klassificeras som PII (personligt identifierbar information).
1. Om du vill använda verktyget i inkognitofönster eller InPrivate-läge följer du anvisningarna för din webbläsare:
    1. I Microsoft Edge navigerar du till **tillägg** eller skriver _Edge://Extensions_ i URL-fältet och väljer sedan **information** för tillägget. Markera kryss rutan **Tillåt i InPrivate**i inställningar för tillägg.
    1. I Chrome navigerar du till **anknytningar** eller skriver _Chrome://Extensions_ i URL-fältet och väljer **information** för tillägget. I tilläggs inställningar väljer du skjutreglaget för **Tillåt i inkognitofönster**.
1. Gå till sidan SharePoint-webbplats i SharePoint Online som du vill granska. Vi har tillåtit för "fördröj laddning" av objekt på sidor. Därför kommer verktyget inte att sluta fungera automatiskt (det här är genom att designa alla scenarier för sid inläsningar). Om du vill stoppa samlingen väljer du **stoppa**. Kontrol lera att sid inläsningen är klar innan du stoppar data insamlingen eller att du bara gör en ofullständig spårning.
1. Klicka på knappen för knapps tillägget ![Page Diagnostics för SharePoint-logotyp](../media/page-diagnostics-for-spo/pagediag-icon32.png) Om du vill ladda verktyget och få följande tillägg i snabb menyn:

    ![Popup-menyn för nätverksdiagnostik](../media/page-diagnostics-for-spo/pagediag-Landing.png)

Välj **Start** för att börja samla in data för analys.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>Det här visas i verktyget Page Diagnostics för SharePoint

1. Klicka på ellipsen (...) i det övre högra hörnet av verktyget för att hitta följande länkar:
   1. Länken **ytterligare resurser** innehåller allmän vägledning och information om verktyget, inklusive en länk till den här artikeln.
   1. Länken **ge feedback** är en länk till webbplatsen för _SharePoint-webbplatser och samarbets användare_ .
   1. Med **om** -länken ingår den installerade versionen av verktyget och en direkt länk till verktyget tredje part.  
1. **Korrelations-ID: t, SPRequestDuration, SPIISLatency**, **sid inläsnings tid**och **URL** -information är informations och kan användas i några få skäl.

    ![Information om Page Diagnostics](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** är ett viktigt element när du arbetar med Microsofts support eftersom det tillåter att de samlar in ytterligare diagnostikdata för den specifika sidan.
   - **SPRequestDuration** är den tid det tar för SharePoint att bearbeta sidan. Strukturell navigering, stora bilder, massor av API-samtal kan bidra till längre varaktigheter.
   - **SPIISLatency** är tiden i millisekunder som tar för SharePoint Online att läsa in sidan. Detta värde inkluderar inte den tid det tar för webb programmet att svara.
   - **Sid inläsnings tid** är den totala tiden som har registrerats av sidan från den tid då svaret togs emot och renderades i webbläsaren. Det här värdet påverkas av en mängd olika faktorer, inklusive nätverks svars tid, datorns prestanda och den tid det tar för webbläsaren att läsa in sidan.
   - **Sidans URL** (Uniform Resource Locator) är webb adressen för den aktuella sidan.

1. På fliken [**diagnostiska test**](#how-to-use-the-diagnostic-tests-tab) visas analys resultaten i tre kategorier; **Ingen åtgärd krävs**, **förbättrings möjligheter** och **åtgärd krävs**. Varje test resultat representeras av ett objekt i en av dessa kategorier enligt beskrivningen i följande tabell:

    |Kategori  |Tvåfärgad  |Beskrivning  |
    |---------|---------|---------|
    |**Åtgärd krävs** |Röda |Test resultatet hamnar utanför bas linjen och påverkar sid prestanda. Följ reparations vägledningen.|
    |**Förbättrings möjligheter** |Blått |Test resultatet hamnar utanför bas linjen och kan bidra till prestanda problem. Testspecifika kriterier kan tillkomma.|
    |**Ingen åtgärd krävs** |Havsgrön |Test resultatet hamnar i testets bas linje värde.|

    ![Nätverksdiagnostik](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. En flik för [**nätverks spårning**](#how-to-use-the-network-trace-tab) tillhandahåller information om begär Anden och svar på sidans konstruktion.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>Så här använder du fliken diagnostiska test

När du analyserar en SharePoint-modern eller klassisk publicerings webbplats med Page Diagnostics för SharePoint Tool analyseras resultaten med hjälp av fördefinierade regler som jämför resultat mot original Plans värden och som visas på fliken **diagnostiska test** . regler för vissa tester kan använda olika original värden för moderna portaler och klassiska publicerings webbplatser beroende på hur specifika prestanda egenskaper skiljer sig mellan de två.

Test resultat som visas i de **förbättrade möjligheterna till förbättring** eller **uppmärksamhet** visar vilka områden som ska granskas mot rekommenderad praxis och kan väljas för att visa ytterligare information om resultatet. Information för varje objekt inkluderar en länken _Lär dig mer_ som tar dig direkt till lämplig vägledning för testet. Test resultat som visas i kategorin **Ingen åtgärd krävs** visar att den relevanta regeln följs och inte innehåller ytterligare information när det är markerat.

Informationen på fliken diagnostiska test visar inte hur du utformar sidor, men framhäver faktorer som kan påverka sid prestanda. Vissa sid funktioner och anpassningar har en oundviklig inverkan på sid prestanda och bör ses över för att det ska vara en väsentlig åtgärd.

Röda och gula resultaten kan även indikera webb delar som uppdaterar data oftare. Till exempel uppdateras inte företags nyheter, men anpassade webb delar är ofta byggda för att hämta de senaste nyheterna i stället för att implementera cachade element som kan förbättra den övergripande användar upplevelsen. Tänk på följande när du inkluderar webb delar på en sida som det ofta finns enkla sätt att minska prestandan genom att utvärdera värdet för varje tillgänglig parameter för att säkerställa att den är korrekt inställd för dess avsedda ändamål.

>[!NOTE]
>De grupp webbplatser som inte har publicerings funktionen aktive rad kan inte använda CDN. När du kör verktyget på de här webbplatserna förväntas CDN-testet inte och kan ignoreras, men alla återstående tester är tillämpliga. Med ytterligare funktioner för SharePoint-publicering kan du öka sid inläsnings tiden så att den inte ska aktive ras bara för att tillåta CDN-funktioner.

>[!IMPORTANT]
>Test regler läggs till och uppdateras regelbundet så se den senaste versionen av verktyget för information om aktuella regler och specifik information som ingår i test resultaten. Du kan kontrol lera versionen genom att hantera dina anknytningar och fil namns tillägget aviserar om det finns en uppdatering.

## <a name="how-to-use-the-network-trace-tab"></a>Så här använder du fliken nätverks spårning

Fliken **nätverks spårning** innehåller detaljerad information om båda förfrågningarna om att bygga sidan och de svar som tas emot från SharePoint.

1. **Leta efter objekt inläsnings tider flaggade som röda**. Varje begäran och svar är färgkodad för att visa att den påverkar övergripande sid prestanda med följande svars värden:
    - Grönt: \< 500ms
    - Gul: 500-1000ms
    - Rött: \> 1000ms

    ![Nätverks spårning](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    I bilden ovan visas det röda objektet för standard sidan. Det visar alltid rött såvida inte sidan laddas i \< 1000ms (mindre än 1 sekund).

2. **Testa objekt inläsnings tider**. I vissa fall visas ingen tids-eller färg indikator eftersom objekten redan har cachelagrats av webbläsaren. Testa detta genom att öppna sidan, rensa webbläsarens cache och sedan klicka på **Starta** som framtvingar en "kall inläsning" av sidan. Detta ska sedan jämföras med "varm-Sidan Load" eftersom den också kan avgöra vilka objekt som cachelagras på sidan.

3. **Dela relevanta uppgifter med andra som kan hjälpa dig att undersöka problem**. Om du vill dela med dig av informationen eller informationen i verktyget med utvecklarna eller en teknisk support-person klickar du på **Exportera till JSON** (som på bilden ovan). Det gör att du kan ladda ned resultaten, som kan visas i en JSON-fil.

    Om du har valt att använda funktionen för förhands granskning *aktivera export till* har export typen att visas som **export till**har gjort.

    ![Nätverks spårning](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> De här resultaten innehåller URL: er och kan klassificeras som PII (personligt identifierbar information). Kontrol lera att du följer organisationens rikt linjer innan du distribuerar denna information.

## <a name="engaging-with-microsoft-support"></a>Engagera dig med Microsofts support

Vi har inkluderat en **Microsoft Support Level-funktion** som bara bör användas när du arbetar direkt med ett support ärende. Användning av den här funktionen ger ingen förmån när den används utan support team och kan göra att sidan går betydligt långsammare. Det finns ingen ytterligare information när du använder den här funktionen i verktyget eftersom ytterligare information läggs till i loggningen i tjänsten.

Ingen ändring visas förutom att du får ett meddelande om att du har aktiverat den och att din sida fungerar markant genom 2-3 gånger långsammare prestanda medan den är aktive rad. Det är bara relevant för den aktuella sidan och den aktiva sessionen. Av den anledningen bör detta användas sparsamt och bara när det aktivt används med support.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Så här aktiverar du Microsoft Support nivå funktionen

1. Öppna verktyget Page Diagnostics for SharePoint.
2. Tryck på **Alt + Skift-L**på tangent bordet. Då visas kryss rutan **Aktivera support loggning** .
3. Markera kryss rutan och klicka sedan på **Starta** för att läsa in sidan på nytt och generera utförlig loggning.

    ![Alternativet support aktiverat](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    Observera att CorrelationID (visas högst upp i verktyget) och ge det till din support representant så att de kan samla in ytterligare information om den diagnostiska sessionen.

## <a name="related-topics"></a>Relaterade ämnen

[Justera SharePoint Online-prestanda](tune-sharepoint-online-performance.md)

[Justera Office 365-prestanda](tune-microsoft-365-performance.md)

[Prestanda i den moderna SharePoint-upplevelsen](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[Nätverk för innehålls leverans](content-delivery-networks.md)

[Använda Office 365-innehålls leverans nätverk (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
