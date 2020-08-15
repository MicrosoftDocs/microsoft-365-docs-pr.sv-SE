---
title: Prestanda justering för Office 365 med bas linjer och prestanda historik
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
description: Lär dig hur du kontrollerar historiken för dina klient dator anslutningar för att hjälpa dig att upptäcka kommande problem tidigt.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694584"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Prestanda justering för Office 365 med bas linjer och prestanda historik

Det finns några enkla sätt att kontrol lera anslutnings prestandan mellan Office 365 och ditt företag som låter dig skapa en grov bas linje för din anslutning. Att känna till prestanda historiken för dina klient dator anslutningar kan hjälpa dig att upptäcka kommande problem tidigt, identifiera och förutse problem.
  
Om du inte har använt för att arbeta med prestanda problem är den här artikeln utformad för att hjälpa dig att överväga några vanliga frågor, till exempel hur vet du att det problem du ser är ett prestanda problem och inte ett fel i Office 365-tjänsten? Hur kan jag planera för bra prestanda på lång sikt? Hur kan du hålla ett öga på prestandan? Om din grupp eller dina klienter upplever låg prestanda i Office 365 och du undrar över några av de här frågorna läser du på.
  
> [!IMPORTANT]
> **Har du ett prestanda problem mellan klienten och Office 365 just nu?** Följ stegen som beskrivs i [planen för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Något du bör veta om prestanda i Office 365

Office 365 bor i ett högpresterande, dedicerat Microsoft-nätverk som är stadigt övervakat, utan till riktiga människor. En del av syftet med att underhålla Office 365-molnet är att justera prestanda och effektivisera det. Eftersom klienter som använder Office 365-molnet måste ansluta via Internet är det en bra ansträngning att finjustera prestandan för Office 365-tjänsterna också. Prestanda förbättringar kommer aldrig att stanna i molnet, och det finns massor av problem med att hålla molnet smidigt och snabbt. Om du upplever ett prestanda problem med att ansluta från din plats till Office 365 är det bäst att inte börja med och vänta på ett support ärende. Istället bör du börja undersöka problemet med "Inside Out". Det innebär att du börjar i ditt nätverk och fungerar på ett annat sätt än Office 365. Innan du öppnar ett ärende med Office 365-support kan du samla in data och vidta åtgärder som kan analyseras och kanske lösa problemet.
  
> [!IMPORTANT]
> Var uppmärksam på kapacitets planering och begränsningar i Office 365. Den informationen placerar dig före kurvan när du försöker lösa ett problem med prestanda. Här är en länk till [tjänst beskrivningarna Microsoft 365 och Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Det här är ett centralt nav och alla tjänster som erbjuds av Office 365 har en länk till deras egna tjänst beskrivningar härifrån. Det innebär att om du vill se standard gränserna för SharePoint Online, till exempel klickar du på [SharePoint Online Service Description](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) och letar reda på [SharePoint Online-området för gränser](https://go.microsoft.com/fwlink/p/?LinkID=856113). 
  
Se till att du går in i din fel sökning med att det är en rörlig skala, det är inte att uppnå ett idealiskt värde och bibehålla det permanent (om du tror att det här är så kan du vara mycket stressade med stora mängder data), vilket gör abonnemanget för prestanda påverkan. Du kan, och om du vill, få en grov uppfattning om dina prestanda mål, men många av de olika variablerna spelar till prestanda, och därför varierar prestanda. Det är samma slag av prestanda. 
  
Prestanda fel sökningen handlar inte om att uppfylla vissa mål och att du behåller dessa nummer obegränsat, det handlar om att förbättra befintliga aktiviteter, med alla variabler. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Vad innebär det att prestanda problem ser ut?

För det första måste du se till att det du upplever är ett prestanda problem och inte en tjänst. Ett problem med prestanda skiljer sig från en tjänst händelse i Office 365. Så här kan du berätta för dem.
  
Om Office 365-tjänsten har problem kan det vara en tjänst olycka. Du kommer att se röda eller gula ikoner under **aktuell hälsa** i Microsoft 365 Admin Center, men du kan även få låga prestanda på klient datorer som ansluter till Office 365. Om den aktuella hälso rapporten till exempel visar en röd ikon och du **ser det** bredvid Exchange kan du också få ett par samtal från personer i organisationen som klagat på att klient post lådorna som använder Exchange Online fungerar dåligt. I så fall är det rimligt att anta att din Exchange Online-prestanda blev en skadelidande för problem inom tjänsten. 
  
![Instrument panelen för Office 365 med alla arbets belastningar som är gröna, förutom Exchange, som visar att tjänsten har återställts.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
I det här läget ska Office 365-administratören kontrol lera **aktuell hälsa** och sedan **Visa information och historik**ofta för att hålla dig uppdaterad om underhåll som utförs på systemet. Den **aktuella hälso** instrument panelen har gjorts för att uppdatera dig om ändringar och problem i tjänsten. Anteckningarna och förklaringarna som är skrivna för hälso historiken, administratören till admin, finns där för att hjälpa dig att mäta din påverkan och för att hålla dig Inlagd i arbetet. 
  
![En bild av hälso instrument panelen för Office 365 som förklarar att Exchange Online-tjänsten har återställts och varför.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Prestanda problem är inte ett tjänst problem, trots att olyckor kan orsaka långsam prestanda. Prestanda problem ser ut så här:
  
- Ett prestanda problem beror på vad administrations centret för **aktuell hälsa** rapporterar för tjänsten. 
    
-  Det tar lång tid att slutföra eller aldrig slutföra en funktion som är relativt sömlös. 
    
- Du kan även replikera problemet, eller, minst, du vet att det kommer att inträffa om du använder rätt steg.
    
-  Om problemet är oregelbundet är det fortfarande ett mönster, till exempel 10:00 att du vet att du har ett samtal från användare som inte kan använda Office 365 på ett tillförlitligt sätt och att samtalen uppträder dygnet runt. 
    
Det låter bekant; kanske är du för van. När du vet att det är ett prestanda problem blir frågan "Hur gör du det". Resten av den här artikeln hjälper dig att avgöra exakt det.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Definiera och testa prestanda problem

Prestanda problem uppstår ofta över tiden, så det kan vara svårt att definiera det faktiska problemet. Du måste skapa en bra problem-instruktion och en bra idé om ärende kontexten, och sedan måste du upprepa test stegen för att vinna dagen. Om du inte har något eget problem kan du gå förlorade. Varför? Här är några exempel på problem meddelanden som inte ger tillräckligt med information:
  
- Om du växlar från min inkorg till kalendern använde jag inte något meddelande och nu är det en kaffe paus. Kan du göra så att den fungerar som den ska?
    
- Uppladdning av mina filer till SharePoint Online tar för alltid. Varför är det långsamt i eftermiddag, men den andra gången är det snabbt? Går det inte bara att vara snabbt?
    
Det finns flera problem som beror på problemet ovan. Det finns många tvetydigheter att hantera. till exempel:
  
- Det är oklart hur byte mellan inkorg och kalender används för den bärbara datorn.
    
- Vad innebär det att "det är" snabbt "?
    
- Hur länge är "för alltid"? Är det några sekunder, eller hur många minuter, eller skulle kunna gå till lunch och det skulle sluta tio minuter efter att användaren har varit tillbaka?
    
Allt det här är utan att administratören och fel sökaren inte kan känna till många detaljer från problem satserna som dessa. Till exempel när problemet påbörjas; Att användaren kan arbeta hemifrån och bara se långsam byte i hem nätverk. Att användaren måste köra flera andra RAM intensiva program på den lokala klienten, eller att användaren kör ett äldre operativ system eller inte har kört de senaste uppdateringarna.
  
När användare rapporterar ett prestanda problem finns det mycket information att samla in. Insamling av denna information är en del av en process som kallas problemet eller som undersöker den. Här följer en grundläggande omfattnings lista som du kan använda för att samla in information om prestanda problem. Den här listan är inte fullständig, men det är bara ett ställe att starta en egen: 
  
- På vilket datum problemet inträffar och med vilken tid på dygnet?
    
- Vilken typ av klient dator använde du och hur ansluter den till företags nätverket (VPN, tråd bunden, trådlös kommunikation)?
    
- Arbetade du på kontoret?
    
- Har du prövat samma åtgärder på en annan dator och samma sak?
    
- Följ de steg som ger dig problem så att du kan skriva de åtgärder du tar ner.
    
- Hur långsamt i sekunder eller minuter är prestanda?
    
- Var i världen bor du?
    
Vissa av dessa frågor är mer uppenbara än andra. De flesta är att förstå en fel sökare behöver de exakta stegen för att återskapa problemet. Efter alla, hur kan du spela in vad som är fel och hur kan du testa om problemet är åtgärdat? Mindre uppenbart är saker som "vilket datum och vilken tid hade du för problem?", och var i världen finns du? ", information som kan användas för att hitta. Det kan betyda att underhåll pågår redan på delar av företagets nätverk, beroende på när användaren fungerade. Om ditt företag till exempel har en hybrid implementation, som en hybrid SharePoint-sökning, som kan söka i Sök index i både SharePoint Online och en lokal SharePoint Server 2013-instans, kan uppdateringar aktive ras i den lokala server gruppen. Om ditt företag är i molnet kan system underhåll läggas till för att lägga till eller ta bort nätverks maskin vara, installera uppdateringar som är företagsomfattande eller göra ändringar i DNS eller annan huvud infrastruktur.
  
När du felsöker ett problem med prestanda är det lite som en brottslighet, men du måste vara exakt och iaktta eventuella slut satser. För att göra detta måste du få en god problem policy genom att samla in bevis. Den bör innehålla datorns kontext, användarens kontext, när problemet påbörjas och de exakta stegen som visar prestanda problem. Den här problem rapporteringen bör vara den översta sidan i dina anteckningar. Genom att gå igenom problem instruktionen igen efter att du har utfört den måste du testa och bevisa om de åtgärder du vidtar har löst problemet. Det är viktigt att veta när ditt arbete är klart.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Vet du hur prestandan ser ut när den var bra?

Om du är Unlucky känner ingen. Ingen hade nummer. Det betyder att ingen kan svara på den enkla frågan om hur många sekunder det hade tagit för att få upp en inkorg i Office 365? ", eller" hur lång tid använde den när chefer hade ett Lync Online-onlinemöte? ", vilket är ett vanligt scenario för många företag.
  
Det här är en bas linje för prestanda.
  
Med original planer får du en kontext för din prestanda. Du bör ta en original plan ibland oftare, beroende på företagets behov. Om du är ett större företag kan din åtgärds grupp ta original planerna för din lokala miljö. Om du till exempel korrigerar alla Exchange-servrar under den första måndagen i månaden, och alla dina SharePoint-servrar på tredje måndagen, har din åtgärds grupp antagligen en lista med uppgifter och scenarier som den utför efter uppdatering för att bevisa att viktiga funktioner fungerar. Om du till exempel öppnar Inkorgen, klickar på Skicka/ta emot och kontrollerar att mapparna uppdateras, eller i SharePoint, bläddrar du till sidan för företags sökning och gör en sökning som returnerar resultat.
  
Om dina program finns i Office 365 kan du använda några av de grundläggande original planerna för att mäta tiden (i millisekunder) från en klient dator i nätverket, till en utgångs punkt, eller den plats där du lämnar nätverket och kan gå ut till Office 365. Här är några användbara original planer som du kan undersöka och spela in:
  
- Identifiera enheterna mellan klient datorn och utgångs punkten, till exempel proxyservern.
    
  - Du måste känna till enheterna så att du har kontext (IP-adresser, typ av enhet, et osv) för prestanda problem som uppstår.
    
  - Proxyservrar är vanliga avgångs punkter, så du kan kontrol lera vilken proxyserver den är inställd på, i webbläsaren.
    
  - Det finns verktyg från tredje part som kan upptäcka och mappa nätverket, men det säkraste sättet att veta att dina enheter är att be en medlem i din nätverks grupp.
    
- Identifiera din Internet leverantör (ISP), skriv ner deras kontakt information och fråga hur många kretsar hur mycket bandbredd du har.
    
- I ditt företag kan du identifiera resurser för enheterna mellan klienten och slut punkten, eller identifiera en nöd situation för att prata med eventuella nätverks problem.
    
Här är några bas linjer som gör det enkelt att testa med verktyg:
  
- Tid från klient datorn till utgångs punkten i millisekunder
    
- Tid från ditt utgångs läge till Office 365 i millisekunder
    
- Plats i världen för servern som matchar URL-adresserna för Office 365 när du bläddrar
    
- Hastigheten hos Internet leverantörens DNS-matchning i millisekunder, inkonsekvenser för paketets ankomst (nätverks Darr), uppladdning och nedladdnings tid i millisekunder
    
Om du inte vet hur du ska utföra de här stegen går vi till mer information i den här artikeln. 
  
## <a name="what-is-a-baseline"></a>Vad är en bas linje?

Du vet hur det påverkar effekten när det blir dåligt, men om du inte känner till historiken över dina prestanda data är det omöjligt att ha en kontext för hur dåligt den kan ha blivit och när. Om du inte har någon original plan saknar du viktig ledtråd för att lösa pusslet: bilden i rutan pussel. Vid prestanda fel sökning behöver du en  *jämförelse*  punkt. Enkla prestanda bas linjer är inte svårt att ta sig. Din åtgärds grupp kan utföras enligt ett schema. Låt oss säga att anslutningen ser ut så här: 
  
![En grundläggande nätverks bild med molnet klient, proxy och Office-365.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Det innebär att du har kontrollerat nätverks teamet och fått reda på att du lämnar företaget till Internet via en proxyserver och att proxyservern hanterar alla begär Anden som klient datorn skickar till molnet. I det här fallet bör du rita en förenklad version av anslutningen som visar alla mellanliggande enheter. Infoga nu verktyg som du kan använda för att testa prestandan mellan klienten, utgångs punkten (där du lämnar nätverket för Internet) och Office 365-molnet.
  
![Grundläggande nätverk med klient, proxy och moln samt verktyg förslag PSPing, TraceTCP och nätverks spårning.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Alternativen visas som **enkla** och **avancerade** på grund av den mängd expertis du behöver för att hitta prestanda data. En nätverks spårning tar mycket tid jämfört med kommando rads verktyg som PsPing och TraceTCP. De här två kommando rads verktygen valdes eftersom de inte använder ICMP-paket som blockeras av Office 365 och att de ger tid i millisekunder som det tar att lämna klient datorn eller proxyservern (om du har åtkomst) och komma till Office 365. Varje enskilt hopp från en dator till en annan slutar med ett tids värde och det är perfekt för bas linjer! Med dessa kommando rads verktyg kan du till och med lägga till ett port nummer i kommandot, det är användbart eftersom Office 365 kommunicerar via port 443, som är den port som används för SSL och TLS-säkerhet (Secure Sockets Layer). Men andra verktyg från tredje part kan vara bättre. Microsoft stöder inte alla de här verktygen, så om du av någon anledning inte kan få PsPing och TraceTCP att fungera kan du gå vidare till en nätverks spårning med ett verktyg som Netmon. 
  
Du kan ta en original plan före kontors tid, igen under stor användning och sedan återigen efter timmar. Det innebär att du kanske har en mappstruktur som ser ut ungefär så här i slutet:
  
![Grafik föreslår ett sätt att ordna dina prestanda data i mappar.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Du bör också välja en namngivnings konvention för dina filer. Här är några exempel:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Det finns massor av olika sätt att göra det, men det **\<dateTime\>\<what's happening in the test\>** är en bra plats att börja använda det. Det är bara att få en hel del när du försöker Felsöka problem senare. Senare kan du säga "Jag tog två spårningar den 8 februari, en visade bra prestanda och ett visades dåligt, så vi kan jämföra dem". Det här är mycket bra för fel sökning. 
  
Du måste ha ett organiserat sätt för att behålla dina historiska original planer. I det här exemplet gav de enkla metoderna tre kommando rads resultat och resultaten samlades in som skärm dum par, men du kan ha nätverks dum par i stället. Använd den metod som passar dig bäst. Lagra dina historiska original planer och hänvisa till dem vid punkter där du märker ändringar i beteendet hos online tjänster. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Varför samla in prestanda data under en pilot?

Det finns ingen bättre tid att börja skapa original planer än under en pilot för Office 365-tjänsten. Ditt Office kan innehålla tusen användare, hundratals tusen eller det kan ha fem, men även med ett fåtal användare kan du utföra tester för att mäta variationer i prestanda. I ett stort företag kan ett representativt urval av flera hundra användare som piloterar Office 365 projiceras utåt till flera tusen så att du vet var det kan uppstå problem.
  
Om det rör sig om ett litet företag, där det finns en person som deltar i tjänsten samtidigt och det inte finns någon pilot, kan du behålla prestanda mått så att du har data att visa för alla som kan behöva Felsöka en åtgärd som inte fungerar som vanligt. Om du till exempel märker att det är en plötslig som du kan göra för att det ska gå att överföra en medels Tor bild när den används väldigt snabbt.
  
## <a name="how-to-collect-baselines"></a>Så här samlar du in original planer

För alla fel söknings planer måste du identifiera dessa saker på ett minimum:
  
- Den klient dator du använder (typen av dator eller enhet, en IP-adress och de åtgärder som orsakade problemet)
    
- Där klient datorn är placerad i världen (till exempel om den här användaren har en VPN-anslutning till nätverket, en fjärran sluten eller i företagets intranät)
    
- Utgångs punkten som klient datorn använder från nätverket (den punkt där trafiken lämnar företaget till en Internet leverantör eller Internet)
    
 Du kan ta reda på nätverkets layout från nätverks administratören. Om du använder ett litet nätverk kan du ta en titt på de enheter som ansluter dig till Internet och ringa din Internet leverantör om du har frågor om layouten. Skapa en bild av den slutgiltiga layouten för din referens. 
  
Det här avsnittet är uppdelat i enkla kommando rads verktyg och-metoder och mer avancerade verktygs alternativ. Vi kommer att få enkla metoder först. Men om du har ett prestanda problem nu kan du gå till avancerade metoder och testa åtgärds planen för fel sökning av prestanda.
  
### <a name="simple-methods"></a>Enkla metoder

Syftet med dessa enkla metoder är att lära sig att ta, förstå och korrekt Spara grundläggande original Plans bas linjer över tiden så att du får information om Office 365-prestanda. Här är det väldigt enkla diagrammet som du ser innan:
  
![Grundläggande nätverk med klient, proxy och moln samt verktyg förslag PSPing, TraceTCP och nätverks spårning.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP är inkluderat i den här skärm bilden eftersom det är ett användbart verktyg för att visa, i millisekunder, hur lång tid det tar att bearbeta och hur många nätverks hopp, eller anslutningar från en dator till nästa, som begäran tar att nå ett mål. TraceTCP kan också ge servrar namn som används under hopp, som kan vara användbara för en Microsoft Office 365-felsökning i support. > TraceTCP kommandon är mycket enkelt, till exempel: >  `tracetcp.exe outlook.office365.com:443`> kom ihåg att inkludera port numret i kommandot! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) är en gratis nedladdning men använder Wincap. Wincap är ett verktyg som också används och installeras av NetMon. Vi använder också Netmon i avsnittet avancerade metoder. 
  
 Om du har flera kontor måste du ha en uppsättning data från en klient på var och en av dessa platser. Det här testet mäter svar, som i det här fallet är ett nummer värde som beskriver tiden mellan en klient som skickar en begäran till Office 365 och Office 365 som svarar på begäran. Testet härstammar i din domän på en klient dator och ser ut som en rund resa från nätverket, via en utgångs punkt, via Internet till Office 365 och tillbaka. 
  
Det finns några olika sätt att hantera utgångs punkten, i det här fallet proxyservern. Du kan antingen spåra från 1 till 2 och sedan 2 till 3 och sedan addera talen i millisekunder för att få en total summa för nätverkets kant. Eller så kan du konfigurera anslutningen så att den inte används för att kringgå proxyn för Office 365-adresser. I ett större nätverk med en brand vägg, en omvänd proxyserver eller en kombination av de två kan du behöva göra undantag på den proxyserver som gör att trafiken kan passera för många URL-adresser. Listan med slut punkter som används av Office 365 finns i [URL: er och IP-adressintervall för office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Om du har en autentiseringsserver börjar du genom att testa undantag för följande:
  
- Portarna 80 och 443
    
- TCP och HTTPs
    
- Anslutningar som är utgående till någon av dessa webb adresser:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*. sharepoint.com
    
- \*. outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
Alla användare måste ha tillåtelse att få till gång till dessa adresser utan att någon proxyserver stör eller verifieras. I ett mindre nätverk bör du lägga till dessa i din Internet-lista. 
  
Om du vill lägga till dessa i din lista över undantag i Internet Explorer går du till **verktyg** \> **Internet alternativ** \> **Connections** \> **nätverks inställningar** \> **Avancerat**. På fliken Avancerat hittar du också din proxyserver och proxyserver. Du kan behöva klicka på kryss rutan **Använd en proxyserver för ditt lokala nätverk**för att komma åt knappen **Avancerat** . Du bör kontrol lera att **ingen Använd proxyserver för lokala adresser** är markerad. När du klickar på **Avancerat**visas en text ruta där du kan ange undantag. Avgränsa URL-adresserna ovan med semikolon, till exempel:
  
\*. microsoftonline.com; \*. SharePoint.com
  
När du har kringgåt din proxy bör du kunna använda ping eller PsPing direkt på en Office 365-URL. Nästa steg är att testa ping- **Outlook.Office365.com**. Om du använder PsPing eller ett annat verktyg som gör att du kan ange ett port nummer för kommandot, PsPing mot **Portal.microsoftonline.com:443** för att se genomsnittlig fördröjnings tiden i millisekunder. 
  
Tiden för den rundade resan är ett nummer värde som mäter hur lång tid det tar att skicka en HTTP-begäran till en server, till exempel outlook.office365.com, och få svar tillbaka som bekräftar att servern har gjort det. Det här är en förkortning av detta. Detta bör vara en relativt kort tids period.
  
Du måste använda [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) eller ett annat verktyg som inte använder ICMP-paket som blockeras av Office 365 för att kunna göra det här testet. 
  
 **Så här använder du PsPing för att få en total fördröjning i millisekunder direkt från en Office 365-URL**
  
1. Kör en upphöjd kommando tolk genom att utföra de här stegen:
    
1. Klicka på **Start**.
    
2. I rutan **Påbörja sökning** skriver du cmd och trycker sedan på CTRL + SKIFT + RETUR.
    
3. Om dialog rutan **kontroll av användar konto** visas kontrollerar du att den åtgärd som visas är det du vill ha och klickar sedan på **Fortsätt**.
    
2. Navigera till den mapp där verktyget (i det här fallet PsPing) är installerat och testa dessa Office 365-URL: er.
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Kommandot PSPing går till microsoft-my.sharepoint.com port 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Se till att du inkluderar port numret för 443. Kom ihåg att Office 365 fungerar på en krypterad kanal. Om du PsPing utan port numret Miss lyckas din begäran. När du har skickat Pingat den korta listan kan du titta efter genomsnitts tiden i millisekunder (MS). Det är det du vill spela in!
  
![Bild som visar en illustration av en klient för PSPing med en rund rese tid på 2,8 millisekunder.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Om du inte är bekant med att kringgås, och föredrar att ta steget-för-steg, måste du först ta reda på namnet på din proxyserver. I Internet Explorer går du till **verktyg** \> **Internet alternativ** \> **anslutningar** \> **nätverks inställningar** \> **Avancerat**. På fliken **Avancerat** ser du att din proxyserver visas. Pinga till proxyservern vid kommando tolken genom att slutföra den här uppgiften: 
  
 **Pinga proxyservern och få ett värde för en rund resa i millisekunder för steg 1 till 2**
  
1. Kör en upphöjd kommando tolk genom att utföra de här stegen:
    
1. Klicka på **Start**.
    
2. I rutan **Påbörja sökning** skriver du cmd och trycker sedan på CTRL + SKIFT + RETUR.
    
3. Om dialog rutan **kontroll av användar konto** visas kontrollerar du att den åtgärd som visas är det du vill ha och klickar sedan på **Fortsätt**.
    
2. Skriv ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> och tryck sedan på RETUR. Om du har PsPing eller något annat verktyg installerat kan du välja att använda verktyget i stället. 
    
    Kommandot kan se ut ungefär så här: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy: 80
    
3. När spårningen slutar skicka testpaket får du en liten sammanfattning som visar ett medelvärde i millisekunder och det är det värde du följer. Ta en skärmdump av uppmaningen och spara den med hjälp av din namn konvention. I den här punkten kan du även fylla i diagrammet med värdet.
    
Du kanske har gjort en spårning i tidiga morgon och din klient kan komma åt proxyservern (eller vilken Utgående server som går direkt till Internet). I det här fallet kan dina nummer se ut så här:
  
![Bild som visar tiden för fördröjning från en klient till en proxyserver på 2,8 millisekunder.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Om din klient dator är en av de olika sätten att få åtkomst till proxyservern (eller utgångs servern) kan du köra nästa led i testet genom att fjärrans luta till PsPing till en Office 365-URL därifrån. Om du inte har till gång till datorn kan du kontakta nätverks resurserna för att få hjälp med nästa steg och få exakta nummer. Om det inte går kan du ta en PsPing mot Office 365-URL: en och jämföra den med PsPing eller ping-tiden mot proxyservern. 
  
Om du till exempel har 51,84 millisekunder från klienten till Office 365-URL: en, och du har 2,8 millisekunder från klienten till proxyservern (eller utgångs punkten), har du 49,04 millisekunder från utgången till Office 365. Om du har en PsPing på 12,25 millisekunder från klienten till proxyservern under höjden på dagen och 62,01 millisekunder från klienten till Office 365-URL: en 49,76 är det medelvärdet för proxyn som gäller för Office 365-URL: en.
  
![Ytterligare bild som visar ping i millisekunder från klienten till proxy bredvid klienten till Office 365 så att värdena kan subtraheras.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Om du har problem med fel sökning kan det vara intressant att hålla dessa rikt linjer. Om du till exempel normalt har cirka 40 till 59 millisekunder av svar från proxyservern eller utgångs punkten för Office 365-URL: en, och ha en klient som proxyserver eller utgångs punkt med cirka 3 till 7 millisekunder (beroende på hur mycket nätverks trafik du ser under den tiden) kommer du att Buffon vet att något är problematiskt om din senaste tre klient till proxy-eller utgående original plan visar en fördröjning på 45 millisekunder.
  
### <a name="advanced-methods"></a>Avancerade metoder

Om du vill veta vad som händer med dina Internet-förfrågningar till Office 365 måste du bekanta dig med nätverks spårning. Det spelar ingen roll vilka verktyg du föredrar för de här spårningarna, HTTPWatch, Netmon,/Fiddler-loggar, wireshark,, Developer Dashboard Tool eller något annat gör så länge verktyget kan fånga och filtrera nätverks trafik. I det här avsnittet ser du att det är bra att köra fler än ett av de här verktygen för att få en mer fullständig bild av problemet. När du testar fungerar vissa av de här verktygen också som proxyservrar i sin egen rättighet. Verktyg som används i Companion-artikeln, [plan för prestanda fel sökning för Office 365](performance-troubleshooting-plan.md), include [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)eller [wireshark](https://www.wireshark.org/).
  
Att ta en bas linje är den enkla delen av den här metoden och många av stegen är samma som när du felsöker ett problem med prestanda. De mer avancerade metoderna för att skapa original planer för prestanda kräver att du tar och lagrar nätverks spårningar. De flesta av exemplen i den här artikeln använder SharePoint Online, men du bör utveckla en lista över vanliga åtgärder i de Office 365-tjänster som du abonnerar på för att testa och spela in. Här är ett exempel på en original plan:
  
- Bas linje lista för SPO-* * steg 1: * * Bläddra på Start sidan för SPO webbplats och gör en nätverks spårning. Spara spårningen. 
    
- Original lista för SPO- **steg 2:** Sök efter en period (till exempel företagets namn) via Enterprise Search och gör en nätverks spårning. Spara spårningen. 
    
- Baseline-lista för SPO- **steg 3:** Ladda upp en stor fil till ett SharePoint Online-dokumentbibliotek och gör en nätverks spårning. Spara spårningen. 
    
- Original lista för SPO – **steg 4:** Bläddra på Start sidan på OneDrive-webbplatsen och gör en nätverks spårning. Spara spårningen. 
    
Listan ska innehålla de viktigaste vanliga åtgärderna som användarna tar mot SharePoint Online. Observera att det sista steget för att spåra till OneDrive för företag – en jämförelse mellan start sidan för SharePoint Online (som ofta anpassas efter företag) och start sidan för OneDrive för företag, som inte är anpassat. Det här är ett mycket grundläggande test när det gäller en SharePoint Online-webbplats med långsam laddning. Du kan skapa en post av denna skillnad i testningen.
  
Om du befinner dig i ett prestanda problem är många av stegen desamma som när du tar en original plan. Nätverks spårningar blir kritiskt, så vi hanterar  *hur*  du gör de viktiga spårningarna bredvid. 
  
För att du ska kunna lösa prestanda  *problem måste du*  ta en titt när du upplever prestanda problemet. Du måste ha de rätta verktygen tillgängliga för att samla in loggar, och du behöver en åtgärds plan, det vill säga en lista över fel söknings åtgärder som ska vidtas för att samla in den bästa informationen som du kan. Det första du ska göra är att registrera datum och tid för testet så att filerna kan sparas i en mapp som visar tids inställningen. Sedan kan du begränsa ned till själva problem stegen. Det här är de exakta stegen du kan använda för att testa. Glöm inte grunderna: om problemet bara gäller Outlook kontrollerar du att problem beteendet inträffar i en Office 365-tjänst. Genom att begränsa omfattningen av detta problem kan du fokusera på något du kan lösa. 
  
## <a name="see-also"></a>Se även

[Hantera slut punkter för Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

