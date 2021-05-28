---
title: Scenarier och användningsfall för Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
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
description: Hitta scenarier om hur du använder SharePoint Syntex i organisationen.
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697071"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a>Scenarier och användningsfall för Microsoft SharePoint Syntex

Använd följande exempelscenarier för att visa en uppfattning om hur du kan SharePoint Syntex i din organisation.

- [Scenario: Spåra data från fakturor med formulärbearbetning](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [Scenario: Spåra information från kontrakt med dokumentförståelse](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [Scenario: Undvik risker med hantering av arkivhandlingar, dokumentstyrning och efterlevnadsprocesser baserat SharePoint Syntex](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [Scenario: Hämta information från dokument som tidigare inte var tillgängliga](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [Scenario: Förbättra databearbetningen för att ge insikter och analys](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [Scenario: Automatisera orderbearbetning](adoption-scenarios.md#scenario-automate-order-processing)
- [Scenario: Förenkla förnyelseprocessen för visa](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: Spåra data från fakturor med formulärbearbetning

Du kan till exempel konfigurera en process med hjälp av SharePoint Syntex och Power Automate att spåra och övervaka fakturor.

1. Konfigurera ett bibliotek för att lagra fakturadokumenten.
1. Utbilda modellen så att den känner igen fält i dokumenten.
1. Extrahera de fält du vill spåra till en lista.
1. Konfigurera ett flöde för att meddela dig om specifika händelser, till exempel:
    - En ny faktura läggs till.
    - En faktura har förfallodagen gått ut.
    - En faktura är för ett belopp som är större än ditt automatiska godkännandebelopp.

![Spåra och övervaka fakturor med SharePoint Syntex och Power Automate](../media/content-understanding/process-invoices-flow.png)

När du automatiserar det här scenariot kan du:

- Spara tid och pengar genom att automatiskt extrahera data från fakturor i stället för att göra dem manuellt.
- Minska potentiella fel och säkerställ bättre efterlevnad genom att använda arbetsflöden för att kontrollera fakturor och meddela dig om eventuella problem.

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: Spåra information från kontrakt med dokumentförståelse

Ett annat exempel är att skapa en process för att identifiera de kontrakt företaget har med andra företag eller enskilda personer. Konfigurera en modell för att extrahera viktig information från dessa kontrakt, t.ex. kundnamn, avgifter, datum eller annan viktig information, och lägg till informationen i biblioteket som fält som du snabbt kan visa. Använd en bevarandeetikett på dokumentbiblioteket för att säkerställa att kontrakt inte kan tas bort innan en viss tid för att följa dina affärsregler.

1. Börja på innehållscentret och skapa en ny dokumentförståelsemodell för kontrakt.
1. Upload exempeldokument för positiva och negativa exempel, kör sedan utbildningen för att identifiera kontraktsdokument och granska resultaten.
1. Utbilda extraheraren för att identifiera fält i kontrakten, till exempel kundnamn, avgift och datum, och testa sedan extraheraren.
1. När modellen är klar kan du använda modellen på ett bibliotek där du kan överföra kontrakt.
1. Använd en bevarandeetikett för datumfältet, så att kontrakten bevaras i biblioteket under den tid som krävs.

![Spåra och övervaka kontrakt med SharePoint Syntex och bevarandeetiketter](../media/content-understanding/process-contracts-flow.png)

När du automatiserar det här scenariot kan du:

- Spara tid och pengar genom att automatiskt extrahera data från kontrakten i stället för att göra dem manuellt.
- Säkerställ bättre efterlevnad genom att använda bevarandeetiketter för att säkerställa att kontrakten bevaras på rätt sätt.

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: Undvik risker med hantering av arkivhandlingar, dokumentstyrning och efterlevnadsprocesser baserat SharePoint Syntex

Att minska risker är ett vanligt mål för de flesta företag. Du kan behöva:

- Ett bättre sätt att tillhandahålla/tillämpa informationsstyrning i klientorganisationen.
- För att förbättra systemet för klassificering av dokument, e-postmeddelanden och andra kommunikationssätt som anses vara "arkivhandlingar" för projekt.
- Granska kvitton, kontrakt och så vidare för att säkerställa efterlevnad av företagets policyer.
- För att säkerställa att projekt har all dokumentation som krävs för efterlevnad.

Konfigurera vissa processer för efterlevnad med SharePoint Syntex för att registrera och klassificera, granska och flagga dokument och formulär som behöver bättre styrning. Du kan förlita dig på SharePoint Syntex för att automatiskt klassificera innehåll i stället för att förlitar sig på slutanvändare att tagga manuellt, eller så kan efterlevnadsteamet manuellt tillämpa styrningsregler och arkivering. Du kan också aktivera en förenklad sökupplevelse, hantera datavolymer, använda hantering av arkivhandlingar och bevarandeprinciper, säkerställa efterlevnad och bästa praxis för arkivering och rensning.

När du automatiserar det här scenariot kan du känna dig säker på följande:

- Efterlevnad upprätthålls och risken minskar.
- Taxonomi och hantering av poster tillämpas konsekvent och korrekt.
- Innehållsvolymerna styrs.
- Anställda kan enkelt hitta rätt information i rätt sammanhang.

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: Hämta information från dokument som tidigare inte var tillgängliga

De flesta organisationer har stora lagringsgränser med juridiska dokument, principer, kontrakt, HR-dokument och riktlinjer för styrning. Mina dessa datakällor för att extrahera värdefull information, t.ex. projekt, teman, personer, geografiska områden och så vidare.

En HR-chef behöver till exempel snabbt tillgång till alla HR-dokument – inklusive meritförteckningar, personalregler och andra formulär. Och de vill snabbt kunna identifiera nödvändig information från meritförteckningar och andra HR-relaterade dokument utan att manuellt gå igenom dokumenten. De letar efter en lösning som gör att de snabbt kan hitta den information de behöver utan att manuellt behöva gå igenom tusentals meritförteckningar, hr-policyer och annan dokumentation som kan spridas över flera webbplatser.

När du automatiserar det här scenariot kan du:

- Lås upp kunskap från digitalt innehåll.
- Klassificera HR-principer, meritförteckningar, säljdokument, tekniska ritningar, kontoplaner och extrahera information.
- Hitta snabbt rätt information eller dokument som du letar efter.
- Få direkt åtkomst till den senaste informationen.
- Minska söktiderna.

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a>Scenario: Förbättra databearbetningen för att ge insikter och analys

Ett läkemedelsföretag kan till exempel använda Syntex SharePoint extrahera information från FDA-dokument för att besvara frågor som deras ledare har. Att ha svaren mer lättillgängliga kan minska tiden som behövs för att skapa dessa svar och öka tillgängligheten för data för att skapa mer exakta svar på ledningsfrågor.

En projektledare behöver till exempel snabbt ge svar på produktrelaterade frågor från mitt ledningsteam. De behöver hitta information och mätvärden relaterade till frågor i en konsoliderad instrumentpanel. De letar efter en lösning som extraherar den information de behöver från produktetiketter, produktbroschyrer och annat material och genererar en konsoliderad rapport som de kan använda när de rapporterar tillbaka till sin ledning.

När du automatiserar det här scenariot kan du:

- Minska tiden för att få svar.
- Öka datatillgängligheten.
- Ge mer exakta svar.

## <a name="scenario-automate-order-processing"></a>Scenario: Automatisera orderbearbetning

Med SharePoint Syntex kan du minska tiden för manuell bearbetning av kundorder. Du kan till exempel ladda upp order från fax, e-post eller papper till SharePoint genom att använda OCR-bearbetning och sedan extrahera metadata från dessa order så att du kan uppfylla dem genom att använda automatiserade processer.

En leverantörshanterare vill till exempel minska fel som orsakas av manuell datainmatning. De vill undvika manuell granskning och datainmatning av inkommande kundorder (papper, fax eller e-post) för att minska felen i deras affärssystem. De vill ha en lösning som använder AI- och maskininlärningstekniker för att verifiera information om inkommande order, extrahera basdata och automatiskt skicka dem till deras ERP-system, för att uppfylla order och synkronisering.

När du automatiserar det här scenariot kan du se till att:

- Ordnings- och leveransprecisionen ökar.
- Avgifter eller kostnader som är förknippade med order- eller leveransfel minskas.
- Fördröjningar i fakturering eller betalningar minskar.
- Personalkostnaderna minskas.

## <a name="scenario-simplify-visa-renewal-process"></a>Scenario: Förenkla förnyelseprocessen för visa

SharePoint Syntex kan hjälpa dig att automatisera påminnelser och förnyelser för viktig kontraktsinformation. En personalchef behöver till exempel se till att de anställdas visas uppdaterad och/eller förnyas i tid. De vill ge användare en enkel och intuitiv process för att uppdatera sina visas. De behöver en lösning som extraherar förnyelsedatum från kontrakt och automatiskt skickar påminnelser till anställda när deras förnyelsedatum närmar sig.

När du automatiserar det här scenariot kan du se till att:

- Icke-efterlevnadsnivåerna försämras.
- Antalet manuella påminnelser minskas.
- Antalet avgifter för icke-efterlevnad minskar.

## <a name="see-also"></a>Se även

[Införande av Microsoft SharePoint Syntex: Komma igång](adoption-getstarted.md)