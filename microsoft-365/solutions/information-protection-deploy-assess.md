---
title: Utvärdera datasekretessrisker och identifiera känsliga objekt med Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Fastställ sekretessregler för data, relevanta scenarier, beredskap och typer av känslig information som finns i din Microsoft 365 miljö.
ms.openlocfilehash: 6801f0af70e08d2b4efdc9e27f1cb1f1d636b821
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929174"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Utvärdera datasekretessrisker och identifiera känsliga objekt med Microsoft 365

Att utvärdera de bestämmelser och risker för datasekretess som gäller för organisationen är ett viktigt första steg innan relaterade förbättringsåtgärder implementeras, inklusive sådana som kan uppnås Microsoft 365 funktioner och tjänster. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Potentiellt tillämpliga sekretessregler för data

En bra referens om det bredare ramverket för bestämmelser om datasekretess finns i [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) och en serie artiklar om dataskyddsförordningen [(GDPR)](/compliance/regulatory/gdpr)samt annat material om bestämmelser som du kan vara föremål för i din bransch eller region.

### <a name="gdpr"></a>GDPR

GDPR, den mest välkända och citerade av datasekretessförordningen, reglerar insamling, lagring, bearbetning och delning av alla personuppgifter som relaterar till en identifierad eller identifierbar fysisk person som är bosatt i Europeiska unionen (EU). 

Enligt GDPR, artikel 4: 

- "personuppgifter" avser all information som relaterar till en identifierad eller identifierbar naturlig person ('data subject'); En identifierbar fysisk person är en person som kan identifieras, direkt eller indirekt, särskilt genom referens till en identifierare som ett namn, ett identifikationsnummer, platsdata, en onlineidentifierare eller en eller flera faktorer som är specifika för den fysiska, genetiskt, mentala, ekonomiska, kulturella eller sociala identiteten hos den naturliga personen.

### <a name="iso-27001"></a>ISO 27001

Att följa andra standarder som ISO 27001 har också identifierats av flera europeiska övervakande myndigheter som en giltig proxy för allas användare, processer och teknikspektrum. De standarder som den anger överlappar och följer ISO-27001-drivna skyddsmetoder kan ses som proxy och vissa sekretessåtaganden under vissa omständigheter.

### <a name="other-data-privacy-regulations"></a>Andra sekretessregler för data

Andra framträdande bestämmelser om datasekretess anger också krav för hantering av personuppgifter.

