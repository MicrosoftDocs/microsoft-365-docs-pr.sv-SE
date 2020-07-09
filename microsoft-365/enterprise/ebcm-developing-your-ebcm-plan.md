---
title: Att tänka på för företagets affärskontinuitetsplan
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Saker du bör tänka på när du utvecklare en molnmedveten affärskontinuitetsplan.
ms.openlocfilehash: 35aa5fb74b8281a089ef0b58998cd297507cc46f
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083521"
---
# <a name="developing-your-continuity-plan"></a>Utveckla en kontinuitetsplan

I det här avsnittet får du information om hur du utvecklar en affärskontinuitetsplan som tar hänsyn till Microsoft 365-beroenden. Här rekommenderar vi metoder för att analysera dina företagsfunktioner och identifiera vilka som är beroende av Microsoft 365-tjänster. Du kommer att utföra den här analysen med bedömningen att det kommer att bli fel i tjänsten och att du måste förbereda för dessa eventualiteter.

Generellt sett omfattar affärskontinuitetsplanering fyra aspekter: bedömning, planering, funktionsvalidering samt kommunikation och samordning.

## <a name="assessment"></a>Bedömning
Du måste först identifiera företagsfunktionerna i organisationen och de tjänster och processer som stöder dem. Det här innefattar att göra en analys av påverkan på verksamheten, där varje företagsfunktion rangordnas enligt hur kritisk den är och du identifierar de processer och tjänster som varje funktion är beroende av. Här är en exempeltabell du kan använda för att komma igång med din egen bedömning.

