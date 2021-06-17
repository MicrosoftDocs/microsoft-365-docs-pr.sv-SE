---
title: Kom igång med hantering av insiderrisker
description: Konfigurera Insider-riskhantering i din organisation.
keywords: Microsoft 365, hantering av insiderrisk, riskhantering, efterlevnad
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 18d6079141d7fe0cd5b4c7187f51e5fa7079b844
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998758"
---
# <a name="get-started-with-insider-risk-management"></a>Kom igång med hantering av insiderrisker

Använd insider-principer för riskhantering för att identifiera riskfyllda aktiviteter och hanteringsverktyg för att agera på riskvarningar i organisationen. Utför följande steg för att konfigurera förutsättningar och konfigurera en princip för insider-riskhantering.

>[!IMPORTANT]
>Microsoft 365 Insider-riskhanteringslösningen tillhandahåller ett alternativ på klientorganisationsnivå som hjälper kunder att främja intern styrning på användarnivå. Administratörer på innehavarnivå kan konfigurera behörigheter för att ge åtkomst till den här lösningen för medlemmar i organisationen och konfigurera dataanslutningar i efterlevnadscentret för Microsoft 365 för att importera relevanta data för att stödja identifiering av potentiellt riskabel aktivitet på användarnivå. Kunder bekräftar insikter som är relaterade till den enskilda användarens beteende, karaktär eller prestanda material som relaterar till anställning kan beräknas av administratören och göras tillgänglig för andra i organisationen. Dessutom bekräftar kunder att de måste genomföra en egen fullständig undersökning relaterad till den enskilda användarens beteende, karaktär eller prestanda i material som är relaterad till anställning, och inte bara förlita sig på insikter från insider-riskhanteringstjänsten. Kunder är ensamt ansvariga för att använda Microsoft 365 Insider-riskhanteringstjänsten och alla associerade funktioner eller tjänster i enlighet med alla tillämpliga lagar, inklusive lagar som relaterar till personidentifiering och åtgärder för åtgärder.

Mer information om hur insiderriskpolicyer kan hjälpa dig att hantera risker i din organisation finns i [Insider-riskhantering i Microsoft 365.](insider-risk-management.md)

## <a name="subscriptions-and-licensing"></a>Prenumerationer och licensiering

Innan du börjar med Insider-riskhantering bör du bekräfta din [Microsoft 365-prenumeration](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) och eventuella tillägg. För att komma åt och använda Insider-riskhantering måste din organisation ha någon av följande prenumerationer eller tillägg:

- Microsoft 365 E5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 E3-prenumeration + tillägget Microsoft 365 E5 efterlevnad
- Microsoft 365 E3-prenumeration + tillägget Microsoft 365 E5 Insider Risk Management
- Microsoft 365 A5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 A3-prenumeration + tillägget Microsoft 365 A5 efterlevnad
- Microsoft 365 A3-prenumeration + tillägget Microsoft 365 A5 Insider Risk Management
- Microsoft 365 G5-prenumeration (betald eller utvärderingsversion)
- Microsoft 365 G3-prenumeration + tillägget Microsoft 365 G5 efterlevnad
- Microsoft 365 G3-prenumeration + tillägget Microsoft 365 G5 Insider Risk Management
- Office 365 E3-prenumeration + Enterprise Mobility and Security E3 + Microsoft 365 E5 compliance-tillägget

Användare som ingår i insider-riskhanteringsprinciper måste tilldelas en av licenserna ovan.

