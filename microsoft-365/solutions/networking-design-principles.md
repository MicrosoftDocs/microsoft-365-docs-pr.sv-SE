---
title: Nätverka upp (till molnet)– en arkitekts arkitektur
description: Lär dig hur du optimerar nätverket för molnanslutning genom att undvika de vanligaste fallgropar.
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
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904642"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Nätverka upp (till molnet)– en arkitekts arkitektur

I den här artikeln [beskriver Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect på Microsoft hur du optimerar nätverket för molnanslutning genom att undvika de vanligaste fallgropar. 

## <a name="about-the-author"></a>Om författaren

![Foto av Ed Fisher](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Jag är för närvarande en principal technical specialist i regionen Syd öst med fokus på säkerhet & efterlevnad. Jag har arbetat med kunder som flyttar över till Office 365 under de senaste 10 åren. Jag har arbetat med mindre verkstäder med några få platser för myndigheter och företag med miljontals användare som distribuerats över hela världen och många andra kunder däremellan, med majoriteten av de flesta med tusentals användare, flera platser i olika delar av världen, behovet av högre säkerhetsnivå och en mängd olika efterlevnadskrav. Jag har hjälpte hundratals företag och miljoner användare att flytta till molnet på ett säkert och säkert sätt.

Med en bakgrund under de senaste 25 åren som omfattar säkerhet, infrastruktur och nätverksteknik, och har flyttat två av mina tidigare arbetsgivare till Office 365 innan jag gick med i Microsoft, har jag gått med på din sida av tabellen många gånger och kommer ihåg hur det ser ut. Även om inga två kunder någonsin är desamma har de flesta liknande behov, och när de använder en standardiserad tjänst som någon SaaS- eller PaaS-plattform brukar de bästa metoderna vara desamma.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Det är inte nätverket – det är så du använder det!

Oavsett hur många gånger det händer misslyckas det aldrig  att förstå hur kreativa säkerhetsteam och nätverksteam försöker komma igång med hur de tror att de ska ansluta till Microsofts molntjänster. Det finns alltid en viss säkerhetspolicy, efterlevnadsstandard eller ett bättre sätt att använda den utan att vara beredd  att delta i en konversation om vad de försöker uppnå eller hur de är bättre, enklare, mer kostnadseffektiva och mer effektiva sätt att göra det.

När den här typen av saker eskaleras för mig går jag med på att ta utmaningen och gå igenom hur och varför de ska göra och ta dem dit de ska vara. Men om jag är helt frank måste jag dela det ibland med mig av att jag ibland bara vill låta dem göra vad de vill och komma tillbaka och säga att jag sade att det inte fungerar när de till sist sammanfogar det. Ibland vill jag kanske göra det, men det *gör jag inte.* Vad jag gör är att försöka förklara allt som jag kommer att inkludera i det här inlägget. Oavsett vilken roll du har kan det vara bra att ha nytta av Microsoft-molntjänster i organisationen. Det kan vara bra att göra det.

## <a name="guiding-principles"></a>Vägledande principer

Vi börjar med några grundregler kring det vi gör här. Vi diskuterar hur man ska ansluta säkert till molntjänster för att säkerställa minsta komplexitet och högsta prestanda, samtidigt som verklig säkerhet bibehålls. Inget av det som följer är mot något av det här, även om du eller din kund inte kan använda din favoritproxyserver för allt.

- **Bara för att du** kan det betyder inte det att du ska: Eller att omstava Dr. Ian The Jurassic Park-filmen "... Ja, ja, men säkerhetsteamet var så upptaget med om de kunde komma ihåg om de inte kunde tänka om de skulle göra det eller inte."
- **Säkerhet innebär inte komplexitet: Du** är inte säkrare bara för att du spenderar mer pengar, dirigerar via fler enheter eller klickar på fler knappar.
- **Office 365 är** åtkomet via Internet : Men det är inte samma sak som att Använda Office 365 på Internet. Det är en SaaS-tjänst som hanteras av Microsoft och hanteras av dig. Till skillnad från webbplatser du besöker på Internet får du i själva verket en översikt över hur programmet fungerar och kan tillämpa de kontroller som du behöver för att uppfylla dina policyer och efterlevnadsstandarder, så länge du förstår att även om du kan uppfylla dina mål, kanske du bara måste göra dem på ett annat sätt.
- Att ta fram en webbplats är en **dålig,** lokaliserad verksamhet är bra: Alla vill alltid ha tillbaka all Internettrafik för alla användare till en central punkt, vanligtvis så att de kan övervaka den och upprätthålla policyn, men ofta eftersom den antingen blir billigare än att tillhandahålla Internetåtkomst på alla deras platser, eller det är precis så de gör det. Men de där såddadepointerna är just det ... punkter där trafikstockningar. Det är inget fel med att hindra användarna från att bläddra till Eller strömma videoklipp på katter, men behandla inte verksamhetskritisk verksamhetstrafik på samma sätt.
- Om **DNS** inte är nöjd är du inte alls nöjd: Det bästa utformade nätverket kan ha en dålig DNS, oavsett om det är genom att återkommande förfrågningar till servrar i andra delar av världen eller genom att använda internetleverantörens DNS-servrar eller andra offentliga DNS-servrar som cachelagrar INFORMATION om DNS-upplösning.
- **Bara för att det** var så du brukade göra det betyder inte det att du ska göra det nu: Tekniken förändras hela tiden och Office 365 är inget undantag. Att tillämpa säkerhetsåtgärder som utvecklats och distribuerats för lokala tjänster eller för att kontrollera webbsurfning kommer inte att ge samma säkerhetsnivå och kan ha betydande negativ inverkan på prestanda.
- **Office 365 är byggt för** åtkomst via Internet – det är det i korthet. Oavsett vad du vill göra mellan dina användare och din kant går trafiken fortfarande över Internet när den lämnar ditt nätverk och innan den når vårt. Även om du använder Azure ExpressRoute för att dirigera viss latenskänslig trafik från ditt nätverk direkt till vårt, är Internetanslutning absolut nödvändigt. Acceptera det. Tänk inte över det.

## <a name="where-bad-choices-are-often-made"></a>Där dåliga val ofta görs

Det finns många platser där dåliga beslut fattas för säkerhetens namn, men det är de här som jag träffar oftast kunder på. Många kundkonversationer involverar alla dessa på en gång.

### <a name="insufficient-resources-at-the-edge"></a>Otillräckliga resurser vid kanten

Det är väldigt få kunder som distribuerar grönafältmiljöer och de har många års erfarenhet av hur deras användare arbetar och hur deras utgående Internet ser ut. Oavsett om kunder har proxyservrar eller tillåter direkt åtkomst och bara NAT utgående trafik så har de gjort det i många år och överväger inte hur mycket mer de kommer att börja förstå genom kanten när de flyttar vanliga interna program till molnet.

Bandbredd är alltid ett orosmoment, men NAT-enheter kanske inte har tillräckligt med hästkraft för att hantera den ökade belastningen och kan starta att anslutningar stängs tillfälligt för att frigöra resurser. De flesta klientprogram som ansluter till Office 365 förväntar sig beständiga anslutningar och en användare som använder Office 365 fullt ut kan ha 32 eller fler samtidiga anslutningar. Om NAT-enheten släpper dem på ett sätt som inte längre finns kan det hända att apparna slutar svara när de försöker använda anslutningarna som inte längre finns där. När de ger upp och försöker upprätta nya anslutningar lägger de ännu mer belastning på nätverksutrustningen.

### <a name="localized-breakout"></a>Lokaliserad breakout

Allt annat i den här listan handlar om en sak – att gå ur ditt nätverk och gå till vårt så snabbt som möjligt. Att backa upp användarnas trafik till en central punkt för utgående trafik, särskilt när den utgående punkten ligger i en annan region än de som användarna befinner sig i, introducerar onödig fördröjning och påverkar både klientupplevelsen och nedladdningshastigheten. Microsoft har närvaropunkter över hela världen med en frontend för alla våra tjänster och peering  upprättas med nästan alla större Internetleverantör, så att routning av användarnas trafik lokalt ser till att den snabbt når vårt nätverk med minsta möjliga fördröjning.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-lösningstrafiken ska följa den utgående internetsökvägen

För att en klient ska kunna hitta en slutpunkt måste den så klart använda DNS. Microsofts DNS-servrar utvärderar källan till DNS-begäranden för att säkerställa att vi returnerar det svar som, i Internettermer, ligger närmast källan för begäran. Kontrollera att DNS-posterna är konfigurerade så att namnmatchningsförfrågningar går ut på samma väg som användarnas trafik, så att du inte ger dem lokal utgång men till en slutpunkt i en annan region. Det innebär att låta lokala DNS-servrar "gå till roten" i stället för att vidarebefordra till DNS-servrar i fjärranslutna datacenter. Och se upp med offentliga och privata DNS-tjänster, som kan cachelagra resultat från en del av världen och ge dem till förfrågningar från andra delar av världen.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>För proxy eller inte till proxy, är det frågan

En av de första sakerna att tänka på är om du ska proxyanvändares anslutningar till Office 365. Det här är enkelt: proxy inte. Office 365 har åtkomst via Internet, men det är inte Internet. Det är en förlängning av dina kärntjänster och bör behandlas som sådana. Allt som du kanske vill att en proxyserver ska göra, till exempel DLP, programkontroll eller innehållsinspektion, är redan tillgängligt för dig i tjänsten och kan användas i skala och utan att behöva knäcka TLS-krypterade anslutningar. Men om du verkligen vill proxytrafik som du inte kan styra på annat sätt ska du vara uppmärksam på vår vägledning [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) för och trafikkategorierna på [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . Vi har tre trafikkategorier för Office 365. Optimera och Tillåt bör verkligen gå direkt och kringgå din proxy. Standardinställningen kan vara proxierad. Informationen finns i de här dokument ... läsa dem.

De flesta kunder som inte vill använda en proxyserver kommer till att inse att när klienten skickar en HTTP CONNECT-begäran till proxyn är proxyn nu bara en dyr extra router. Protokollen som används, till exempel MAPI och RTC, är inte ens protokoll som webbproxier förstår, så även om TLS knäckar får du inte riktigt någon extra säkerhet. Du  får extra fördröjning. Mer [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) information finns i kategorierna Optimera, Tillåt och Standard för Microsoft 365-trafik.

Slutligen bör du ta hänsyn till den övergripande påverkan på proxyn och dess motsvarande svar för att ta itu med den påverkan. När fler och fler anslutningar görs via proxyn kan den minska TCP-skalfaktorn så att den inte behöverbuffert så mycket trafik. Jag har sett kunder där deras proxy proxy är så överbelastade att de använde en Scale Factor på 0. Eftersom Scale Factor är ett exponentiellt värde och vi gärna använder 8, har varje minskning av Scale Factor-värdet stor negativ påverkan på dataflödet.

TLS-kontrollen betyder SÄKERHET! Men det är inte riktigt! Många kunder med proxy proxy vill använda dem för att kontrollera all trafik, vilket innebär att TLS "bryter och kontrollerar". Om du gör det för en webbplats som nås via HTTPS (problem med sekretess oavsett) kan din proxyserver behöva göra det för 10 eller till och med 20 samtidiga strömmar för några hundra millisekunder. Om en stor nedladdning eller en video involveras kan en eller flera av anslutningarna pågå mycket längre, men i stort sett upprättas, överförs och stängs de flesta av anslutningarna mycket snabbt. Om du bryter och kontrollerar innebär det att proxyn måste göra dubbelt så mycket arbete. För varje anslutning från klienten till proxyn måste proxyn även göra en separat anslutning tillbaka till slutpunkten. Så 1 blir 2, 2 blir 4, 32 blir 64 ...se var jag går? Du har antagligen storlek på din proxylösning för typisk webbsurfning, men när du försöker göra samma sak för klientanslutningar till Office 365 kan antalet samtidiga, långa anslutningar vara storleksorder större än vad du storleksanpassar för.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming är inte viktigt, förutom att *det är*

De enda tjänsterna i Office 365 som använder UDP är Skype (kommer snart att dras tillbaka) och Microsoft Teams. Teams använder UDP för direktuppspelningstrafik inklusive ljud-, video- och presentationsdelning. Direktuppspelning av trafik kan till exempel spelas upp direkt, till exempel om du har ett onlinemöte med röst, video och bildspel eller demonstrationer. De använder UDP eftersom paketen släpps, eller kommer ur ordning, blir det nästan omärkligt av användaren och strömmen kan bara fortsätta.

Om du inte tillåter utgående UDP-trafik från klienter till tjänsten kan de komma tillbaka till att använda TCP. Men om ett TCP-paket  släpps avbryts allt tills retransmission Timeout (RTO) går ut och det saknade paketet kan skickas på nytt. Om ett paket kommer ur ordning stannar allt tills andra paket anländer och kan sättas ihop i ordning. Båda leder till percepterbara störningar i ljudet (kommer ihåg Max Utrymme?) och video (klickade du på något ... oj, det finns det) och leder till dålig prestanda och en dålig användarupplevelse. Och kommer jag ihåg vad jag ställde upp ovan om proxy? När du tvingar en Teams-klient att använda en proxy tvingar du den att använda TCP. Så nu orsakar du negativ prestanda två gånger.

### <a name="split-tunneling-may-seem-scary"></a>Delade tunnlar kan verka obehagligt

Men det är det inte. Alla anslutningar till Office 365 finns via TLS. Vi erbjuder TLS 1.2 ganska länge och kommer snart att inaktivera äldre versioner eftersom äldre klienter fortfarande använder dem och det är en risk.

Att tvinga en TLS-anslutning, eller 32 av dem, att gå via en VPN innan de sedan går till tjänsten ger inte någon säkerhet. Det lägger till svarstid och minskar det totala dataflödet. I vissa VPN-lösningar tvingar den även UDP att tunnel genom TCP, vilket återigen kommer att ha mycket negativ påverkan på direktuppspelningstrafik. Och om du inte gör TLS-kontrollen finns det ingen upp och nedsida. Ett mycket vanligt tema bland kunder, nu när större delen av arbetsstyrkan är fjärransluten, är att de ser betydande bandbredd och prestandaeffekter från att göra så att alla användare ansluter med en VPN, i stället för att konfigurera delade tunnlar för åtkomst till optimera kategori [av Office 365-slutpunkter.](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)

Det är en enkel lösning att skapa delade tunnlar, och det är ett sätt att göra det. Läs mer i Optimera [Office 365-anslutningar för fjärranvändare med VPN-delade tunnlar.](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="the-sins-of-the-past"></a>Förfluten tid

Många gånger beror det på att det finns dåliga val från en kombination av (1) att du inte vet hur tjänsten fungerar, (2) att försöka följa företagets policyer som skrivits innan molnet införas, och (3) säkerhetsgrupper som kanske inte är lätt att övertyga om att det finns mer än ett sätt att uppnå sina mål. Förhoppningsvis hjälper ovanstående, och länkarna nedan, med den första. Sponsring från ledningen kan behövas för att komma förbi den andra. Att hantera målen för säkerhetsprinciperna i stället för deras metoder hjälper till med det tredje. Från villkorsstyrd åtkomst till innehållsmoderering, DLP till informationsskydd, slutpunktsverifiering till nolldagarshot – alla slutpunktsmål en rimlig säkerhetsprincip kan ha uppnås med vad som är tillgängligt i Office 365, och utan något beroende av lokal nätverksutrustning, tvingade VPN-tunnlar och TLS-avbrott och inspektera.

Andra gånger går det inte att skala maskinvara som var storleksänderad och införskaffad innan organisationen började flytta till molnet för att hantera de nya trafikmönstren och belastningen. Om du verkligen måste dirigera all trafik genom en enda utgående punkt och/eller proxy den, är du redo att uppgradera nätverksutrustning och bandbredd i enlighet med detta. Övervaka användningen noggrant för båda, eftersom upplevelsen inte minskar långsamt när fler användare börjar. Allt blir bra tills den lutande punkten nås, så alla får det här.

## <a name="exceptions-to-the-rules"></a>Undantag till reglerna

Om din [](/azure/active-directory/manage-apps/tenant-restrictions)organisation kräver begränsningar för klientorganisationen måste du använda en proxy med TLS-avbrott och inspektera för att tvinga fram viss trafik genom proxyn, men du behöver inte tvinga all trafik genom den.  Det är inte ett helt eller inget alls, så var uppmärksam på vad som behöver ändras av proxyn.

Om du tillåter delade tunnlar men också använder en proxy för allmän webbtrafik ska du se till att PAC-filen definierar vad som måste dirigeras samt hur du definierar intressant trafik för vad som går genom VPN-tunneln. Vi erbjuder exempel på PAC-filer [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) för att göra det lättare att hantera.

## <a name="conclusion"></a>Sammanfattning

Tusentals organisationer, inklusive nästan alla Fortune 500, använder Office 365 varje dag för sina verksamhetskritiska funktioner. Det gör de på ett säkert sätt och det gör de via Internet.

Oavsett vilka säkerhetsmål du har finns det olika sätt att uppnå dem som inte kräver VPN-anslutningar, proxyservrar, TLS bryter och inspekterar eller centraliserad utgående Internet för att få användarnas trafik från ditt nätverk och vidare till våra så snabbt som du kan, vilket ger bästa möjliga prestanda, oavsett om ditt nätverk är företagets huvudkontor eller ett fjärranslutet kontor eller så arbetar användaren hemma. Våra riktlinjer baseras på hur Office 365-tjänsterna byggs och för att säkerställa en säker och mer exakt användarupplevelse.

## <a name="further-reading"></a>Vidare läsning

[Principer för Office 365-nätverksanslutning](../enterprise/microsoft-365-network-connectivity-principles.md)

[URL-adresser och IP-adressintervall för Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Hantera Office 365-slutpunkter](../enterprise/managing-office-365-endpoints.md)

[Office 365 IP-adress och URL webbtjänst](../enterprise/microsoft-365-ip-web-service.md)

[Utvärdera Nätverksanslutningar för Office 365](../enterprise/assessing-network-connectivity.md)

[Office 365 nätverks- och prestandajustering](../enterprise/network-planning-and-performance.md)

[Utvärdera Nätverksanslutningar för Office 365](../enterprise/assessing-network-connectivity.md)

[Prestandajustering för Office 365 med baslinjer och prestandahistorik](../enterprise/performance-tuning-using-baselines-and-history.md)

[Plan för prestandafelsökning för Office 365](../enterprise/performance-troubleshooting-plan.md).

[Nätverk för innehållsleverans (CDN)](../enterprise/content-delivery-networks.md)

[Microsoft 365 anslutningstest](https://connectivity.office.com/)

[Hur Microsoft bygger ett snabbt och tillförlitligt globalt nätverk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 Nätverksbloggen](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-anslutning för fjärranvändare som använder VPN-delade tunnlar](../enterprise/microsoft-365-vpn-split-tunnel.md)