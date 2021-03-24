---
title: Resursplanering för Microsoft 365 Enterprise – Arkitektur för cybersäkerhet
description: Lär dig hur du övervinner säkerhetsutmaningar i Microsoft Enterprise-arkitekturen från Kozeta Garrett, Cybersecurity Architect på Microsoft.
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
ms.openlocfilehash: 7cd9098766024093a0b9fa2d6e95131bf13d09df
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052488"
---
# <a name="security-hurdles-you-can-sail-overone-architects-viewpoint"></a>Säkerhets hur du kan segla över – En arkitekts arkitektur

I den här artikeln beskriver [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect på Microsoft, de största säkerhetsutmaningarna hon stöter på i företagsorganisationer och rekommenderar metoder för att bli hotad över dessa hinder.

## <a name="about-the-author"></a>Om författaren

![Kozeta Garrett-foto](../media/solutions-architecture-center/kozeta-garrett-security.jpg)

I min roll som Cloud Security Architect har jag arbetat med flera organisationer för att tillhandahålla strategiska och tekniska råd som fokuserar på att utforma och implementera säkerhetsarkitektur för kunder som migrerar till Microsoft 365 och Azure, utveckla företagsäkerhetslösningar och bidra till att transformera säkerhetsarkitektur och kultur för företagets motståndskraft. Min upplevelse omfattar identifiering och svar av incidenter, analys av skadlig programvara, testning av programvara och rekommenderade förbättringar av IT-säkerhet och försvar. Jag känner starkt för inledande transformationer som leder till säkerhet som en möjliggörare för verksamheten, inklusive modernisering.

Det är mest tillfredsställande att se hur organisationer som har infört ett säkerhets moderniseringssen tänkesätt under de senaste åren har en stor position som gör att de kan fortsätta att fungera på ett säkert sätt, trots den senaste situationen med COVID-19. Tyvärr har dessa omständigheter också varit ett uppringningssamtal för vissa kunder, som inte var redo för det omedelbart behov. Många organisationer slutför de måste snabbt modernisera sin ackumulerade IT-säkerhetssituation och förbättra sin säkerhetssituation över natten så att de kan agera under dessa extremt ovanliga omständigheter.

Den goda nyheten är att Microsoft har tagit del av flera bra resurser för att hjälpa organisationer att snabbt bli bättre på säkerheten. Förutom de här resurserna vill jag dela med mig av de viktigaste utmaningarna som jag har stött på med kunder varje dag, i samband med att du kan segla över dessa hinder.

Jag bor för närvarande i Northern Virginia, nära vårt lands huvudstad, Washington DC. Jag älskar nästan alla former av utomhusaktiviteter och träningar, som att springer, vandra och bada. För att motarbeta dessa tycker jag om lika mycket matlagning, mat och resor.

## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Samarbeta med säkerhetsteamet från början av införandet av molnet

Till att börja med kan jag inte nog betona hur viktigt det är att teamen i organisationen koordinerar från början. Säkerhetsteam måste fasas ut som kritiska partner i de tidiga stegen av införande och utformning av molnet. Det innebär att få säkerhetsteam att bli redo för molnanvändningen, inte bara för de nya funktionerna i verksamheten (till exempel bra användarupplevelse från säkra mobila enheter, program med fullständiga funktioner eller att skapa värde på företagsdata utöver de begränsade funktionerna i e-post- och produktivitetsprogram) utan även att utnyttja funktionerna för lagring, AI och datoranalyser som hjälper dig att lösa nya och gamla säkerhetsutmaningar. Säkerhetsteam måste ingå i hanteringen av alla aspekter av skiftet, inklusive personer (kultur), processer (utbildning) och teknik för att lyckas. Det innebär också att investera i modernisering och kontinuerlig förbättring av Security Operations Center (SOC). Arbeta tillsammans för att justera din säkerhetsstrategi med dina affärsstrategier och miljötrender för att säkerställa att den digitala transformationen görs på ett säkert sätt. När detta görs bra utvecklar organisationer möjligheten att anpassa sig snabbare till förändringar, inklusive förändringar av företag, IT och säkerhet.

Där jag ser kunder resa över hinder mest är när det inte finns något verkligt samarbete mellan verksamheten och SOC-teamen. Medan operationsteamet trycks och får fullmakt med knappa tidsgränser för att använda molnet, är säkerhetsteamen inte alltid med tidigt i processen med att revidera och planera en omfattande säkerhetsstrategi. Det innebär att integrera olika molnkomponenter och komponenter på plats. Denna brist på samarbete kommer längre ned till olika grupper som verkar arbeta i silos för att implementera kontroller för specifika komponenter, vilket leder till ökad komplexitet i implementering, felsökning och integrering.

Kunder som seglar över dessa hinder har bra samarbeten mellan operationerna och styrningen och säkerhets- och riskhanteringsteamen för att modernisera säkerhetsstrategin och kraven för att skydda hybridmolnarbetsbelastningar. De laserfokuserade på de slutliga säkerhetsmålen och -resultaten – dataskydd och system och tjänsters tillgänglighet i enlighet med styrning av cybersäkerhet, risker och efterlevnadskrav. Dessa organisationer utvecklar tidiga samarbeten mellan operations- och governance-teamet och SOC, som är avgörande för sättet att utforma säkerhetsdesignen och som maximerar värdet på deras investeringar.

## <a name="build-a-modern-identity-based-security-perimeter"></a>Skapa en modern (identitetsbaserad) säkerhets perimeter

Därefter bör du använda en nollförtroendearkitektur . Det börjar med att skapa en modern, identitetsbaserad säkerhets perimeter. Utforma säkerhetsarkitekturen där varje åtkomstförsök, oavsett om det är lokala eller molnbaserade, hanteras som icke betrodda tills den verifierats – "lita aldrig på, verifiera alltid". Den här design metoden ökar inte bara säkerhet och produktivitet, utan gör också att användarna kan arbeta var som helst med valfri enhetstyp. De avancerade molnkontrollerna i Microsoft 365 hjälper dig att skydda användarnas identiteter och samtidigt kontrollera åtkomsten till värdefulla resurser baserat på användarrisknivå.

En rekommenderad konfiguration finns i [Identitets- och enhetsåtkomstkonfigurationer.](../security/defender-365-security/microsoft-365-policies-configurations.md)

## <a name="transition-security-controls-to-the-cloud"></a>Gå över säkerhetskontroller till molnet

Många säkerhetsteam använder fortfarande de traditionella säkerhets metodtipsen som skapats för en lokal värld, inklusive att underhålla en "nätverks perimetersäkerhet" och försöka "tvinga" de lokala säkerhetsverktygen och kontroller till molnlösningar. Sådana kontroller är inte utformade för molnet, är inaktiva och hindrar införandet av moderna molnfunktioner. Processer och verktyg som fungerar för en perimetersäkerhetsmetod för nätverket har visat sig vara ineffektiva, inbyggda för molnkapaciteten och tillåter inte att moderna och automatiserade säkerhetsfunktioner används.

Du kan segla över det här hinder genom att byta skyddsstrategier till moln hanterat skydd, automatiserad undersökning och åtgärd, automatiserad penntestning, Defender för Office 365 och incidentanalys. Kunder som använder moderna enhetshanteringslösningar har implementerat automatiserad hantering, standardiserad korrigering, antivirus, tillämpning av policy och programskydd på alla enheter (oavsett om det är en smartphone, personlig dator, bärbar dator eller surfplatta). På så sätt slipper du använda VPN, Microsoft System Center Configuration Manager (SCCM) och Active Directory-gruppprinciper. Detta, i kombination med villkorsstyrda åtkomstprinciper, ger kraftfull kontroll och insyn samt effektiviserad åtkomst till resurser oavsett var användarna arbetar.

## <a name="strive-for-best-together-security-tools"></a>Strävar efter "bästa tillsammans" säkerhetsverktyg

En annan hinder jag ser att kunder stöter på är att de tar det bästa av ras till säkerhetsverktygen. Att kontinuerligt lager av "bäst av ras"-punktlösningar för att tillgodose nya säkerhetsbehov orsakar att företagssäkerheten bryts. Även med de bästa miljön integreras inte verktygen i de flesta miljöer eftersom det blir för dyr och komplext. Det skapar i sin tur luckor i synligheten eftersom det finns fler varningar om triage än vad gruppen kan hantera. Att träna SecOps-teamet på nya verktyg blir också en konstant utmaning.

Den "enkla metoden är bättre" fungerar också för säkerheten. I stället för att gå efter "de bästa av rasverktyg" kan du segla över den här hindert genom att använda en strategi som är "bäst tillsammans" med verktyg som fungerar tillsammans som standard. Microsofts säkerhetsfunktioner skyddar hela organisationen med integrerat skydd mot hot som omfattar program, användare och moln. Integrering gör det möjligt för en organisation att vara mer flexibel och minska risken genom att begränsa attacker vid start och snabbt åtgärda attacker.

## <a name="balance-security-with-functionality"></a>Balansera säkerhet med funktioner

När jag har kommit från en lång bakgrund och erfarenhet inom cybersäkerhet brukar jag föredrar att börja med den säkraste konfigurationen direkt, så att organisationer kan slappna av säkerhetskonfigurationer baserat på deras drift- och säkerhetsbehov. Men det kan gå till ett högt pris på förlorade funktioner och en dålig användarupplevelse. Som många organisationer har lärt sig, och om säkerheten är för svår för användarna, kommer de att hitta ett sätt att komma runt dig, till exempel med hjälp av ohanterade molntjänster. Hur svårt det än är för mig att acceptera har jag kommit på att det måste göras en grundläggande funktionssäkerhetsbalans.

Organisationer som inser att användare ska göra allt som behövs för att få jobbet gjort bekräftar att skuggning av IT-besväret inte är värd att försöka. De känner igen att IT-anställda är de största medarbetarna när det gäller Shadow IT och användningen av icke-godkända SaaS-program för sitt jobb. De har flyttat sin strategi för att uppmuntra användningen (i stället för att dölja den) och fokuserat på att minska den exponering för risker som den kan skapa. Organisationens säkerhetsteam ser inte att allt blockeras, loggas och skickas via en omvänd proxy eller vpn. Dessa säkerhetsteam dubbeltrycker i stället på sitt arbete för att skydda värdefulla och känsliga data från att exponeras för fel parter eller skadliga program. De arbetar för att skydda dataintegriteten. De använder mer avancerade funktioner för molninformationsskydd, inklusive kryptering, säker multifaktorautentisering, automatiserad risk och efterlevnad samt CASB-funktioner (Cloud App Security Broker) samtidigt som de tillåter och även uppmuntrar skyddad delning över flera plattformar. De förvandlar skuggad IT till inspirerande kreativitet, produktivitet och samarbete, som gör att deras företag kan hålla sig kvar i konkurrenskraften.

## <a name="adopt-a-methodical-approach"></a>Använda en metodisk metod

De flesta av de utmaningar jag har erfarenhet av att implementera molnsäkerhet på olika organisationer, oavsett bransch, har varit mycket lika. För det första finns det gott om bra dokumentation om specifika funktioner, men det finns en nivå av förvirring på organisationsnivå om vad som gäller för dem, var säkerhetsfunktionerna överlappar varandra och hur funktioner ska integreras. Det finns också en nivå av osäkerhet om vilka säkerhetsfunktioner som är förkonfigurerade och som kräver konfiguration av organisationen. DESSUTOM har SOC-teamen tyvärr inte haft den fulla exponering, utbildning eller budgettilldelning som krävs för att förbereda den snabba molnövertagandet och digitala transformationen som deras organisationer redan har.

Microsoft har rensat dessa hinder genom att använda flera resurser som är avsedda att hjälpa dig att ta en metodisk metod för din säkerhetsstrategi och implementering.

|Resurs   |Mer information  |
|---------|---------|
|[Viktigaste åtgärderna för säkerhetsteam för att stödja arbete hemifrån](../security/top-security-tasks-for-remote-work.md)      | Om du plötsligt stöder en arbetsstyrka hemma i hemmet kan du använda den här artikeln för att snabbt öka säkerheten. Den innehåller de viktigaste rekommenderade uppgifterna baserat på din licensplan.    |
|[Microsoft 365 Security for Business Decisions Makers](../security/Microsoft-365-security-for-bdm.md)    | När du har tid för en mer omfattande plan innehåller den här artikeln rekommendationer som spänner över Microsoft 365, prioriterade efter attackytan. Det har även ett kalkylblad som du kan använda för att sortera på licensiering och område (till exempel identitet, skydd mot hot och övervakning).  |
|[Rekommendationer om Microsoft-säkerhetsarkitektur](/security/compass/compass)    | Om du är säkerhetsarkitekt ser du till att se säkerhetsrekommendationer ordnade efter gren, t.ex. identitet, nätverk och säkerhetsåtgärder.   |
|[Rekommendationer om Microsoft Security Operations](/security/compass/security-operations-videos-and-decks)|Lär dig mer om Microsofts rekommendationer för att konfigurera och köra ett Säkerhets operations Center (SOC) |
|[CiSO-workshoputbildning (Chief Information Security Officer)](/security/ciso-workshop/ciso-workshop)   | Om du inte har varit så bra med molnsäkerhet ska du inte missa den här serien med videor.        |
|[docs.security.com/security](/security/)    | Teknisk vägledning från Microsoft om säkerhetsstrategi och arkitektur.        |
| | |

Alla dessa resurser är avsedda att användas som en utgångspunkt och är anpassade för organisationens behov.