---
title: Nätverk (till molnet) - En arkitekt synvinkel
description: Beskrivning.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 778693787c3d26806b02a2ffbde57e3347326d87
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522275"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a>Nätverk (till molnet) - En arkitekt synvinkel

I den här artikeln beskriver [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect på Microsoft, hur du optimerar nätverket för molnanslutning genom att undvika de vanligaste fallgroparna. 

## <a name="about-the-author"></a>Om författaren

![Ed Fisher foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Jag är för närvarande en teknisk specialist i sydöstra regionen med fokus på säkerhet & compliance. Jag har arbetat med kunder som flyttar till Office 365 under de senaste tio åren. Jag har arbetat med mindre butiker med en handfull platser till myndigheter och företag med miljontals användare spridda runt om i världen, och många andra kunder däremellan, med de flesta har tiotusentals användare, flera platser i olika delar av världen, behovet av en högre grad av säkerhet, och en mängd efterlevnadskrav. Jag har hjälpt hundratals företag och miljontals användare att flytta till molnet på ett säkert och säkert sätt.

Med en bakgrund under de senaste 25 åren som inkluderar säkerhet, infrastruktur och nätverksteknik, och efter att ha flyttat två av mina tidigare arbetsgivare till Office 365 innan jag började på Microsoft, har jag varit på din sida av bordet många gånger och kom ihåg hur det är. Även om inga två kunder någonsin är desamma, de flesta har liknande behov, och när de konsumerar en standardiserad tjänst som någon SaaS eller PaaS plattform, de bästa metoderna tenderar att vara densamma.



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>Det är inte nätverket - det är hur du (mis) använder det!

Oavsett hur många gånger det händer, misslyckas det aldrig att förvåna mig hur *kreativa* säkerhetsteam och nätverksteam försöker få med hur de tycker att de ska ansluta till Microsofts molntjänster. Det finns alltid någon säkerhetspolicy, efterlevnadsstandard eller bättre sätt de insisterar på att använda, utan att vara villiga att delta i en konversation om vad det är de försöker åstadkomma, eller *hur* de är bättre, enklare, mer kostnadseffektiva och mer högpresterande sätt att göra det. 

När denna typ av sak eskaleras till mig, jag är oftast villig att ta utmaningen och gå igenom dem genom hows och whys och få dem dit de behöver vara. Men om jag är helt uppriktig, måste jag dela att ibland vill jag bara låta dem göra vad de vill, och komma tillbaka för att säga att jag sa till dig så när de slutligen medger att det inte fungerar. Jag kanske vill göra det ibland, men jag *gör inte.* Vad jag gör är att försöka förklara allt vad jag kommer att inkludera i det här inlägget. Oavsett din roll, om din organisation vill använda Microsofts molntjänster, det finns förmodligen en viss visdom i vad som följer som kan hjälpa dig.


## <a name="guiding-principles"></a>Riktlinjer
Låt oss börja med några grundregler kring vad vi gör här. Vi diskuterar hur du på ett säkert sätt kan ansluta till molntjänster för att säkerställa minsta komplexitet och maximal prestanda, samtidigt som verklig säkerhet upprätthålls. Inget av vad som följer är räknare till något av detta, även om du, eller din kund, inte kommer att få använda din favorit proxyserver för allt.

- **Bara för att du kan, betyder inte att du borde** - Eller att parafrasera Dr Ian Malcolm från Jurassic Park filmen ". . . Ja, ja, men ditt säkerhetsteam var så upptagen med om de kunde att de inte sluta att tänka om de borde."    
- **Säkerhet betyder inte komplexitet** - Du är inte säkrare bara för att du spenderar mer pengar, rutt genom fler enheter, eller klicka på fler knappar.
- **Office 365 nås via Internet** – Men det är inte samma sak som att Office 365 är Internet. Det är en SaaS-tjänst som hanteras av Microsoft och administreras av dig. Till skillnad från webbplatser du besöker på Internet, får du faktiskt kika bakom gardinen, och kan tillämpa de kontroller du behöver för att uppfylla dina policyer och dina efterlevnadsstandarder, så länge du förstår att medan du kan uppfylla dina mål, kan du bara behöva göra dem på ett annat sätt.
- **Chokepoints är dåliga, lokaliserade breakouts är bra** - Alla vill alltid backhaul all sin Internet-trafik för alla sina användare till någon central punkt, oftast så att de kan övervaka den och genomdriva politik, men ofta eftersom det är antingen billigare än etablering Internet-åtkomst på alla sina platser, eller det är bara hur de gör det. Men de där chokepointsna är precis att... punkter där trafiken kvävs. Det är inget fel med att hindra användarna från att bläddra till Instagram eller strömma kattvideor, men behandla inte din verksamhetskritiska affärsapplikationstrafik på samma sätt.
- **Om DNS inte är nöjd, är inte något lyckligt** - Det bäst utformade nätverket kan lamslås av dålig DNS, oavsett om det är genom att upprepa förfrågningar till servrar i andra delar av världen eller använda din Isp:s DNS-servrar eller andra offentliga DNS-servrar som cachelagrar DNS-lösningsinformation. 
- **Bara för att det är så du brukade göra det, betyder inte att det är så du ska göra det nu** - Teknik ändras hela tiden och Office 365 är inget undantag. Att tillämpa säkerhetsåtgärder som har utvecklats och distribuerats för lokala tjänster eller för att kontrollera webbsurfning kommer inte att ge samma säkerhetsnivå och kan ha en betydande negativ inverkan på prestanda.
- **Office 365 byggdes för att nås via Internet** - Det är det i ett nötskal. Oavsett vad du vill göra mellan dina användare och din kant, trafiken går fortfarande över Internet när den lämnar ditt nätverk och innan den kommer in på vår. Även om du använder Azure ExpressRoute för att dirigera viss latenskänslig trafik från nätverket direkt till vårt, är Internet-anslutning absolut nödvändig. Acceptera det. Tänk inte för mycket på det.

## <a name="where-bad-choices-are-often-made"></a>Där dåliga val ofta görs

Även om det finns gott om platser där dåliga beslut fattas i säkerhetens namn, är dessa de jag möter oftast med kunder. Många kundsamtal involverar alla dessa på en gång.

### <a name="insufficient-resources-at-the-edge"></a>Otillräckliga resurser vid kanten
Mycket få kunder distribuerar greenfield miljöer, och de har många års erfarenhet av hur deras användare fungerar och hur deras Internet utgående är. Oavsett om kunderna har proxyservrar eller tillåter direkt åtkomst och helt enkelt NAT utgående trafik, de har gjort det i flera år och inte överväga hur mycket mer de kommer att börja pumpa genom sin kant när de flyttar traditionellt interna program ut till molnet.

Bandbredd är alltid ett problem, men NAT-enheter kanske inte har tillräckligt med hästkrafter för att hantera den ökade belastningen och kan börja stänga anslutningar i förtid för att frigöra resurser. De flesta klientprogram som ansluter till Office 365 förväntar sig beständiga anslutningar och en användare som använder Office 365 kan ha 32 eller fler samtidiga anslutningar. Om NAT-enheten tappar dem i förtid kan dessa appar inte svara när de försöker använda de anslutningar som inte längre finns där. När de ger upp och försöker etablera nya anslutningar, lägger de ännu mer belastning på ditt nätverk redskap.

### <a name="localized-breakout"></a>Lokaliserad breakout
Allt annat i denna lista kommer ner till en sak - att få bort ditt nätverk och på vår så snabbt som möjligt. Backhauling dina användares trafik till en central utgående punkt, särskilt när den utgående punkten är i en annan region än dina användare är i, introducerar onödig latens och påverkar både klientupplevelsen och nedladdningshastigheter. Microsoft har närvaropunkter över hela världen med fronten för alla våra tjänster och peering som upprättats med praktiskt taget alla större Internet-leverantören, så routing dina användares trafik ut *lokalt* säkerställer att det kommer in i vårt nätverk snabbt med minsta latens. 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-matchningstrafik bör följa internetvägen för utgående
Naturligtvis, för en klient att hitta en slutpunkt, måste den använda DNS. Microsofts DNS-servrar utvärderar källan till DNS-begäranden för att säkerställa att vi returnerar det svar som, i Internettermer, är närmast källan till begäran. Kontrollera att DNS:n är konfigurerad så att namnmatchningsbegäranden går ut samma sökväg som användarnas trafik, så att du inte ger dem lokal utgående utan till en slutpunkt i en annan region. Det innebär att låta lokala DNS-servrar "gå till rot" i stället vidarebefordra till DNS-servrar i fjärrdatacenter. Och se upp för offentliga och privata DNS-tjänster, som kan cache resultat från en del av världen och tjäna dem till förfrågningar från andra delar av världen.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Till proxy eller inte proxy, det är frågan
En av de första sakerna att tänka på är om proxy användarnas anslutningar till Office 365. Den där är lätt; proxy. Office 365 nås via Internet, men det är inte Internet. Det är en förlängning av din kärntjänster och bör behandlas som sådana. Allt du kanske vill ha en proxy att göra, till exempel DLP eller antimalware eller innehållsinspektion, är redan tillgängligt för dig i tjänsten, och kan användas i stor skala och utan att behöva knäcka TLS-krypterade anslutningar. Men om du verkligen vill proxy trafik som du annars inte kan kontrollera, uppmärksamma vår vägledning på [https://aka.ms/pnc](https://aka.ms/pnc) och de kategorier av trafik på [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Vi har tre trafikkategorier för Office 365. Optimera och tillåt verkligen ska gå direkt och kringgå din proxy. Standard kan proxied. Detaljerna finns i dessa dokument . . . läsa dem.

De flesta kunder som insisterar på att använda en proxy, när de faktiskt tittar på vad de gör, kommer att inse att när klienten gör en HTTP CONNECT-begäran till proxy, är proxy nu bara en dyr extra router. De protokoll som används som MAPI och RTC är inte ens protokoll som webb proxyservrar förstår, så även med TLS sprickbildning du egentligen inte får någon extra säkerhet. Du *får* extra latens. Se [https://aka.ms/pnc](https://aka.ms/pnc) mer information om detta, inklusive kategorierna Optimera, Tillåt och Standard för Microsoft 365-trafik.

Slutligen, beakta den totala effekten på proxy och dess motsvarande svar för att hantera denna effekt. Eftersom fler och fler anslutningar görs via proxy, kan det minska TCP Scale Factor så att den inte behöver buffra så mycket trafik. Jag har sett kunder där deras fullmakter var så överbelastade att de använde en skala faktor 0. Eftersom Scale Factor är ett exponentiellt värde och vi gillar att använda 8, är varje minskning av skalfaktorvärdet en enorm negativ inverkan på dataflödet.

TLS-inspektion betyder säkerhet! Men inte riktigt! Många kunder med fullmakter vill använda dem för att inspektera all trafik, och det betyder TLS "bryta och inspektera." När du gör det för en webbplats som nås via HTTPS (integritetsproblem trots) kan din proxy behöva göra det för tio eller till och med tjugo samtidiga strömmar för några hundra millisekunder. Om det finns en stor nedladdning eller kanske en video inblandade, en eller flera av dessa anslutningar kan pågå mycket längre, men på det hela taget, de flesta av dessa anslutningar upprätta, överföra och stänga mycket snabbt. Att göra paus och inspektera innebär att proxyn måste göra dubbla arbetet. För varje anslutning från klienten till proxyn måste proxyn också göra en separat anslutning tillbaka till slutpunkten. Så, en blir två, två blir fyra, trettiotvå blir sextiofyra . . . ser du vart jag är på väg? Du förmodligen storlek din proxy lösning alldeles utmärkt för typiska webbsurfning, men när du försöker göra samma sak för klientanslutningar till Office 365, antalet samtidiga, långlivade anslutningar kan vara storleksordningar större än vad du storlek för.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming är inte viktigt, förutom att det *är*
De enda tjänster i Office 365 som använder UDP är Skype (snart att dras tillbaka) och Microsoft Teams. Team använder UDP för direktuppspelning av trafik, inklusive ljud-, video- och presentationsdelning. Strömmande trafik är live, till exempel när du har ett onlinemöte med röst, video och presentation av däck eller utföra demos. Dessa använder UDP för om paket tas bort, eller anländer i fel ordning, det är praktiskt taget osynlig av användaren och strömmen kan bara fortsätta. 

När du inte tillåter utgående UDP-trafik från klienter till tjänsten kan de återgå till att använda TCP. Men om ett TCP-paket tas *bort, stoppas allt* tills timeouten för återöverföring (RTO) upphör att gälla och det saknade paketet kan återsändas. Om ett paket kommer i oordning stannar allt tills de andra paketen anländer och kan monteras ihop igen i ordning. Båda leder till märkbara buggar i ljudet (kom ihåg Max Headroom?) och video (har du klicka someth . . . åh, där är det) och leda till dåliga prestanda och en dålig användarupplevelse. Och kom ihåg vad jag satte upp ovan om fullmakter? När du tvingar en Teams-klient att använda en proxy tvingar du den att använda TCP. Så nu orsakar du negativa prestandaeffekter två gånger.

### <a name="split-tunneling-may-seem-scary"></a>Delad tunnel kan verka skrämmande
Men det är det inte. Alla anslutningar till Office 365 är över TLS. Vi har erbjudit TLS 1.2 ett bra tag nu och kommer att inaktivera äldre versioner snart eftersom äldre klienter fortfarande använder dem och det är en risk.

Tvinga en TLS-anslutning, eller trettiotvå av dem, att gå över en VPN innan de sedan går till tjänsten inte lägga till säkerhet. Det lägger latens och minskar det totala dataflödet. I vissa VPN-lösningar tvingar det även UDP till tunnel genom TCP som återigen kommer att ha en mycket negativ inverkan på strömmande trafik. Och om du inte gör TLS inspektion, det finns ingen upp, alla nackdelen. Ett mycket vanligt tema bland kunder för närvarande, nu när de flesta av deras personal är avlägsen, är att de ser betydande bandbredd och prestanda effekter från att göra alla sina användare ansluta med hjälp av en VPN, istället för att konfigurera delad tunnel för åtkomst till [Optimera kategori Office 365 slutpunkter](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).

Det är en enkel fix att göra delad tunnel och det är en du bör göra. Mer information finns i [Optimera Office 365-anslutning för fjärranvändare med delad VPN-tunnel](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).


## <a name="the-sins-of-the-past"></a>Synder i det förflutna
Många gånger, anledningen till dåliga val görs kommer från en kombination av (1) utan att veta hur tjänsten fungerar, (2) försöker följa företagets policyer som skrevs innan du antar molnet, och (3) säkerhetsteam som kanske inte är lätt övertygad om att det finns mer än ett sätt att uppnå sina mål. Förhoppningsvis ovanstående, och länkarna nedan, kommer att hjälpa till med den första. Executive sponsring kan krävas för att komma förbi den andra. Att ta itu med säkerhetspolitikens mål, snarare än deras metoder, hjälper till med den tredje. Från villkorad åtkomst till innehållsmoderering, DLP till informationsskydd, slutpunktsvalidering till nolldagshot – alla slutmål som en rimlig säkerhetsprincip kan ha kan utföras med vad som är tillgängligt i Office 365 och utan något beroende av lokala nätverksväxlar, påtvingade VPN-tunnlar och TLS-avbrott och inspektion. 

Andra gånger kan maskinvara som har storlek och inköpts innan organisationen började flytta till molnet helt enkelt inte skalas upp för att hantera de nya trafikmönstren och belastningarna. Om du verkligen måste dirigera all trafik genom en enda utgående punkt, och / eller proxy det, vara beredd att uppgradera nätverksutrustning och bandbredd därefter. Noggrant övervaka användningen på båda, eftersom upplevelsen inte kommer att minska långsamt som fler användare ombord. Allt kommer att bli bra tills tipping point nås, då alla lider. 

## <a name="exceptions-to-the-rules"></a>Undantag från reglerna

Om din organisation kräver [klientbegränsningar](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)måste du använda en proxy med TLS-paus och inspektera för att tvinga viss trafik genom proxyn, men du behöver inte tvinga all trafik genom den.  Det är inte en allt eller inget proposition, så var uppmärksam på vad som behöver ändras av proxy. 

Om du ska tillåta delad tunnel men också använda en proxy för allmän webbtrafik, se till att din PAC-fil definierar vad som måste gå direkt samt hur du definierar intressant trafik för vad som går genom VPN-tunneln. Vi erbjuder exempel PAC filer på [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) som kommer att göra detta lättare att hantera.

## <a name="conclusion"></a>Sammanfattning

Tiotusentals organisationer, inklusive nästan hela Fortune 500, använder Office 365 varje dag för sina verksamhetskritiska funktioner. De gör det på ett säkert sätt, och de gör det via Internet.

 Oavsett vilka säkerhetsmål du har i spel, det finns sätt att utföra dem som inte kräver VPN-anslutningar, proxyservrar, TLS bryta och inspektera, eller centraliserad Internet utgående för att få dina användares trafik från ditt nätverk och vidare till vår så fort du kan, vilket ger bästa prestanda, oavsett om ditt nätverk är företagets huvudkontor, ett avlägset kontor , eller den användaren som arbetar hemma. Vår vägledning baseras på hur Office 365-tjänsterna är byggda och för att säkerställa en säker och högpresterande användarupplevelse.

## <a name="further-reading"></a>Ytterligare läsning

[Principerna för nätverksanslutning i Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)

[URL-adresser och IP-adressintervall för Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges?redirectSourcePath=%252fen-us%252farticle%252fOffice-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Hantera Office 365-slutpunkter](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

[Webbtjänsten Office 365 IP-adress och URL](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

[Bedöma nätverksanslutningen för Office 365](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Nätverks- och prestandajustering för Office 365](https://docs.microsoft.com/office365/enterprise/network-planning-and-performance)

[Bedöma nätverksanslutningen för Office 365](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](https://docs.microsoft.com/office365/enterprise/performance-tuning-using-baselines-and-history)

[Felsökningsplan för prestanda för Office 365](https://docs.microsoft.com/office365/enterprise/performance-troubleshooting-plan)

[Nätverk för innehållsleverans](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)

[Anslutningstest för Microsoft 365](https://connectivity.office.com/)

[Så bygger Microsoft sitt snabba och pålitliga globala nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blogg för Office 365-nätverk](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-anslutning för fjärranvändare som använder delad VPN-tunnel](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


