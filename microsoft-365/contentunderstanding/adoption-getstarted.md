---
title: 'Microsoft SharePoint Syntex: komma igång'
description: Lär dig hur du använder och implementerar SharePoint-Syntex i din organisation för att hjälpa dig att lösa dina företags problem.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 95e1ad15a62762c8b28203e178d4d4ae7906e38a
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760248"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex: komma igång

Tänk på de intelligenta innehålls tjänsterna som är tillgängliga i SharePoint-Syntex med tre delar:

- **Innehålls förståelse:** skapa ej kodade AI-modeller för att klassificera och extrahera information från innehåll så att metadata kan identifieras och återanvändas automatiskt. Läs mer om [innehålls förståelse](document-understanding-overview.md).
- **Innehålls bearbetning:** Automatisera insamling, intag och kategorisering av innehåll och strömlinjeforma innehållsbaserade processer genom att använda Power autoautomatisera. Läs mer om [innehålls bearbetning](form-processing-overview.md).
- **Innehålls överensstämmelse:** Kontrol lera och hantera innehåll för att förbättra säkerheten och styrningen med integrering med Microsoft informations skydd.

Med nya AI-tjänster och-kapaciteter kan du skapa program för innehålls förståelse och klassificering direkt i innehålls hanterings flödet med hjälp av SharePoint Syntex:

|Manuell inmatning| Formulär bearbetning | Dokument förståelse |
|:-------|:--------|:--------|
| Data inmatning och arbets kraft för allt innehåll. | Identifiera filer och hämta data från strukturerade eller halv strukturerade dokument, till exempel formulär och fakturor. |  Identifiera och extrahera data från ostrukturerade dokument, till exempel bokstäver eller kontrakt, där de textenheter som du vill extrahera finns i meningar eller vissa områden i dokumentet. |
| Active.   |  Anpassat, assisterande.  | Färdiga, automatiserade. |
| Personer som sköter arbetet. | I ämnes experter (SMF). | Små och medel stora företag är mindre inblandade. |

I följande tabell förklaras tillgänglighet och licensiering för SharePoint Syntex:

