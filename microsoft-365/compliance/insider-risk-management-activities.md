---
title: Undersöka Insider-riskhanteringsaktiviteter
description: Läs mer om att undersöka insider-riskhanteringsaktiviteter i Microsoft 365
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
ms.openlocfilehash: b4b770733b9e62b39a07c8699619ac5f7d692ec5
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327131"
---
# <a name="investigate-insider-risk-management-activities"></a>Undersöka Insider-riskhanteringsaktiviteter

Att undersöka riskfyllda användaraktiviteter är ett viktigt första steg för att minimera Insider-risker för organisationen. Dessa risker kan vara aktiviteter som genererar varningar från principer för Insider-riskhantering, eller risker från aktiviteter som identifieras av principer men inte omedelbart skapar en varning för insiderriskhantering för användarna. Du kan undersöka dessa typer av aktiviteter med hjälp av **användaraktivitetsrapporterna (förhandsversionen)** eller med **instrumentpanelen Avisering.**

## <a name="user-activity-reports-preview"></a>Användaraktivitetsrapporter (förhandsversion)

Med användaraktivitetsrapporter kan du undersöka aktiviteter för specifika användare under en viss tidsperiod utan att behöva tilldela dem tillfälligt eller uttryckligen till en princip för Insider-riskhantering. I de flesta scenarier med insider-riskhantering definieras användarna uttryckligen i principer och de kan ha principvarningar (beroende på utlösande händelser) och riskpoäng som associeras med aktiviteterna. Men i vissa fall kanske du vill undersöka aktiviteterna för användare som inte uttryckligen definierats i en princip. Det kan vara användare som du har fått ett tips om användaren och potentiellt riskfyllda aktiviteter, eller användare som normalt inte behöver tilldelas till en princip för insider-riskhantering.

När du har konfigurerat indikatorer på sidan för **Insider-riskhantering Inställningar** identifieras användaraktivitet för riskabel aktivitet kopplad till de valda indikatorerna. Du behöver inte konfigurera en princip för användaraktivitetsrapporter för att identifiera och rapportera riskfyllda aktiviteter av användare i organisationen. Aktiviteter som ingår i användaraktivitetsrapporter kräver inte utlösande händelser för att aktiviteterna ska visas. Den här konfigurationen innebär att all upptäckt aktivitet för användaren är tillgänglig för granskning, oavsett om den har en utlösande händelse eller om den skapar en avisering. Rapporter skapas per användare och kan innehålla alla aktiviteter under en anpassad 90-dagarsperiod. Flera rapporter för samma användare stöds inte.

När du granskat aktiviteter för en användare kan undantag från enskilda aktiviteter avvisas som enstaka aktiviteter som en enstaka aktivitet, dela eller skicka en länk till rapporten via e-post med andra affärsverksamheter, eller välja att tilldela användaren tillfälligt eller uttryckligen en princip för insider-riskhantering. Användarna måste ha tilldelats rollen *Rollgrupp för insiderriskhanteringsroller* för att kunna visa **sidan Användaraktivitetsrapporter.**  

![Översikt över användaraktivitetsrapport för Insider-riskhantering](../media/insider-risk-user-activity-report-overview.png)

Du kan komma igång genom att **välja Hantera rapporter** i avsnittet Undersök **användaraktivitet** på sidan Översikt över **Insider-riskhantering.** Om du vill visa aktiviteter för en användare väljer **du först Skapa användaraktivitetsrapport** och fyller i följande fält i **rapportfönstret Ny användaraktivitet:**

- **Användare:** Sök efter en användare efter namn eller e-postadress
- **Startdatum:** Använd kalenderkontrollen till att välja startdatum för användaraktiviteter.
- **Slutdatum:** Använd kalenderkontrollen till att välja slutdatum för användaraktiviteter. Det valda slutdatumet måste vara längre än två dagar efter det valda startdatumet och högst 90 dagar från det valda startdatumet.
Det brukar ta upp till 10 timmar innan nya rapporter är klara för granskning. När rapporten är klar ser du Rapport *klar i* kolumnen **Status** på sidan Användaraktivitetsrapport. Välj användaren för att visa den detaljerade rapporten:

![Användaraktivitetsrapport för Insider-riskhantering](../media/insider-risk-user-activity-report.png)

**Användaraktivitetsrapporten för den** valda användaren innehåller flikarna **Användaraktivitet och** **Aktivitetsutforskaren:**

- **Användaraktivitet:** Använd den här diagramvyn för att undersöka aktiviteter och visa potentiella aktiviteter som inträffar i sekvenser. Den här fliken är strukturerad för att möjliggöra snabb granskning av ett ärende, inklusive en historisk tidslinje för alla aktiviteter, aktivitetsinformation, aktuell riskinformation för användaren i ärendet, sekvensen av riskhändelser och filtreringskontroller som hjälper till med det pågående arbetet.
- **Aktivitetsutforskaren:** **Fliken** Aktivitetsutforskaren ger risk att utforska med ett omfattande analysverktyg som innehåller detaljerad information om aktiviteter. Med Aktivitetsutforskaren kan granskare snabbt granska en tidslinje med identifierade riskfyllda aktiviteter och identifiera och filtrera alla riskaktiviteter som associeras med aviseringar. Mer information om hur du använder Aktivitetsutforskaren finns i *avsnittet Aktivitetsutforskaren* längre fram i den här artikeln.

## <a name="alert-dashboard"></a>Avisering instrumentpanelen

Varningar för Insider-riskhantering genereras automatiskt av riskindikatorer som definierats i insider-riskhanteringsprinciper. Dessa varningar ger efterlevnadsanalytiker och efterlevnadsanalytiker en uppsyn över den aktuella riskstatusen och gör det möjligt för organisationen att hantera och vidta åtgärder för identifierade risker. Som standard genererar principer en viss mängd aviseringar med låg, [](insider-risk-management-settings.md#alert-volume) medel och hög allvarlighetsgrad, men du kan öka eller minska aviseringsvolymen så att den passar dina behov. Du kan dessutom konfigurera tröskelvärdet för [avisering för principindikatorer](insider-risk-management-settings.md#indicator-level-settings-preview) när du skapar en ny princip med principguiden.

Titta på [videon](https://www.youtube.com/watch?v=KgmpxBLJLPI) om trekantiga insiderriskvarningar för en översikt över hur aviseringar ger information, sammanhang och relaterat innehåll för riskabel aktivitet och hur du kan göra din undersökningsprocess mer effektiv.

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

När ärendet har skapats kan finansanalytiker och analytiker hantera och agera på ärendet. Mer information finns i artikeln om [Insider-riskhanteringsfall.](insider-risk-management-cases.md)
