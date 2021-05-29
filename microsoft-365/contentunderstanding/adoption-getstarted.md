---
title: 'Införande av Microsoft SharePoint Syntex: Komma igång'
description: Lär dig hur du använder och implementerar SharePoint Syntex i din organisation för att hjälpa dig att lösa affärsproblem.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 62e65f9be25e2c482cca78577048d504ee93097a
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698982"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Införande av Microsoft SharePoint Syntex: Komma igång

Tänk på att de intelligenta innehållstjänster som finns SharePoint Syntex har tre delar:

- **Innehållsförståelse:** Skapa AI-modeller utan kod för att klassificera och extrahera information från innehåll för att automatiskt tillämpa metadata för upptäckt och återanvändning av kunskap. Läs mer om [innehållsförståelse.](document-understanding-overview.md)
- **Innehållsbearbetning:** Automatisera insamling, påtagande och kategorisering av innehåll och effektivisera innehållscentrerade processer med hjälp av Power Automate. Läs mer om [innehållsbearbetning](form-processing-overview.md).
- **Innehållsefterlevnad:** Kontrollera och hantera innehåll för att förbättra säkerhet och styrning med integrering med Microsoft Information Protection.

Med nya AI-tjänster och funktioner kan du bygga in innehållsförståelse och klassificeringsappar direkt i innehållshanteringsflödet med hjälp av SharePoint Syntex. Det finns två olika sätt att förstå innehållet. Den modelltyp du använder baseras på filformat och användningsfall:

| Formulärbearbetning | Dokumenttolkning |
|:-------|:-------|
| Skapad från dokumentbibliotek. | Skapad i innehållscentret, en del av SharePoint Syntex. |
| Modell skapad i AI-verktyget. | Modell som skapats i gränssnittet. |
| Används för semistrukturerade filformat. | Används för ostrukturerade filformat. |
| Infogbar klassificerare. | Utbildare med valfria extraherare. |
| Begränsad till ett enskilt bibliotek. | Kan tillämpas på flera bibliotek. |
| Utbilda i PDF, JPG, PNG-format, totalt 50 MB/500 pp. | Träna på 5-10 PDF-, Office- eller e-postfiler, inklusive negativa exempel. |

