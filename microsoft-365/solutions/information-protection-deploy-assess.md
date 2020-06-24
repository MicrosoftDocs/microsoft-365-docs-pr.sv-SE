---
title: Bedöma datasekretessrisker och identifiera känsliga objekt med Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Bestäm reglerna för datasekretess, relevanta scenarier, din beredskap och de känsliga informationstyper som finns i din Microsoft 365-miljö.
ms.openlocfilehash: f8d8fd0b5e6d8876dead566a50408cb2e7419386
ms.sourcegitcommit: 4512f54ba80d869d4c04e8f9bd897d1878280852
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "44854358"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Bedöma datasekretessrisker och identifiera känsliga objekt med Microsoft 365

Att bedöma de datasekretessbestämmelser och risker som din organisation omfattas av är ett viktigt första steg innan du implementerar relaterade förbättringsåtgärder, inklusive de som kan uppnås med Microsoft 365-funktioner och tjänster. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Potentiellt tillämpliga datasekretessbestämmelser

En bra referens på det bredare regelverket för datasekretessregler finns i [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) och [artikelserien om GDPR-förordningen (General Data Protection Regulation)](../compliance/gdpr.md)samt annat material om de regler som du kan omfattas av i din bransch eller region.

### <a name="gdpr"></a>GDPR

GDPR, den mest välkända och citerade av dataskyddsbestämmelserna, reglerar insamling, lagring, bearbetning och delning av personuppgifter som rör en identifierad eller identifierbar fysisk person som är bosatt i Europeiska unionen (EU). 

Enligt GDPR artikel 4: 

- personuppgifter: all information som rör en identifierad eller identifierbar fysisk person ("registrerad"). En identifierbar fysisk person är en person som direkt eller indirekt kan identifieras, särskilt med hänvisning till en identifierare, t.ex.

### <a name="iso-27001"></a>ISO 27001

Efterlevnad av andra standarder som ISO 27001 har också erkänts av flera europeiska tillsynsmyndigheter som en giltig fullmakt av uppsåt över människor, process och teknik spektrum. De standarder som anges överlappning och efterlevnad av ISO-27001-drivna skyddsmekanismer kan betraktas som en proxy som uppfyller vissa integritetsskyldigheter under vissa omständigheter.

### <a name="other-data-privacy-regulations"></a>Andra bestämmelser om datasekretess

Andra framstående datasekretessbestämmelser anger också krav för hantering av personuppgifter.

I USA, dessa inkluderar California Consumer Protection Act[(CCPA](../compliance/ccpa-faq.md)), HIPAA-HITECH (USA hälso-och sjukvård integritetslagen), och Graham Leach Bliley Act (GLBA). Ytterligare statliga bestämmelser finns också på plats eller under utveckling. 

Runt om i världen, ytterligare exempel inkluderar Tysklands nationella GDPR Implementation Act (BDSG), Brasilien Data Protection Act (LGPD), och många andra.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Regelmappning till microsoft 365 tekniska kontrollkategorier

Många av de dataskyddsrelaterade reglerna har överlappande krav, så du bör förstå vilka regler de omfattas av innan du utvecklar något tekniskt kontrollsystem. 

För senare referens i artiklarna i denna övergripande lösning, ger denna tabell utdrag från ett urval av datasekretessbestämmelser. 

