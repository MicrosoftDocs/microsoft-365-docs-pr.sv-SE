---
title: Prestandajustering för Office 365 med baslinjer och prestandahistorik
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Lär dig hur du kontrollerar historiken för klientdatoranslutningar så att du kan upptäcka nya problem tidigt.
ms.openlocfilehash: 87b1d43df560fc7fea5aadfbf1c422eb22883067
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928150"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Prestandajustering för Office 365 med baslinjer och prestandahistorik

Det finns några enkla sätt att kontrollera prestandan för anslutningen mellan Office 365 och ditt företag, vilket gör det enklare att upprätta en ungefärlig baslinje för anslutningen. Det kan vara bra att känna till prestandahistoriken för klientdatoranslutningar för att kunna upptäcka och identifiera problem tidigt och förutse eventuella problem.
  
Den här artikeln är avsedd för den som inte är van att arbeta med prestandaproblem, och hjälper till med vanliga frågor som: Hur vet jag att det jag ser är ett prestandaproblem och inte ett problem med Office 365-tjänsten? Hur planerar du bra prestanda på lång sikt? Hur kan jag hålla ett öga på prestandan? Om din grupp eller dina klienter har låg prestanda när du använder Office 365 och du undrar över några av de här frågorna, så är det här rätt artikel för dig.
  
> [!IMPORTANT]
> **Är det prestandaproblem mellan din klient och Office 365 just nu?** Följ anvisningarna i planen för [prestandafelsökning för Office 365.](performance-troubleshooting-plan.md) 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Något du bör veta om prestanda i Office 365

Office 365 finns i ett dedikerat Microsoft-nätverk med hög kapacitet, som inte bara övervakas automatiserat utan även av verkliga personer. I Office 365-molnets underhåll ingår finjustering av prestanda och effektivisering där det är möjligt. Eftersom klienterna i Office 365-molnet måste ansluta via Internet är det kontinuerligt viktigt att finjustera prestanda även i Office 365-tjänsterna. Prestandaförbättringarna i molnet är ständig, och vi har samlat in mycket erfarenhet för att hålla molnet snabbt och felfritt. Om du upplever prestandaproblem när du ansluter från din plats till Office 365 är det bäst att inte börja med och vänta på ett supportfall. I stället bör du börja undersöka problemet "inifrån och ut". Det vill säga börja i ditt nätverk och arbeta dig ut på Office 365. Innan du öppnar ett ärende för Office 365-supporten kan du samla in data och vidta åtgärder som utforskar problemet och som kan lösa det.
  