Om du inte har ett befintligt Microsoft 365 Enterprise, E5-abonnemang och vill prova insider-riskhantering kan [](https://www.microsoft.com/microsoft-365/enterprise) du lägga till [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) i ditt befintliga abonnemang eller registrera dig för en utvärderingsversion av Microsoft 365 Enterprise E5.

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>Steg 1: Aktivera behörigheter för Insider-riskhantering

>[!Important]
>När du har konfigurerat rollgrupperna kan det ta upp till 30 minuter för rollgruppsbehörigheterna att gälla för tilldelade användare i organisationen.

Det finns fyra rollgrupper som används för att konfigurera behörigheter för hantering av insiderriskhanteringsfunktioner. Om du vill fortsätta med de här konfigurationsstegen måste innehavaradministratörerna först tilldela dig rollgruppen **Insider Risk Management** eller Insider Risk **Management** Admin. För att komma åt och hantera insider-riskhanteringsfunktioner efter den första konfigurationen måste användarna vara medlemmar i minst en rollgrupp för insider-riskhantering.

Beroende på strukturen hos ditt team för efterlevnadshantering finns alternativ för att tilldela användare till specifika rollgrupper för att hantera olika uppsättningar med insider-riskhanteringsfunktioner. Om du  vill visa fliken Behörigheter i Säkerhets- och efterlevnadscenter för Office 365  & och hantera rollgrupper, måste du vara tilldelad till rollgruppen Organisationshantering eller ha rollen *Rollhantering.* Välj bland de här rollgruppsalternativen när du konfigurerar insider-riskhantering:

| **Rollgrupp** | **Rollbehörigheter** |
| :------------- | :------------------- |
| **Insider-riskhantering** | Använd den här rollgruppen för att hantera insider-riskhantering för organisationen i en enda grupp. Genom att lägga till alla användarkonton för angivna administratörer, analytiker, ekonomi och granskare kan du konfigurera behörigheter för Insider-riskhantering i en enda grupp. Den här rollgruppen innehåller alla behörighetsroller för Insider-riskhantering och associerade behörigheter. Den här konfigurationen är det enklaste sättet att snabbt komma igång med insider-riskhantering och är en god passform för organisationer som inte behöver separata behörigheter som definierats för separata användargrupper. När du använder den här konfigurationen bör du se till att alltid ha minst en användare tilldelad till den här rollen för att säkerställa att dina principer fungerar som förväntat och så att användaren kan skapa och redigera principer, konfigurera lösningsinställningar och granska hälsovarningar för principer.|
| **Insider-riskhanteringsadministratör** | Använd den här rollgruppen när du först konfigurerar Insider-riskhantering och senare för att dela upp Insider-riskadministratörer i en definierad grupp. Användare i den här rollgruppen kan aktivera och visa analysinsikter och skapa, läsa, uppdatera och ta bort principer för insider-riskhantering, globala inställningar och tilldelningar av rollgrupper. När du använder den här konfigurationen bör du se till att alltid ha minst en användare tilldelad till den här rollen för att säkerställa att dina principer fungerar som förväntat och så att användaren kan skapa och redigera principer, konfigurera lösningsinställningar och granska hälsovarningar för principer. |
| **Analytiker för hantering av interna risker** | Använd den här gruppen för att tilldela behörigheter till användare som fungerar som insider-riskfallsanalytiker. Användare i den här rollgruppen kan komma åt och visa alla varningar för Insider-riskhantering, fall, analysinsikter och meddelandemallar. De kan inte komma åt Insider-risken i Innehållsutforskaren. |
| **Utredare för hantering av interna risker** | Använd den här gruppen för att tilldela behörigheter till användare som ska agera som insider-riskgruppsbehörigheter. Användare i den här rollgruppen kan komma åt alla varningar för insider-riskhantering, ärenden, meddelandemallar och Innehållsutforskaren för alla ärenden. |
| **Insider-riskhanteringsgranskningar** | Använd den här gruppen för att tilldela behörigheter till användare som ska granska aktiviteter inom insider-riskhantering. Användare i den här rollgruppen kan komma åt granskningsloggen för Insider-risker. |

> [!NOTE]
> De här rollgrupperna stöds för närvarande inte i PIM (Privileged Identity Management). Mer information om PIM finns i Tilldela [Azure AD-roller i Behörighetsidentitetshantering.](/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Lägga till användare i en rollgrupp för Insider-riskhantering

Utför följande steg för att lägga till användare i en rollgrupp för Insider-riskhantering:

1. Logga in [https://protection.office.com/permissions](https://protection.office.com/permissions) med autentiseringsuppgifter för ett administratörskonto i din Microsoft 365-organisation.

2. I &amp; Säkerhetsefterlevnadscenter går du till **Behörigheter.** Välj länken för att visa och hantera roller i Office 365.

3. Välj den rollgrupp för Insider-riskhantering som du vill lägga till användare i och välj **sedan Redigera rollgrupp.**

4. Välj **Välj medlemmar** i det vänstra navigeringsfönstret och välj sedan **Redigera**.

5. Välj **Lägg** till och markera sedan kryssrutan för alla användare som du vill lägga till i rollgruppen.

6. Välj **Lägg** till och välj sedan **Klar**.

7. Välj **Spara** för att lägga till användare i rollgruppen. Välj **Stäng** för att slutföra stegen.

## <a name="step-2-enable-the-microsoft-365-audit-log"></a>Steg 2: Aktivera Microsoft 365-granskningsloggen

Insider-riskhantering använder Microsoft 365-granskningsloggar för användarinsikter och aktiviteter som identifieras i principer och analysinsikter. Microsoft 365-granskningsloggarna är en sammanfattning av alla aktiviteter inom organisationen och insider-riskhanteringsprinciper kan använda dessa aktiviteter för att generera principinsikter.

Stegvisa instruktioner för hur du aktiverar granskning finns i [Aktivera eller inaktivera granskningsloggsökning.](turn-audit-log-search-on-or-off.md) När du aktiverar granskningen visas ett meddelande om att granskningsloggen förbereds och att du kan köra en sökning om några timmar efter att förberedelserna har slutförts. Du behöver bara göra den här åtgärden en gång. Mer information om hur du använder Microsoft 365-granskningsloggen finns i [Söka i granskningsloggen.](search-the-audit-log-in-security-and-compliance.md)

## <a name="step-3-enable-and-view-insider-risk-analytics-insights-optional"></a>Steg 3: Aktivera och visa insikter om Insider-riskanalyser (valfritt)

Med Insider-riskhanteringsanalyser kan du göra en utvärdering av potentiella Insider-risker i organisationen utan att konfigurera insiderriskprinciper. Denna utvärdering kan hjälpa din organisation att identifiera potentiella områden med högre användarrisk och hjälpa till att bestämma typen och omfattningen av principer för hantering av insiderrisk som du kan överväga att konfigurera. Den här utvärderingen kan också hjälpa dig att fastställa behov av ytterligare licensiering eller framtida optimering av befintliga principer. Analyssökningsresultaten kan ta upp till 48 timmar innan insikterna är tillgängliga som rapporter för granskning. Mer information om analysinsikter finns i Inställningar för [Insider-riskhantering: Analys (förhandsversion)](insider-risk-management-settings.md#analytics-preview) och titta på videon om Insider Risk Management Analytics för att bättre förstå hur analyser kan hjälpa dig att identifiera potentiella [Insider-risker](https://www.youtube.com/watch?v=5c0P5MCXNXk) och hjälpa dig att snabbt vidta åtgärder.

För att aktivera Insider risk Analytics måste du vara medlem i rollgruppen *för Insider-riskhantering,* *Insider-riskhanteringsadministratör* eller Microsoft 365 global administratör. 

Utför följande steg för att aktivera Insider Risk Analytics:

1. Gå till [Insider-riskhantering i Microsoft 365](https://compliance.microsoft.com) **efterlevnadscenter.**
2. Välj **Kör genomsökning** på **fliken Översikt över Insider-risker** i din **organisation.** Den här åtgärden aktiverar analyssökning för organisationen. Du kan också aktivera genomsökning i organisationen genom att gå till **Insider-riskinställningar** Analys (förhandsversion) och aktivera Genomsökning av klientorganisationens användaraktivitet för att  >   identifiera **potentiella Insider-risker.**
3. I **informationsfönstret Analys** väljer du **Kör genomsökning för att starta sökningen för din organisation**. Analyssökningsresultaten kan ta upp till 24 timmar innan insikterna är tillgängliga som rapporter för granskning.

När du har granskat analysinsikterna väljer du insiderriskprinciper och konfigurerar de associerade förutsättningarna för att bäst uppfylla organisationens strategi för insiderrisker.

## <a name="step-4-configure-prerequisites-for-policies"></a>Steg 4: Konfigurera krav för principer

De flesta insider-riskhanteringsprinciper har krav som måste konfigureras för policyindikatorer för att generera relevanta aktivitetsaviseringar. Konfigurera nödvändiga krav beroende på vilka principer du planerar att konfigurera för din organisation.

### <a name="configure-microsoft-365-hr-connector"></a>Konfigurera Microsoft 365 HR-koppling

Insider-riskhantering har stöd för import av användar- och loggdata som importerats från tredjepartsplattformar för riskhantering och personalavdelningen. Med datakopplingen för Microsoft 365 Human Resources (HR) kan du hämta personaldata från CSV-filer, inklusive uppsägningsdatum för användare, sista anställningsdatum, meddelanden om planen för prestandaförbättringar, åtgärder för prestationsgranskning och status för ändring på arbetsnivå. Dessa data hjälper till att skapa varningsindikatorer i insider-riskhanteringsprinciper och är en viktig del av konfigurationen av den fullständiga riskhanteringstäckningen i organisationen. Om du konfigurerar fler än en HR-koppling för organisationen hämtar Insider-riskhantering automatiskt indikatorer från alla HR-kopplingar.

Microsoft 365 HR-kopplingen krävs när du använder följande principmallar:

- Avgående användardatastöld
- Överträdelser av säkerhetsprincip av användare som slutar
- Överträdelse av säkerhetsprincip av en missnöjd användare
- Dataläckage av missnöjda användare

Stegvisa [anvisningar för hur du](import-hr-data.md) konfigurerar Microsoft 365 HR-kopplingen för din organisation finns i artikeln Konfigurera en koppling för HR-data för din organisation. När du har konfigurerat HR-kopplingen återgår du till de här konfigurationsstegen.

### <a name="configure-data-loss-prevention-dlp-policies"></a>Konfigurera DLP-principer (Data Loss Prevention)

Insider-riskhantering kan användas med DLP-principer för att identifiera avsiktlig eller oavsiktlig exponering av känslig information för oönskade parter för DLP-varningar med hög allvarlighetsnivå. När du konfigurerar en Insider-riskhanteringsprincip med någon av **mallarna** för Dataläckor måste du tilldela en specifik DLP-princip till principen.

DLP-principer hjälper till att identifiera användare för att aktivera riskbedömning i insider-riskhantering för hög allvarlighetsgrad DLP-varningar för känslig information och är en viktig del av konfigurationen av fullständig riskhanteringstäckning i organisationen. Mer information om Insider-riskhantering och integrering med DLP-principer och överväganden vid planering finns i [Insider-principer för riskhantering.](insider-risk-management-policies.md#general-data-leaks)

>[!IMPORTANT]
>Kontrollera att du har slutfört följande:
>
>- Du förstår och konfigurerar användarnas omfattning i både DLP- och Insider-riskhanteringsprinciperna så att de ger den täckning du förväntar dig.
>- Kontrollera att inställningen **för incidentrapporter** i DLP-principen för Insider-riskhantering som används med dessa mallar är konfigurerad för varningar *på* hög allvarlighetsnivå. Varningar för Insider-riskhantering genereras inte från DLP-principer med fältet **Incidentrapporter** inställt på *Låg* eller *Medel.*

En DLP-princip krävs när du använder följande principmallar:

- Allmänna dataläckor
- Dataläckor av prioritetsanvändare

Stegvisa anvisningar för hur du konfigurerar DLP-principer för organisationen finns i artikeln [Skapa,](create-test-tune-dlp-policy.md) testa och finjustera en DLP-princip. När du har konfigurerat en DLP-princip återgår du till de här konfigurationsstegen.

### <a name="configure-priority-user-groups"></a>Konfigurera prioritetsanvändargrupper

Insider-riskhantering innehåller stöd för att tilldela prioriterade användargrupper till principer för att hjälpa användare med unika riskaktiviteter med kritiska positioner, hög datanivå och nätverksåtkomst eller en tidigare historik över riskbeteendet. Att skapa en prioritetsgrupp och tilldela användare till gruppen hjälpomfattningsprinciper för de unika omständigheter som presenteras av dessa användare.

En prioritetsgrupp krävs när följande principmallar används:

- Överträdelser av säkerhetsprincip av prioritetsanvändare
- Dataläckor av prioritetsanvändare

I artikeln [Komma igång med inställningar för insider-riskhantering](insider-risk-management-settings.md#priority-user-groups-preview) finns stegvisa instruktioner om hur du skapar en prioriterad användargrupp. När du har konfigurerat en prioritetsgrupp går du tillbaka till konfigurationsstegen.

### <a name="configure-physical-badging-connector-optional"></a>Konfigurera fysisk badging-koppling (valfritt)

Insider-riskhantering har stöd för import av användar- och loggdata från fysiska kontroll- och åtkomstplattformar. Med den fysiska badgingkopplingen kan du hämta åtkomstdata från JSON-filer, inklusive användar-ID, åtkomstpunkts-ID, åtkomsttid och datum samt åtkomststatus. Dessa data hjälper till att skapa varningsindikatorer i insider-riskhanteringsprinciper och är en viktig del av konfigurationen av den fullständiga riskhanteringstäckningen i organisationen. Om du konfigurerar fler än en fysisk badging-koppling för organisationen hämtar Insider-riskhantering automatiskt indikatorer från alla fysiska badging-kopplingar. Information från Fysiska tillägg till andra Insider-risker-signaler när du använder alla mallar för Insider-riskpolicyer.

>[!IMPORTANT]
>För att insider-riskhanteringsprinciper ska använda och korrelera signaldata relaterade till avgående och uppsagda användare med händelsedata från din fysiska kontroll och åtkomstplattformar måste du också konfigurera Microsoft 365 HR-kopplingen. Om du aktiverar den fysiska anslutningen för fysisk aktivitet utan att aktivera Microsoft 365 HR-kopplingen bearbetar insiders riskhanteringsprinciper endast händelser för obehörig fysisk åtkomst för användare i organisationen.

Stegvisa [anvisningar](import-physical-badging-data.md) för hur du konfigurerar kopplingen Fysiskt dåligt för din organisation finns i artikeln Konfigurera en koppling för fysisk aktivitet för din organisation. När du har konfigurerat kopplingen återgår du till de här konfigurationsstegen.

### <a name="configure-microsoft-defender-for-endpoint-optional"></a>Konfigurera Microsoft Defender för slutpunkt (valfritt)

[Microsoft Defender för Endpoint är](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) en säkerhetsplattform för företag som utformats för att hjälpa företagsnätverk att förhindra, upptäcka, undersöka och hantera avancerade hot. Om du vill se säkerhetsöverträdelser bättre i organisationen kan du importera och filtrera Defender för slutpunktsaviseringar för aktiviteter som används i principer som skapats från mallar för säkerhetsöverträdelser för Insider-riskhantering.

Om du skapar principer för säkerhetsbrott måste du ha Microsoft Defender för slutpunkt konfigurerad i organisationen och aktivera Defender för Slutpunkt för insider-riskhanteringsintegrering i Defender Säkerhetscenter för att importera säkerhetsöverträdelser. Mer information om krav finns i artikeln [Minimikrav för Microsoft Defender för slutpunkter.](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)

I artikeln [Konfigurera avancerade funktioner i Defender](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) för slutpunkt finns stegvisa anvisningar för hur du konfigurerar Defender för Slutpunkt för insider-riskhanteringsintegrering. När du har konfigurerat Microsoft Defender för slutpunkten återgår du till de här konfigurationsstegen.

## <a name="step-5-configure-insider-risk-settings"></a>Steg 5: Konfigurera inställningar för Insider-risker

[Insider-riskinställningar](insider-risk-management-settings.md) gäller för alla principer för Insider-riskhantering, oavsett vilken mall du valde när du skapar en princip. Inställningar konfigureras med hjälp av **kontrollen för Insider-risker** som finns längst upp på alla flikar för Insider-riskhantering. De här inställningarna styr sekretess, indikatorer, övervakning av fönster och intelligenta identifieringar.

Innan du konfigurerar en princip definierar du följande inställningar för Insider-risker:

1. I [Microsoft 365 efterlevnadscenter](https://compliance.microsoft.com)går du till **Insider-riskhantering** och väljer Inställningar för **Insider-risker** i det övre högra hörnet på valfri sida.
2. På sidan **Sekretess** väljer du en sekretessinställning för att visa användarnamn för principaviseringar.
3. På sidan **Indikatorer** markerar du de aviseringsindikatorer som du vill tillämpa på alla insiderriskprinciper.

    >[!IMPORTANT]
    >Om du vill få aviseringar om riskabel aktivitet som definieras i principerna måste du välja en eller flera indikatorer. Om indikatorerna inte har konfigurerats i Inställningar kan inte indikatorerna väljas i Insider-riskprinciper.

4. På sidan **Princip tidsramar** väljer [](insider-risk-management-settings.md#policy-timeframes) du de tidsramar för principen som ska gälla för en användare när de utlöser en matchning för en insider-riskprincip.
5. På sidan **Intelligenta identifieringar** konfigurerar du följande inställningar för Insider-riskprinciper:
    - [Undantag för filtyp](insider-risk-management-settings.md#file-type-exclusions)
    - [Tröskelvärden för ovanlig filaktivitet](insider-risk-management-settings.md#threshold-for-unusual-file-activity)
    - [Aviseringsvolymnivå](insider-risk-management-settings.md#alert-volume)
    - [Aviseringsstatus för Microsoft Defender för slutpunkt](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [Domäninställningar](insider-risk-management-settings.md#domains-preview)
6. På sidan **Export-aviseringar** kan du aktivera export av information om Insider-riskvarningar med hjälp av Office 365-hanterings-API:er om det behövs.
7. På sidan **Prioritet för användargrupper** skapar du en prioritetsgrupp för användare och lägger till användare om de inte har skapats **i steg 3.**
8. På sidan **Power Automate-flöden** konfigurerar du ett flöde från mallar för Insider-riskflöden eller skapar ett nytt flöde. Stegvisa [anvisningar finns i](insider-risk-management-settings.md#power-automate-flows-preview) artikeln Komma igång med inställningar för insider-riskhantering.
9. På sidan **Prioritetstillgångar konfigurerar** du prioritetstillgångar för att använda data från din fysiska kontroll och åtkomstplattform som importerats av kopplingen Fysiskt dåligt. Stegvisa [anvisningar finns i](insider-risk-management-settings.md#priority-physical-assets-preview) artikeln Komma igång med inställningar för insider-riskhantering.
10. På microsoft **Teams-sidan** kan du aktivera Microsoft Teams-integrering med Insider-riskhantering för att automatiskt skapa ett team för samarbete i fall eller användare. Stegvisa [anvisningar finns i](insider-risk-management-settings.md#microsoft-teams-preview) artikeln Komma igång med inställningar för insider-riskhantering.
11. Välj **Spara** för att aktivera de här inställningarna för dina Insider-riskprinciper.

## <a name="step-6-create-an-insider-risk-management-policy"></a>Steg 6: Skapa en princip för insider-riskhantering

Insider-riskhanteringsprinciper omfattar tilldelade användare och definierar vilka typer av riskindikatorer som ska konfigureras för varningar. Innan aktiviteter kan utlösa aviseringar måste en princip konfigureras. Använd principguiden för att skapa nya principer för insider-riskhantering.

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com) går du till **Hantering av insiderrisk** och väljer fliken **Princip**.
2. Välj **Skapa princip** för att öppna principguiden.
3. På sidan **Principmall** väljer du en principkategori och väljer sedan mallen för den nya principen. De här mallarna består av villkor och indikatorer som definierar den riskaktivitet du vill identifiera och undersöka. Granska förutsättningarna, utlösande händelser och upptäckta aktiviteter flr mallen för att bekräfta att denna principmall passar dina behov.

    >[!IMPORTANT]
    >Vissa principmallar har förutsättningar som måste konfigureras för att principen ska generera relevanta varningar. Om du inte har konfigurerat tillämpliga principförutsättningar, se **Steg 4** ovan.

4. Gå vidare genom att klicka på **Nästa.**
5. På sidan **Namn och beskrivning** färdigställer du följande fält:
    - **Namn (obligatoriskt)**: Ange ett eget namn på principen. Namnet kan inte ändras när principen har skapats.
    - **Beskrivning (valfritt)**: Ange en valfri beskrivning av principen.

6. Gå vidare genom att klicka på **Nästa.**
7. På sidan **Användare och grupper** väljer du **Inkludera alla användare och grupper** eller **Inkludera specifika användare och grupper** för att definiera vilka användare eller grupper som är inkluderade i principen, eller välj **Lägg till eller redigera prioriterade användargrupper** om du har valt en mall som är baserad på prioriterade användare. Genom att välja **Inkludera alla användare och grupper** kommer den att leta efter utlösande händelser för alla användare och grupper i din organisation för att börja tilldela riskpoäng för principen. Genom att välja **Inkludera specifika användare och grupper** kan du definiera vilka användare och grupper som ska tilldelas till principen.
8. Gå vidare genom att klicka på **Nästa.**
9. På sidan **Innehåll som ska prioriteras** kan du tilldela (vid behov) källorna som ska prioriteras, vilket ökar möjligheten till att generera en varning om hög allvarlighet för dessa källor. Välj ett av följande alternativ:

    - **Jag vill ange SharePoint-webbplatser, känslighetsetiketter och/eller känslig information som prioriterade innehåll**. Om du väljer det här alternativet aktiveras informationssidor i guiden för att konfigurera dessa kanaler.
    - **Jag vill inte ange prioriterat innehåll just nu (du kan göra det när principen har skapats)**. Om du väljer detta alternativ hoppar du över sidorna med kanalinformation i guiden.

10. Gå vidare genom att klicka på **Nästa.**

11. Om du i föregående steg valde **Jag vill ange SharePoint-webbplatser, känslighetsetiketter och/eller typer av känslig information som prioriterat innehåll**, kommer du att se informationssidorna för *SharePoint-webbplatser*, *Typer av känslig information* och *Känslighetsetiketter*. Använd dessa informationssidor för att definiera SharePoint, typer av känslig information och känslighetsetiketter som ska prioriteras i principen.

    - **SharePoint-webbplatser**: Välj **Lägg till SharePoint-webbplats** och välj SharePoint-webbplatserna som du har tillgång till och som du vill prioritera. Till exempel *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Typ av känslig information**: Välj **Lägg till typ av känslig information** och välj känslighetstyperna som du vill prioritera. Till exempel *“Amerikanskt bankkontonummer”* och *“Kreditkortsnummer”*
    - **Känslighetsetiketter**: Välj **Lägg till känslighetsetikett** och välj etiketterna som du vill prioritera. Till exempel *“Konfidentiell”* och *“Hemlighet”*.

12. Gå vidare genom att klicka på **Nästa.**
13. På sidan **Indikatorer och utlösande händelser** kommer du att se [indikatorerna](insider-risk-management-settings.md#indicators) som du har definierat som tillgängliga på sidan **Inställningar för insiderrisk** > **Indikatorer**. Om du valde en mall för *Dataläckor* i början av guiden måste du välja en DLP-princip i **DLP-principens** nedrullningsbara lista för att aktivera utlösande indikatorer för principen eller välja den inbyggda utlösande händelsen.

    >[!IMPORTANT]
    >Om indikatorer på den här sidan inte kan väljas måste du välja de indikatorer som du vill aktivera för alla principer. Du kan använda knappen **Aktivera indikatorer** i guiden eller välja indikatorerna på sidan **Hantering av insiderrisk** > **Inställningar** > **Principindikatorer**.

    Välj de indikatorer som du vill tillämpa på principen. Om du föredrar att inte använda principens standardtrösklar för dessa indikatorer, inaktivera **Använd standardtrösklar som rekommenderas av Microsoft** och ange tröskelvärdena för varje vald indikator.

    - Om du har valt minst en *Office-* eller *Enhetsindikator*, väljer du **Förstärkare av riskpoäng** efter behov. Förstärkare av riskpoäng kan endast användas på valda indikatorer.
    - Om du har valt en av principmallarna *Datastöld* eller *Dataläckor*, väljer du en eller flera metoder för **Sekvensidentifiering** och en metod för **Identifiering av kumulativ dataexfiltrering** för principen.

14. Gå vidare genom att klicka på **Nästa.**
15. På sidan **Tröskelvärden för indikatorn** väljer du alternativet att använda standardindikatortrösklar eller att specificera anpassade trösklar för enskilda indikatorer. Välj lämplig nivå för varje indikator för att generera önskad nivå av aktivitetsvarningar.
16. Gå vidare genom att klicka på **Nästa.**
17. På sidan **Granskning** granskar du inställningarna du har valt för principen och eventuella förslag eller varningar för dina val. Välj **Redigera** för att ändra något av principvärdena eller välj **Skicka** för att skapa och aktivera policyn.

## <a name="next-steps"></a>Nästa steg

När du har slutfört de här stegen för att skapa din första insider-riskhanteringspolicy börjar du få aviseringar från aktivitetsindikatorer efter ungefär 24 timmar. Konfigurera ytterligare principer efter behov med hjälp av anvisningarna i steg 4 i den här artikeln eller stegen i [Skapa en ny Insider-riskprincip.](insider-risk-management-policies.md#create-a-new-policy)

Mer information om hur du undersöker insiderriskvarningar **och instrumentpanelen** aviseringar finns i [Varningar för Insider-riskhanteringsvarningar.](insider-risk-management-alerts.md)