| Förordning | Artikel/avsnitt | Utdrag | Tillämpliga tekniska kontrollkategorier |
|:-------|:-----|:-------|:-------|
| GDPR | Artikel 5.1 f | Personuppgifter ska behandlas på ett sätt som säkerställer lämplig säkerhet för personuppgifterna, inklusive skydd mot obehörig eller olaglig behandling och mot oavsiktlig förlust, förstörelse eller skada, med hjälp av lämpliga tekniska eller organisatoriska åtgärder ("integritet och sekretess".  |  -Jag är inte så bra som jag kan göra. <br> Identitet <br> Enhet <br> Skydd mot hot <br> Skydda information <br> Styr information <br> Upptäck och svara |
|  | Artikel 32.1 a | Med hänsyn till den senaste tekniken, kostnaderna för genomförandet och arten, omfattningen, sammanhanget och syftet med behandlingen samt risken för varierande sannolikhet och allvarlighetsgrad för fysiska personers fri- och rättigheter, ska den registeransvarige och bearbetningsföretaget vidta lämpliga tekniska och organisatoriska åtgärder för att säkerställa en säkerhetsnivå som är lämplig för risken. , bland annat i förekommande fall: a) pseudonymisering och kryptering av personuppgifter. | Skydda information |
|  | Artikel 13.2 a | "... Den registeransvarige ska vid den tidpunkt då personuppgifter erhålls förse den registrerade med följande ytterligare information som är nödvändig för att säkerställa en rättvis och öppen behandling: a) den period för vilken personuppgifterna kommer att lagras, eller om detta inte är möjligt, de kriterier som används för att fastställa denna period. | Styr information |
|  | Artikel 15.1 e | Den registrerade ska ha rätt att från den registeransvarige bekräfta om huruvida personuppgifter om honom eller henne behandlas eller inte, och om så är fallet, tillgång till personuppgifter och följande uppgifter: e) förekomsten av rätten att begära rättelse eller radering av personuppgifter eller begränsning av behandlingen av personuppgifter om den registrerade eller att invända mot sådan behandling | Upptäck och svara |
| LGPD (LGPD) | Artikel 46 | Behandlingsagenter ska vidta säkerhets-, tekniska och administrativa åtgärder som kan skydda personuppgifter från obehörig åtkomst och oavsiktlig eller olaglig förstörelse, förlust, ändring, kommunikation eller någon typ av felaktig eller olaglig behandling. | Skydda information <br> Styr information <br> Upptäck och svara|
|  | Artikel 48 | Den registeransvarige skall meddela den nationella myndigheten och den registrerade förekomsten av ett säkerhetstillbud som kan skapa risk eller relevant skada för de registrerade. | Upptäck och svara |
| HIPPA-HITECH | 45 CFR 164.312 e(1) | Vidta tekniska säkerhetsåtgärder för att skydda mot obehörig åtkomst till elektronisk skyddad hälsoinformation som överförs via ett elektroniskt kommunikationsnät. | Skydda information |
|  | 45 C.F.R. 164.312 e.2 ii | Införa en mekanism för att kryptera elektronisk skyddad hälsoinformation när det anses lämpligt. | Skydda information |
|  | 45 CFR 164.312 c(2) | Implementera elektroniska mekanismer för att bekräfta att elektronisk skyddad hälsoinformation inte har ändrats eller förstörts på ett otillåtet sätt. | Styr information |
|  | 45 CFR 164.316 b(1)i) | Om en åtgärd, verksamhet eller bedömning krävs av detta kapitel för att dokumenteras, föra en skriftlig (som kan vara elektronisk) register över åtgärden, verksamheten eller bedömningen | Styr information |
|  | 45 CFR 164.316 b(1)ii) | Behåll den dokumentation som krävs enligt punkt b.1 i detta avsnitt i sex år från den dag då den skapades eller det datum då den senast gällde, beroende på vilket som inträffar senare. | Styr information |
|  | 45 C.F.R. 164.308 a.1 ii(D) | Implementera procedurer för att regelbundet granska register över informationssystemaktivitet, till exempel granskningsloggar, åtkomstrapporter och rapporter för spårning av säkerhetsincidenter | Upptäck och svara |
|  | 45 C.F.R. 164.308 a.6 ii | Identifiera och reagera på misstänkta eller kända säkerhetsincidenter. i möjligaste mån mildra de skadliga effekterna av säkerhetsincidenter som är kända för den berörda enheten eller intresseföretag som omfattas, och dokumentera säkerhetsincidenter och deras resultat. | Upptäck och svara |
|  | 45 C.F.R. 164.312 b | Implementera maskinvaru-, programvaru- och procedurmekanismer som registrerar och undersöker aktivitet i informationssystem som innehåller eller använder elektronisk skyddad hälsoinformation. | Upptäck och svara |
| CCPA (på andra sätt) | 1798.105 c | Ett företag som tar emot en verifierbar begäran från en konsument om att radera konsumentens personuppgifter i enlighet med underavdelning (a) i detta avsnitt ska radera konsumentens personuppgifter från sina register och uppmana alla tjänsteleverantörer att radera konsumentens personuppgifter från sina register | Upptäck och svara |
|  | 1798.105 d | (undantag från 1798.105 c) <br> Ett företag eller en tjänsteleverantör ska inte vara skyldig att uppfylla en konsuments begäran om att radera konsumentens personuppgifter om det är nödvändigt för företags- eller tjänsteleverantören att upprätthålla konsumentens personuppgifter för att: (se gällande bestämmelser för ytterligare information). | Upptäck och svara |
|||||