En mer fullständig jämförelse av funktionerna finns i Skillnaden [mellan dokumentförståelse och formbearbetningsmodeller.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifiera pilotscenarion för att optimera

För att förbereda för SharePoint och Syntex i organisationen måste du först förstå scenarier som kan vara användbara. Med hjälp av "varför" kan du avgöra vilken modell som kommer att användas och hur du strukturerar organisationen baserat på var modellen ska tillämpas. Här är några scenarier där dokument förstå kan hjälpa din organisation:

- **Innehållsbearbetning:** Bearbeta kontrakt, arbetsutdrag och andra formulärliknande dokument. Sköta formulären, utbilda modellen för att förstå och mappa fälten och kör sedan dina formulär för att automatiskt samla in data. Mer information finns i [Översikt över formulärbearbetning](form-processing-overview.md).
- **Fakturaanalys:** Hämta relevant information från dina fakturor och kontrollera att de följer principen eller behandlas på rätt sätt.

Tänk på olika sätt som SharePoint Syntex kan hjälpa din organisation:

- Automatisera affärsprocesser
- Förbättra sökprecisionen
- Hantera efterlevnadsrisker

När du funderar på vilka affärsscenarier du ska tänka på bör du ställa dig följande frågor:

- Löser det ett verkligt problem?
- Kommer den att användas ofta eller ha stor påverkan?
- Går det att få tag i den?
- Kan du mäta framgång?

Prioritera scenarier utifrån påverkan och enkelhet vid implementering. Gör ditt första fokusområde mer effekt scenarier som också kan enkelt implementeras. Av prioritera scenarier med lägre effekt som är svåra att implementera.

Använd [exempelscenarier och använd ärenden](adoption-scenarios.md) för att visa en uppmaning om hur du kan SharePoint Syntex i organisationen.

## <a name="identify-roles--responsibilities"></a>Identifiera roller & ansvarsområden

Vem i organisationen ska skapa och hantera modeller? Följande roller kan vara inblandade:

| SharePoint-/Knowledge-administratör | Administratör för Power-plattformen | Knowledge Manager | Modellägare |
|:-------|:-------|:-------|:-------|
| AAD-roll| AAD-roll | AAD-roll | Mästare |
| Konfigurera formulärbearbetning | Konfigurera common data service environment for form processing | Samla in användningsfall | Samla in användningsfall för företag |
| Hantera innehållscenter och behörigheter| Köpa och tilldela AIB-krediter | Upprätta metodtips och granska modellanalyser | Skapa och använda modeller |

Knowledge Manager, Business Process Owner och ägare av innehållsmodeller skapar exempelmodeller och är mästare på införandet i organisationen.
Andra som kan vara inblandade: efterlevnadsadministratörer, taxonomihanterare.

Var ska modeller byggas och användas? Finns det befintliga processer eller lagringsplatsen som kan förbättras?

- Formulärbearbetning: Bestäm vilka webbplatser som ska få åtgärden Formulärbearbetning.
- Dokumentförståelse: Du kan skapa flera innehållscenter för olika affärsområden.

## <a name="strategic-positioning"></a>Strategiska positionering

Arbeta med intressenter för att se till att de är i linje med strategin för att SharePoint Syntex. Gör efterforskningar och ge följande resurser som hjälp med den här positionen:

- Affärsresultat:
  - Möjliga räkenskapsresultat
  - Möjliga smidiga resultat
  - Mall för affärsresultat
- Intressenter/Exec-sponsor, köp/justering
  - Affärsfalls bildspel
  - Finansmodeller
  - Företagsberedskap – kultur

## <a name="identify-stakeholders"></a>Identifiera intressenter

Identifiera projektets intressenter.

|Roll |Ansvarsområden |Department |
|:-------|:-------|:--------|
| Sponsor(er)   | Kommunicera visioner och värden på hög nivå till företaget   |  Ledning   |
| Project eller lead | Övervaka hela startkörningen och lanseringsprocessen | Project hantering |
| Kunskapsadministratörer| Skapa och hantera innehållscenter | IT eller annan avdelning|
| Innehållshanterare och modellägare| Samla in användningsfall och skapa och använda modeller | Alla avdelningar|
| Mästare | Hjälpa till att sprida och hantera stötande hantering | Alla avdelningar (personal) |
| Innehavaradministratör | Konfigurera inställningar på klientnivå | IT-avdelning|
| Power Platform-administratör| Konfigurera en vanlig miljö för datatjänster | IT-avdelning|

> [!Note]
> Vi rekommenderar att alla de här rollerna har uppfyllts under hela utrullningen, men du kanske upptäcker att du inte behöver dem alla för att komma igång med din identifierade lösning.

## <a name="readiness-checklist"></a>Checklista för beredskap

För att förbereda dig för SharePoint Syntex måste du:

![Beredskap för innehållsförståelse](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planera sluttillståndet
    - Dokument förstå modeller är medel och inte slutet.
    - Planera hur du utnyttjar värdet på extraherade metadata med:
      - Söka
      - Filtrera och visa formatering
      - Efterlevnad
      - Automation
2. Identifiera
    - Förstå befintlig informationsarkitektur och användning av innehållshanteringsfunktion.
    - Finns det några befintliga innehållstyper som tänkbara modeller?
    - Vilka befintliga processer skulle förbättras med metadata?
3. Design
    - Utforma din metod för informationsarkitektur, hanterade metadata och innehållstyper
    - Utforma processen för definition, skapande och hantering.

## <a name="engage-your-organization"></a>Engagera organisationen

1. Identifiera innehavarna, bekräfta scenarier och utveckla projektplanen.
1. Konfigurera inställningar och använd licenser.
1. Börja informera och utbilda – rekrytera mästare.
1. Distribuera stegvis.  
1. Samla in feedback och iterera.
1. Allt eftersom användningen växer planerar vi för AI Builder-krediter efter behov.

## <a name="see-also"></a>Se även

[Scenarier och användningsfall för SharePoint Syntex](adoption-scenarios.md)