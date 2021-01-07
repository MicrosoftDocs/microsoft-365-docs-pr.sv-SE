---
title: Nätverk upp (till molnet) – en arkitekts synvinklar
description: Lär dig hur du optimerar nätverket för moln anslutningar genom att undvika de vanligaste fall GRO par.
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
ms.openlocfilehash: 175903949b639740ad00b29013d5748b99bdb2de
ms.sourcegitcommit: ddfb4f3e34deb733e8625e845e4dfd1fcc066ceb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49771853"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Nätverk upp (till molnet) – en arkitekts synvinklar

I den här artikeln, [Erik Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect på Microsoft, beskrivs hur du optimerar nätverket för moln anslutningar genom att undvika de vanligaste fall GRO par. 

## <a name="about-the-author"></a>Om författaren

![Erik Fisher-foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Jag är för närvarande en huvudsaklig teknisk specialist i den södra öst-regionen som fokuserar på säkerhets & efterlevnad. Jag har arbetat med kunder som flyttar till Office 365 under de senaste 10 åren. Jag har arbetat med mindre butiker med en fåtal av platser till statliga myndigheter och företag med miljon tals användare i världen, och många andra kunder emellan, med massor av tusentals användare, flera platser i olika delar av världen, behovet av högre säkerhet och ett stort antal efterföljandekrav. Jag har hjälpt hundratals företag och miljon tals användare att flytta till molnet säkert och säkert.

Med en bakgrunds bild under de senaste 25 åren med säkerhet, infrastruktur och nätverks teknik och som har flyttat två av mina tidigare arbetsgivare till Office 365 innan du ansluter till Microsoft, har jag varit på en sida av en mängd olika tider och kan komma ihåg vad som är bra. Även om inga två kunder är samma, har mest liknande behov och när en standardiserad tjänst såsom SaaS-eller PaaS-plattform används är det bästa sättet att vara samma.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Det är inte nätverket – det är så du kan (MIS) använda det!

Det spelar ingen roll hur många gånger det tar att det inte går att överraska mig hur *kreativa* säkerhets team och nätverks Team försöker få information om hur de ska ansluta till Microsofts moln tjänster. Det finns alltid vissa säkerhets principer, efterlevnadar standard eller bättre sätt de måste att använda, utan att behöva delta i en konversation om vad det är som de försöker åstadkomma, eller *hur* de är bättre, enklare, mer kostnads effektiva och mer på att göra detta.

När den här sorteringen är eskalerad till mig är jag vanligt vis villig att ta en utmaning och gå igenom vad de gör och få dem att vara. Men om jag är helt Frank måste jag dela det ibland jag vill för att bara låta dem göra vad de ska och komma tillbaka till Säg att jag får ett meddelande om att det inte fungerar. Jag kanske vill göra det ibland men jag vill *inte*. Vad jag gör är att förklara vad jag ska ta med i det här inlägget. Oberoende av din roll, om din organisation vill använda Microsofts moln tjänster, finns det troligen vissa ned idéerna som kan hjälpa dig.

## <a name="guiding-principles"></a>Väg LED ande principer

Låt oss komma igång med vissa regler för jorden. Vi diskuterar hur du säkert ansluter till moln tjänster för att säkerställa minimi kraven och maximal prestanda, samtidigt som verklig säkerhet upprätthålls. Inget av ovanstående är en räknare, även om du eller din kund inte kommer att använda din favorit Server för allting.

- Det **innebär att du inte kan**: eller till Paraphrase Dr. Ian Malcolm från Jurassic Park-filmen "... Ja, ja, men din säkerhets grupp var så upptagen, oavsett om de kunde göra det eller inte. "
- **Säkerhet betyder inte komplexitet**: du är inte säkrare just nu eftersom du tillbringar mer pengar, dirigerar fler enheter eller klickar på fler knappar.
- **Office 365 nås via Internet**: men det är inte samma sak som Office 365 är Internet. Det är en SaaS tjänst som hanteras av Microsoft och administreras av dig. Till skillnad från webbplatser du besöker på Internet gör du verkligen att titta bakom Curtain och kan använda de kontroller som behövs för att uppfylla dina principer och dina krav på efterlevnad, så länge du förstår att du kan möta dina mål.
- **Chokepoints är dåligt, lokaliserade breakouts är bra**: alla får alltid all sin Internet trafik till alla sina användare till en viss central plats, så att de kan övervaka det och genomföra principer, men ofta för att det är billigare än att ge Internet åtkomst på alla sina platser, eller så är det bara hur det fungerar. Men dessa chokepoints är exakt det... Poäng där trafikstrypningar är. Det finns inget fel med att förhindra att användarna surfar på Instagram eller direktuppspelande Cat-videor, men du kan inte hantera ditt uppdrag – kritisk affärs program trafik på samma sätt.
- **Om DNS Ain ' t glad, Ain ' t inget** svar: det bästa nätverket kan vara hamstrung av dåligt DNS, oavsett om det är en återkommande begäran till servrar i andra delar av världen eller använder din Internet leverantörs DNS-server eller andra offentliga DNS-servrar som CACHELAGRAr DNS-matchningstid.
- Det är precis så som **du gör så här för att göra det nu**: tekniska ändringar och Office 365 är inte ett undantag. Säkerhets åtgärder som har utvecklats och distribuerats för lokala tjänster eller för kontroll av webbsurfning kommer inte att tillhandahålla samma säkerhets garanti och kan ha en avsevärd negativ inverkan på prestanda.
- **Office 365 har utformats för att kunna nås via Internet**: det är i en nötskal. Oavsett vad du vill göra mellan användarna och din sida, kommer trafiken att gå över Internet när den lämnar nätverket och innan det får i vårt. Även om du använder Azure ExpressRoute för att dirigera viss fördröjnings känslig trafik från ditt nätverk direkt till vår, är Internet anslutningen absolut nödvändig. Godkänn det. Bry dig inte om det.

## <a name="where-bad-choices-are-often-made"></a>Där felaktiga val ofta görs

Det finns massor av platser där felaktiga beslut fattas i säkerhets namnet, men de är de som jag ofta träffar med kunder. Många kund samtal inkluderar alla dessa på en gång.

### <a name="insufficient-resources-at-the-edge"></a>Otillräckliga resurser på kanten

Många kunder distribuerar Greenfield-miljöer och de har många års erfarenhet av hur deras användare kan arbeta och hur deras Internet utgångs gilla. Om kunder har proxyservrar eller tillåter direkt åtkomst och helt enkelt NAT utgående trafik, har de gjort det för år och behöver inte veta hur mycket det är att starta pumpen genom sin kant när de flyttar vanligt vis interna program till molnet.

Bandbredd är alltid ett problem, men det kan hända att de inte har tillräckligt med kraftiga krafter för att hantera den ökade belastningen och kan komma att avsluta anslutningar för tidigt för att frigöra resurser. De flesta klient program som ansluter till Office 365 förväntar sig permanenta anslutningar och en användare som använder Office 365 fullt ut kan ha 32 eller fler samtidiga anslutningar. Om en NAT-enhet tar bort dem för tidigt kan de programmen sluta svara när de försöker använda de anslutningar som inte längre finns där. När de ger upp och försöker upprätta nya anslutningar kan de sätta in ännu mer på din nätverks utrustning.

### <a name="localized-breakout"></a>Lokaliserad översikten

Allt annat i den här listan kommer att gå ned till en enda sak – att komma igång med nätverket och till så snabbt som möjligt. Genom att se till att dina användares trafik behålls till en central utgångs punkt, särskilt om den utgångs punkten är i ett annat område än användarna är i, inför en onödig fördröjning och påverkar både klientens upplevelse och nedladdnings hastighet. Microsoft har närvaro frågor i hela världen med fram sidan av alla våra tjänster och peer-datorer som är etablerade med praktiskt taget varje huvud Internet-leverantör, så att användarens trafik kan ut *lokalt* garanterar att det hamnar i vårt nätverk snabbt med minsta möjliga svars tid.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-namnupplösning bör följa vägen för Internet avgångar

För att en kund ska kunna hitta slut punkter måste den naturligtvis använda DNS. Microsofts DNS-servrar utvärderar källan för DNS-begäranden för att se till att vi returnerar svaret i Internet termer, närmast källan till begäran. Kontrol lera att din DNS-konfiguration är konfigurerad så att namn matchnings förfrågningarna fungerar på samma sätt som användarens trafik, lest du ger dem lokal utfallet men till en slut punkt i en annan region. Det innebär att du kan låta lokala DNS-servrar "gå till rot" istället för att vidarebefordra till DNS-servrar i fjärrdatakälla. Och se upp med offentliga och privata DNS-tjänster, som kan cachelagra resultat från en del av världen och betjäna dem till önskemål från andra delar av världen.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Till proxy eller inte till proxyserver, det vill säga frågan

Ett av de första sakerna som du bör överväga är att gruppanvändare ansluter till Office 365. Det är enkelt, Använd inte proxy. Office 365 nås via Internet men är inte Internet. Det är en förlängning av kärn tjänsterna och bör behandlas som sådana. Allt du kanske vill att en proxyserver ska göra, till exempel DLP eller skadlig program vara eller innehålls kontroll, finns redan tillgänglig i tjänsten och kan användas i takt och utan att du behöver knäcka TLS-krypterade anslutningar. Men om du vill ha en replikeringstrafik som du inte kan kontrol lera, kan du betala genom vår vägledning [https://aka.ms/pnc](https://aka.ms/pnc) och kategorier av trafik på [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Vi har tre trafik kategorier för Office 365. Optimera och Tillåt verkligen att gå direkt och kringgå din proxy. Standard kan vara proxy. Informationen är i dessa dokument... läsa dem.

De flesta kunder som måste på att använda en proxyserver, när de faktiskt tittar på vad de gör, kommer att inse att när klienten gör en HTTP-anslutningsbegäran till proxyservern är det bara en dyr extra router. Protokollen som används, till exempel MAPI och REALity, är inte till ännu olika protokoll som webb proxyservrar förstår, så även med TLS som knäcker dig, får du inte extra säkerhet. Du *får* extra svars tid. Läs mer [https://aka.ms/pnc](https://aka.ms/pnc) om detta, inklusive optimerings-, Tillåt-och standard kategorierna för Microsoft 365-trafik.

Slutligen bör du tänka på den allmänna effekten av proxyn och dess motsvarande svar på den effekten. Allteftersom mer och fler anslutningar görs via proxyservern kan det minska TCP-skalan så att den inte måste buffra så mycket trafik. Jag visade kunder var deras proxyservrar hade så överbelastade att de använde en skalnings faktor på 0. Eftersom skalnings faktor är ett exponentiellt värde och vi gillar 8, är varje minskning av skalnings faktorns värde en enorm negativ inverkan på data flödet.

TLS-inspektion innebär säkerhet! Men inte riktigt det! Många kunder med proxyservrar vill använda dem för att kontrol lera all trafik och det innebär att TLS "bryta och inspektera". När du gör det för en webbplats som nås via HTTPS (sekretess frågor utan problem) kanske din proxy måste göra det för 10 eller till och med 20 samtidiga strömmar i några hundra millisekunder. Om det finns en stor nedladdning eller en video som är involverad kan en eller flera av dessa anslutningar vara längre, men de flesta av dessa anslutningar upprättar, överför och stänger snabbt. Om du gör paus och inspekterar måste den fungera dubbelt. För varje anslutning från klienten till proxyservern måste proxyservern också ansluta tillbaka till slut punkten. Det betyder att 1 blir 2, 2 blir 4, 32 blir 64... se var jag håller? Du har förmodligen begränsat storleken på din proxyserver för vanlig webbsurfning, men när du försöker göra samma sak för klient anslutningar till Office 365 kan antalet samtidiga lång tids lösa anslutningar vara större än vad du har för storlek.

### <a name="streaming-isnt-important-except-that-it-is"></a>Direkt uppspelning är inte viktigt, förutom att det *är*

De enda tjänster i Office 365 som använder UDP är Skype (snart kommer att dras tillbaka) och Microsoft Teams. Teams använder UDP för strömnings trafik, inklusive ljud-, video-och presentations delning. Direkt uppspelnings trafik är aktiv, till exempel när du har ett onlinemöte med röst, video och bild spel. Dessa använder UDP på grund av att om paket tas bort, eller anländer i rätt ordning, är det praktiskt taget inte heller möjligt att komma igång.

Om du inte tillåter utgående UDP-trafik från klienter till tjänsten kan de använda TCP. Men om ett TCP-paket bryts *avbryts allting* tills timeout-värdet för överföring (RTO) upphör att gälla och det paket som saknas kan överföras. Om ett paket tar slut kan allting sluta tills de andra paketen ankommer och kan sättas ihop i rätt ordning. Båda leder till perceptiblea problem i ljudet (kom ihåg Max utrymme?) och video (klickade på något... Det är bara att göra det och få en dålig prestanda och en dålig användar upplevelse. Och kom ihåg vad jag lägger upp ovanför om proxyservrar? När du tvingar en Teams-klient att använda en proxyserver tvingar du den att använda TCP. Det innebär att du får negativa prestanda konsekvenser två gånger.

### <a name="split-tunneling-may-seem-scary"></a>Delad tunnel kan verka skrämmande

Men det är inte det. Alla anslutningar till Office 365 är över TLS. Vi har beviljat TLS 1,2 för ett tag nu och kommer att inaktivera äldre versioner, eftersom äldre klienter fortfarande använder dem och det är en risk.

Tvinga fram en TLS-anslutning, eller 32 av dem, för att gå över ett VPN-nätverk innan de går till tjänsten kan du inte lägga till säkerhet. Det gör att du kan lägga till fördröjningar och reducerar hela flödet. I vissa VPN-lösningar tvingar den även UDP-tunnel via TCP, vilket återigen får en mycket negativ påverkan på strömnings trafiken. Och såvida du inte genomför en TLS-kontroll finns det ingen upp och alla nack delar. Ett mycket vanligt tema bland kunder, nu när de flesta av deras arbets styrka är fjärr, är det viktigt att de ser betydande bandbredd och prestanda påverkan från att göra alla sina användare kopplade till en VPN-anslutning, i stället för att konfigurera dela tunnlar för Access för att [optimera kategorierna för Office 365-slutpunkter](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).

Det är en enkel lösning för att dela tunnlar och det är en du bör göra. För mer information, se till att [optimera Office 365-anslutningar för fjärran vändare via VPN-delning](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel).

## <a name="the-sins-of-the-past"></a>Synderna

Många gånger är orsaken till att felaktiga val görs från en kombination av (1) som inte vet hur tjänsten fungerar, (2) som försöker följa företags principer som har skrivits innan de använde molnet och (3) säkerhets team som kanske inte är lätt övertygade om att det finns mer än ett sätt att nå sina mål. Förhoppnings vis kan ovanstående och länkarna nedan vara till hjälp med den första. Executive-finansiering kan krävas för att passera förbi den andra. Med den tredje kan du adressera sina mål för säkerhets principer, snarare än deras metoder. Från villkorlig åtkomst till innehålls redigering, DLP till informations skydd, slut punkts validering för noll-dagars hot – alla slut mål en skälig säkerhets policy kan ha kunnat utföras med vad som är tillgängligt i Office 365 och utan något beroende på lokala nätverks redskap, tvingande VPN-tunnlar och TLS-och kontroll.

Andra tider, maskin vara som är storlek och inköpt innan organisationen började gå till molnet kan helt enkelt inte skalas upp för att hantera de nya trafik mönstren och belastningarna. Om du verkligen måste dirigera all trafik via en enda avgångs punkt och/eller proxy måste du vara beredd att uppgradera nätverks utrustning och bandbredd. Använd noga bättre övervakning på båda samtidigt som upplevelsen inte minskar långsamt allteftersom fler användare ombord. Allting kommer att vara bra tills den nedlutande punkten nås och sedan alla lider.

## <a name="exceptions-to-the-rules"></a>Undantag från reglerna

Om din organisation kräver [begränsningar för innehavare](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)måste du använda en proxy med TLS-avbrott och kontrol lera att tvinga fram viss trafik via proxyservern, men du behöver inte tvinga fram all trafik genom den.  Det är inte ett helt eller inget förslag, så du bör vara uppmärksam på vad som behöver ändras av proxyservern.

Om du ska tillåta delade tunnlar men också använda en proxyserver för allmän webb trafik bör du kontrol lera att PAC-filen definierar vad som måste gå direkt och hur du definierar en intressant trafik för vad som går genom VPN-tunneln. Vi tillhandahåller exempel PAC-filer [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) som gör det enklare att hantera.

## <a name="conclusion"></a>Sammanfattning

Många tusen organisationer, inklusive nästan alla förmögenhet 500, använder Office 365 varje dag för sina verksamhets kritiska funktioner. De gör det säkert och de gör det via Internet.

Oavsett vilka säkerhets mål du har i spelet kan du använda dem som inte kräver VPN-anslutningar, proxyservrar, TLS-avbrott och kontroll, eller centraliserad Internet-avslut för att få användarens trafik att avsluta ditt nätverk och på så sätt som möjligt, oavsett om nätverket är företagets huvud kontor, ett fjärrkontor eller den användaren jobbar hemma. Vår vägledning baseras på hur Office 365-tjänsterna är byggda och för att säkerställa en säker och välfungerande användar upplevelse.

## <a name="further-reading"></a>Läs vidare

[Principerna för nätverks anslutningen för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[URL-adresser och IP-adressintervall för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Hantera Office 365-slutpunkter](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[Office 365 IP-adress och URL webbtjänst](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[Utvärdera Nätverksanslutningar för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Office 365 nätverks- och prestandajustering](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[Utvärdera Nätverksanslutningar för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Plan för prestandafelsökning för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan).

[Nätverk för innehållsleverans (CDN)](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Microsoft 365 anslutningstest](https://connectivity.office.com/)

[Hur Microsoft bygger ett snabbt och tillförlitligt globalt nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 Nätverksbloggen](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-anslutning för fjärran vändare via VPN-delning](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