>[!Important]
>Detta är inte avsett att vara en uttömmande förteckning. Se [Compliance Manager](../compliance/compliance-manager-overview.md) eller din juridiska rådgivare eller efterlevnadsrådgivare för ytterligare information om tillämpligheten av de angivna avsnitten till de listade tekniska kontrollkategorierna.
>

## <a name="knowing-your-data"></a>Känna till dina data

Oavsett vilka regler du omfattas av, där olika användardatatyper inom och utanför organisationen interagerar med dina system är alla viktiga faktorer som kan påverka din övergripande strategi för skydd av personuppgifter, med förbehåll för bransch- och myndighetsregler som gäller för din organisation. Detta inkluderar var personuppgifter lagras, vilken typ det är och hur mycket av dem som finns, och under vilka omständigheter de samlades in.
 
![Att veta dina data: Vilken typ det är, och hur mycket av det som finns, och under vilka omständigheter det samlades in](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Dataportabilitet 

Data flyttas också runt med tiden när de bearbetas, förfinas och andra versioner härleds från den. En första ögonblicksbild räcker aldrig. Det måste finnas en pågående process för att känna till dina data. Detta är en av de största utmaningarna för stora organisationer som hanterar betydande mängder personuppgifter. Organisationer som inte tar itu med "vet dina data" problemet kan potentiellt sluta med mycket hög risk och eventuella böter från tillsynsmyndigheter.

![Datalivscykeln](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Om personuppgifterna

För att ta itu med datasekretessbestämmelser kan du inte lita på allmänna föreställningar om var du tror att personuppgifter kan finnas, varken nu eller i framtiden. Regler för datasekretess kräver att organisationer visar att de vet var personuppgifterna är fortlöpna. Detta gör det viktigt att ta en första ögonblicksbild av alla dina datakällor för eventuell lagring av personlig information, inklusive din Microsoft 365-miljö, och upprätta mekanismer för kontinuerlig övervakning och identifiering.

Om du inte redan har bedömt din övergripande beredskap och risk i samband med datasekretessbestämmelser kan du använda följande 3-stegsramverk för att komma igång. 

>[!Note]
>Denna artikel och dess innehåll är inte avsedda att ta plats i juridisk rådgivning. Det ger bara några grundläggande vägledning och länkar till verktyg som kan vara till hjälp i ett tidigt skede av din bedömning.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Steg 1: Utveckla en grundläggande förståelse för organisationens personliga datascenarier 

Du måste mäta exponering för datasekretessrisk baserat på vilken typ av personuppgifter som den för närvarande hanterar, var de lagras, vilka skyddskontroller som placeras på den, hur dess livscykel hanteras och vem som har tillgång till dem. 

Som utgångspunkt är det viktigt att inventera vilka typer av personuppgifter som finns i din Microsoft 365-miljö. Använd dessa kategorier:

- Medarbetardata som krävs för att utföra dagliga affärsfunktioner
- Data som organisationen har om sina företagskunder, partners och andra relationer i B2B-scenariot (Business-to-Business)
- Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i B2C-scenariot (Business-to-customer)

Här är ett exempel på olika typer av data för typiska avdelningar i en organisation.

![Typer av personuppgifter](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

En stor del av de personuppgifter som omfattas av datasekretessförordningen samlas vanligtvis in och lagras utanför Microsoft 365. Alla personuppgifter från konsumentinriktade webb- eller mobilappar skulle behöva exporteras från sådana program till Microsoft 365 för att bli föremål för granskning av datasekretess inom Microsoft 365. 

Din datasekretessexponering i Microsoft 365 kan vara mer begränsad i förhållande till dina webbprogram och CRM-system, som den här lösningen inte tar upp.

Det är också viktigt att tänka på följande vanliga utmaningar för efterlevnad av datasekretess när du utvärderar din riskprofil:

 - **Spridning av personuppgifter.** Hur spridd är information om ett visst ämne? Är det känt tillräckligt väl för att övertyga tillsynsmyndigheter om att det finns ordentliga kontroller? Kan det undersökas och åtgärdas vid behov?
- **Skyddar mot exfiltration.** Hur skyddar du personuppgifter av en viss typ eller källa från att äventyras och hur man svarar om det var?
- **Skydd kontra risk.** Vilka mekanismer för informationsskydd är lämpliga i förhållande till risken och hur man upprätthåller kontinuitet och produktivitet och minimerar slutanvändarens påverkan om slutanvändarens ingripande krävs? Ska till exempel manuell klassificering eller kryptering användas?
- **Lagring av personuppgifter.** Hur länge behöver information som innehåller personuppgifter bevaras av giltiga affärsskäl och hur man undviker tidigare keep-it-forever-metoder, balanserade med lagringsbehov för kontinuitet i verksamheten?
- **Hantering av registrerade förfrågningar.** Vilka mekanismer kommer att behövas för att hantera registrerade förfrågningar (DSR) och eventuella avhjälpande åtgärder, till exempel anonymisering, bortredigeringsverktyg och radering?
- **Löpande övervakning och rapportering.** Vilken typ av daglig övervaknings-, utrednings- och rapporteringsteknik finns tillgänglig för de olika datatyperna och källorna?
- **Begränsningar av databehandling.** Finns det begränsningar för dataanvändning för information som samlas in eller lagras med hjälp av dessa metoder som organisationen måste återspegla i sekretesskontroller? Åtaganden om att personuppgifter inte kommer att användas av försäljningspersonal kan till exempel kräva att din organisation inför mekanismer för att förhindra överföring eller lagring av informationen i system som är associerade med försäljningsorganisationen.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Medarbetardata som krävs för att utföra dagliga affärsfunktioner

Organisationer av naturen måste samla in uppgifter om anställda för elektronisk identitet och HR-ändamål, med förbehåll för vad de samtycker till i sina anställningsavtal. Så länge en person arbetar för ett företag, är detta vanligtvis inte ett problem. Organisationen kanske vill införa mekanismer för att förhindra att skadliga aktörer exfiltration eller läckande anställdas personuppgifter. 

Om en person lämnar ett företag har organisationer vanligtvis processer, procedurer och bevarande- och borttagningsscheman för att ta bort användarkonton, inaktivera postlådor och personliga enheter och ändra medarbetarstatus i saker som personalsystem. I situationer där rättstvister är inblandade kan en anställd eller en annan part i en rättslig utredning ha giltiga skäl för att få information om personuppgifter som lagras i organisationens system. Vid vissa tillfällen kan den parten begära att sådana uppgifter tas bort eller anonymiseras. 

För att tillgodose sådana behov bör organisationer ha processer och procedurer på plats som tar itu med förebyggande, detektiv och korrigerande behov för att underlätta sådana förfrågningar, och notera att viss information om en anställd rimligen kan anses vara avgörande för affärskontinuiteten. Till exempel information som en person har skapat en fil eller utfört en funktion. 

>[!Note]
>För undersökande och reparationstekniker för personuppgifter i Microsoft 365, se [artikeln övervaka och svara .](information-protection-deploy-monitor-respond.md) Du kanske också vill använda automatiska klassificerings- och skyddssystem för att se till att personuppgifter kontrolleras när de är inne i organisationen, samt förhindra att de lämnar organisationen i situationer med illvilliga aktörer. Mer information finns i artikeln om [skyddsinformation.](information-protection-deploy-protect-information.md)
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Data som organisationen har om sina företagskunder i B2B-scenariot

Insamling av B2B-information är också en utmaning eftersom din organisation kan behöva föra register över kundnamn och transaktioner i sina olika system för kontinuitetsändamål men ändå skydda den informationen från oavsiktlig eller skadlig exfiltration. Precis som medarbetardata måste organisationer ha principer, procedurer och tekniska kontroller för att skydda sådana data, samt åldras enligt definierade lagrings- och borttagningsscheman. 

Vanligtvis har avtal med externa kunder, partner och andra entiteter som organisationen gör affärer språk som behandlar hanteringen av sådana data, inklusive skydd, lagring och borttagning både under och efter att entiteten har en relation med organisationen. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i B2C-scenariot

Denna kategori är den som de flesta människor tänker på för datasekretess, på grund av många offentliga fall av kunddataläckage. Detta kan vara avsiktligt, till exempel en tredje part som är kontrakterad till leverantören, eller oavsiktlig, till exempel exfiltration av en skadlig aktör. Konsumentskydd är en av de främsta anledningarna till att EU och andra har antagit dessa bestämmelser. Datasekretessregler som GDPR och CCPA kräver att du planerar för:

- [Handlingsplaner](../compliance/gdpr-action-plan.md) och [checklistor för ansvarsberedskap](../compliance/gdpr-arc-office365.md)
- [Konsekvensbedömningar av dataskydd](../compliance/gdpr-data-protection-impact-assessments.md)
- [Meddelanden om intrång](../compliance/gdpr-breach-office365.md)
- [Begäranden från registrerad person](../compliance/gdpr-dsr-office365.md)

Om din organisation inte gör en hel del direkt-från-konsument datainsamling, kan denna kategori vara mindre av ett problem. Du kan dock fortfarande behöva gå igenom de processer som beskrivs i dessa artiklar för att uppnå efterlevnad.

### <a name="step-1-summary"></a>Sammanfattning av steg 1

Att förstå din exponering för risk- och datasekretessreglering är ett viktigt första steg som baseras på en grundläggande förståelse av organisationens scenarier för personuppgifter.

Om du inte har personuppgifter från konsumenter i din Microsoft 365-miljö eller om de är begränsade till vissa delar av miljön och behovet av en teknisk kontroll bygger på att det finns dataexponering av konsumenttyp, behöver den tekniska kontrollen endast användas i delar av miljön med hög risk, inte överallt.

Även om en rekommendation om en extern organisation eller standardkontrolluppsättning, till exempel från efterlevnadspoäng i Microsoft 365, kan hjälpa dig att informera din kontrollstrategi, bör ditt val av implementering drivas av datainventeringsmedvetenhet för att kvantifiera din verkliga riskexponering.

De flesta organisationer kommer att ha viss exponering för ett av ovanstående scenarier. Att ta ett helhetsgrepp på bedömning är viktigt.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Steg 2: Bedöma din beredskap för att följa reglerna för datasekretess

Även om de är specifika för GDPR, ger de frågor som ställs i det kostnadsfria [verktyget för Microsoft GDPR-utvärdering](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) en bra start för att förstå din övergripande datasekretessberedskap. 

Organisationer som omfattas av andra datasekretessbestämmelser, till exempel CCPA i USA eller Brasiliens LGPD, kan också dra nytta av verktygets inventering av beredskap på grund av överlappande bestämmelser med GDPR.

GDPR-bedömning består av följande avsnitt:

| | |
|:-------|:-----|
| Styrning | <ol><li>Anger din sekretesspolicy uttryckligen vilken datainformation som behandlas? </li><li>Kör du regelbundet konsekvensbedömningar för sekretessen? </li><li> Använder du ett verktyg för att hantera personlig information (PI)? </li><li> Har du laglig rätt att bedriva verksamhet med hjälp av PI-data på en viss individ? Spårar du samtycke för data? </li><li> Spårar, implementerar och hanterar du granskningskontroller? Övervakar du dataläckage? </li></ol>|
| Borttagning och anmälan | <ol><li>Ger ni uttryckliga instruktioner om hur användarnas data kan nås? </li><li> Har du dokumenterade processer för att hantera opt out-samtycke? </li><li> Har du en automatisk raderingsprocess för data? </li><li>   Har du en process för att validera identitet när du samarbetar med en kund? </li></ol>|
| Riskreducering och informationssäkerhet | <ol><li>Använder du verktyg för att skanna ostrukturerade data? </li><li>Är alla servrar uppdaterade och utnyttjar du brandväggar för att skydda dem? </li><li>Kör du regelbundna säkerhetskopior av dina servrar? </li><li>Övervakar du aktivt dataläckage? </li><li>Krypterar du dina data i vila och i överföring? </li></ol>|
| Policyhantering | <ol><li>Hur hanterar du dina bindande företagsregler (BCRs)? </li><li>Spårar du samtycke för data? </li><li> Omfattar dina avtal dataklassificeringar och hanteringskrav på en skala från 1 till 5, 5 som omfattas helt och hållet? </li><li>Har du och regelbundet testa en incidentresponsplan? </li><li>Vilken princip använder du för att hantera åtkomst? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Steg 3: Identifiera känsliga informationstyper som förekommer i Microsoft 365-miljön. 

Det här steget innebär identifiering av särskilda typer av känslig information som är föremål för specifika regelkontroller samt förekomst av dem i din Microsoft 365-miljö. 

Att hitta innehåll i din miljö som innehåller personligt kan vara en formidabel uppgift, som tidigare omfattade en kombination av att använda efterlevnadssökning, eDiscovery, Advanced eDiscovery, DLP och granskning. 

Med den nya **dataklassificeringslösningen** i Microsoft Compliance-administrationscentret har detta blivit mycket enklare med [Content Explorer-funktionen,](../compliance/data-classification-content-explorer.md) som fungerar med antingen inbyggda eller anpassade känsliga informationstyper, inklusive de som är relaterade till personuppgifter.
 
### <a name="sensitive-information-types"></a>Typer av känslig information

Administrationscentret för Microsoft Compliance är förinstallerat med över 100 känsliga informationstyper, de flesta relaterade till att identifiera och hitta personuppgifter. Dessa inbyggda typer av känslig information kan hjälpa till att identifiera och skydda kreditkortsnummer, bankkontonummer, passnummer med mera, baserat på mönster som definieras av ett reguljärt uttryck (regex) eller en funktion. Mer information finns i [Vad de känsliga informationstyperna letar efter](../compliance/what-the-sensitive-information-types-look-for.md).

Om du behöver identifiera och skydda en organisationsspecifik eller regional typ av känsliga objekt, till exempel ett anpassat format för medarbetar-ID:er eller annan personlig information som inte redan omfattas av en inbyggd känslig informationstyp, kan du skapa en anpassad känslig informationstyp med följande metoder: 

- Powershell
- Anpassade regler med exakt datamatchning (EDM)
- Via administratörsgränssnittet för Efterlevnadscenter, vilket markeras i [artikeln Använd efterlevnadspoäng och efterlevnadshanteraren](information-protection-deploy-compliance.md)

Du kan också anpassa en befintlig, inbyggd känslig informationstyp.

Se dessa artiklar för mer information:

- [Anpassa en inbyggd typ av känslig information](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Vanliga typer av känslig information](../compliance/custom-sensitive-info-types.md)
- [Skapa en anpassad känslig informationstyp i Säkerhets- & Compliance Center](../compliance/create-a-custom-sensitive-information-type.md)
- [Skapa en anpassad känslig informationstyp i Security & Compliance Center PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Skapa anpassade känsliga informationstyper med exakt datamatchningsbaserad klassificering](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Innehållsutforskaren

Ett viktigt verktyg som för att fastställa förekomsten av känsliga objekt i din miljö är den nya [Content Explorer](../compliance/data-classification-content-explorer.md) i Microsoft 365 Compliance admin center. Det är ett automatiserat verktyg för inledande och pågående skanning av hela din Microsoft 365-prenumeration för förekomsten av känsliga informationstyper och visning av resultaten.
 
Med det nya content explorer-verktyget kan du snabbt identifiera platserna för känsliga objekt i din miljö, antingen med hjälp av inbyggda känsliga informationstyper eller anpassade. Detta kan innebära att man upprättar en process och tilldelade ansvar att regelbundet undersöka förekomsten och platsen för känsliga objekt.

Tillsammans med de andra stegen som markeras i den här artikeln är detta en utgångspunkt för att identifiera din totala riskexponering, beredskap och placering av känsliga objekt för att skydda genom planerad Konfiguration och övervakning av Microsoft 365. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andra metoder för att identifiera personuppgifter i din miljö

Förutom Innehållsutforskaren har organisationer tillgång till funktionen Innehållssökning för att skapa anpassade sökningar för att hitta personuppgifter i sin miljö, med hjälp av avancerade sökkriterier och anpassade filter.

Detaljerad vägledning om användningen av Content Search för upptäckt av personuppgifter finns i [den här artikeln](../compliance/search-for-and-find-personal-data.md). Innehållssökning och andra identifieringstekniker utforskas också i [DSR för GDPR och CCPA](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs).

Ytterligare insikter om utrednings- och reparationstekniker för personuppgifter i Microsoft 365 finns i [artikeln monitor och svara .](information-protection-deploy-monitor-respond.md)