**Exempel på BIA (Business Impact Assessment – bedömning av påverkan på verksamheten**

Det här är ett BIA-dokument för `name of the service, system, process, or function`

|BIA-fält|Beskrivning|
|---------|---------|
|BIA-typ|`is it a business process or technology, service or system?`|
|BIA-namn|`name of the service/system/function/process`|
|tjänstbeskrivning|`give a full description of the service, process, or function`|
|företagsfunktion|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|räkenskapsår|`the current fiscal year, re-evaluate these on a regular basis`|
|kritikalitet|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|affärsenhet|`name of the business unit that owns this business function`|
|process (tjänst, funktion)|`the name of the process, service, or feature`|
|chef för affärsgrupp|`the name and contact information of the senior leader of the business group that owns this business process`|
|Har tekniken ett upprättat **internt** SLA eller OLA?|`please explain in as much detail as possible`|
|Har tekniken ett upprättat **externt** SLA eller OLA?|`please explain in as much detail as possible`|
|Har tekniken ett känt exekutivt mandat som driver ett specifikt process-SLA? Om ja, beskriv i detalj.|`details here`|
|Kommer förlust eller komprometterande av data associerade med de här tjänsterna att utlösa en stor händelse? Om ja, beskriv i detalj.|`details here`|
|Har tjänsten en tillfällig lösning eller ett alternativt på plats för vissa eller alla av dess huvudfunktioner? Om ja, beskriv i detalj.|`details here`|
|Bearbetar, lagrar eller överför tjänsten kunddata, till exempel information som går att koppla till en specifik individ (PII)? Om ja, beskriv i detalj.|`details here`|
|BIA-status|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|slutförandedatum|`the date this BIA was completed`|
|BIA-samordnare|`name of the person or group who is responsible for developing and maintaining this BIA`|
|BIA-godkännande|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|medverkande|`optional list of the people who helped develop this BIA and their contact information`|
|BIA-godkännandeplats|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Planering

Titta nu på olika affärsprocesser för att se var det finns sammanhängande beroenderelationer. Utifrån resultatet gör du prioriteringar och utformar återhämtningsstrategier och standarddriftsprocedurer som stöder dina strategier.

Du kan använda [Tjänstkarta för Microsoft](https://docs.microsoft.com/azure/azure-monitor/insights/service-map) som hjälp med mappningen. Tjänstkarta för Microsoft identifierar automatiskt programkomponenter i Windows- och Linux-system och mappar alla TCP-beroenden, identifierar anslutningar och fjärrstyrda tredjepartssystem som appen är beroende av. Den mappar även beroenden till områden av nätverket som traditionellt är mörka, till exempel Active Directory.

Här är ett exempel på en beroendeanalys (DA – Dependency Analysis) du kan använda som utgångspunkt. I beroendeanalysen (DA) identifierar och undersöker du processberoenden. Se till att inkludera personer, leverantörer, kunder, samarbeten och anläggningar. Data från analysen används till att identifiera luckor mellan återställningskraven för en process och återställningsfunktionerna för stödjande beroenden.


|fält|beskrivning|
|---------|---------|
|processtyp|         |
|samordnare|         |
|slutfördes av|         |
|slutdatum|         |
|medverkande|         |
  
## <a name="capability-validation"></a>Funktionsvalidering

När du har inventerat dina affärsprocesser och kartlagt relationerna till andra processer och tekniker måste du skapa valideringsscenarier för alla processer. I princip ska du ta reda på hur du ska validera affärsprocessernas kontinuitetsplaner. Du kommer troligen finna att vissa är viktigare än andra och att du vill prioritera dem.
Kom ihåg att regelbunden utbildning av medarbetare om svar på incidenter och kontinuitetsåtgärder är viktigt när planen har upprättats. Granskningar efter incidenter ska användas för att förbättra återhämtningsstrategierna genom att lägga till information från varje validering eller test.

![funktionsvalidering visio](../media/ebcm/capability-validation-visio.png)

## <a name="incident-coordination-and-communication"></a>Samordning och kommunikation vid incidenter

Under en tjänstincident kan normala kommunikationskanaler vara påverkade eller försämrade, så du bör i förväg ordna med alternativ som hjälper organisationen att hålla kontakten vid en incident. Det är viktigt att kommunikationskanaler upprättas, testas för säkerhet och efterlevnad, och att användarna utbildas i användning innan störningarna sker. En övergång vid fel från ett känt tillstånd till ett annat känt tillstånd är mycket bättre jämfört med att användarna kommer på okända ad hoc-lösningar mitt i en kris.

På Microsoft har varje tjänstteam upprättat interna alternativa kommunikationskanaler som hjälper oss med samordningen när våra normala kommunikationskanaler inte är tillgängliga. Det är till exempel reservlösningar för telefoni och ljudkonferenser, Yammer-grupper, Teams-grupper, interna Service Health-instrumentpaneler och intern programvara för incidenthantering.

Under din BIA- och DA-analys mappar du kritiska processer och de tekniker eller tjänster de är beroende av. Ägna särskild uppmärksamhet åt kommunikationen under den här fasen av planeringen och fundera över alternativ. Här är några exempel.

- Om e-post är din primära metod för information till användare och intressenter, och e-posttjänsten är försämrad eller otillgänglig, till exempel Microsoft Teams, Yammer eller någon annan tredjepartstjänst som reserv. Nyckeln är att upprätta dem i förväg och informera användarna om vart de ska gå. En Yammer-tråd kommer inte att vara användbar om ingen vet att den finns eller om ingen har ett bokmärke för den.  
- Om dina interna processer för incidenthantering förlitar sig på röstkommunikation för att samordna svaren ska du upprätta en alternativ telefonilösning som används vid en kris. Lösningen behöver inte vara helt jämförbar med den primära tjänsten men ska tillhandahålla en minsta samarbetsnivå där det går att samordna affärskontinuitets- och incidenthanteringsteamen. Om du dessutom ber användarna att publicera sina mobiltelefonnummer i företagets globala adresslista kan det ge en ytterligare nivå av reservkommunikation i extrema fall.
- Det kan vara en bra idé at skapa en anpassad Service Health-instrumentpanel, eller någon annan liknande webbplats, som kan ge statusuppdateringar vid en incident. Att i förväg informera användare vart de ska gå för att få information minskar antalet onödiga samtal till supportavdelningen och gör användarna trygga i att situationen hanteras snabbt och effektivt. Använd O365 Service Communications API för väva in det här i M365 för att få en ännu högre synlighetsnivå.  
- Det är viktigt att platsen för affärskontinuitetsplaner och standarddriftsprocedurer är välkända. Vi rekommenderar att du har kopior online och offline av kritisk dokumentation, till exempel med SharePoint Online eller OneDrive för företag konfigurerat för automatisk synkronisering på lokala enheter. För tjänst-/nätverksdriftscenter och andra liknande team som är absolut kritiska för återställning kan det också vara en bra idé att ha papperskopior tillgängliga som kan användas vid nödläge.

## <a name="know-your-external-points-of-integration"></a>Känn till dina externa integreringspunkter

Oavsett affärsmodell har alla företag integreringspunkter med kunder, partners och leverantörer. Leveranskedjan för affärsvärden bygger på integrering med externa entiteter. En förbättring av affärskontinuiteten vid störningar i tjänsten kräver överväganden – och skydd – av varje integreringspunkt.  
När du analyserar din leveranskedja ska du tänka på extern kommunikation på samma sätt som intern kommunikation analyseras. Förlitar sig dina kunder på Exchange Online-servrar som enda metod att kontakta dig? Har du upprättat och gjort leverantörerna medvetna om alternativa kommunikationsmetoder, om drifttiden påverkas? Här är en exempeltabell som ger förslag på hur du kan organisera tänkandet.

|namn på extern entitet|scenario för påverkande incident|Integrerade Microsoft 365-tjänster|alternativ|
|---------|---------|---------|---------|
|`vendor name`|e-postflöde|Exchange Online är det enda kommunikationsmedlet med Contoso|konfigurera externa Microsoft Teams-kanaler eller samarbetsprogram från tredje part          |
|`service supplier name`|chatt|Microsoft Teams|snabbmeddelandefunktioner från tredje part|
|`partner name`|röstfunktioner|Microsoft Teams|mobil eller allmän pstn      |
|`supplier name`|fildelning|externt delade SharePoint-webbplatser och OneDrive|fildelning från tredje part         |
