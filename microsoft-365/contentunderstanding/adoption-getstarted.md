---
title: 'Införande av Microsoft SharePoint Syntex: Komma igång'
description: Lär dig hur du använder och implementerar SharePoint Syntex i din organisation för att hjälpa dig att lösa dina företagsproblem.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597064"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Införande av Microsoft SharePoint Syntex: Komma igång

Tänk på att intelligenta innehållstjänster som finns i SharePoint Syntex har tre delar:

- **Innehållsförståelse:** Skapa AI-modeller utan kod för att klassificera och extrahera information från innehåll för att automatiskt tillämpa metadata för identifiering och återanvändning av kunskap. Läs mer om [innehållsförståelse.](document-understanding-overview.md)
- **Innehållsbearbetning:** Automatisera innehållsindelning, insamling och kategorisering av innehåll och effektivisera innehållscentrerade processer med Power Automate. Läs mer om [innehållsbearbetning.](form-processing-overview.md)
- **Efterlevnad av innehåll:** Kontrollera och hantera innehåll för att förbättra säkerhet och styrning med integrering med Microsoft Information Protection.

Med nya AI-tjänster och funktioner kan du skapa innehållsförståelse- och klassificeringsappar direkt i innehållshanteringsflödet med hjälp av SharePoint Syntex. Det finns två olika sätt att förstå innehållet. Vilken modelltyp du använder beror på filformat och användningsfall:

| Formulärbearbetning | Dokumentförståelse |
|:-------|:-------|
| Skapad från dokumentbibliotek. | Skapad i innehållscentret, en del av SharePoint Syntex. |
| Modell skapad i AI-verktyget. | Modell som skapats i gränssnittet. |
| Används för semistrukturerade filformat. | Används för ostrukturerade filformat. |
| Infogbar klassificerare. | Utbildare med valfria extraherare. |
| Begränsad till ett enskilt bibliotek. | Kan tillämpas på flera bibliotek. |
| Utbilda i PDF, JPG, PNG-format, totalt 50 MB/500 pp. | Utbilda dig på 5–10 PDF-, Office- eller e-postfiler, inklusive negativa exempel. |

