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
description: Fastställ datasekretessbestämmelser, relevanta scenarier, din beredskap och vilka typer av känslig information som finns i Din Microsoft 365-miljö.
ms.openlocfilehash: c5a1662f5e82c8b8b9439439df0ee369d45e7616
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931908"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Utvärdera datasekretessrisker och identifiera känsliga objekt med Microsoft 365

Att utvärdera de sekretessregler och risker som gäller för din organisation är ett viktigt första steg innan relaterade förbättringsåtgärder implementeras, inklusive sådana som kan uppnås med Microsoft 365-funktioner och -tjänster. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Potentiellt tillämpliga sekretessregler för data

En bra referens till det bredare ramverket för dataskyddsregler för datasekretess finns i [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) och serien med artiklar om dataskyddsförordningen [(GDPR),](../compliance/gdpr.md)samt annat material om bestämmelser som du kan omfattas av inom din bransch eller region.

### <a name="gdpr"></a>GDPR

GDPR, den mest kända och citerade av datasekretessreglerna, reglerar insamling, lagring, bearbetning och delning av personuppgifter som är relaterade till en identifierad eller identifierbar fysisk person som är bosatt i EU. 

Enligt GDPR, artikel 4: 

- "personuppgifter" avser all information som relaterar till en identifierad eller identifierbar fysisk person ('data subject'); En identifierbar fysisk person är en person som kan identifieras, direkt eller indirekt, särskilt med referens till en identifierare som ett namn, ett IDENTIFIKATIONSNUMMER, platsdata, en onlineidentifierare eller en eller flera faktorer som är specifika för den fysiska, genetiskta, mentala, ekonomiska, sociala eller sociala identiteten hos den naturliga personen.

### <a name="iso-27001"></a>ISO 27001

Att följa andra standarder som ISO 27001 har också känts igen av flera europeiska myndigheter som en giltig proxy av avsikter för personer, processer och teknikspektrum. De standarder som anges överlappar varandra och att påverkas av ISO-27001-drivna skyddsmetoder kan ses som proxy under vissa omständigheter.

### <a name="other-data-privacy-regulations"></a>Andra sekretessregler för data

Andra framträdande sekretessregler för data specificerar också krav för hantering av personuppgifter.

I USA omfattar dessa California Consumer Protection Act[(CCPA),](../compliance/ccpa-faq.md)HIPAA-HITECH (United States Health Care Privacy Act) och Graham Leach Bliley Act (GLBA). Ytterligare tillståndsspecifika bestämmelser är också på plats eller under utveckling. 

Runt om i världen kan ytterligare exempel vara Tysklands National GDPR Implementation Act (BDSG), Brazil Data Protection Act (LGPD) och många fler.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Mappning av regler till kategorier för teknisk kontroll i Microsoft 365

Många av de datasekretessrelaterade bestämmelser har överlappande krav, så du bör förstå vilka bestämmelser de omfattas av innan du utvecklar ett tekniskt kontrollschema. 

Den här tabellen innehåller utdrag från ett urval av sekretessregler för data för senare referens i artiklarna om den här övergripande lösningen. 

