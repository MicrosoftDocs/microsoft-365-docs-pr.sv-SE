---
title: Använda Efterlevnadshanteraren för att hantera förbättringsåtgärder
ms.author: chvukosw
author: chvukosw
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 09/29/2020
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
description: Lär dig hur du använder Efterlevnadspoäng och Efterlevnadshanteraren för att förbättra skyddsnivån för personuppgifter.
ms.openlocfilehash: 26e9f54ce77869f4f6ef07c18147483628ddc223
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229305"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Använda Efterlevnadshanteraren för att hantera förbättringsåtgärder

Microsoft Compliance Manager kan hjälpa dig att hantera förbättringar relaterade till datasekretessbestämmelser som EU:s allmänna [dataskyddsförordning (GDPR),](/compliance/regulatory/gdpr) [California Consumer Protection Act CCPA),](/compliance/regulatory/ccpa-faq)HIPAA-HITECH (US Health Care Privacy Act) och Brazil Data Protection Act (LGPD).

Den här artikeln innehåller vägledning om hur du använder verktyget i datasekretesssyfte.

> [!NOTE]
> Rekommendationer från Compliance Manager ska inte tolkas som en garanti för överensstämmelse. Det är upp till dig att utvärdera och verifiera hur effektiv kundkontrollerna är i olika regelverk. Dessa tjänster omfattas av de allmänna villkoren i [villkoren för onlinetjänster.](https://go.microsoft.com/fwlink/?linkid=2108910) Se även [vägledning Microsoft 365 om licensiering för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="getting-started-with-compliance-manager"></a>Komma igång med Efterlevnadshanteraren

#### <a name="what-is-compliance-manager"></a>Vad är Efterlevnadshanteraren

[Efterlevnadshanteraren](../compliance/compliance-manager.md) är ett arbetsflödesbaserat riskutvärderingsverktyg i Microsoft 365 Efterlevnadscenter att hantera aktiviteter för regelefterlevnad som är relaterade till Microsofts molntjänster. Som en del av Microsoft 365- eller Azure Active Directory-prenumerationen (Azure AD) hjälper Efterlevnadshanteraren dig att hantera regelefterlevnad i den delade ansvarsfördelningsmodellen för Microsoft-molntjänster.

**Redo att använda utvärderingar**

Efterlevnadshanteraren tillhandahåller färdiga [](../compliance/compliance-manager-assessments.md) mallar för att skapa bedömningar som är anpassade till datasekretessrelaterade bestämmelser som GDPR och HIPAA/HITECH. Mallarna har inbyggd kontrollmappning som hjälper dig att vidta förbättringsåtgärder för att uppfylla kraven i reglerna. Varje bedömning innehåller information om de kontroller som krävs för varje regel som är specifika för måltjänsten, uppdelade upp av kontroller som du hanterar och kontroller som Microsoft hanterar.

Med hjälp av en färdig mall kan du snabbt komma igång med riskbedömning. Allt eftersom du snabbt kan använda Efterlevnadshanteraren kan du anpassa en färdig mall genom att lägga till egna kontroller och förbättringsåtgärder, eller så kan du skapa egna utvärderingar som passar organisationens behov.

Visa en [fullständig lista över utvärderingsmallar som](../compliance/compliance-manager-templates-list.md) tillhandahålls av Efterlevnadshanteraren.

**Efterlevnadspoäng i realtid**

Efterlevnadshanteraren ger dig även ett efterlevnadsresultat som mäter hur långt du slutfört rekommenderade förbättringsåtgärder i kontroller. Du kan använda denna poäng för att övervaka dina framsteg och prioritera åtgärder baserat på deras möjlighet att minska risken.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Använda snabbstartsguiden för Efterlevnadshanteraren

[Snabbstartsguiden för Efterlevnadshanteraren](../compliance/compliance-manager-quickstart.md) innehåller mer avancerad vägledning och länkar till viktiga resurser som hjälper dig att arbeta med Efterlevnadshanteraren:

- [Första besöket: bekanta dig med Efterlevnadshanteraren](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Arbeta med instrumentpanelen för Efterlevnadshanteraren
    - Förstå din efterlevnadspoäng
    - Learning om förbättringsåtgärder
    - Förstå utvärderingar och mallar
- [Så här går det till: konfigurera Efterlevnadshanteraren för att hantera dina efterlevnadsaktiviteter](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Skapa och hantera din första bedömning
    - Utföra implementerings- och testarbete på förbättringsåtgärder för att slutföra kontroller i dina utvärderingar
    - Förstå hur olika åtgärder påverkar ditt efterlevnadsresultat
- [Skalning: använd avancerade funktioner för att uppfylla dina behov](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Skapa anpassade utvärderingar för att spåra icke-Microsoft 365 produkter
    - Ändra befintliga mallar för att lägga till eller ta bort kontroller
    - Konfigurera automatisk testning av förbättringsåtgärder

## <a name="how-your-compliance-score-is-calculated"></a>Hur din efterlevnadspoäng beräknas

Efterlevnadsresultatet beräknas utifrån en kombination av microsoft- och kund hanterade kontrollimplementeringar. Se [beräkningen av efterlevnadspoäng](../compliance/compliance-score-calculation.md) för en detaljerad förklaring.

Kontroller tilldelas ett poängvärde baserat på om de är obligatoriska eller godtyckliga, och om de är preventativa, godtyckliga eller korrigerande. Dessa utgör kollektivt risken att inte implementera den i förhållande till andra kontroller.

I den här artikeln om beräkning av efterlevnadsresultat får förebyggande kontroller ett högre poängresultat än de som är obligatoriska och obligatoriska kontroller ger högre poäng än godtyckliga.

I användargränssnittet för efterlevnadsresultat visas inte dessa parametrar, inte heller möjligheten att filtrera efter dem. Men om du hämtar den associerade mallen från Efterlevnadshanteraren visar den resulterande datauppsättningen de här parametrarna för de flesta bestämmelser.

För tekniska kontroller uppdaterar Efterlevnadshanteraren automatiskt förbättringsåtgärdsresultatet när åtgärden har implementerats och testats. Andra icke-tekniska kontrollåtgärder, till exempel åtgärder som fungerar eller relaterade till dokumentation, måste registreras manuellt så att de implementeras innan &mdash; &mdash; poäng räknas mot din poäng.

Du många implementerar även vissa förbättringsåtgärder för andra ändamål, till exempel om du använder bevarandeetiketter av andra orsaker än efterlevnad av datasekretesssregler, så att du kan få kredit för att använda en sådan funktion även om den används för andra ändamål, och inte en del av en avsiktlig &mdash; &mdash; efterlevnadsåtgärd.

Efterlevnadsresultatet bör ses som ett relativt mått för att spåra förbättringar i bred skala. Du bör inte uppnå ett perfekt resultat.

## <a name="additional-guidance"></a>Ytterligare vägledning

Här är några viktiga tips för hur du använder Efterlevnadshanteraren för att få bättre regelefterlevnad för datasekretess:

- Varje datasekretessförordningen har en kombination av tekniska kontroller, dokumentationsspecifikationer och drift-, process- och rapporteringskrav. Alla dessa visas i förbättringsåtgärderna.

- Om du vill fokusera vyn över förbättringsåtgärder i ditt intresse  kan du filtrera efter åtgärdstyp på fliken Lösningar i efterlevnadshanterarens administratör. Läs mer om hur [du filtrerar instrumentpanelen i Efterlevnadshanteraren.](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view)

- Den relativa prioriteten för förbättringsåtgärder som identifieras i Efterlevnadshanteraren bör ses som en del av en bredare riskgranskning tillsammans med den datasekretessrisk du har fastställt att din organisation behöver hantera.

- Även om bedömningsmallarna för gdpr, LGPD, CCPA och HIPAA-HITECH valts, visas till exempel nästan 400 förbättringsåtgärder i Efterlevnadshanteraren, även om aggregeringen för förbättringsåtgärder gäller flera olika regelkrav. Du kan förbättra den här långa listan med åtgärdsfiltret för förbättringar för att minska resultatet till en mer hanterbar lista.

- Med filtret Kategorier kan du filtrera förbättringsåtgärder genom logisk gruppering, som artiklarna Spåra, Förhindra, Skydda, Behålla och Undersöka artiklar i den övergripande lösningen stämmer överens med.

- Vissa kontroller som listas i förbättringsåtgärderna kan ses som mer direkt knutna till en särskild regelartikel, medan andra kontroller kan vara mer indirekt kopplade till reglernas ande och många gånger är bara rekommenderade aktiviteter eller bästa metoder.