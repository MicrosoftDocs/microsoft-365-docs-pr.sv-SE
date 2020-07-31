---
title: Säkerhetshinder du kan segla över – En arkitekts synvinkel
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
ms.openlocfilehash: cdb6b557bf2f46a2338d929547167cf89a048695
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522283"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Säkerhetshinder du kan segla över – En arkitekts synvinkel

I den här artikeln beskriver [Kozeta Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/), Cybersecurity Architect på Microsoft, de största säkerhetsutmaningarna hon stöter på företagsföretag och rekommenderar metoder för att segla över dessa hinder. 

## <a name="about-the-author"></a>Om författaren

![Kozeta Garrett foto](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

I min roll som Cloud Security Architect har jag arbetat med flera organisationer för att ge strategisk och teknisk vägledning med fokus på att utforma och implementera säkerhetsarkitektur för kunder som migrerar till Microsoft 365 och Azure, utveckla företagssäkerhetslösningar och hjälpa till att omvandla säkerhetsarkitektur och kultur för affärsresiliens. Min erfarenhet omfattar incidentdetektering och svar, analys av skadlig kod, penetrationstester och erande förbättringar av IT-säkerhet och försvarshållning. Jag brinner mycket för att leda transformationer som resulterar i säkerhet som möjliggörare för verksamheten, inklusive moderniseringsinsatser.

Det har varit mest tillfredsställande att se hur organisationer som antagit en säkerhet modernisering tänkesätt under de senaste åren är i en bra position som gör det möjligt för dem att fortsätta att fungera på distans på ett säkert sätt, trots den senaste COVID-19 situation. Tyvärr har dessa omständigheter också fungerat som en väckarklocka för vissa kunder, som inte var redo för detta omedelbara behov. Många organisationer inser att de måste modernisera snabbt, gå i pension sina ackumulerade IT-säkerhet skuld, och förbättra sin säkerhet hållning över natten så att de kan fungera i dessa extremt ovanliga omständigheter.

Den goda nyheten är Microsoft har kurerat några stora resurser för att hjälpa organisationer snabbt ramp upp sin säkerhetsposition. Utöver dessa resurser, skulle jag vilja dela de största utmaningarna jag har stött på med kunder dagligen i hopp om att du kan segla över dessa hinder.

Jag bor för närvarande i norra Virginia, nära vårt lands huvudstad, Washington DC. Jag älskar nästan alla former av utomhusaktiviteter och motion, som löpning, cykling, vandring och simning. För att motverka dessa jag njuta av lika mycket matlagning, gourmetmat och resor. 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>Samarbeta med säkerhetsteamet från början av molnanvändning

Till att börja med kan jag inte nog betona hur viktigt det är för team i din organisation att samordna från början. Säkerhetsteam måste omfamnas som kritiska partner i ett tidigt skede av molnanvändning och design. Detta innebär att säkerhetsteam måste vara ombord för att kämpa för molnanvändning, inte bara för de extra funktionerna i företaget (till exempel en fantastisk användarupplevelse från säkra mobila enheter, fullständiga funktionsprogram eller att skapa värde på företagsdata utöver de begränsade e-post- och produktivitetsprogrammen) utan också för att utnyttja lagrings-, AI- och datoranalysfunktionerna som hjälper till att lösa nya och gamla säkerhetsutmaningar. Säkerhetsteam måste ingå i hanteringen av alla aspekter av denna förändring, inklusive människor (kultur), processer (utbildning) och teknik för att lyckas. Det innebär också att investera i modernisering och kontinuerlig förbättring av Security Operations Center (SOC). Arbeta tillsammans för att anpassa din säkerhetsstrategi till din affärsstrategi och miljötrender för att säkerställa att den digitala omvandlingen sker på ett säkert sätt. När detta görs på ett bra sätt utvecklar organisationer möjligheten att anpassa sig snabbare till förändringar, inklusive ändringar i verksamheten, IT och säkerhet. 

Där jag ser kunder snubbla över hinder mest är när det inte finns något verkligt partnerskap mellan verksamheten och SOC team. Medan driftteamet pressas och uppdrag med snäva tidsfrister för att anta molnet, är säkerhetsteamen inte alltid inkluderade tidigt i processen för att revidera och planera en omfattande säkerhetsstrategi. Detta innebär att integrera olika molnkomponenter samt komponenter på prem. Denna brist på partnerskap sipprar ytterligare ner till olika team som verkar arbeta i silor för att implementera kontroller för sina specifika komponenter, vilket leder till ökad komplexitet i implementering, felsökning och integration.

Kunder som seglar över dessa hinder har goda partnerskap mellan operations- och styrnings- och säkerhets- och riskhanteringsteamen för att förnya säkerhetsstrategin och kraven för att skydda hybridmolnarbetsbelastningar. De fokuserar på de slutliga säkerhetsmålen och resultaten – dataskydd och system och tjänster tillgänglighet i enlighet med cybersäkerhetsstyrning, risk och efterlevnadskrav. Dessa organisationer utvecklar tidiga partnerskap mellan deras operations- och styrningsteam och SOC som är avgörande för säkerhetsdesignmetoden och maximerar värdet av sina investeringar. 

## <a name="build-a-modern-identity-based-security-perimeter"></a>Skapa en modern (identitetsbaserad) säkerhetsperimeter

Anta sedan en Zero Trust-arkitekturmetod. Detta börjar med att bygga en modern, identitetsbaserad säkerhetsperimeter. Utforma säkerhetsarkitekturen där varje åtkomstförsök, oavsett om det är prem eller moln, behandlas som ej betrodd tills den har verifierats – "lita aldrig på, verifiera alltid". Den här designmetoden ökar inte bara säkerheten och produktiviteten, utan gör det också möjligt för användare att arbeta var som helst med vilken enhetstyp som helst. De sofistikerade molnkontrollerna som ingår i Microsoft 365 hjälper dig att skydda användarnas identiteter samtidigt som du kontrollerar åtkomsten till värdefulla resurser baserat på användarrisknivå.

En rekommenderad konfiguration finns i [Konfigurationer för identitet och enhetsåtkomst](../enterprise/microsoft-365-policies-configurations.md). 

## <a name="transition-security-controls-to-the-cloud"></a>Övergångssäkerhetskontroller till molnet

Många säkerhetsteam använder fortfarande de traditionella säkerhetstips som skapats för en all lokal värld, inklusive att upprätthålla en "nätverksperimetersäkerhet" och försöka "tvinga" säkerhetsverktygen och kontrollerna på för-prem till molnlösningar. Sådana kontroller har inte utformats för molnet, är ineffektiva och hindrar användningen av moderna molnfunktioner. Processer och verktyg som fungerar för en säkerhetsstrategi för nätverks perimeter har visat sig vara ineffektiva, hindrande av molnfunktioner och gör det inte möjligt att dra nytta av moderna och automatiserade säkerhetsfunktioner.

Du kan segla över detta hinder genom att flytta försvarsstrategierna till molnhanterad skydd, automatiserad undersökning och reparation, automatiserad penntestning, avancerat hotskydd och incidentanalys. Kunder som använder moderna enhetshanteringslösningar har implementerat automatiserad hantering, standardiserad korrigering, antivirus, policykontroll och programskydd på alla enheter (oavsett om det är en smartphone, en persondator, bärbar dator eller surfplatta). Detta eliminerar behovet av en VPN- Microsoft System Center Configuration Manager (SCCM) och Active Directory-gruppprinciper. Detta, i kombination med principer för villkorlig åtkomst, ger kraftfull kontroll och synlighet samt strömlinjeformad åtkomst till resurser oavsett var användarna arbetar från.

## <a name="strive-for-best-together-security-tools"></a>Sträva efter "bästa tillsammans" säkerhetsverktyg

Ett annat hinder jag ser kunder snubbla över tar en "best of breed" strategi för säkerhetsverktyg. Kontinuerligt skiktning "best of breed" punkt lösningar för att ta itu med nya säkerhetsbehov orsakar företagens säkerhet att brytas ned. Även med de bästa avsikter, verktyg i de flesta miljöer inte får integreras eftersom det blir för dyrt och komplicerat. Detta skapar i sin tur luckor i synligheten eftersom det finns fler varningar till triage än laget kan hantera. Omskolning secOps-teamet på nya verktyg blir också en ständig utmaning.

Den "enkla är bättre" strategi fungerar för säkerhet också. Istället för att gå efter "best of breed" verktyg, segla över detta hinder genom att anta en "bästa tillsammans" strategi med verktyg som fungerar tillsammans som standard. Microsofts säkerhetsfunktioner skyddar hela organisationen med integrerat hotskydd som omfattar program, användare och moln. Integrering gör det möjligt för en organisation att bli mer flexibel och minska risken genom att innehålla angripare vid inresa och snabbt åtgärda attacker.

## <a name="balance-security-with-functionality"></a>Balansera säkerhet med funktioner

Eftersom jag kommer från en lång cybersäkerhet bakgrund och erfarenhet, tenderar jag att föredra att börja med den säkraste konfigurationen ur lådan och låta organisationer att slappna av säkerhetskonfigurationer baserat på deras operativa och säkerhetsbehov. Detta kan dock komma till ett rejält pris av förlorad funktionalitet och dålig användarupplevelse. Som många organisationer har lärt sig, om säkerheten är för svårt för användare, kommer de att hitta ett sätt att komma runt dig, inklusive att använda ohanterade molntjänster. Så svårt som det är för mig att acceptera, har jag kommit att inse att den känsliga funktionalitet-säkerhet balans måste uppnås.

Organisationer som inser att användarna kommer att göra vad som krävs för att få sina jobb gjort erkänna att "Shadow IT slaget" är inte värt att slåss. De inser att IT-anställda är de största brottslingarna när det gäller Shadow IT och användningen av icke-godkända SaaS-ansökningar för sitt jobb. De har flyttat sin strategi för att uppmuntra dess användning (i stället för att undertrycka) och fokusera på att minska de risker exponering det kan skapa. Organisationens säkerhetsteam insisterar inte på att allt blockeras, loggas och skickas via en omvänd proxy eller en VPN. I stället fördubblar dessa säkerhetsteam sina ansträngningar för att skydda värdefulla och känsliga data från att utsättas för fel parter eller skadliga appar. De arbetar för att skydda dataintegriteten. De utnyttjar mer avancerade funktioner för skydd av molninformation, inklusive kryptering, säker multifaktorautentisering, automatiserad risk och efterlevnad och CASB-funktioner (Cloud App Security Broker) samtidigt som de möjliggör och till och med uppmuntrar den skyddade delningen mellan flera plattformar. De förvandlar skugg-IT till inspirerande kreativitet, produktivitet och samarbete som gör att deras verksamhet kan hålla sig på konkurrensfördelar.


## <a name="adopt-a-methodical-approach"></a>Anta ett metodiskt tillvägagångssätt 

De flesta av de utmaningar jag har upplevt med att implementera molnsäkerhet på olika organisationer, oavsett bransch, har varit mycket lika. För det första, medan det finns gott om bra dokumentation om specifika funktioner och funktioner, finns det en nivå av förvirring på organisationsnivå om vad som gäller för dem, där säkerhetsfunktioner överlappar varandra och hur funktioner ska integreras. Det finns också en grad av osäkerhet om vilka säkerhetsfunktioner som förkonfigureras ur lådan och som kräver konfiguration av organisationen. Dessutom har SOC-teamen tyvärr inte haft full exponering, utbildning eller budgettilldelning som behövs för att förbereda för den snabba molnanvändning och digitala omvandling som deras organisationer redan genomgår.

För att hjälpa dig att undanröja dessa hinder har Microsoft kurerat flera resurser som utformats för att hjälpa dig att ta en metodisk metod för din säkerhetsstrategi och implementering. 


|Resurs   |Mer information  |
|---------|---------|
|[Viktigaste åtgärderna för säkerhetsteam för att stödja arbete hemifrån](../security/top-security-tasks-for-remote-work.md)      | Om du befinner dig plötsligt stödja en mestadels arbete-at-home arbetskraft, hjälper den här artikeln dig ramp upp säkerheten snabbt. Den innehåller de vanligaste rekommenderade uppgifterna baserat på din licensplan.    |
|[Microsoft 365 Security for Business Beslutsfattare](../security/Microsoft-365-security-for-bdm.md)    | När du har tid för en mer omfattande plan innehåller den här artikeln rekommendationer som sträcker sig över Microsoft 365, som prioriteras av angreppsytan. Den levereras även med ett kalkylblad som du kan använda för att sortera på licensiering och område (till exempel identitet, skydd mot hot och övervakning).  |
|[Rekommendationer för Microsofts säkerhetsarkitektur](https://docs.microsoft.com/security/compass/compass)    | Om du är säkerhetsarkitekt måste du se säkerhetsrekommendationer som organiseras efter ämnesområde, inklusive identitets-, nätverks- och säkerhetsåtgärder.   |
|[Rekommendationer för Microsoft Security Operations](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|Lär dig Microsofts rekommendationer för att konfigurera och köra ett Security Operations Center (SOC) |
|[Workshop för informationssäkerhet (CISO)](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | Om du inte har gjort det tidigare till molnsäkerheten ska du inte missa den här videoserien.        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | Teknisk vägledning från hela Microsoft för säkerhetsstrategi och arkitektur.        |
| | |

Alla dessa resurser är utformade för att användas som utgångspunkt och anpassade för din organisations behov. 