En mer fullständig jämförelse av funktionerna finns i Skillnaden mellan [dokumentförståelse och modeller för formulärbearbetning.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifiera pilotföretagsscenarier för att optimera

För att förbereda dig för att använda SharePoint Syntex i organisationen måste du först förstå scenarier som kan vara användbara. "Varför" hjälper till att avgöra vilken modell som kommer att användas och hur du strukturerar din organisation baserat på var modellen ska användas. Här är några scenarier där dokumentförståelse kan hjälpa din organisation:

- **Innehållsbearbetning:** Bearbeta kontrakt, arbetssatser och andra formulärliknande dokument. Sammanställ formulären, utbilda modellen för att förstå och mappa fälten och kör sedan dina formulär för att automatiskt samla in data. Mer information finns i [formulärbearbetningsöversikten.](form-processing-overview.md)
- **Fakturaanalys:** Hämta relevant information från dina fakturor och kontrollera att de följer principen eller bearbetas på rätt sätt.

Tänk på olika sätt som SharePoint Syntex kan hjälpa din organisation:

- Automatisera affärsprocesser
- Förbättra sökprecisionen
- Hantera efterlevnadsrisker

När du funderar på vilka affärsscenarier du bör tänka på bör du ställa dig själv följande frågor:

- Löser det ett verkligt problem?
- Kommer den att användas ofta eller ha stor påverkan?
- Går det att skaffa?
- Kan du mäta framgången?

Prioritera scenarier baserat på påverkan och enkel implementering. Gör ditt första fokusområde mer effekt scenarier som också kan enkelt implementeras. Av prioritera scenarier med lägre effekt som är svåra att implementera.

Använd följande exempelscenarier för att visa en uppfattning om hur du kan använda SharePoint Syntex i organisationen.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: Spåra data från fakturor med formulärbearbetning

Du kan till exempel konfigurera en process med funktionerna SharePoint Syntex och Power Automate för att spåra och övervaka fakturor.

1. Konfigurera ett bibliotek för att lagra fakturadokumenten.
1. Utbilda modellen så att den känner igen fält i dokumenten.
1. Extrahera de fält du vill spåra till en lista.
1. Konfigurera ett flöde för att meddela dig om specifika händelser, till exempel:
    - En ny faktura läggs till.
    - En faktura går förbi förfallodatumet.
    - En faktura är för ett belopp som är större än ditt automatiska godkännandebelopp.

![Spåra och övervaka fakturor med SharePoint Syntex och Power Automate](../media/content-understanding/process-invoices-flow.png)

När du automatiserar det här scenariot kan du:

- Spara tid och pengar genom att automatiskt extrahera data från fakturor i stället för att göra det manuellt.
- Minska potentiella fel och säkerställ bättre efterlevnad genom att använda arbetsflöden för att kontrollera fakturor och meddela dig om eventuella problem.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: Spåra information från kontrakt med dokumentförståelse

Ett annat exempel är att skapa en process för att identifiera kontrakt som företaget har med andra företag eller enskilda personer. Konfigurera en modell för att extrahera viktig information från dessa kontrakt, till exempel kundnamn, avgifter, datum eller annan viktig information, och lägg till informationen i biblioteket som fält som du snabbt kan visa. Använd en bevarandeetikett på dokumentbiblioteket för att säkerställa att kontrakt inte kan tas bort innan en viss tid för att följa företagets bestämmelser.

1. Börja på innehållscentret och skapa en ny dokumentförståelsemodell för kontrakt.
1. Ladda upp exempeldokument för positiva och negativa exempel och kör sedan utbildningen för att identifiera kontraktsdokument och granska resultaten.
1. Utbilda extraheraren för att identifiera fält i kontrakten, till exempel kundnamn, avgift och datum, och testa sedan extraheraren.
1. När modellen är klar kan du använda modellen för ett bibliotek där du kan ladda upp kontrakt.
1. Använd en bevarandeetikett för datumfältet, så att kontrakten bevaras i biblioteket under den tid som krävs.

![Spåra och övervaka kontrakt med SharePoint Syntex och bevarandeetiketter](../media/content-understanding/process-contracts-flow.png)

När du automatiserar det här scenariot kan du:

- Spara tid och pengar genom att automatiskt extrahera data från kontrakten i stället för att göra dem manuellt.
- Säkerställ bättre efterlevnad genom att använda bevarandeetiketter för att säkerställa att kontrakten bevaras på ett lämpligt sätt.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: Undvik risker med hantering av arkivhandlingar, dokumentstyrning och efterlevnadsprocesser baserade på SharePoint Syntex

Att minska risker är ett vanligt mål för de flesta företag. Du kan behöva:

- Ett bättre sätt att tillhandahålla/tillämpa informationsstyrning i klientorganisationen.
- För att förbättra systemet för klassificering av dokument, e-postmeddelanden och andra kommunikationssätt som anses vara "arkivhandlingar" för projekt.
- För att granska kvitton, kontrakt och så vidare, för att säkerställa att företagets policyer följs.
- För att säkerställa att projekt har all dokumentation som krävs för efterlevnad.

Konfigurera vissa processer för efterlevnad med SharePoint Syntex för att registrera och klassificera, granska och flagga dokument och formulär som behöver bättre styrning. Du kan förlita dig på att SharePoint Syntex automatiskt klassificerar innehåll i stället för att förlita sig på att slutanvändarna taggas manuellt, eller att efterlevnadsteamet manuellt tillämpar styrningsregler och arkivering. Du kan också möjliggör en förenklad sökupplevelse, hantera datavolymer, tillämpa principer för hantering av arkivhandlingar och kvarhållningsprinciper, säkerställa efterlevnad och bästa praxis för arkivering och rensning.

När du automatiserar det här scenariot kan du känna dig säker på att:

- Efterlevnad upprätthålls och risken minskar.
- Taxonomi och hantering av arkivhandlingar tillämpas konsekvent och korrekt.
- Innehållsvolymerna kontrolleras.
- Anställda kan enkelt hitta rätt information i rätt sammanhang.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: Hämta information från dokument som tidigare inte var tillgängliga

De flesta organisationer har stora lagringsplatsen för juridiska dokument, principer, kontrakt, HR-dokument och riktlinjer för styrning. Mina dessa datakällor för att extrahera värdefull information, t.ex. projekt, tidefrågor, personer, geografiska områden och så vidare.

En HR-chef behöver till exempel snabb åtkomst till alla HR-dokument – inklusive meritförteckningar, HR-policyer och andra formulär. Och de vill snabbt kunna identifiera nödvändig information från meritförteckningar och andra HR-relaterade dokument utan att manuellt bläddra igenom dokumenten. De letar efter en lösning som gör att de snabbt kan hitta den information de behöver utan att manuellt behöva gå igenom tusentals meritförteckningar, HR-policyer och annan dokumentation som kan spridas på flera webbplatser.

När du automatiserar det här scenariot kan du:

- Lås upp kunskap från digitalt innehåll.
- Klassificera HR-principer, meritförteckningar, säljdokument, tekniska ritningar, kontoplaner och extrahera information.
- Hitta snabbt rätt information eller dokument som du letar efter.
- Få direkt åtkomst till den senaste informationen.
- Minska söktiderna.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Scenario: Förbättra databearbetningen för att ge insikter & analys

Ett läkemedelsföretag kan till exempel använda SharePoint Syntex för att extrahera information från FDA-dokument för att besvara frågor som deras ledare har. Att ha svaren lättillgängliga kan minska tiden som behövs för att skapa dessa svar och öka tillgängligheten på data för att skapa mer korrekta svar på ledares frågor.

En projektledare behöver till exempel snabbt ge svar på produktrelaterade frågor från min ledningsgrupp. De behöver hitta information och mätvärden relaterade till frågor i en konsoliderad instrumentpanel. De letar efter en lösning som extraherar den information de behöver från produktetiketter, produktbroschyrer och annat material och skapar en konsoliderad rapport som de kan använda när de rapporterar tillbaka till sina ledningsteam.

När du automatiserar det här scenariot kan du:

- Minska tiden för att få svar.
- Öka datatillgängligheten.
- Ge mer exakta svar.

### <a name="scenario-automate-order-processing"></a>Scenario: Automatisera orderbearbetning

Med SharePoint Syntex kan du minska tiden det tar för manuell bearbetning av kundorder. Du kan till exempel ladda upp order från fax, e-post eller papper till SharePoint genom att använda OCR-bearbetning och sedan extrahera metadata från dessa order så att du kan uppfylla dem genom att använda automatiserade processer.

En leverantörshanterare vill till exempel minska fel som orsakas av manuell datainmatning. De vill undvika manuell granskning och datainmatning av inkommande kundorder (papper, fax eller e-post) för att minska felen i deras affärssystem. De vill ha en lösning som använder AI- och maskininlärningstekniker för att verifiera information om inkommande order, extrahera basdata och automatiskt skicka in dem i deras ERP-system, för att uppfylla order och synkronisering.

När du automatiserar det här scenariot kan du se till att:

- Precisionen för order och leverans ökar.
- Avgifter eller andra avgifter som är förknippade med order- eller leveransfel minskas.
- Fördröjningar i fakturering eller minska betalningar.
- Personalkostnaderna minskas.

### <a name="scenario-simplify-visa-renewal-process"></a>Scenario: Förenkla förnyelseprocessen för visa

Med SharePoint Syntex kan du automatisera påminnelser och förnyelser för viktig kontraktsinformation. En HR-chef måste till exempel se till att de anställdas visas uppdaterad och/eller förnyas i tid. De vill ge användare en enkel och intuitiv process för att uppdatera sina visas. De behöver en lösning som extraherar förnyelsedatum från kontrakt och automatiskt skickar påminnelser till anställda när deras förnyelsedatum närmar sig.

När du automatiserar det här scenariot kan du se till att:

- Icke-efterlevnadsnivåerna försämras.
- Antalet manuella påminnelser minskas.
- Antalet vite för utebliven efterlevnad minskar.

## <a name="identify-roles--responsibilities"></a>Identifiera roller & ansvarsområden

Bestäm vem i organisationen som ska skapa och hantera modeller? Följande roller kan vara inblandade:

| SharePoint/Knowledge-administratör | Administratör för Power Platform | Knowledge Manager | Modellägare |
|:-------|:-------|:-------|:-------|
| AAD-roll| AAD-roll | AAD-roll | Mästare |
| Konfigurera formulärbearbetning | Konfigurera en gemensam datatjänstmiljö för formulärbearbetning | Samla in användningsfall | Samla in användningsfall för företag |
| Hantera innehållscenter och behörigheter| Köpa och tilldela AIB-krediter | Upprätta metodtips och granska modellanalyser | Skapa och använda modeller |

Knowledge Manager, business process owner and content model owner create sample models and champion adoption in the organization.
Andra som kan vara inblandade: Efterlevnadsadministratör, taxonomihanterare.

Var ska modeller byggs och användas? Finns det befintliga processer eller lagringsplatsen som kan förbättras?

- Formulärbearbetning: Bestäm vilka webbplatser som ska få åtgärden Formulärbearbetning.
- Dokumentförståelse: Du kan skapa flera innehållscenter för olika affärsområden.

## <a name="strategic-positioning"></a>Strategiska positionering

Arbeta med intressenter för att se till att de är i linje med strategin för att använda SharePoint Syntex. Gör efterforskningar och ge följande resurser som hjälp med den här positionen:

- Affärsresultat:
  - Möjliga räkenskapsresultat
  - Möjliga smidiga resultat
  - Resultatmall för företag
- Intressenter/Exec-sponsor – köp/justering
  - Affärsfalls bildspel
  - Finansmodeller
  - Beredskap för företaget – kultur

## <a name="identify-stakeholders"></a>Identifiera intressenter

Identifiera projektets intressenter.

|Roll |Ansvarsområden |Department |
|:-------|:-------|:--------|
| Huvudsponsorer   | Kommunicera visioner och värden på hög nivå till företaget   |  Ledning   |
| Projektledarna | Övervaka hela lanseringen av körningen och lanseringsprocessen | Projektledning |
| Kunskapsadministratörer| Skapa och hantera innehållscenter | IT eller annan avdelning|
| Innehållshanterare och modellägare| Samla in användningsfall och skapa och använda modeller | Alla avdelningar|
| Mästare | Hjälp till att sprida och hantera stötande hantering | Alla avdelningar (personal) |
| Innehavaradministratör | Konfigurera inställningar på klientorganisationsnivå | IT-avdelning|
| Administratör för Power Platform| Konfigurera en vanlig datatjänstmiljö | IT-avdelning|

> [!Note]
> Även om vi rekommenderar att var och en av de här rollerna har uppfyllts under hela utrullningen kan det hända att du inte behöver alla för att komma igång med din identifierade lösning.

## <a name="readiness-checklist"></a>Checklista för beredskap

För att förbereda för att implementera SharePoint Syntex måste du:

![Beredskap för innehållsförståelse](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planera sluttillståndet
    - Dokumentförståelsemodeller är ett medel, inte slutet.
    - Planera hur du utnyttjar värdet i extraherade metadata med:
      - Sök
      - Filtrera och visa formatering
      - Efterlevnad
      - Automation
2. Identifiera
    - Förstå befintlig informationsarkitektur och innehållshanteringsfunktionsanvändning.
    - Finns det några befintliga innehållstyper som tänkbara modeller?
    - Vilka befintliga processer skulle förbättras med metadata?
3. Design
    - Utforma din metod för informationsarkitektur, hanterade metadata och innehållstyper
    - Utforma processen för definition, skapande och hantering.

## <a name="engage-your-organization"></a>Engagera organisationen

1. Identifiera innehavarna, bekräfta scenarier och utveckla projektplanen.
1. Konfigurera inställningar och använda licenser.
1. Börja informera och utbilda – rekrytera mästare.
1. Distribuera stegvis.  
1. Samla in feedback och iterera.
1. Allt eftersom användningen växer planera för AI Builder-krediter efter behov.