I USA omfattar dessa California Consumer Protection Act[(CCPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (United States Health Care Privacy Act) och Graham Leach Bliley Act (GLBA). Ytterligare tillståndsspecifika bestämmelser är också på plats eller är under utveckling. 

Runt om i världen kan ytterligare exempel vara Tysklands National GDPR Implementation Act (BDSG), Brazil Data Protection Act (LGPD) och många fler.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Regelmappning till Microsoft 365 kategorier för teknisk kontroll

Många av de datasekretessrelaterade bestämmelser har överlappande krav, så du bör förstå vilka bestämmelser de omfattas av innan du utvecklar ett tekniskt kontrollschema. 

Den här tabellen innehåller utdrag från ett urval av sekretessregler för data för senare referens i artiklarna om den här övergripande lösningen. 

| Regler | Artikel/avsnitt | Utdrag | Tillämpliga kategorier för teknisk kontroll |
|:-------|:-----|:-------|:-------|
| GDPR | Artikel 5(1)(f) | Personuppgifter ska bearbetas på ett sätt som säkerställer tillräcklig säkerhet för personuppgifter, inklusive skydd mot obehörig eller olaglig bearbetning och mot oavsiktlig förlust, intrång eller skada, genom att använda lämpliga tekniska åtgärder eller organisationsåtgärder ('integritet och konfidentialitet'.  |  (Alla) <br> Identitet <br> Enhet <br> Skydd mot hot <br> Skydda information <br> Reglera information <br> Upptäcka och agera |
|  | Artikel (32)(1)(a) | Med hänsyn till grafikens status, kostnader för implementering och typ, omfattning, sammanhang och syftet med bearbetningen samt risken för olika sannolikheter och allvarlighetsgrad för rättigheter och funktionshinder för naturliga personer, ska kontrollanten och processorn implementera lämpliga tekniska och organisatoriska åtgärder för att säkerställa en säkerhetsnivå som är lämplig för risken , inklusive hur mycket som är lämpligt: (a) anonymisering och kryptering av personuppgifter. | Skydda information |
|  | Artikel (13)(2)(a) | "... den registeransvarige ska, vid den tidpunkt då personuppgifter inhämtas, ge registrerade uppgifter med följande ytterligare information som behövs för att säkerställa en rättvis och transparent bearbetning: (a) den period då personuppgifterna ska lagras, eller, om det inte är möjligt, de villkor som används för att fastställa den perioden. | Reglera information |
|  | Artikel (15)(1)(e) | Den registrerade har rätt att från kontrollanten bekräfta huruvida personuppgifter om honom eller henne bearbetas och, i sådana fall, åtkomst till personuppgifter och följande information: (e) det finns rätt att begära från kontrollanten för att radera eller radera personliga data eller begränsning av bearbetningen av personuppgifter om de data som är aktuella eller objekt för sådana data bearbetar | Upptäcka och agera |
| LGPD | Artikel 46 | Bearbetande ombud ska vidta säkerhets-, tekniska och administrativa åtgärder som kan skydda personuppgifter mot obehörig åtkomst och oavsiktliga eller olagliga situationer av intrång, förlust, ändring, kommunikation eller någon typ av obehörig behandling. | Skydda information <br> Reglera information <br> Upptäcka och agera|
|  | Artikel 48 | Kontrollanten måste informera den nationella behörigheten och till den registrerade om ett säkerhetstillbud som kan skapa risk eller relevant skada för datapersonerna. | Upptäcka och agera |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementera tekniska säkerhetsåtgärder för att skydda mot obehörig åtkomst till elektronisk skyddad hälsoinformation som skickas via ett elektroniskt kommunikationsnätverk. | Skydda information |
|  | 45 C.F.R. 164,312(e)(2)(ii) | Implementera en mekanism för att kryptera elektronisk skyddad hälsoinformation när det anses lämpligt. | Skydda information |
|  | 45 CFR 164.312(c)(2) | Implementera elektroniska mekanismer för att bekräfta att elektronisk skyddad hälsoinformation inte har ändrats eller destruerats på ett obehörigt sätt. | Reglera information |
|  | 45 CFR 164.316(b)(1)(i) | Om en åtgärd, aktivitet eller bedömning krävs av den här underdelen för att dokumenteras ska du föra ett skriftligt (som kan vara elektroniskt) register över åtgärden, aktiviteten eller utvärderingen | Reglera information |
|  | 45 CFR 164.316(b)(1)(ii) | Behåll den dokumentation som krävs enligt paragraf (b)(1) i det här avsnittet i sex år från datumet då den skapades eller datumet då den senast var i kraft, beroende på vilket som inträffar senare. | Reglera information |
|  | 45 C.F.R. 164,308(a)(1)(ii)(D) | Implementera procedurer för att regelbundet granska poster för informationssystems aktivitet, till exempel granskningsloggar, åtkomstrapporter och rapporter om säkerhetsincidenter | Upptäcka och agera |
|  | 45 C.F.R. 164,308(a)(6)(ii) | Identifiera och svara på misstänkta eller kända säkerhetsincidenter minimera, i den utsträckning som kan vara tillåtna, skadliga effekter av säkerhetstillbud som är kända för den täckta enheten eller affärsrelationen och dokumentera säkerhetstillbud och deras resultat. | Upptäcka och agera |
|  | 45 C.F.R. 164,312(b) | Implementera maskinvara, programvara och procedurmekanismer som registrerar och undersöker aktivitet i informationssystem som innehåller eller använder elektronisk skyddad hälsoinformation. | Upptäcka och agera |
| CCPA | 1798.105(c) | Ett företag som får en verifierbar begäran från en konsument om att radera en konsuments personliga information enligt indelningen (a) i detta avsnitt ska radera konsumentinformation från sina arkivhandlingar och hänvisa alla tjänsteleverantörer till att radera användarens personliga information från sina arkivhandlingar | Upptäcka och agera |
|  | 1798.105(d) | (undantag till 1798.105(c) <br> Ett företag eller en tjänsteleverantör har inte krav på sig att följa en konsument begäran om att radera konsumentinformation om det är nödvändigt för företaget eller tjänsteleverantören att upprätthålla konsumentinformation för att: (mer information finns i den aktuella lagstiftningen). | Upptäcka och agera |
|||||

>[!Important]
>Listan är inte uttömmande. Mer information [om tillämpligheten](../compliance/compliance-manager.md) i de citerade avsnitten i de angivna kategorierna för teknisk kontroll finns i Efterlevnadshanteraren eller den juridiska rådgivaren eller efterlevnadsrådgivaren.
>

## <a name="knowing-your-data"></a>Känna till dina data

Oavsett vilka bestämmelser du är beroende av, där olika användardatatyper inom och utanför organisationen interagerar med dina system, är alla viktiga faktorer som kan påverka din övergripande strategi för dataskydd, inom området för bransch- och myndighetsföreskrifter som gäller för din organisation. Det omfattar var personliga data lagras, vilken typ av data det är och hur mycket av dem det finns och under vilka omständigheter de har samlats in.
 
![Känna till dina data: Vilken typ av data är och hur mycket av dem det finns, och under vilka omständigheter de har samlats in](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Dataporterbarhet 

Data flyttas också över tiden när de bearbetas, förfinas och andra versioner härleds från den. En första ögonblicksbild räcker aldrig. Det måste finnas en pågående process för att känna till dina data. Det representerar en av de största utmaningarna för stora organisationer som hanterar stora mängder personlig information. Organisationer som inte tar itu med problemet "känner till dina data" kan potentiellt hamna med mycket hög risk och eventuellt bot från regleringsföretag.

![Datalivscykel](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Var dina personliga data finns

För att ta itu med sekretessregler för data kan du inte förlita dig på allmänna frågor om var du tror att personuppgifter kan finnas, antingen nu eller i framtiden. Sekretessregler för data kräver att organisationer bevisar att de kontinuerligt vet var personuppgifter finns. Det här gör det viktigt att ta en första ögonblicksbild av alla dina datakällor för möjlig lagring av personlig information, inklusive din Microsoft 365-miljö, och skapa mekanismer för kontinuerlig övervakning och identifiering.

Använd följande 3-stegsram för att komma igång om du inte redan har gjort en bedömning av din övergripande beredskap och risker som är kopplade till bestämmelser om datasekretess. 

![Steg för att bedöma din övergripande beredskap och risker i samband med sekretessregler för data](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Denna artikel och dess innehåll är inte avsedda att i stället för juridiska rådgivningstjänster. Den innehåller bara några grundläggande vägledning och länkar till verktyg som kan vara till hjälp i de tidiga stegen av utvärderingen.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Steg 1: Utveckla en grundförståelse av organisationens personliga datascenarier 

Du behöver mäta exponering av datasekretessrisker baserat på vilken typ av personuppgifter den hanterar för närvarande, var den lagras, vilka skyddskontroller som sätts på den, hur livscykeln hanteras och vem som har åtkomst till den. 

Som en utgångspunkt är det viktigt att inventera vilka typer av personlig information som finns i din Microsoft 365 miljö. Använd följande kategorier:

- Data om anställda som krävs för att utföra dagliga affärsfunktioner
- Data som organisationen har om sina företagskunder, partner och andra relationer i scenariot B2B (företag till företag)
- Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i scenariot företag till kund (B2C)

Här är ett exempel på de olika typerna av data för typiska avdelningar i en organisation.

![Typer av personliga data](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

En stor del av den personliga information som omfattas av sekretesskydd för data samlas vanligtvis in och lagras utanför Microsoft 365. All personlig information från webbprogram som tillhör konsumenter eller mobila program måste ha exporterats från sådana program till Microsoft 365 för att kunna bli granskad av datasekretess inom Microsoft 365. 

Exponering av datasekretess i Microsoft 365 kan vara mer begränsad i förhållande till dina webbprogram och CRM-system, vilket inte åtgärdas av den här lösningen.

Det är också viktigt att tänka på följande vanliga utmaningar med datasekretessefterlevnad när du utvärderar din riskprofil:

 - **Distribution av personliga data.** Hur utspritt är information om ett visst ämne? Är det känt att det är tillräckligt bra för att övertyga reglerande myndigheter att det finns rätt kontroller? Kan den undersökas och åtgärdas vid behov?
- **Skyddar mot exfiltrering.** Hur skyddar du personliga data av en viss typ eller källa från att komprometteras och hur du svarar om de var det?
- **Skydd kontra risk.** Vilka informationsskyddsmetoder är lämpliga i förhållande till risken och hur du bevarar affärskontinuiteten och produktiviteten och minimerar påverkan från slutanvändarna om det krävs åtgärder från slutanvändaren? Ska till exempel manuell klassificering eller kryptering användas?
- **Lagring av personliga data.** Hur länge måste information som innehåller personuppgifter sparas av giltiga affärsorsaker och hur du kan undvika en tidigare metod för evigheter, balanserad med bevarandebehov för affärskontinualitet?
- **Hantera förfrågningar från dataförfrågningar.** Vilka mekanismer kommer att behövas för att hantera DSR-begäranden (Data Subject Requests) och alla åtgärder, till exempel anonymisering, redaion och borttagning?
- **Löpande övervakning och rapportering.** Vilken typ av teknik för dagliga övervakning, tidpunkter och rapportering är tillgängliga för olika datatyper och källor?
- **Begränsningar i databearbetningen.** Finns det begränsningar för dataanvändning för information som samlas in eller lagras med de här metoderna som organisationen måste återspegla i sekretesskontroller? Till exempel kan åtaganden som personliga data inte kommer att användas av säljpersonal kräva att organisationen använder mekanismer för att förhindra överföring eller lagring av informationen i system som är associerade med säljorganisationen.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Data om anställda som krävs för att utföra dagliga affärsfunktioner

Organisationer måste samla in data om anställda i elektronisk identitet och personalsyfte, enligt vad de samtycker till i sina anställningsavtal. Så länge en person arbetar på ett företag är detta vanligtvis inte ett problem. Organisationen kan vilja införa mekanismer för att förhindra att skadliga aktör exfiltrerar eller läcker personaldata. 

Om en person lämnar ett företag har organisationer vanligtvis processer, procedurer och scheman för bevarande och borttagning för att ta bort användarkonton, inaktivera postlådor och personliga enheter och ändra status för anställda i till exempel personalsystem. I situationer där rättstvist ingår kan en anställd eller en annan part i en juridisk undersökning ha giltiga skäl till att skaffa information om personuppgifter som lagras i organisationens system. Under vissa tillfällen kan parten begära att sådana data tas bort eller anonymiseras. 

För att tillgodose sådana behov bör organisationer ha processer och procedurer som tillgodoser preventativa, administrativa och korrigerande behov för att underlätta sådana förfrågningar, och se till att viss information om en anställd rimligen kan anses vara viktig för affärskontinuering. Till exempel information som en enskild person har redigerat en fil eller utfört en funktion. 

>[!Note]
>Information om tekniker för att åtgärda personliga data i Microsoft 365 finns i [artikeln om att övervaka och åtgärda.](information-protection-deploy-monitor-respond.md) Du kanske även vill använda automatiska klassificerings- och skyddsscheman för att kontrollera att personuppgifter kontrolleras medan de finns i organisationen, samt förhindra att de lämnar organisationen i skadliga aktörssituationer. Mer information [finns i artikeln om](information-protection-deploy-protect-information.md) att skydda information.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Data som organisationen har om sina företagskunder i B2B-scenariot

Insamling av B2B-information är också en utmaning eftersom din organisation kan behöva föra register över kundnamn och transaktioner i sina olika system för affärskontinuisering och ändå skydda informationen från oavsiktlig eller skadlig exfiltrering. Liksom med anställdas data måste organisationer ha principer, procedurer och tekniska kontroller för att skydda sådana data och ålderskontroller i enlighet med definierade scheman för bevarande och borttagning. 

Vanligtvis har avtal med externa kunder, partner och andra enheter som organisationen gör affärer med språk för hantering av sådana data, inklusive skydd, lagring och borttagning både under och efter att entitet har en relation med organisationen. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i B2C-scenariot

Den här kategorin är den som många tänker på när det gäller datasekretess, på grund av många offentliga förekomster av läckage av kunddata. Detta kan vara avsiktligt, till exempel en tredje part som omfattas av kontrakt till leverantören, eller oavsiktlig, till exempel exfiltrering av en illvillig aktör. Konsumentdataskydd är en av de primära anledningarna till att EU och andra har antagit dessa bestämmelser. Sekretessregler som GDPR och CCPA kräver att du planerar för:

- [Handlingsplaner och](/compliance/regulatory/gdpr-action-plan) [checklista för beredskap med ansvarsberedskap](/compliance/regulatory/gdpr-arc-Office365)
- [Utvärdering av dataskyddseffekter](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Meddelanden om intrång](/compliance/regulatory/gdpr-breach-Office365)
- [Begäranden från registrerad person](/compliance/regulatory/gdpr-dsr-Office365)

Om organisationen inte använder så mycket insamling direkt från konsumentdata kan den här kategorin vara mindre av ett problem. Du kan dock fortfarande behöva gå igenom processerna som beskrivs i dessa artiklar för att uppnå efterlevnad.

### <a name="step-1-summary"></a>Steg 1-sammanfattning

Att förstå exponeringen mot risk- och datasekretess är ett viktigt första steg, baserat på en grundläggande förståelse av organisationens personliga datascenarier.

Om du inte har personuppgifter från konsumenter i din Microsoft 365-miljö eller den begränsas till vissa delar av miljön och det finns en teknisk kontroll som visar att det finns exponering av data av konsumenttyp, kanske den tekniska kontrollen bara behöver användas i delar av miljön med hög risk, inte överallt.

Även om en rekommendation för en extern organisation eller standardkontrolluppsättning, till exempel från Efterlevnadshanteraren i Microsoft 365, kan hjälpa dig att informera om din kontrollstrategi, bör ditt val av implementering drivs av information om datainventeringen för att mäta den verkliga risken.

De flesta organisationer kommer att ha en viss exponering för någon av ovanstående scenarier. Det är viktigt att ta en metod där det är viktigt att ha en metod att bedöma.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Steg 2: Utvärdera din beredskap att följa sekretessregler för data

Även om det är specifikt för GDPR, så är frågorna som det kostnadsfria Microsoft GDPR-utvärderingsverktyget ger en bra början på att förstå din övergripande beredskap med datasekretess. [](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) 

Organisationer som omfattas av andra bestämmelser om datasekretess, till exempel CCPA i USA eller Brasiliens LGPD, kan också dra nytta av det här verktygets lager av beredskap på grund av överlappande bestämmelser med GDPR.

GDPR-utvärdering består av följande avsnitt:

| Avsnitt | Beskrivning |
|:-------|:-----|
| Styrning | <ol><li>Anger din sekretesspolicy uttryckligen vilken datainformation som bearbetas? </li><li>Kör du regelbundet bedömningar av sekretesseffekter (PIAs)? </li><li> Använder du ett verktyg för att hantera personlig information (PI)? </li><li> Har du juridisk behörighet att göra affärer med PI-data för en enskild person? Spårar du medgivande för data? </li><li> Spårar, implementerar och hanterar du granskningskontroller? Övervakar du när data läcker ut? </li></ol>|
| Borttagning och avisering | <ol><li>Ger du explicita instruktioner om hur användarnas data kan nås? </li><li> Har du dokumenterat processer för hantering av avanmälning av medgivande? </li><li> Har du en automatiserad borttagningsprocess för data? </li><li>   Har du en process för att verifiera identitet när du kontaktar en kund? </li></ol>|
| Minskning av risker och informationssäkerhet | <ol><li>Använder du verktyg för att söka igenom ostrukturerade data? </li><li>Är alla servrar uppdaterade och använder du brandväggar för att skydda dem? </li><li>Säkerhetskopierar du servrarna regelbundet? </li><li>Övervakar du aktivt för att se om data läcker ut? </li><li>Krypterar du data vilan och vid överföring? </li></ol>|
| Principhantering | <ol><li>Hur hanterar du dina bindningsregler (BCR-regler)? </li><li>Spårar du medgivande för data? </li><li> Omfattar kontrakten dataklassificering och hanteringskrav från 1 till 5 och 5 är helt övertäckta? </li><li>Har du och regelbundet testar en svarsplan för incidenter? </li><li>Vilken princip använder du för att hantera åtkomst? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Steg 3: Identifiera typer av känslig information som förekommer i Microsoft 365 miljö. 

Det här steget omfattar identifiering av särskilda typer av känslig information som är föremål för särskilda regler och förekomst av dem i din Microsoft 365 miljö. 

Att hitta innehåll i din miljö som innehåller personligt kan vara en överväldigande uppgift, tidigare tillsammans med att använda efterlevnadssökning, eDiscovery, Advanced eDiscovery, DLP och granskning. 

Med den nya lösningen för **dataklassificering** i administrationscentret för [](../compliance/data-classification-content-explorer.md) Microsoft-efterlevnad har det blivit mycket enklare med funktionen Innehållsutforskaren, som fungerar med inbyggda eller anpassade typer av känslig information, inklusive sådana som rör personuppgifter.
 
### <a name="sensitive-information-types"></a>Typer av känslig information

Administrationscentret för Microsofts efterlevnad är förinstallerat med över 100 typer av känslig information och de flesta är relaterade till att identifiera och hitta personuppgifter. Dessa inbyggda typer av känslig information kan hjälpa till att identifiera och skydda kreditkortsnummer, bankkontonummer, passnummer med mera, baserat på mönster som definieras av ett reguljärt uttryck (regex) eller en funktion. Mer information finns i Vad [typer av känslig information letar efter.](../compliance/sensitive-information-type-entity-definitions.md)

Om du behöver identifiera och skydda en organisationsspecifik eller regional typ av känsliga objekt, till exempel ett anpassat format för anställnings-ID eller annan personlig information som inte redan omfattas av en inbyggd typ av känslig information, kan du skapa en anpassad typ av känslig information med följande metoder: 

- PowerShell
- Anpassade regler med exakta datamatchning (EDM)
- Via administrationsgränssnittet för efterlevnadscenter, som markerats i [artikeln Use Compliance Score and Compliance Manager](information-protection-deploy-compliance.md)

Du kan också anpassa en befintlig, inbyggd typ av känslig information.

Mer information finns i följande artiklar:

- [Anpassa en inbyggd typ av känslig information](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Mer information om typer av känslig information](../compliance/sensitive-information-type-learn-about.md)
- [Skapa en anpassad typ av känslig information i Säkerhets- & Säkerhets- och efterlevnadscenter](../compliance/create-a-custom-sensitive-information-type.md)
- [Skapa en anpassad typ av känslig information i Säkerhets- och efterlevnadscenter PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Skapa anpassade typer av känslig information med Exact Data Match-baserad klassificering](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Innehållsutforskaren

Ett viktigt verktyg för att fastställa förekomsten av känsliga [](../compliance/data-classification-content-explorer.md) objekt i din miljö är den nya Innehållsutforskaren i administrationscentret för Microsoft 365 efterlevnad. Det är ett automatiskt verktyg för första och pågående genomsökning av hela Microsoft 365-prenumerationen för förekomst av typer av känslig information och visning av resultaten.
 
Med det nya verktyget Innehållsutforskaren kan du snabbt identifiera platser för känsliga objekt i din miljö med hjälp av inbyggda typer av känslig information eller anpassade. Det kan innebära att upprätta en process och tilldelad ansvar att regelbundet undersöka närvaro och plats för känsliga objekt.

Tillsammans med de andra stegen som beskrivs i den här artikeln utgör detta en utgångspunkt för att identifiera den totala exponeringen, beredskapen och placeringen av känsliga objekt som ska skyddas genom planerad Microsoft 365 konfiguration och övervakning. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andra metoder för att identifiera personuppgifter i din miljö

Förutom Innehållsutforskaren har organisationer tillgång till funktionen Innehållssökning för att skapa anpassade sökningar för att hitta personliga data i miljön, med hjälp av avancerade sökvillkor och anpassade filter.

Detaljerade instruktioner om hur du använder innehållssökning för identifiering av personuppgifter finns i den [här artikeln.](/compliance/regulatory/gdpr) Innehållssökning och andra identifieringstekniker utforskas också i [DSR för GDPR och CCPA.](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs)

Ytterligare insikter om lösningar och tekniker för personliga data i Microsoft 365 finns i artikeln om övervakning [och svar.](information-protection-deploy-monitor-respond.md)

> [!NOTE]
> Information om hur du hittar känslig information i filer som lagras lokalt finns i [Azure Information Protection.](/azure/information-protection/quickstart-findsensitiveinfo)