> [!IMPORTANT]
> Var uppmärksam på kapacitetsplanering och begränsningar i Office 365. Den informationen gör att du kommer kurvan när du försöker lösa ett prestandaproblem. Här är en länk till [tjänstbeskrivningarna för Microsoft 365 och Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Det här är ett centralt nav och alla tjänster som erbjuds av Office 365 har en länk som går till deras egna tjänstbeskrivningar härifrån. Det innebär att om du till exempel behöver se standardbegränsningarna för SharePoint Online klickar du på Tjänstbeskrivning för [SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) och letar reda på avsnittet Begränsningar för [SharePoint Online.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) 
  
Se till att du går in i felsökningen och förstår att prestandan är en skjutskala, det handlar inte om att uppnå ett idealiserat värde och att underhålla det permanent (om du tror att det är så är det, så kommer tillfälliga uppgifter med hög bandbredd, som att göra ett stort antal användare, eller att göra stora datamigreringar vara mycket stressigt , så planera för prestandaeffekter då). Du kan och bör ha en grov uppfattning om dina prestandamål, men många variabler spelar in prestanda och därför varierar prestandan. Det är prestandan. 
  
Felsökning av prestandan handlar inte om att nå specifika mål och ha ett obestämt antal, utan om att förbättra befintliga aktiviteter med alla variabler. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Hur ser då ett prestandaproblem ut?

Först måste du se till att det verkligen handlar om ett prestandaproblem och inte ett problem med själva tjänsten. Ett prestandaproblem skiljer sig från tjänstproblem i Office 365. Så här skiljer du dem åt.
  
Om det är ett tjänstproblem i Office 365-tjänsten är det ett tjänstproblem. Röda eller gula ikoner visas under Aktuell **status** i administrationscentret för Microsoft 365, och du kanske också märker långsam prestanda på klientdatorer som ansluter till Office 365. Om till exempel en röd ikon visas  för Aktuell status och Undersöker visas intill Exchange, kan du också få samtal från personer i organisationen med klagomål på att klientpostlådor som använder Exchange Online fungerar dåligt. I så fall är det lämpligt att anta att Exchange Online-prestandan är offer för problem inom tjänsten. 
  
![Office 365 Health-instrumentpanelen med alla arbetsbelastningar gröna, förutom Exchange, som visar Tjänsten har återställts.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
I det här läget bör du som Office  365-administratör kontrollera Aktuell status och sedan Visa information och historik ofta, för att hålla dig uppdaterad om det underhåll vi utför i systemet.  Instrumentpanelen **Aktuell** status har gjorts för att uppdatera dig om ändringar och problem i tjänsten. De anteckningar och förklaringar som finns i hälsohistoriken admin till admin är till för att hjälpa dig avgöra hur du påverkas och hålla dig publicerad om det pågående arbetet. 
  
![En bild av Office 365-hälsoinstrumentpanelen som förklarar att Exchange Online-tjänsten har återställts och varför.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Ett prestandaproblem är inte ett tjänstproblem även om låg prestanda också kan orsaka tjänstproblem. Ett prestandaproblem ser ut så här:
  
- Ett prestandaproblem uppstår oavsett vad som rapporterar aktuell **status** för tjänsten i administrationscentret. 
    
-  Ett beteende som tidigare var relativt sömlöst tar lång tid att slutföra eller slutförs aldrig. 
    
- Du kan replikera problemet eller vet att det kan replikeras om du gör rätt serie med steg.
    
-  Om problemet uppstår oregelbundet finns det fortfarande ett mönster. Du vet till exempel att du klockan 10:00 brukar få samtal från användare som inte har tillförlitlig åtkomst till Office 365, och att samtalen utar sig runt klockan 12:00. 
    
Det låter förmodligen bekant. kanske alltför bekant. När du vet att det är ett prestandaproblem uppstår frågan: "Vad gör du nu?" I resten av den här artikeln får du hjälp med att avgöra exakt det.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Definiera och testa prestandaproblem

Prestandaproblem uppstår ofta med tiden, så det kan vara svårt att definiera exakt vad problemet är. Du måste skapa en bra problemräkning och en god uppfattning om problemkontexten, och sedan måste du upprepa upprepade teststeg för att vinna dagen. Annars kan felet bli så att du förlorar det. Varför? Här är några exempel på problemrapporter som inte tillhandahåller tillräcklig information:
  
- Det brukade vara så enkelt att växla från Inkorgen till kalendern att jag inte märkte det, men nu tar det hela kaffepausen. Kan du få det att fungera som det brukade?
    
- Det tar evigheter att ladda upp mina filer till SharePoint Online. Varför går det långsamt på eftermiddagen men snabbt vid andra tidpunkter? Kan det inte vara snabbt hela nu?
    
Problemrapporterna ovan medför flera stora utmaningar. Det finns många tvetydigheter. till exempel:
  
- Det är oklart hur växlingen mellan Inkorgen och Kalendern brukade fungera på den bärbara datorn.
    
- Vad är "snabbt" när användaren säger "Kan det inte bara vara snabbt"?
    
- Hur länge är "evigheter"? Är det flera sekunder eller flera minuter, eller kan användaren gå på lunch och avslutas upp tio minuter efter att användaren kommit tillbaka?
    
Allt detta utan tanke på att administratören och felsökaren inte kan vara medvetna om så många detaljer från problemrapporter som dessa. Till exempel när problemet uppstod: Att användaren arbetar hemifrån och bara ser långsam växling när användaren är på ett hemnätverk. Att användaren måste köra flera andra RAM-resurskrävande program på den lokala klienten, eller så kör användaren ett äldre operativsystem eller inte har kört de senaste uppdateringarna.
  
När användare rapporterar ett prestandaproblem finns det en mängd information att samla in. Att samla in den här informationen är en del av att undersöka problemet och undersöka problemet. Följande är en grundläggande lista som du kan använda för att samla in information om prestandaproblem. Listan är inte uttömmande men den ger dig något att utgå från när du startar en egen lista: 
  
- Vilket datum hände problemet, och ungefär vilken tid på dagen eller natten?
    
- Vilken typ av klientdator använde du och hur ansluter den till företagsnätverket (VPN, kabel, trådlöst)?
    
- Arbetade du på distans eller på kontoret?
    
- Provade du att utföra samma åtgärder på en annan dator och se samma beteende?
    
- Gå igenom de steg som ger dig problem, så att du kan skriva ned vad du gör.
    
- Hur långsam i sekunder eller minuter är prestandan?
    
- Var i världen befinner du dig?
    
Vissa av dessa frågor är mer uppenbara än andra. De flesta förstår att en felsökare behöver de exakta stegen för att återskapa problemet. Hur kan du annars registrera vad som är fel och testa om problemet är åtgärdat? Mindre uppenbart är sådant som "Vilket datum och vilken tid såg du problemet?" och "Var i världen befinner du dig?", information som kan användas tillsammans. Beroende på när användaren arbetade kan några timmars tidsskillnad innebära att underhåll redan pågår i delar av företagets nätverk. Om företaget till exempel har en hybridimplementering, som en hybrid-SharePoint-sökning som kan köra frågor i sökindex i både SharePoint Online och en lokal SharePoint Server 2013-instans, kan uppdateringar redan vara på gång i den lokala servergruppen. Om hela företaget finns i molnet kan systemunderhåll innebära att nätverksmaskinvara läggs till eller tas bort, att uppdateringar distribueras till hela företaget eller att ändringar av DNS eller annan kärninfrastruktur ändras.
  
När du felsöker ett prestandaproblem är det lite som en brottsplats – du måste vara exakt och observant för att kunna dra slutsatser utifrån bevisen. För att kunna göra det måste du skapa en bra problemräkning genom att samla in bevis. Problemet bör innefatta dator, användarens kontext, när problemet uppstod och de exakta steg som exponerade prestandaproblemet. Den här problemsatsen ska vara och förbli den översta sidan i dina anteckningar. När du går igenom problemutdraget igen efter att du har arbetat med lösningen gör du ett test och bevisar om de åtgärder du vidtar har löst problemet. Det är viktigt att veta när ditt arbete är klart.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Vet du hur prestandan såg ut när den var bra?

Om du har tur finns det ingen som vet det. Ingen har några siffror. Det innebär att ingen kan besvara den enkla frågan "Hur många sekunder tog det att öppna Inkorgen i Office 365?" eller "Hur lång tid tog det när ledningen hade ett Lync Online-möte?", vilket är ett vanligt scenario på många företag.
  
Det som saknas här är en baslinje för prestanda.
  
Baslinjer ger dig ett sammanhang för prestandan. Du bör då och då göra en baslinje ofta, beroende på företagets behov. Om ni är ett större företag kanske operationsteamet redan har gjort baslinjer för den lokala miljön. Om du till exempel korrigerar alla Exchange-servrar den första måndagen i månaden, och alla SharePoint-servrar på den tredje måndagen, har operationsteamet förmodligen en lista med aktiviteter och scenarier som körs efter korrigering för att bevisa att kritiska funktioner fungerar. Du kan till exempel öppna Inkorgen, klicka på Skicka/ta emot och kontrollera att mapparna uppdateras eller, i SharePoint, bläddra på webbplatsens huvudsida, gå till företagssökningssidan och göra en sökning som returnerar resultaten.
  
Om programmen finns i Office 365 kan du göra några grundläggande baslinjer för den tid (i millisekunder) som det tar från en klientdator i nätverket till en utgående punkt, eller till den punkt där du lämnar nätverket och går ut till Office 365. Här är några användbara baslinjer som du kan undersöka och registrera:
  
- Identifiera enheterna mellan klientdatorn och din utgående punkt, till exempel din proxyserver.
    
  - Du måste känna till enheterna så att du har kontexten (IP-adresser, enhetstyper osv.) för eventuella prestandaproblem som kan uppstå.
    
  - Proxyservrar är vanliga utgående punkter, så att du kan titta i webbläsaren och se vilken proxyserver den är inställd att använda, om det finns några.
    
  - Det finns verktyg från tredje part som kan identifiera och mappa nätverket, men det säkraste sättet att känna till dina enheter är att fråga en medlem i nätverksgruppen.
    
- Identifiera din Internetleverantör (ISP), skriv ned deras kontaktinformation och fråga hur många kretsar det finns för bandbredd.
    
- Inom företaget identifierar du resurser för enheterna mellan klienten och den utgående punkten eller identifierar en nödkontakt att prata med om nätverksproblem.
    
Här är några baslinjer som kan beräknas med enkla tester med verktyg:
  
- Tid från klientdatorn till den utgående punkten i millisekunder
    
- Tid från den utgående punkten till Office 365 i millisekunder
    
- Plats i världen för den server som löser URL:erna för Office 365 när du bläddrar
    
- Hastigheten på Internetleverantörens DNS-upplösning i millisekunder, inkonsekvenser i paket ankomst (nätverksjitter), tider för uppladdning och nedladdning i millisekunder
    
Om du inte vet hur du utför de här stegen hittar du mer information i den här artikeln. 
  
## <a name="what-is-a-baseline"></a>Vad är en baslinje?

Du kommer att se effekterna när det går dåligt, men om du inte känner till dina historiska prestandadata går det inte att ha ett sammanhang för hur dåligt det kan ha blivit och när. Utan en baslinje går du alltså miste om den viktigaste ledtråden till problemet: bilden på kartongen. När du felsöker prestandan behöver du en *jämförelsepunkt.* Enkla prestandabaslinjer är inte svåra att göra. Ditt team kan få i uppdrag att genomföra dem enligt ett schema. Anta till exempel att din anslutning ser ut så här: 
  
![En grundläggande nätverksbild som visar klienten, proxy och Office 365-molnet.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Det innebär att du har kollat med nätverksgruppen och fått reda på att du lämnar företaget för Internet via en proxyserver som hanterar alla förfrågningar som klientdatorn skickar till molnet. I det här fallet bör du rita en förenklad version av anslutningen som innehåller alla mellanliggande enheter. Nu kan du infoga verktyg som du kan använda för att testa prestanda mellan klienten, den utgående punkten (där du lämnar ditt nätverk för Internet) och Office 365-molnet.
  
![Grundläggande nätverk med klient, proxy och moln samt verktygsförslag, PSPing, TraceTCP och nätverksspårningar.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Alternativen är Enkla och **Avancerade eftersom** **det** finns så mycket expertkunskaper du behöver för att hitta prestandadata. Nätverksspårning tar lång tid jämfört med att köra kommandoradsverktyg som PsPing och TraceTCP. Dessa två kommandoradsverktyg väljs eftersom de inte använder ICMP-paket, som kommer att blockeras av Office 365, och eftersom de visar den tid i millisekunder som det tar att lämna klientdatorn eller proxyservern (om du har åtkomst) och nå Office 365. Varje enskilt hopp från en dator till en annan har ett tidsvärde, vilket är perfekt för baslinjer! Dessa kommandoradsverktyg låter dig även lägga till ett portnummer i kommandot, vilket är användbart eftersom Office 365 kommunicerar via port 443, som är den port som används av SSL (Secure Sockets Layer) och TLS (Transport Layer Security). Men andra verktyg från tredje part kan vara bättre lösningar för din situation. Microsoft stöder inte alla dessa verktyg, så om du av någon anledning inte kan få PsPing och TraceTCP att fungera kan du gå vidare till en nätverksspårning med ett verktyg som Netmon. 
  
Du kan göra en baslinje före arbetstid, en gång till under kraftig användning och sedan igen efter arbetstid. Det innebär att du kan ha en mappstruktur som till slut ser ut lite så här:
  
![Grafiken föreslår ett sätt att organisera prestandadata i mappar.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Du bör också ha ett sätt att benämna dina filer. Här är några exempel:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Det finns många olika sätt att göra detta, men formatet är **\<dateTime\>\<what's happening in the test\>** en bra början. Om du använder det här noga kommer det att underlätta mycket när du ska felsöka problem senare. Du kommer senare att kunna säga "Jag gjorde två spårningar den 8 februari, en visade bra prestanda och en visade dålig, så vi kan jämföra dem". Det här är mycket användbart för felsökning. 
  
Det är viktigt att ordna alla baslinjer på ett organiserat sätt. I det här exemplet tog den enkla metoden fram tre utdata från kommandoraden och resultatet samlades in som skärmbilder, men om du vill kan du välja att spara filer i nätverket i stället. Använd den metod som passar dig bäst. Lagra dina historiska baslinjer och ha dem som referens när du märker ändringar i online-tjänstens beteende. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Varför samla in prestandadata under ett pilottest?

Det är bäst att börja skapa baslinjer redan i pilotversion av Office 365-tjänsten. Office kan ha tusentals användare, hundratusentals, eller bara fem, men även med ett litet antal användare kan du utföra tester för att mäta svängningar i prestanda. För stora företag kan ett representativt urval av flera hundra användare av pilottestningen av Office 365 projiceras utåt på flera tusentals så att du vet var problem kan uppstå innan de uppstår.
  
För små företag där alla användare går till tjänsten samtidigt och det inte finns någon pilottestning kan du behålla prestandaåtgärder så att du har data att visa för de som ska felsöka problem. Om du till exempel helt plötsligt märker att du kan gå en sväng runt byggnaden under den tid det tar att ladda upp en medelstor bild där det brukade ske mycket snabbt.
  
## <a name="how-to-collect-baselines"></a>Hur du samlar in baslinjer

För alla felsökningsplaner behöver du som minst identifiera följande saker:
  
- Klientdatorn du använder (typ av dator eller enhet, IP-adress och de åtgärder som orsakade problemet)
    
- Klientdatorns plats i världen (till exempel om den här användaren har en VPN-anslutning till nätverket, arbetar på distans eller i företagets intranät)
    
- Den utgående punkt som klientdatorn använder från nätverket (den punkt där trafiken lämnar företaget och går till en Internetleverantör eller Internet)
    
 Du kan få nätverkslayouten från nätverksadministratören. Om du har ett litet nätverk kan du titta på enheterna som ansluter dig till Internet och ringa Internet-leverantören om du har frågor om layouten. Skapa en bild av den färdiga layouten som referens. 
  
Det här avsnittet är uppdelat i enkla kommandoradsbaserade verktyg och metoder, och mer avancerade verktyg. Först går vi in på enkla metoder. Men om du har prestandaproblem just nu bör du gå till avancerade metoder och prova åtgärdsplanen för prestandafelsökning.
  
### <a name="simple-methods"></a>Enkla metoder

Syftet med de enkla metoderna är att lära dig att göra, förstå och korrekt lagra enkla prestandabaslinjer så att du får information om Office 365-prestanda. Här är ett mycket enkelt diagram som du har sett förut:
  
![Grundläggande nätverk med klient, proxy och moln samt verktygsförslag, PSPing, TraceTCP och nätverksspårningar.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> I den här skärmbilden syns TraceTCP, som är ett användbart verktyg för att visa (i millisekunder) hur lång tid en begäran tar att behandla, och hur många nätverkshopp eller anslutningar från en dator till nästa som det tar för en begäran att nå ett mål. TraceTCP kan också ge namnen på servrar som används under hopp, vilket kan vara användbart för felsökare i Microsoft Office 365-supporten. > TraceTCP-kommandon kan vara mycket enkla, till exempel: >> Kom ihåg att inkludera  `tracetcp.exe outlook.office365.com:443` portnumret i kommandot! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) är en kostnadsfri nedladdning, men använder Wincap. Wincap är ett verktyg som även används och installeras av Netmon. Vi använder även Netmon i avsnittet om avancerade metoder. 
  
 Om du har flera kontor måste du även ha en uppsättning data från en klient på var och en av de platserna. Det här testet mäter svarstiden, vilket i det här fallet är ett talvärde som beskriver tiden det tar mellan det att en klient skickar en begäran till Office 365 och office 365 som svarar på begäran. Testet utgår från din domän på en klientdator och mäter en resa från ditt nätverk, ut genom en utgående punkt, över Internet till Office 365 och tillbaka. 
  
Det finns några olika sätt att hantera den utgående punkten, i det här fallet proxyservern. Du kan spåra från 1 till 2 och sedan 2 till 3 och sedan addera talen i millisekunder för att få en totalsumma vid kanten av nätverket. Eller så kan du konfigurera anslutningen för att kringgå proxyn för Office 365-adresser. I ett större nätverk med en brandvägg, omvänd proxyserver eller en kombination av dessa kan du behöva göra undantag för proxyservern som gör att trafik kan passera för många URL:er. Listan över slutpunkter som används av Office 365 finns i [Office 365 URL:er och IP-adressintervall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Om du har en autentiserande proxy kan du börja med att testa undantag för följande:
  
- Portarna 80 och 443
    
- TCP och IP:er
    
- Anslutningar som är utgående till någon av dessa URL:er:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
Alla användare måste kunna komma åt de här adresserna utan någon inblandning från proxy eller autentisering. I ett mindre nätverk bör du lägga till dessa i förbikopplingslistan för proxyadresser i webbläsaren. 
  
Om du vill lägga till dessa i förbikopplingslistan för proxyadresser i Internet Explorer går du till **Verktyg** \> **LAN-inställningar** \>  \> **för Internetalternativanslutningar** \> **Avancerat.** På fliken Avancerat hittar du även din proxyserver och proxyserverport. Du kan behöva klicka i kryssrutan Använd en **proxyserver** för nätverket för att komma åt **knappen** Avancerat. Se till att Förbikoppla **proxyserver för lokala adresser** är markerat. När du klickar **på** Avancerat visas en textruta där du kan ange undantag. Avgränsa URL:erna med jokertecken ovan med semikolon, till exempel:
  
\*.microsoftonline.com; \*.sharepoint.com
  
När du kringgår din proxy bör du kunna använda ping eller PsPing direkt på en Office 365-URL. Nästa steg är att testa **ping** outlook.office365.com . Om du använder PsPing eller ett annat verktyg där du kan ange ett portnummer i kommandot kan du göra en PsPing på **portal.microsoftonline.com:443** för att se den genomsnittliga tiden dit och tillbaka i millisekunder. 
  
Tids för svar, eller RTT (Round-trip time, eller RTT, är ett värde som innebär den tid det tar att skicka en HTTP-begäran till en server som outlook.office365.com och få ett svar som bekräftar att servern vet att du gjorde det. Ibland används förkortningen RTT. Det bör vara en relativt kort tid.
  
Du måste använda [PSPing](/sysinternals/downloads/psping) eller ett annat verktyg som inte använder ICMP-paket som blockeras av Office 365 för att kunna göra det här testet. 
  
 **Så här använder du PsPing för att få en tidsresa i millisekunder direkt från en Office 365-URL**
  
1. Kör en upphöjd kommandotolk genom att utföra följande steg:
    
1. Klicka på **Start**.
    
2. Skriv **cmd i** rutan Starta sökning och tryck sedan på CTRL+SKIFT+RETUR.
    
3. Om dialogrutan **User Account Control** visas bekräftar du att den visar det du vill och klickar sedan på **Fortsätt.**
    
2. Gå till den mapp där verktyget (i det här fallet PsPing) är installerat och testa följande Office 365-URL:er:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![PSPing-kommandot till microsoft-my.sharepoint.com port 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Se till att inkludera portnumret 443. Kom ihåg att Office 365 fungerar på en krypterad kanal. Om du gör en PsPing utan portnummer kommer din begäran att misslyckas. När du har pingat den korta listan letar du efter den genomsnittliga tiden i millisekunder (ms). Det är den du vill spela in!
  
![Bild som visar en bild av klienten för proxy-PSPing med en tidsfördrundning på 2,8 millisekunder.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Om du inte är bekant med att kringgå proxy och föredrar att ta ett steg i steget måste du först ta reda på namnet på din proxyserver. I Internet Explorer går du till **Verktyg** \> **Internetalternativ** \> **Anslutningar** \> **LAN-inställningar** \> **Avancerat.** På **fliken** Avancerat visas din proxyserver. Pinga proxyservern i en kommandotolk genom att utföra den här uppgiften: 
  
 **Pinga proxyservern och få tidsfördrundning i millisekunder för steg 1 till 2**
  
1. Kör en upphöjd kommandotolk genom att utföra följande steg:
    
1. Klicka på **Start**.
    
2. Skriv **cmd i** rutan Starta sökning och tryck sedan på CTRL+SKIFT+RETUR.
    
3. Om dialogrutan **User Account Control** visas bekräftar du att den visar det du vill och klickar sedan på **Fortsätt.**
    
2. Skriv ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> och tryck sedan på RETUR. Om du har PsPing eller något annat verktyg installerat kan du välja att använda det verktyget i stället. 
    
    Ditt kommando kan se ut som något av följande exempel: 
    
  - pinga ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. När spårningen slutar att skicka testpaket kommer du att få en liten sammanfattning som visar ett medelvärde, i millisekunder, och det är värdet som du är ute efter. Ta en skärmbild av uppmaningen och spara den enligt dina namngivningskonventioner. Vid det här läget kan det även vara bra att fylla i värdet i diagrammet.
    
Du kanske har gjort en spårning tidigt på morgonen och din klient kan komma till proxyn (eller den utgående servern till Internet) snabbt. I det här fallet kan talen se ut så här:
  
![Bild som visar tidsfördrundning för tidsfördrundning från en klient till en proxy på 2,8 millisekunder.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Om klientdatorn är en av få med åtkomst till proxyservern (eller den utgående servern) kan du köra nästa del av testet genom att fjärransluta till den datorn och köra kommandotolken för att göra en PsPing på en Office 365-URL därifrån. Om du inte har tillgång till den datorn kan du kontakta nätverksresurserna för att få hjälp med nästa del och få exakta siffror på så sätt. Om det inte är möjligt kan du göra en PsPing för den i fråga fråga Office 365-URL:en och jämföra den med PsPing- eller Ping-tiden med din proxyserver. 
  
Om det till exempel tar 51,84 millisekunder från klienten till Office 365-URL:en och det tar 2,8 millisekunder från klienten till proxyn (eller den utgående punkten) tar det 49,04 millisekunder från den utgående punkten till Office 365. På samma sätt, om PsPing tar 12,25 millisekunder från klienten till proxy mitt på dagen och 62,01 millisekunder från klienten till Office 365 URL är det genomsnittliga värdet för proxys utgående adress till Office 365 URL 49,76 millisekunder.
  
![Ytterligare bild som visar ping i millisekunder från klient till proxy bredvid klienten till Office 365, så att värdena kan subtraheras.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Vad gäller felsökning kan det hända att du hittar något intressant bara genom att hålla kvar dessa baslinjer. Om du till exempel normalt har cirka 40 till 59 millisekunder svarstid från proxyn eller den utgående punkten till Office 365-URL: en och har en klient för proxy eller utgående punktfördröjning på ca 3 till 7 millisekunder (beroende på mängden nätverkstrafik du ser under den tiden på dagen) kommer du helt säkert att känna till något problematiskt om dina tre senaste klienter för proxy eller utgående baslinjer visar en svarstid på 45 millisekunder.
  
### <a name="advanced-methods"></a>Avancerade metoder

Om du verkligen vill veta vad som händer med dina Internet-förfrågningar till Office 365 måste du bekanta dig med nätverksspårningar. Det spelar ingen roll vilka verktyg du föredrar för dessa spårningar, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, Developer Dashboard-verktyget eller något annat, så länge verktyget kan samla in och filtrera nätverkstrafik. Du kommer att se i det här avsnittet att det är bra att köra fler än ett av dessa verktyg för att få en mer fullständig bild av problemet. När du testar fungerar några av dessa verktyg själva som proxy. Bland de verktyg som används i den tillhörande artikeln Prestandafelsökningsplan för [Office 365](performance-troubleshooting-plan.md)finns [Netmon 3.4,](https://www.microsoft.com/download/details.aspx?id=4865) [HTTPWatch](https://www.httpwatch.com/download/)eller [WireShark.](https://www.wireshark.org/)
  
Att skapa en prestandabaslinje är den enkla delen av den här metoden och många av stegen är desamma som när du felsöker ett prestandaproblem. De mer avancerade metoderna för att skapa baslinjer för prestanda kräver att du gör och lagrar nätverksspårningar. I de flesta av exemplen i den här artikeln används SharePoint Online, men du bör ta fram en lista med vanliga åtgärder med alla Office 365-tjänster som du prenumererar på för att testa och spela in. Här är ett exempel på en baslinje:
  
- Baslinjelista för SPO - ** Steg 1: ** Besök startsidan för SPO-webbplatsen och gör en nätverksspårning. Spara spårningen. 
    
- Baslinjelista för SPO - **Steg 2:** Sök efter en term (till exempel ditt företags namn) via Enterprise Search och gör en nätverksspårning. Spara spårningen. 
    
- Baslinjelista för SPO - **Steg 3: Ladda** upp en stor fil till ett SharePoint Online-dokumentbibliotek och gör en nätverksspårning. Spara spårningen. 
    
- Baslinjelista för SPO - **Steg 4:** Besök startsidan för OneDrive-webbplatsen och gör en nätverksspårning. Spara spårningen. 
    
Den här listan bör innehålla de viktigaste vanliga åtgärder som användare kan vidta mot SharePoint Online. Observera att det sista steget, att spåra att gå till OneDrive för företag, bygger upp en jämförelse mellan laddning av SharePoint Onlines startsida (som ofta anpassas för företag) och OneDrive för företag startsida, som sällan anpassas. Det här är ett väldigt grundläggande test när det gäller en SharePoint Online-webbplats som laddar in långsamt. Du kan bygga in ett register över den här skillnaden i din testning.
  
Om du befinner dig mitt i ett prestandaproblem blir många av stegen desamma som när du gör en baslinje. Nätverksspårningar blir viktiga, så vi ska behandla  *härnäst*  hur de viktiga spårningarna ska ske. 
  
För att ta itu med  *ett prestandaproblem*  just nu måste du göra en spårning när du upplever prestandaproblemet. Du måste ha tillgång till rätt verktyg för att samla in loggar och du behöver en handlingsplan, det vill säga en lista över felsökningsåtgärder för att samla in den bästa information som du kan. Det första du behöver göra är att registrera datum och tid för testet så att filerna kan sparas i en mapp som speglar tidsinställningen. Därefter går du vidare till själva problemstegen. Det här är de exakta steg du kommer att använda för att testa. Kom ihåg grunderna: om problemet endast är med Outlook ska du se till att problemet beteendet bara sker i en Office 365-tjänst. Genom att begränsa problemets omfattning kan du fokusera på något du kan lösa. 
  
## <a name="see-also"></a>Se även

[Hantera Office 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)