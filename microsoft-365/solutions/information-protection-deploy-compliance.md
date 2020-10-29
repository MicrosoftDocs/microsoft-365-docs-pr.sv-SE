---
title: Använda Compliance Manager för att hantera förbättrings åtgärder
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
description: Lär dig hur du kan använda poäng-och efterföljandekrav för att förbättra skydds nivån för dina person uppgifter.
ms.openlocfilehash: f90826795197b392f629eb8eec71b7f27081b697
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791888"
---
# <a name="use-compliance-manager-to-manage-improvement-actions"></a>Använda Compliance Manager för att hantera förbättrings åtgärder

Med Microsoft Compliance Manager kan du hantera förbättringar i samband med data integritets bestämmelser som Europeiska unionens [allmänna data skydds förordning (GDPR)](../compliance/gdpr.md), [California konsument skydd Act CCPA)](../compliance/ccpa-faq.md), HIPAA-HITECH (Health värna om sjukvård) och Brasilien Data Protection Act (LGPD).

I den här artikeln beskrivs hur du använder det här verktyget för data integritet.

>[!Note]
>Rekommendationer från Compliance Manager ska inte tolkas som en garanti för överensstämmelse. Det är upp till dig att utvärdera och kontrol lera effektiviteten hos kund kontroller i din regelverks miljö. Dessa tjänster lyder under villkoren i villkoren för [online tjänster](https://go.microsoft.com/fwlink/?linkid=2108910). Se även [Microsoft 365 licens guide för säkerhet och efterlevnad](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)
>

## <a name="getting-started-with-compliance-manager"></a>Komma igång med Compliance Manager

#### <a name="what-is-compliance-manager"></a>Vad är Compliance Manager?

[Compliance Manager](../compliance/compliance-manager.md) är ett flödes verktyg för riskbedömning i Microsoft 365 Compliance Center för hantering av regler för regelefterlevnad som är relaterade till Microsofts moln tjänster. Som en del av ditt Microsoft 365-eller Azure Active Directory (Azure AD-abonnemang) kan du använda Autentiseringshanteraren för att hantera efterlevnad i den delade ansvars modellen för Microsofts moln tjänster.

**Klar att använda utvärderingar**

Compliance Manager innehåller färdiga mallar för att [bygga utvärderingar](../compliance/compliance-manager-assessments.md) som är justerade efter data integritets regler, till exempel GDPR och HIPAA/HITECH. Mallarna har inbyggd kontroll som hjälper dig att vidta åtgärder för att uppfylla förordningens krav. Varje bedömning ger information om de kontroller som varje förordning ringer för specifikt till mål tjänsten, uppdelad genom kontroller som du hanterar och styr Microsoft hanterar. 

Genom att använda en fördefinierad mall kan du snabbt komma igång med riskbedömningar. När du blir mer vana i att använda Compliance Manager kan du anpassa en fördefinierad mall genom att lägga till egna kontroller och förbättringar, eller så kan du skapa egna anpassade utvärderingar som passar organisationens behov.

Visa en [fullständig lista över kostnadsmallar för utvärderings](../compliance/compliance-manager-templates-list.md) hanteraren.

**Kompatibilitetsstatus i real tid**

Efterföljandekrav ger också en uppgångs Poäng som mäter dina framsteg när det gäller rekommenderade förbättrings åtgärder i kontroller. Du kan använda poängen för att övervaka dina framsteg och prioritera åtgärder baserat på deras potential att minska riskerna.

#### <a name="use-the-compliance-manager-quickstart-guide"></a>Använda Start guiden för regelefterlevnad

Start guiden för [Compliance Manager](../compliance/compliance-manager-quickstart.md) innehåller stegvisa instruktioner och länkar till viktiga resurser som hjälper dig att arbeta med Compliance Manager:

- [Första gången du besöker: bekanta dig med Compliance Manager](../compliance/compliance-manager-quickstart.md#first-visit-get-to-know-compliance-manager)
    - Arbeta med instrument panelen för regelefterlevnad
    - Förstå hur poängen går till
    - Lär dig mer om förbättrings åtgärder
    - Förstå utvärderingar och mallar
- [Ramp up: Konfigurera Efterföljandekrav för att hantera dina regelefterlevnad-aktiviteter](../compliance/compliance-manager-quickstart.md#ramping-up-configure-compliance-manager-to-manage-your-compliance-activities)
    - Bygga och hantera din första utvärdering
    - Utför implementering och testning av förbättrings åtgärder för att slutföra kontroller i dina utvärderingar
    - Förstå hur olika åtgärder påverkar din regelefterlevnad
- [Öka proportionellt: Använd avancerade funktioner för att möta dina anpassade behov](../compliance/compliance-manager-quickstart.md#scaling-up-use-advanced-functionality-to-meet-your-custom-needs)
    - Skapa anpassade utvärderingar för att spåra icke-Microsoft 365-produkter
    - Ändra befintliga mallar för att lägga till eller ta bort kontroller
    - Ställa in automatiserade test av förbättrings åtgärder

## <a name="how-your-compliance-score-is-calculated"></a>Hur din efterlevnadspoäng beräknas

Ditt uppföljda Poäng beräknas utifrån en kombination av Microsoft-och Kundhanterade kontroller. Visa [resultat beräkning för regelefterlevnad](../compliance/compliance-score-calculation.md) för en detaljerad förklaring.

Kontroller tilldelas ett resultat värde utifrån om de är obligatoriska eller frivilliga och om de är förebyggande, upptäckta eller korrigerade. Dessa representerar risken att inte implementera den i förhållande till andra kontroller.

Som du har lagt till i artikeln om bedömning av efterlevnad får förebyggande kontroller högre poäng än identifiering och korrigering, och obligatoriska kontroller ger högre poäng än mjuka och kära.

Administrations gränssnittet för arbets Poäng visar inte dessa parametrar eller kan inte filtrera efter dem. Om du däremot laddar ned den associerade mallen från Compliance Manager visas dessa parametrar för de flesta regler i den resulterande data uppsättningen.

För tekniska kontroller uppdaterar Compliance Manager automatiskt förbättrings åtgärden när åtgärden har implementerats och testats. Andra, icke-tekniska kontroll åtgärder &mdash; , till exempel sådana som används eller är relaterade till dokumentation, &mdash; måste registreras manuellt som implementerade före Points.

Du kan också genomföra vissa förbättrings åtgärder för andra ändamål &mdash; , till exempel använda lagrings etiketter av andra orsaker än data integritets regler &mdash; , så att du får kredit för att använda en sådan funktion även om den används för andra ändamål och inte i en avsiktlig efterlevnad.

Ditt uppföljda Poäng bör ses som en relativ åtgärd för att spåra förbättringar på brett skal. Du bör inte ha en perfekt poäng.

## <a name="additional-guidance"></a>Ytterligare vägledning

Här är några viktiga tips för hur du använder Compliance Manager för att hjälpa dig att uppnå data integritets reglernas efterlevnad:

- Varje data integritets förordning har en kombination av tekniska kontroller, dokumentations specifikationer och krav för drift, processer och rapporter. Alla de här visas i förbättrings åtgärderna.

- Om du vill fokusera på förbättrings åtgärder i det område som intresserar dig kan du filtrera efter åtgärds typ på fliken **lösningar** i administratörs hanteraren. Lär dig mer om hur [du filtrerar en trädvy](../compliance/compliance-manager-setup.md#filtering-your-dashboard-view).

- De relativa prioriteterna för förbättrings åtgärder som identifieras i Compliance Manager bör betraktas som en del av en bredare risk granskning tillsammans med data integritets risken som du har fastställt för organisationen.

- Till och med förbättrings åtgärd agg regering på flera reglerings krav, om mallarna för regelverk för GDPR, LGPD, CCPA och HIPAA-HITECH är markerade visas kanske inte nästan 400 förbättrings åtgärder i Compliance Manager. För att bättre kunna klara av den här långa listan kan du använda filtret förbättrings åtgärd för att minska resultatet till en mer hanterbar lista.

- Med filtret kategorier kan du filtrera förbättrings åtgärder efter logisk gruppering, vilka spåret, förhindra, skydda, behålla och undersöka artiklar i den här generella lösningen.

- Vissa av kontrollerna i förbättrings åtgärderna kan anses vara direkt knutna till en specifik reglerings artikel, medan andra kontroller kan vara mer indirekt kopplade till en förordnings anda och många gånger är det helt enkelt rekommenderade aktiviteter eller bästa praxis.