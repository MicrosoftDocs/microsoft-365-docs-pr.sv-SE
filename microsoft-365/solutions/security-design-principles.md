---
title: Microsoft 365 Enterprise Resource Planning – Cybersecurity-arkitektur
description: Lär dig hur du kan lösa säkerhets problem i Microsofts företags arkitektur från Kozeta Garrett, Cybersecurity Architect på Microsoft.
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
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 454db3da5c37035cb3146e437761eff0f953b642
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906983"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Säkerhets avresedagen du kan Vinga – en arkitekts synvinklar

I den här artikeln, [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect på Microsoft, beskrivs de viktigaste säkerhets utmaningarna i företags organisationer och rekommenderar metoder för segling via dessa avresedagen. 

## <a name="about-the-author"></a>Om författaren

![Kozeta Garrett foto](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

Jag har arbetat med flera organisationer i min roll som moln skydd för att tillhandahålla strategisk och teknisk vägledning för att utforma och implementera säkerhets arkitektur för kunder som migrerar till Microsoft 365 och Azure, utvecklar företags säkerhetslösningar och hjälper till att omvandla säkerhets arkitektur och kultur för affärs återhämtning. Min upplevelse inkluderar identifiering och svar, skadlig program vara analys, trängande testning och rekommendationer för IT-säkerhet och försvar Posture. Jag är mycket starkt om att ge upphov till en säkerhet som rådgivare för verksamheten, till exempel Modernization.

Det är mest lämpligt att se hur organisationer som har antagit ett värdepapper Modernization Mindset under de senaste åren har en bra ställning som gör att de kan fortsätta att arbeta på ett säkert sätt, trots den senaste COVID-19-situationen. Dessa omständigheter har tyvärr också tagits med i ett nödsamtal för vissa kunder, vilka inte var klara för detta omedelbara behov. Många organisationer är egentliga att de måste modernisera snabbt, dra tillbaka sina obligationer och få sina säkerhets skulder till över natten så att de kan fungera under dessa yttersta sällsynta omständigheter.

De goda nyheterna är att Microsoft har undervisat några fantastiska resurser för att hjälpa organisationer att snabbt öka sin säkerhets Posture. Utöver de här resurserna skulle jag vilja dela de vanligaste utmaningarna som jag har stött på kunderna dagligen i tränaren som du kan använda för dessa avresedagen.

Jag bor för närvarande i norra Virginia, nära landets eget kapital, Washington DC. Jag älskar nästan alla former av aktiviteter på utomhus fot, som att köra, bikea, hiking och tala. För att få en titt på de här funktionerna är det bara att lyssna, gourmet mat och resa. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Partner med säkerhets gruppen från början av molnet

För att börja kan jag inte betona att det är viktigt för team i organisationen att koordineras från början. Säkerhets team måste förstås som kritiska partners i de tidiga faserna av moln antagande och design. Det innebär att du får till gång till mästare i molnet, inte bara för de extrafunktioner du har lagt till i företaget (till exempel en perfekt användar upplevelse från säkra mobila enheter, program för fullständig funktionalitet eller att skapa ett värde på företags data utöver de begränsade funktionerna för e-post och produktivitet), men även för att utnyttja de nya och gamla säkerhets utmaningarna. Säkerhets team måste inkluderas för att hantera alla aspekter av detta Skift, inklusive människor (kultur), processer (utbildning) och teknik. Det innebär också investeringar i Modernization och fort löp ande förbättring av säkerhets åtgärds Center (SOC). Samar beta för att justera din säkerhets strategi med företagets strategier och miljö trender för att säkerställa att den digitala omvandlingen görs säkert. När det är klart kan organisationer utveckla möjligheten att anpassa sig snabbare till ändringar, inklusive förändringar av verksamheten, IT och säkerhet. 

Där jag ser kund resa via avresedagen är det mest när det inte finns något särskilt partnerskap mellan operationerna och SOC Teams. Medan arbets gruppen håller på att tryckas och besvaras med tätt fastställda tids gränser för att kunna använda molnet, inkluderas inte alltid säkerhets teamen tidigt i processen för att omarbeta och planera en omfattande säkerhets strategi. Detta inbegriper integrering av olika moln komponenter samt komponenter på lokala. Detta kan leda till att det inte går att trickles till olika team som verkar fungera i silor för att implementera kontroller för sina specifika komponenter, vilket leder till ökad komplexitet vid implementering, fel sökning och integrering.

Kunder som seglar under dessa avresedagen har ett bra samarbete mellan driften och styrningen och teamerna för säkerhet och riskhantering för att ReVamp säkerhets strategin och kraven för att skydda hybrid moln arbets belastningar. De fokuserar på de ultimata säkerhets målen och resultaten — data skydd och system och tjänster i enlighet med Cybersecurity styrning, risker och efterlevnad. Dessa organisationer utvecklar tidiga samarbeten mellan sina verksamheter och styrelse grupper och SOC som är avgörande för säkerhets utformningen och kommer att maximera värdet på sina investeringar. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Skapa en modern (Identity-baserad) säkerhets perimeter

Därefter kan du använda en tom arkitektur metod. Detta börjar med att skapa en modern, identitetsbaserade säkerhetsperimeter. Designa säkerhets arkitekturen där alla åtkomst försök, oavsett om det är lokala eller molnet, behandlas som icke betrott tills den verifieras – "lita aldrig på, verifiera alltid". Den här designen ökar inte bara säkerheten och produktiviteten, men det gör det också möjligt för användare att arbeta var som helst med valfri enhets typ. De avancerade moln kontrollerna ingår i Microsoft 365 hjälper dig att skydda användarnas identiteter samtidigt som du kontrollerar åtkomsten till värdefulla resurser baserat på risk nivå.

Om du vill ha en rekommenderad konfiguration läser du [konfigurationer för identitets-och enhets åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md). 

## <a name="transition-security-controls-to-the-cloud"></a>Överföra säkerhets kontroller till molnet

Många säkerhets team använder fortfarande traditionell säkerhets metod som är byggd för en lokal värld, inklusive underhåll av en "nätverk för perimeter" och försöker "tvinga fram" säkerhets verktyg och-kontroller på lokala för moln lösningar. Sådana kontroller har inte utformats för molnet, är ineffektiva och hindrar införandet av moderna moln funktioner. Processer och verktyg som fungerar för en säkerhets metod för nätverks perimeter har visat sig vara ineffektivt, kan kringgå moln kapacitet och tillåter inte utnyttja moderna och automatiserade säkerhetsfunktioner.

Du kan använda den här hurdle genom att byta försvar till moln skydd, automatiserad undersökning och reparation, automatiserad penna – testning, Defender för Office 365 och incident analys. Kunder som använder moderna enhets hanterings lösningar har implementerat automatiserad hantering, standard korrigering, antivirus, principbaserad och program skydd på alla enheter (oavsett om det är en smartphone, persondator, bärbar dator eller surfplatta). Detta eliminerar behovet av en VPN-, Microsoft System Center Configuration Manager (SCCM) och Active Directory-grupprinciper. Det här kombinerat med principer för villkorsstyrd åtkomst ger till gång till effektiv kontroll och synlighet samt smidig åtkomst till resurser oavsett var deras användare arbetar.

## <a name="strive-for-best-together-security-tools"></a>Sträva efter ' Best interarbete '-säkerhets verktyg

En annan Hurdle jag ser att kundernas Stumble med är ett "bästa"-tillvägagångs sätt för säkerhets verktyg. För att adressera de nya säkerhets behoven fort löp ande lager med "bästa möjliga" Point-lösningarna kan du dela företags säkerheten. Till och med de bästa avsikterna är verktygen i de flesta miljöer inte integrerade eftersom det blir för dyrt och komplicerat. Detta skapar i sin tur luckor i synbarheten eftersom det finns fler aviseringar att postsortering än gruppen kan hantera. Att öva på SecOps-teamet på nya verktyg blir också en konstant utmaning.

"Enkel" bättre "-metoden fungerar också för säkerhet. I stället för att gå efter "det bästa med ras"-verktyg kan du Vinga över denna Hurdle genom att anta en "Best Inter"-strategi med verktyg som fungerar tillsammans. Microsofts säkerhets funktioner skyddar hela organisationen med integrerat hot-skydd som omfattar program, användare och moln. Integrering gör det möjligt för en organisation att bli mer flexibel och minska risken för attacker med attackerare vid inskrivning och snabb åtgärd.

## <a name="balance-security-with-functionality"></a>Säkerhet med funktioner

Eftersom jag kommer från en lång Cybersecurity bakgrund och upplevelse är det bara att börja använda den säkraste konfigurationen från lådan och låta organisationer minska säkerhets konfigurationerna baserat på deras drift-och säkerhets behov. Men det kan komma till mobilens pris av förlorade funktioner och dåligt användar upplevelse. Så många organisationer har lärt sig om säkerheten är för svår för användarna kan de hitta ett sätt att kringgå det och använda ohanterade moln tjänster. Det är svårt att acceptera, jag har kommit fram till att Delicate funktionalitet måste uppnås.

Organisationer som inser att användarna kan göra vad det tar att få sina jobb klara bekräftar att den "skuggade IT-kampen" inte är värt att bekämpa. De erkänner att den anställda är det största som är den mest felaktiga när den kommer att skugga den och använda icke godkända SaaS-program för deras jobb. De har förflyttat sin strategi för att uppmuntra dess användning (i stället för att undertryckas) och fokuserat på att minska riskerna med att kunna skapa det. De här organisationens säkerhets team måste inte allt som blockeras, loggats och skickas via en omvänd proxyserver eller ett VPN. I stället kan de här säkerhets teamen dubblera sina ansträngningar för att skydda värdefulla och känsliga data från att exponeras för fel parter eller skadliga appar. De kan skydda data integriteten. De utnyttjar en full användning av mer avancerade moln informations skydds funktioner, inklusive kryptering, säker multifaktorautentisering, automatisk risk-och efterlevnad samt Cloud App Security Broker (CASB)-funktioner samtidigt som du tillåter och även kan främja skyddad delning på flera plattformar. De vänder sig skuggan till inspirerande kreativitet, produktivitet och samarbete som gör det möjligt för företaget att fortsätta på konkurrens linjen.


## <a name="adopt-a-methodical-approach"></a>Anta ett metodiskt tillvägagångs sätt 

De flesta av de utmaningar jag har erfarenhet av att implementera moln säkerhet hos olika organisationer, oavsett bransch, är mycket likartade. Till och med att det finns massor av mycket bra dokumentation om specifika funktioner och funktioner finns det en nivå med förvirring på organisations nivå om vad som gäller för dem, där säkerhetsfunktioner överlappar och hur funktioner ska integreras. Det finns också osäkerhet för vilka säkerhetsfunktioner som kommer att förkonfigureras i den här rutan och som kräver konfiguration av organisationen. Dessutom har SOC Teams tyvärr inte haft fullständig exponering, utbildning eller budget tilldelning som behövs för att förbereda sig inför den snabba moln införandet och den digitala transformeringen har redan genomgått.

För att hjälpa dig att ta bort dessa avresedagen har Microsoft granskat flera resurser för att hjälpa dig att vidta ett metodiskt sätt för säkerhets strategin och implementeringen. 


|Resurspool   |Mer information  |
|---------|---------|
|[Viktigaste åtgärderna för säkerhetsteam för att stödja arbete hemifrån](../security/top-security-tasks-for-remote-work.md)      | Om du upptäcker att du plötsligt har stöd för en arbets styrka i hemmet kan du använda den här artikeln för att snabbt öka säkerheten. Den innehåller de vanligaste rekommenderade uppgifterna baserat på din licens plan.    |
|[Microsoft 365 säkerhet för företags besluts fattare](../security/Microsoft-365-security-for-bdm.md)    | När du har tid på en mer omfattande plan innehåller den här artikeln rekommendationer som omfattar Microsoft 365, som prioriteras av attack ytan. Det följer med ett kalkyl blad som du kan använda för att sortera efter licensiering och område (till exempel identitets-, hotets skydd och övervakning).  |
|[Microsoft Security Architecture-rekommendationer](https://docs.microsoft.com/security/compass/compass)    | Om du är en säkerhets arkitekt bör du se säkerhets rekommendationer ordnade efter disciplin, inklusive identitets-, nätverks-och säkerhets åtgärder.   |
|[Microsoft Security Operations-rekommendationer](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Lär dig hur du konfigurerar och kör ett säkerhets åtgärds Center (SOC) |
|[Säkerhets chef för CISO-chef](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Missa inte den här videon om du inte har använt moln säkerheten förut.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Teknisk vägledning från Microsoft för säkerhets strategi och-arkitektur.        |
| | |

Alla de här resurserna är avsedda att användas som utgångs punkt och anpassade efter organisationens behov. 

