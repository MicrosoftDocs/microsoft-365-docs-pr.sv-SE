---
title: Varningar för Insider-riskhantering
description: Läs mer om varningar för insiderriskhantering i Microsoft 365
keywords: Microsoft 365, insiderrisk, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 0ee3fdf19552ee80737f6758e655d297228c469e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226557"
---
# <a name="insider-risk-management-alerts"></a>Varningar för Insider-riskhantering

Varningar för Insider-riskhantering genereras automatiskt av riskindikatorer som definierats i insider-riskhanteringsprinciper. Dessa varningar ger efterlevnadsanalytiker och efterlevnadsanalytiker en uppsyn över den aktuella riskstatusen och gör det möjligt för organisationen att hantera och vidta åtgärder för identifierade risker. Som standard genererar principer en viss mängd aviseringar med låg, [](insider-risk-management-settings.md#alert-volume) medel och hög allvarlighetsgrad, men du kan öka eller minska aviseringsvolymen så att den passar dina behov. Du kan dessutom konfigurera tröskelvärdet för [avisering för principindikatorer](insider-risk-management-settings.md#indicator-level-settings-preview) när du skapar en ny princip med principguiden.

Titta på [videon](https://www.youtube.com/watch?v=KgmpxBLJLPI) om trekantiga insiderriskvarningar för en översikt över hur aviseringar ger information, sammanhang och relaterat innehåll för riskabel aktivitet och hur du kan göra din undersökningsprocess mer effektiv.

## <a name="alert-dashboard"></a>Avisering instrumentpanelen

På instrumentpanelen för **insiderriskvarningar** kan du visa och agera på varningar som genereras av insiderriskprinciper. Varje rapportwidget visar information för de senaste 30 dagarna.

- **Totalt antal aviseringar som behöver granskas:** Det totala antalet aviseringar som behöver granskas och triangel visas, inklusive en uppdelning efter allvarlighetsgrad för aviseringar.
- **Öppna aviseringar under de senaste 30** dagarna: Det totala antalet aviseringar som skapats med principmatchningar under de senaste 30 dagarna, sorterade efter hög, medium och låg allvarlighetsnivå för aviseringar.
- **Genomsnittlig tid för att lösa aviseringar**: En sammanfattning av användbar aviseringsstatistik:
  - Genomsnittlig tid för att lösa varningar med hög allvarlighetsgrad i timmar, dagar eller månader.
  - Genomsnittlig tid för att lösa aviseringar om medelstor allvarlighetsgrad i timmar, dagar eller månader.
  - Genomsnittlig tid för att lösa aviseringar med låg allvarlighetsgrad i timmar, dagar eller månader.

![Instrumentpanel för insiderriskhanteringsvarning](../media/insider-risk-alerts-dashboard.png)

> [!NOTE]
> Insider-riskhantering använder inbyggd aviseringsbegränsning för att skydda och optimera din riskundersökning och granskningsupplevelse. Den här begränsningen gentemot problem som kan leda till att policymeddelanden överbelastas, till exempel felkonfigurerade datakopplingar eller DLP-principer. På grund av detta kan det uppstå en fördröjning i visningen av nya aviseringar för en användare.

## <a name="alert-status-and-severity"></a>Aviseringsstatus och allvarlighetsgrad

Du kan ändra säkerhetsvarningar till någon av följande statusar:

- **Bekräftad:** En avisering har bekräftats och tilldelats till ett nytt eller befintligt ärende.
- **Avvisad:** En avisering som har avvisats som en man i triageprocessen.
- **Behöver granskas:** En ny avisering där åtgärder för tredriangulering ännu inte har genomförts.
- **Löst**: En avisering som är en del av ett stängt och löst ärende.

Aviseringsriskpoäng beräknas automatiskt utifrån flera riskaktivitetsindikatorer. Indikatorerna omfattar typ av riskaktivitet, antalet och frekvensen för aktivitetshändelsen, historiken över användarriskaktiviteten och tillägg av aktivitet risker som kan öka aktivitetens allvarlighetsnivå. Aviseringsriskresultatet driver programmässiga tilldelningar av en risk allvarlighetsnivå för varje avisering och kan inte anpassas. Om aviseringarna är opåverkade och riskaktiviteterna fortsätter att påföras i aviseringen kan allvarlighetsnivån öka. Riskanalytiker och överensstämmelser kan använda varningarnas allvarlighetsgrad för att underlätta varningar i enlighet med organisationens riskprinciper och standarder.

Aviseringsnivåer med allvarlighetsgrad är:

- **Hög allvarlighetsgrad**: Aktiviteterna och indikatorerna för aviseringen utgör en betydande risk. De associerade riskaktiviteterna är allvarliga, repetitiva och viktiga i hög även andra viktiga riskfaktorer.
- **Medelstor allvarlighetsgrad**: Aktiviteterna och indikatorerna för aviseringen kan utgöra en måttlig risk. De associerade riskaktiviteterna är måttliga, vanliga och har ett samband till andra riskfaktorer.
- **Låg allvarlighetsgrad**: Aktiviteterna och indikatorerna för aviseringen utgör en mindre risk. De associerade riskaktiviteterna är mindre, mer oregelbundna och tar inte endast upp andra viktiga riskfaktorer.

## <a name="filter-alerts-on-the-alert-dashboard"></a>Filtrera aviseringar på instrumentpanelen för aviseringar

Det kan vara svårt att granska en stor kö med aviseringar beroende på antalet och typen av aktiva riskhanteringsprinciper för Insider. Med hjälp av aviseringsfilter kan analytiker och prognoser sortera aviseringar efter flera attribut. Om du vill filtrera aviseringar **på instrumentpanelen Aviseringar** väljer du **filterkontrollen.** Du kan filtrera aviseringar efter ett eller flera attribut:

- **Status:** Välj en eller flera statusvärden om du vill filtrera aviseringslistan. Alternativen är *Bekräftad,* *Avvisad,* *Behöver granska* och *Löst*.
- **Allvarlighetsgrad**: Välj en eller flera varningsnivåer med allvarlighetsgrad om du vill filtrera aviseringslistan. Alternativen är *Hög,* *Medel* och *Låg.*
- **Upptäckt tid:** Välj start- och slutdatum för när aviseringen skapades.
- **Princip:** Välj en eller flera principer för att filtrera aviseringarna som genereras av de valda principerna.

## <a name="search-alerts-on-the-alert-dashboard"></a>Sökaviseringar på instrumentpanelen Avisering

Om du vill söka efter aviseringsnamnet för ett visst ord **väljer du sökkontrollen** och skriver ordet för att söka. Sökresultatet visar alla principvarningar som innehåller ordet som definierats i sökningen.

## <a name="triage-alerts"></a>Triageaviseringar

Så här gör du om du vill ha en insider-riskvarning:

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer **fliken** Aviseringar.
2. På **instrumentpanelen Aviseringar** väljer du den avisering du vill triangel.
3. I **informationsfönstret Aviseringar** kan du granska följande flikar och kontrollera varningen:
    - **Sammanfattning:** Den här fliken innehåller allmän information om aviseringen och du kan bekräfta aviseringen och skapa ett nytt ärende eller stänga aviseringen. Den innehåller aktuell status för aviseringen och allvarlighetsnivån för aviseringen, som anges som *Hög,* *Medium* eller *Låg.* Allvarlighetsnivån kan öka eller minska med tiden om aviseringen inte är triangeld.
        - **Vad har hänt (förhandsversion)**: Visar de tre viktigaste riskaktiviteterna och principmatchningar under utvärderingsperioden för aktiviteten, inklusive den typ av överträdelse som associeras med aktiviteten och antalet förekomster.
        - **Användarinformation:** Visar allmän information om användaren som tilldelats aviseringen. Om anonymisering har aktiverats anonymiseras användarnamn, e-postadress, alias och organisationsfält.
        - **Aviseringsinformation:** Innehåller den tid som gått sedan aviseringen skapades, de principer som genererade aviseringen visas och det ärende som genererades från aviseringen visas. För nya aviseringar visas **Ingen i** fältet Case.
        - **Innehåll som upptäckts (förhandsversion)**: Inkluderar innehåll som associeras med riskaktiviteterna för aviseringen och sammanfattar aktivitetshändelser efter viktiga områden. Om du väljer en aktivitetslänk öppnas Aktivitetsutforskaren och ytterligare information om aktiviteten visas.
    - **Användaraktivitet:** På den här fliken visas aktivitetshistoriken för användaren som är kopplad till aviseringen. Den här historiken omfattar andra varningar och aktiviteter som rör riskindikatorer som definierats i mallen som tilldelats för den här aviseringen. Med hjälp av den här historiken kan riskanalytiker och -analytiker faktors i ett tidigare riskabelt beteende för den anställda som en del av triageprocessen.
    - **Åtgärder:** Följande åtgärder är tillgängliga för varje avisering:
        - **Öppna den utökade vyn:** Öppnar instrumentpanelen **i Aktivitetsutforskaren.**
        - **Bekräfta och skapa ärende:** Använd den här åtgärden för att bekräfta och skapa ett nytt ärende för alla aviseringar som är kopplade till en användare. Den här åtgärden ändrar automatiskt aviseringsstatus *till Bekräftad.*
        - **Stäng avisering:** Använd den här åtgärden till att stänga aviseringen. Den här åtgärden ändrar aviseringsstatus till *Löst*.

## <a name="activity-explorer-preview"></a>Aktivitetsutforskaren (förhandsversion)

> [!NOTE]
> Aktivitetsutforskaren är tillgänglig i området aviseringshantering för användare som utlöser händelser efter att den här funktionen är tillgänglig i din organisation.

Aktivitetsutforskaren tillhandahåller riskprognoser och analytiker med ett omfattande analysverktyg som ger detaljerad information om aviseringar. Med Aktivitetsutforskaren kan granskare snabbt granska en tidslinje med identifierade riskfyllda aktiviteter och identifiera och filtrera alla riskaktiviteter som associeras med aviseringar. Om du vill filtrera aviseringar i Aktivitetsutforskaren väljer du filterkontrollen. Du kan filtrera aviseringar efter ett eller flera attribut som visas i informationsfönstret för aviseringen. Aktivitetsutforskaren har också stöd för anpassningsbara kolumner så att vi och analytiker kan fokusera på instrumentpanelen på den information som är viktigast för dem.

![Översikt över Insider-riskhanteringsaktivitetsutforskaren](../media/insider-risk-activity-explorer.png)

Så här använder du Aktivitetsutforskaren: 

1. I Microsoft 365 Efterlevnadscenter går du till **Insider-riskhantering** och väljer **fliken** Aviseringar.
2. På **instrumentpanelen Aviseringar** väljer du den avisering du vill triangel.
3. I **informationsfönstret Aviseringar väljer** du **Öppna expanderad vy**.
4. På sidan för den valda aviseringen väljer du **fliken Aktivitetsutforskaren.**

När du granskar aktiviteter i Aktivitetsutforskaren kan analytiker välja en viss aktivitet och öppna fönstret med aktivitetsinformation. I fönstret visas detaljerad information om aktiviteten som vi och analytiker kan använda under aviseringsprocessen. Den detaljerade informationen kan ge kontext för aviseringen och hjälpa till att identifiera den fullständiga omfattningen av den riskaktivitet som utlöste aviseringen.

![Information om Insider-riskhanteringsaktivitet i Utforskaren](../media/insider-risk-activity-explorer-details.png)

## <a name="create-a-case-for-an-alert"></a>Skapa ett ärende för en avisering

När aviseringen granskas och triangelts kan du skapa ett nytt ärende för att ytterligare undersöka riskaktiviteten. Skapa ett ärende för en avisering genom att följa de här stegen:

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer **fliken** Aviseringar.
2. På **instrumentpanelen Aviseringar** väljer du den avisering du vill bekräfta och skapar ett nytt ärende för.
3. I **informationsfönstret Aviseringar väljer** du **Åtgärder Bekräfta** aviseringar & skapa  >  **ärende**.
4. I dialogrutan Bekräfta avisering och skapa **insider-riskfall** anger du ett namn för ärendet, väljer användare att lägga till som deltagare och lägger till kommentarer som tillämpliga. Kommentarer läggs automatiskt till i ärendet som en ärendeanteckning.
5. Välj **Skapa ärende om** du vill skapa ett nytt ärende eller välj **Avbryt** för att stänga dialogrutan utan att skapa ett ärende.

När ärendet har skapats kan finansanalytiker och analytiker hantera och agera på ärendet. Mer information [finns i artikeln om Insider-riskhanteringsfall.](insider-risk-management-cases.md)