| Formulär bearbetning | Dokument förståelse |
|:-------|:-------|
| Formulär bearbetning är beroende av Power Platform. <br>Information om global tillgänglighet för Power Platform och AI Builder finns i [tillgänglighet för Power Platform](https://dynamics.microsoft.com/geographic-availability/). | Tillgänglig i alla regioner. |
| Använder AI Builder-kredit.<br>Tillgodohavanden kan köpas i batchar med 1M.<br>1M-kredit ingår när Syntex-licenser för 300 + SharePoint köps.<br>1M-kredit möjliggör bearbetning av 2000-filsidor. | Modeller fungerar på alla latinska språk. Förutom engelska: tyska, svenska, engelska, franska, spanska, italienska och portugisiska. |
| Tillhandahålls mot Standard miljön för gemensam data tjänst. | Saknar kapacitets begränsningar. |

Få reda på mer om AI-byggares kredit och enheter i [AI Builder-licensiering](https://docs.microsoft.com/ai-builder/administer-licensing).

Det finns två olika sätt att förstå innehållet. Vilken modell typ du använder är baserad på fil format och användnings fall:

| Formulär bearbetning | Dokument förståelse |
|:-------|:-------|
| Skapades från ett dokument bibliotek. | Skapat i innehålls Center, som ingår i SharePoint Syntex. |
| Modell skapad i AI Builder. | Modell skapad i inbyggt gränssnitt. |
| Används för halv strukturerade fil format. | Används för ostrukturerade fil format. |
| Uppställd klassificerare. | Tågens klassificerare med valfria utdrag. |
| Begränsat till ett enda bibliotek. | Kan tillämpas på flera bibliotek. |
| Utbilda dig på PDF, JPG, PNG-format, totalt 50 MB/500 sid. | Träna på 5-10 PDF-, Office-och e-postfiler, inklusive negativa exempel. |

SharePoint-Syntex integreras med Microsoft 365-funktioner för kompatibilitet som:

- Lagrings etiketter som definierar princip för Arkiv handlingar baserat på dokumentets ålder eller externa händelser.
- Känslighets etiketter som anger principer för DLP, kryptering, delning och villkorsstyrd åtkomst.

Användarna kan använda etiketter eller de kan användas automatiskt av SharePoint Syntex AI-modeller. Analys-och filplanerna tillhandahåller storskalig hantering av etikett användning och-principer.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Identifiera pilot företags scenarier att optimera

För att förbereda dig för att använda SharePoint-Syntex i din organisation måste du först förstå vilka scenarier de kommer att vara användbara. Anledningen hjälper dig att avgöra vilken modell som behövs och hur du strukturerar din organisation baserat på var modellen ska användas. Här är några scenarier där dokument förståelse kan hjälpa din organisation:

- Innehålls bearbetning: process kontrakt, arbets uppgifter och andra formulär-liknande dokument. Intag av formulären, träna modellen för att förstå och Mappa fälten och kör sedan formulären genom att automatiskt samla in data. Mer information finns i [Översikt över formulär bearbetning](form-processing-overview.md).
- Faktura analys: hämta relevant information från dina fakturor och kontrol lera att de följer med policy eller behandlas på lämpligt sätt.

Tänk på hur SharePoint Syntex kan hjälpa din organisation:

- Automatisera affärs processer
- Förbättra Sök precisionen
- Hantera efterlevnad

### <a name="form-processing-scenario-example"></a>Exempel på formulär bearbetnings scenario

Du kan till exempel konfigurera en process med SharePoint Syntex och Power Autostart-funktioner för att spåra och övervaka fakturor.

1. Skapa ett bibliotek för att lagra faktura dokumenten.
1. Träna modellen att känna igen fält i dokumenten.
1. Extrahera de fält du vill spåra till en lista.
1. Skapa ett flöde för att meddela dig om specifika händelser, till exempel:
    - En ny faktura läggs till.
    - En faktura har passerat sin förfallo dag.
    - En faktura är för ett belopp som är större än det automatiska godkännande beloppet.

![Spåra och kontrol lera fakturor med SharePoint Syntex och Power autoautomatisera](../media/content-understanding/process-invoices-flow.png)

När du automatiserar detta scenario kan du:

- Spara tid och pengar genom att automatiskt extrahera data från fakturorna i stället för att göra det manuellt.
- Minska eventuella problem och se till att du får bättre efterlevnad genom att använda arbets flöden för att hantera fakturorna och meddela dig om eventuella frågor.

### <a name="document-understanding-scenario-example"></a>Scenario för dokument förståelse

Du kan också konfigurera en process för att identifiera vilka kontrakt som företaget har med andra företag eller personer. Du kan ställa in en modell för att extrahera viktig information från dessa kontrakt, till exempel klient namn, avgifter, datum eller annan viktig information, och lägga till den i biblioteket som du snabbt kan se. Du kan använda en bevarande etikett i dokument biblioteket för att se till att kontrakt inte kan tas bort före en viss tids period efter det att dina affärs regler är uppfyllda.

1. Börja i innehålls centret och skapa ett nytt dokument förstå modellen för kontrakt.
1. Ladda upp exempel dokument för positiva och negativa exempel och kör sedan utbildningen för att identifiera kontrakts dokument och granska resultatet.
1. Träna in Extractor för att identifiera fält i kontraktet, till exempel klientens namn, avgift och datum, och testa sedan Extractor.
1. När modellen är färdig tillämpar du modellen på ett bibliotek där du kan ladda upp kontrakt.
1. Använd en behållnings etikett till datum fältet, så att kontrakt bevaras i biblioteket Under den tid som organisationen kräver för kontrakt.

![Spåra och övervaka kontrakt med SharePoint-Syntex och bevarande etiketter](../media/content-understanding/process-contracts-flow.png)

När du automatiserar detta scenario kan du:

- Spara tid och pengar genom att automatiskt extrahera data från kontrakten i stället för att göra det manuellt.
- Kontrol lera bättre efterlevnad genom att använda behållnings etiketter för att säkerställa att kontrakten bevaras på lämpligt sätt.

### <a name="tips-for-identifying-scenarios"></a>Tips för att identifiera scenarier

När du funderar på vilka affärs scenarier du bör tänka på kan du ställa följande frågor:

- Löste det ett riktigt problem?
- Kommer det att vara mycket oftare?
- Är det lättare?
- Kan du mäta framgång?

Prioritera scenarier baserat på konsekvenserna och enkelhetens användbarhet. Gör det ursprungliga inlednings området högre påverkan som kan vara lätt att implementera. De ger mindre effekt scenarier som är svåra att implementera.

## <a name="identify-roles--responsibilities"></a>Identifiera roller & ansvars områden

Bestäm vem i organisationen som ska bygga och hantera modellerna? Följande roller kan vara inblandade:

| SharePoint/kunskaps administratör | Administratör för Power Platform | Kunskaps chef | Modell ägare |
|:-------|:-------|:-------|:-------|
| AAD-roll| Lägg till roll | AAD-roll | Representanter |
| Konfigurera formulärbearbetning | Konfigurera gemensam data tjänst miljö för formulär bearbetning | Samla användnings fall | Samlat företags användnings fall |
| Hantera innehålls Center och behörigheter| Köp och tilldela AIB-kredit | Skapa bästa praxis och granska modell analyser | Skapa och använda modeller |

Kunskaps chef, arbets process ägare och ägare av innehålls modell skapa exempel modeller och mästare som antagits i organisationen.
Andra som kan vara inblandade: överensstämmelse administratör, taxonomier.

Var kommer de att bygga och tillämpa modellerna? Finns det befintliga processer som kan förbättras?

- Formulär bearbetning: Bestäm vilka webbplatser som får formulär bearbetnings åtgärd.
- Dokument information: du kan skapa flera innehålls Center för olika företags områden.

## <a name="strategic-positioning"></a>Strategisk placering

Arbeta med intressenter för att säkerställa att de är justerade mot strategin för att använda SharePoint-Syntex. Undersök och ange följande resurser för att hjälpa till med den här placeringen:

- Företags resultat:
  - Potentiella kvitto resultat
  - Potentiella smidiga resultat
  - Mallen företags resultat
- Leverantör av intressenter/exekutiv sponsor
  - Kontors fodral
  - Finans modeller
  - Företags beredskap-kultur

## <a name="identify-stakeholders"></a>Identifiera intressenter

Identifiera intressenterna för projektet.

|Roll |Uppgifter |Department |
|:-------|:-------|:--------|
| Direktör (er)   | Kommunicerar visioner och-värden till företaget   |  Ledarskaps chef   |
| Projektets leads | Övervaka hela kör-och start processen | Projektledning |
| Kunskaps administratörer| Skapa och hantera innehålls Center | DEN eller andra avdelningen|
| Innehålls hanterare och modell ägare| Samla användnings fall och skapa och använda modeller | Alla avdelningar|
| Representanter | Hjälp evangelize och hantering av objekt hantering | Alla avdelningar (personal) |
| Klient organisations administratör | Konfigurera inställningar för klient organisations nivå | IT-avdelning|
| Power Platform-administratör| Konfigurera gemensam data tjänst miljö | IT-avdelning|

> [!Note]
> Även om vi rekommenderar att du har var och en av de här rollerna, kanske du inte behöver allt för att komma igång med din lösning.

## <a name="readiness-checklist"></a>Check lista för beredskap

För att du ska kunna implementera SharePoint-Syntex måste du:

![Beredskap för innehålls förståelse](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. Planera slut tillståndet
    - Dokument förståelse modeller är medel, inte slutet.
    - Planera för att utnyttja värdet för extraherade metadata med:
      - Sökmotor
      - Filtrera och Visa formatering
      - Efterlevnad
      - Åtgärden
2. Bestäm
    - Förstå befintliga funktioner för informations arkitektur och innehålls hantering.
    - Är alla befintliga innehålls typer som passar bra för modeller?
    - Vilka befintliga processer förbättras med metadata?
3. Design
    - Utforma din metod för informations arkitektur, hanterade metadata och innehålls typer
    - Designa processen för definition, skapande, hantering.

## <a name="engage-your-organization"></a>Engagera organisationen

1. Identifiera aktieägare, bekräfta scenarier och utveckla projektplanen.
1. Konfigurera inställningar och tillämpa licenser.
1. Börja medvetenhet och utbildning – rekrytera representanter.
1. Sammanställ i stadier.  
1. Samla in feedback och iterera.
1. Som användning växer en plan för alla AI-byggare om det behövs.