| Regel | Artikel/avsnitt | Utdrag | Tillämpliga kategorier för teknisk kontroll |
|:-------|:-----|:-------|:-------|
| GDPR | Artikel 5(1)(f) | Personuppgifter ska bearbetas på ett sätt som säkerställer tillräcklig säkerhet för personuppgifter, inklusive skydd mot obehörig eller olaglig bearbetning och mot oavsiktlig förlust, intrång eller skada, genom att använda lämpliga tekniska åtgärder eller organisationsåtgärder ('integritet och konfidentialitet').  |  (Alla) <br> Identitet <br> Enhet <br> Skydd mot hot <br> Skydda information <br> Reglera information <br> Upptäcka och agera |
|  | Artikel (32)(1)(a) | Med hänsyn till tillståndet, kostnaderna för implementering och typ, omfattning, sammanhang och syfte med bearbetningen samt risken för olika sannolikheter och allvarlighetsgrad för rättigheter och enkelhet för naturliga personer, ska kontrollanten och processorn implementera lämpliga tekniska och organisatoriska åtgärder för att säkerställa en säkerhetsnivå som är lämplig för risken , inklusive efter behov: (a) kryptering av personuppgifter. | Skydda information |
|  | Artikel (13)(2)(a) | "... När personuppgifter inhämtas ska den registeransvarige lämna in följande ytterligare information som behövs för att säkerställa en rättvis och transparent bearbetning: (a) den period då personuppgifterna ska lagras, eller, om det inte är möjligt, de villkor som används för att fastställa den perioden. | Reglera information |
|  | Artikel (15)(1)(e) | Den registrerade har rätt att från kontrollkontrollen bekräfta huruvida personuppgifter om honom eller henne behandlas och, om så är fallet, åtkomst till personuppgifter och följande information: (e) det finns rätt att begära från kontrollanten för att radera eller radera personliga data eller begränsning av bearbetning av personuppgifter om de data som är registrerade eller objekt för sådan bearbetning | Upptäcka och agera |
| LGPD | Artikel 46 | Bearbetande ombud ska vidta säkerhets-, tekniska och administrativa åtgärder som kan skydda personuppgifter från obehörig åtkomst och oavsiktliga eller olagliga situationer av typen intrång, intrång, kommunikation eller någon typ av olaglig bearbetning. | Skydda information <br> Reglera information <br> Upptäcka och agera|
|  | Artikel 48 | Kontrollanten måste kommunicera till den nationella myndighet och till den registrerade förekomsten av en säkerhetshändelse som kan skapa risk eller relevant skada för datapersonerna. | Upptäcka och agera |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementera tekniska säkerhetsåtgärder för att skydda mot obehörig åtkomst till elektronisk skyddad hälsoinformation som överförs via ett elektroniskt kommunikationsnätverk. | Skydda information |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementera en mekanism för att kryptera elektronisk skyddad hälsoinformation när det anses lämpligt. | Skydda information |
|  | 45 CFR 164.312(c)(2) | Implementera elektroniska mekanismer för att bekräfta att elektronisk skyddad hälsoinformation inte har ändrats eller destruerats på ett obehörigt sätt. | Reglera information |
|  | 45 CFR 164.316(b)(1)(i) | Om en åtgärd, aktivitet eller bedömning krävs av den här underdelen för att dokumenteras, ska du föra in ett skriftligt (som kan vara elektroniskt) register över åtgärden, aktiviteten eller utvärderingen | Reglera information |
|  | 45 CFR 164.316(b)(1)(ii) | Behålla den dokumentation som krävs i paragraf (b)(1) i det här avsnittet i sex år från datumet då den skapades eller det datum då den senast var i kraft, beroende på vilket som inträffar senare. | Reglera information |
|  | 45 C.F.R. 164,308(a)(1)(ii)(D) | Implementera procedurer för att regelbundet granska poster för informationssystems aktivitet, till exempel granskningsloggar, åtkomstrapporter och rapporter om säkerhetstillbud | Upptäcka och agera |
|  | 45 C.F.R. 164,308(a)(6)(ii) | Identifiera och svara på misstänkta eller kända säkerhetstillbud minimera, i den utsträckning som han eller hon kan göra skada av säkerhetstillbud som är kända för den täckta enheten eller affärsrelationen, och dokumentera säkerhetstillbud och deras resultat. | Upptäcka och agera |
|  | 45 C.F.R. 164,312(b) | Implementera maskinvara, programvara och procedurmekanismer som registrerar och undersöker aktivitet i informationssystem som innehåller eller använder elektronisk skyddad hälsoinformation. | Upptäcka och agera |
| CCPA | 1798.105(c) | Ett företag som får en verifierbar begäran från en konsument om att radera konsumentinformation enligt indelningen (a) i detta avsnitt ska radera konsumentinformationen från sina arkivhandlingar och hänvisa alla tjänsteleverantörer till att radera användarens personliga information från sina arkivhandlingar | Upptäcka och agera |
|  | 1798.105(d) | (undantag till 1798.105(c) <br> Ett företag eller en tjänstprovider har inte krav på sig att följa en konsument begäran om att radera konsumentinformation om det är nödvändigt för företaget eller tjänstprovider att bevara konsumentinformation för att: (se den nuvarande lagstiftningen för ytterligare information). | Upptäcka och agera |
|||||

>[!Important]
>Listan är inte uttömmande. Mer information [om hur](../compliance/compliance-manager.md) de citerade avsnitten kan tillämpas i de kategorier av teknisk kontroll som listas finns i efterlevnadshanteraren eller den juridiska rådgivaren eller efterlevnadsrådgivaren.
>

## <a name="knowing-your-data"></a>Känna till dina data

Oavsett vilka bestämmelser du omfattas av är alla viktiga faktorer som kan påverka din övergripande strategi för dataskydd, beroende på vilka bransch- och myndighetsföreskrifter som gäller för din organisation, när olika användardatatyper inom och utanför organisationen interagerar med era system. Det omfattar var personlig information lagras, vilken typ av information det är och hur mycket av det som finns och under vilka omständigheter de har samlats in.
 
![Att känna till dina data: Vilken typ är det, hur mycket av dem det finns och under vilka omständigheter de har samlats in](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Dataporterbarhet 

Data flyttas också med tiden när de bearbetas, förfinas och andra versioner härleds från den. En ursprunglig ögonblicksbild räcker aldrig. Det måste finnas en pågående process för att känna till dina data. Det representerar en av de största utmaningarna för stora organisationer som hanterar stora volymer personuppgifter. Organisationer som inte tar itu med problemet "känner till dina data" kan potentiellt hamna med mycket hög risk och eventuellt bot från regleringsbyråer.

![Datalivscykeln](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Var personliga data finns

När det gäller sekretessregler för data kan du inte förlita dig på allmänna skillnader i var du tror att personuppgifter kan finnas, antingen nu eller i framtiden. Enligt sekretessregler för datasekretess kan organisationer bevisa att de kontinuerligt vet var personuppgifter finns. Det gör det viktigt att ta en första ögonblicksbild av alla dina datakällor för möjlig lagring av personlig information, inklusive Microsoft 365-miljön, och skapa mekanismer för kontinuerlig övervakning och identifiering.

Om du inte redan har gjort en bedömning av din övergripande beredskap och risk i samband med datasekretessföreskrifter kan du komma igång genom att använda följande 3-stegs ramverk. 

![Åtgärder för att bedöma din övergripande beredskap och risker som är kopplade till sekretessregler för data](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Den här artikeln och dess innehåll är inte avsedda att i stället för juridiska rådgivningstjänster. Den innehåller bara grundläggande vägledning och länkar till verktyg som kan vara till hjälp i de tidiga stegen i utvärderingen.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Steg 1: Utveckla en grundläggande förståelse av organisationens personliga datascenarier 

Du måste mäta exponering av datasekretessrisker baserat på vilken typ av personuppgifter den hanterar för närvarande, var den lagras, vilka skyddskontroller som finns på den, hur livscykeln hanteras och vem som har åtkomst till den. 

Som en utgångspunkt är det viktigt att inventera vilka typer av personliga data som finns i din Microsoft 365-miljö. Använd följande kategorier:

- Information om de anställda som krävs för att utföra dagliga affärsfunktioner
- Data som organisationen har om sina företagskunder, partner och andra relationer i scenariot B2B (företag)
- Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i scenariot B2C (företag till kund)

Här är ett exempel på de olika typerna av data för typiska avdelningar i en organisation.

![Typer av personliga data](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

En stor del av de personuppgifter som omfattas av sekretessförordningen samlas vanligtvis in och lagras utanför Microsoft 365. Alla personliga data från webb- eller mobilprogram för konsumenter måste ha exporterats från sådana program till Microsoft 365 för att kunna granskas av datasekretess inom Microsoft 365. 

Din exponering av datasekretess i Microsoft 365 kan vara mer begränsad i förhållande till dina webbprogram och CRM-system, som denna lösning inte behandlar.

Det är också viktigt att tänka på följande vanliga utmaningar med datasekretessefterlevnad när du utvärderar din riskprofil:

 - **Distribution av personliga data.** Hur utspridd är information om ett visst ämne? Är det känt tillräckligt för att övertyga regelorganen om att det finns lämpliga kontroller? Kan den undersökas och åtgärdas vid behov?
- **Skyddar mot exfiltration.** Hur skyddar du personliga data av en viss typ eller källa från att avslöjas och hur du svarar om det var det?
- **Skydd kontra risk.** Vilka informationsskyddsmetoder är lämpliga i förhållande till risken och hur du bevarar affärskontinuiteten och produktiviteten och minimerar slutanvändarkontinuiteten om slutanvändaråtgärd krävs? Ska till exempel manuell klassificering eller kryptering användas?
- **Lagring av personuppgifter.** Hur länge behöver information som innehåller personuppgifter sparas av giltiga affärsorsaker och hur du kan undvika tidigare metodtips för evigheter, balanserade med bevarandebehov för affärskontinualitet?
- **Hanterar dataförfrågningar från registrerade angående data.** Vilka mekanismer kommer att behövas för att hantera dataförfrågningar (DSR:er) och eventuella åtgärdsåtgärder, till exempel anonymisering, redigering och borttagning?
- **Löpande övervakning och rapportering.** Vilken typ av teknik för dags övervakning, tidsrapportering och rapportering är tillgängliga för olika datatyper och källor?
- **Begränsningar i databearbetningen.** Finns det begränsningar för dataanvändning för information som samlas in eller lagras med de här metoderna som organisationen måste återspegla i sekretesskontroller? Till exempel kan åtaganden som personlig information inte kommer att användas av säljpersonal kräva att organisationen använder mekanismer för att förhindra överföring eller lagring av den informationen i system som är associerade med säljorganisationen.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Information om de anställda som krävs för att utföra dagliga affärsfunktioner

Organisationer behöver samla in data om anställda i elektroniskt identitets- och personalsyfte, enligt vad de samtycker till i sina anställningsavtal. Så länge en person arbetar för ett företag är detta vanligtvis inte ett problem. Organisationen kan vilja skapa mekanismer för att förhindra att skadliga aktör exfiltrerar eller läcker personliga data. 

Om en person lämnar ett företag har organisationer vanligtvis processer, procedurer och scheman för bevarande och borttagning för att ta bort användarkonton, inaktivera postlådor och personliga enheter och ändra status för anställda i till exempel personalsystem. I situationer där rättstvist ingår kan en anställd eller en annan part i en juridisk undersökning ha giltiga skäl till att skaffa information om personuppgifter som lagras i organisationens system. Ibland kan parten begära att sådana data tas bort eller anonymiseras. 

För att tillgodose sådana behov bör organisationer ha processer och procedurer som tillgodoser behovet av förebyggande, underhåll och åtgärder för att underlätta sådana förfrågningar, och se till att viss information om en anställd rimligen kan anses vara nödvändig för affärskontinuering. Till exempel information som en enskild person har skrivit en fil eller utfört en funktion. 

>[!Note]
>Vi rekommenderar att du tar del av teknikerna för övervakning och åtgärder för personuppgifter i Microsoft 365 i artikeln om att övervaka [och åtgärda.](information-protection-deploy-monitor-respond.md) Du kanske också vill använda automatiska klassificerings- och skyddsscheman för att se till att personliga data kontrolleras inom organisationen och förhindra att de lämnar organisationen i skadliga aktörssituationer. Mer information [finns i artikeln om att](information-protection-deploy-protect-information.md) skydda information.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Data som organisationen har om sina företagskunder i B2B-scenariot

Insamling av B2B-information är också en utmaning eftersom din organisation kan behöva föra register över kundnamn och transaktioner i sina olika system för affärskontinuisering och ändå skydda informationen från oavsiktlig eller skadlig exfiltrering. Liksom med data om anställda måste organisationer ha policyer, procedurer och tekniska kontroller för att skydda sådana data samt ålderskontrollerna enligt definierade scheman för bevarande och borttagning. 

Vanligtvis har avtal med externa kunder, partner och andra enheter som organisationen gör affärer med språk som hanterar sådana data, inklusive skydd, bevarande och borttagning både under och efter att entiteten har en relation med organisationen. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Data som organisationen har om konsumenter som tillhandahåller information till onlinetjänster som organisationen hanterar i B2C-scenariot

Den här kategorin är den som många tänker på när det gäller datasekretess, på grund av många offentliga förekomster av dataläckage. Detta kan vara avsiktligt, till exempel en tredje part som är kontraktslös till leverantören, eller oavsiktlig, till exempel exfiltrering av en skadlig aktör. Dataskydd är en av de primära anledningarna till att EU och andra har förtroende för dessa bestämmelser. Datasekretessregler som GDPR och CCPA kräver att du gör planering för:

- [Handlingsplaner och](../compliance/gdpr-action-plan.md) [checklista för att ta del av ansvaret](../compliance/gdpr-arc-office365.md)
- [Utvärderingar av dataskyddseffekter](../compliance/gdpr-data-protection-impact-assessments.md)
- [Meddelanden om intrång](../compliance/gdpr-breach-office365.md)
- [Begäranden från registrerad person](../compliance/gdpr-dsr-office365.md)

Om organisationen inte gör mycket direkt från konsumentdatainsamling kan den här kategorin vara mindre viktig. Du kan dock fortfarande behöva gå igenom processerna som beskrivs i dessa artiklar för att uppnå efterlevnad.

### <a name="step-1-summary"></a>Steg 1-sammanfattning

Att förstå exponeringen mot risker och regler om datasekretess är ett viktigt första steg som baseras på en grundläggande förståelse av organisationens personliga datascenarier.

Om du inte har personliga data från konsumenter i din Microsoft 365-miljö eller om den begränsas till vissa delar av miljön och det finns ett behov av teknisk kontroll där det finns exponering av data av konsumenttyp, kanske den tekniska kontrollen bara behöver användas i delar av miljön med hög risk, inte överallt.

Även om en extern organisation eller standardrekommendationer för kontroller, till exempel från Efterlevnadshanteraren i Microsoft 365, kan hjälpa dig att informera om din kontrollstrategi, bör ditt val av implementering drivs av information från datainventeringen för att mäta den verkliga risk exponeringen.

De flesta organisationer har en exponering för någon av ovanstående scenarier. Det är viktigt att ha en metod att göra bedömningar av den.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Steg 2: Utvärdera din beredskap för att följa sekretessregler för data

Även om frågorna är specifika för GDPR, ger frågorna i det kostnadsfria microsoft GDPR-utvärderingsverktyget en bra start på att förstå din övergripande beredskap för datasekretess. [](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) 

Organisationer som omfattas av andra bestämmelser om datasekretess, till exempel CCPA i USA eller Brasiliens LGPD, kan också ha nytta av det här verktygets lager av beredskap på grund av överlappande bestämmelser med GDPR.

GDPR-bedömning består av följande avsnitt:

| Avsnitt | Beskrivning |
|:-------|:-----|
| Styrning | <ol><li>Anger din sekretesspolicy uttryckligen vilken datainformation som bearbetas? </li><li>Kör du regelbundet utvärderingar av sekretesseffekter? </li><li> Använder du ett verktyg för att hantera personlig information (PI)? </li><li> Har du juridisk behörighet att göra affärer med PI-data för en viss person? Spårar du medgivande för data? </li><li> Spårar, implementerar och hanterar du granskningskontroller? Övervakar du dataläckor? </li></ol>|
| Borttagning och avisering | <ol><li>Ger du explicita instruktioner om hur användarnas data kan nås? </li><li> Har du dokumenterat processer för att hantera avanmälning från medgivande? </li><li> Har du en automatiserad borttagningsprocess för data? </li><li>   Har du en process för att verifiera identitet när du kontaktar en kund? </li></ol>|
| Åtgärder för risker och informationssäkerhet | <ol><li>Använder du verktyg för att söka igenom ostrukturerade data? </li><li>Är alla servrar uppdaterade och använder du brandväggar för att skydda dem? </li><li>Säkerhetskopiera servrarna regelbundet? </li><li>Övervakar du aktivt för dataläckor? </li><li>Krypterar du dina data vilan och överföringen? </li></ol>|
| Principhantering | <ol><li>Hur hanterar du dina bcr-regler (Binding Corporate Rules)? </li><li>Spårar du medgivande för data? </li><li> På en skala från 1 till 5 och 5 omfattas kontrakten helt och hållet av dataklassificering och hanteringskrav? </li><li>Har du och testar regelbundet en svarsplan för incidenter? </li><li>Vilken princip använder du för att hantera åtkomst? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Steg 3: Identifiera typer av känslig information som förekommer i Microsoft 365-miljön. 

I det här steget måste du identifiera vissa typer av känslig information som är föremål för särskilda regler och förekomster av dem i Microsoft 365-miljön. 

Att hitta innehåll i din miljö som innehåller personligt kan vara en överväldigande uppgift, tidigare med en kombination av att använda efterlevnadssökning, eDiscovery, Advanced eDiscovery, DLP och granskning. 

Med den nya lösningen för **dataklassificering** i administrationscentret för Microsofts efterlevnad har det blivit mycket enklare med funktionerna i Innehållsutforskaren, som fungerar med inbyggda eller anpassade typer av känslig information, inklusive sådana som är relaterade till personuppgifter. [](../compliance/data-classification-content-explorer.md)
 
### <a name="sensitive-information-types"></a>Typer av känslig information

Administrationscentret för Microsofts efterlevnad är förinstallerat med över 100 typer av känslig information, de flesta av dem relaterade till att identifiera och hitta personuppgifter. Dessa inbyggda typer av känslig information kan hjälpa till att identifiera och skydda kreditkortsnummer, bankkontonummer, passnummer och mer, baserat på mönster som definieras av ett reguljärt uttryck (regex) eller en funktion. Mer information finns i Vad [typer av känslig information letar efter.](../compliance/what-the-sensitive-information-types-look-for.md)

Om du behöver identifiera och skydda en organisationsspecifik eller regional typ av känsliga objekt, t.ex. ett anpassat format för anställnings-ID eller annan personlig information som inte redan omfattas av en inbyggd typ av känslig information, kan du skapa en anpassad typ av känslig information med följande metoder: 

- PowerShell
- Anpassade regler med exakt datamatchning (EDM)
- Via administrationsgränssnittet för efterlevnadscenter, som markerats [i artikeln Använd efterlevnadsresultat och efterlevnadshanteraren](information-protection-deploy-compliance.md)

Du kan också anpassa en befintlig, inbyggd typ av känslig information.

Mer information finns i följande artiklar:

- [Anpassa en inbyggd typ av känslig information](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Läs mer om typer av känslig information](../compliance/sensitive-information-type-learn-about.md)
- [Skapa en anpassad typ av känslig information i Säkerhets- & Efterlevnadscenter](../compliance/create-a-custom-sensitive-information-type.md)
- [Skapa en anpassad typ av känslig information i Security & Compliance Center PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Skapa anpassade typer av känslig information med exakt datamatchning baserad klassificering](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Innehållsutforskaren

Ett viktigt verktyg för att fastställa förekomsten av känsliga [](../compliance/data-classification-content-explorer.md) objekt i miljön är den nya Innehållsutforskaren i administrationscentret för Microsoft 365-efterlevnad. Det är ett automatiskt verktyg för första och pågående genomsökning av hela Microsoft 365-prenumerationen för förekomst av typer av känslig information och visning av resultaten.
 
Med det nya verktyget Innehållsutforskaren kan du snabbt identifiera platser för känsliga objekt i din miljö med hjälp av inbyggda typer av känslig information eller anpassade. Det kan innefatta att upprätta en process och tilldelas ansvar att regelbundet undersöka närvaro och plats för känsliga objekt.

Tillsammans med de andra steg som beskrivs i den här artikeln utgör detta en utgångspunkt för att identifiera den totala risk exponering, beredskap och plats för känsliga objekt för att skydda genom planerad konfiguration och övervakning av Microsoft 365. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andra metoder för att identifiera personuppgifter i din miljö

Förutom Innehållsutforskaren har organisationer tillgång till funktionen Innehållssökning för att skapa anpassade sökningar för att hitta personliga data i miljön, med hjälp av avancerade sökvillkor och anpassade filter.

Detaljerad information om hur du använder Innehållssökning för identifiering av personuppgifter finns i den [här artikeln.](../compliance/search-for-and-find-personal-data.md) Innehållssökning och andra identifieringstekniker utforskas också i [DSR-erna för GDPR och CCPA.](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs)

Ytterligare insikter om teknik för andning av personliga data i Microsoft 365 finns i artikeln om övervakning [och svar.](information-protection-deploy-monitor-respond.md)
