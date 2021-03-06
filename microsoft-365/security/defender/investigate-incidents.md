---
title: Undersöka ärenden i Microsoft 365 Defender
description: Undersök incidenter relaterade till enheter, användare och postlådor.
keywords: incidenter, incidenter, analysera, svar, datorer, enheter, användare, identiteter, e-post, e-post, postlåda, undersökning, diagram, bevis
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105362"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Undersöka ärenden i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från olika enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.

Inom en incident analyserar du aviseringarna som påverkar nätverket, förstår vad de betyder och sorterar bevisen så att du kan skapa en gällande åtgärdsplan.

## <a name="initial-investigation"></a>Inledande undersökning

Innan du börjar med detaljerna tar du en titt på egenskaperna och sammanfattningen av händelsen.

Du börjar genom att välja incidenten i bockkolumnen. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exempel på val av incident i bockkolumnen":::

När du gör det öppnas ett sammanfattningsfönster med viktig information om händelsen, till exempel allvarlighetsgrad, som den har tilldelats, och [kategorierna MITRE ATT &trade;&CK](https://attack.mitre.org/) för händelsen. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exempel på sammanfattningsfönstret för ett incident":::

Härifrån kan du välja **Öppna incidentsida.** Då öppnas huvudsidan för incidenten där du hittar mer sammanfattande information och flikar för aviseringar, enheter, användare, undersökningar och bevis.

Du kan också öppna huvudsidan för en händelse genom att välja incidentnamnet från incidentkön.

## <a name="summary"></a>Sammanfattning

**Sammanfattningssidan** ger en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain. Precis som för andra Microsoft-Microsoft 365 Defender är den i linje med [MITRE &trade; ATT&CK-ramverket.](https://attack.mitre.org/)

I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen. Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.

På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.

Och sista – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du direkt kan identifiera om någon åtgärd krävs av dig.

Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge kunskap om de viktigaste egenskaperna för incidenten som du bör känna till.

## <a name="alerts"></a>Varningar

På fliken **Avisering** kan du visa aviseringskön för aviseringar om händelsen och annan information om dem, till exempel:

- Allvarlighetsgrad.
- Enheterna som var inblandade i aviseringen.
- Varningens källa (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365).
- Orsaken till att de var länkade till varandra.

Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exempel på en aviseringssida för ett incident":::

Som standard sorteras aviseringarna kronologiskt så att du kan se hur händelsen spelats ut med tiden. När du väljer en avisering i en Microsoft 365 Defender visas den aviseringsinformation som är specifik för den övergripande händelsen. 

Du kan se händelser för aviseringen, vilket andra utlöste aviseringar orsakade den aktuella aviseringen och alla berörda enheter och aktiviteter som var inblandade i attacken, inklusive filer, användare och postlådor.

Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Exempel på en sida med aviseringsinformation i ett incident":::

Den här aviseringssidan för incidenter består av följande avsnitt:

- Aviseringsartikel, som innehåller en sammanfattning av vad som har hänt
- Relaterade händelser och aviseringar
- Sammanfattningsinformation

Lär dig hur du använder aviseringskön och aviseringssidorna [i undersöker aviseringar](investigate-alerts.md).

## <a name="devices"></a>Enheter

På **fliken** Enheter visas alla enheter som är relaterade till händelsen. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Sidan Enheter för ett incident":::

Du kan markera bockmarkeringen för en enhet om du vill visa information om enheten, katalogdata, aktiva aviseringar och inloggade användare. Välj namnet på enheten för att visa enhetsinformation i Microsoft Defender för endpoints enhetslager.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exempel på en enhetssida för Microsoft Defender för slutpunkter":::

På sidan enhet kan du samla in ytterligare information om enheten, till exempel alla aviseringar, en tidslinje och säkerhetsrekommendationer. På fliken Tidslinje  kan du till exempel bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.

> [!TIP]
> Du kan göra genomsökningar på begäran på en enhet. I säkerhetscentret Microsoft 365 du Slutpunkter **för > Enhetsinventering**. Välj en enhet med aviseringar och kör sedan en antivirussökning. Åtgärder, till exempel antivirusskanningar, spåras och visas på sidan **Enhetsinventering.** Mer information finns i [Kör Microsoft Defender Antivirus sökning på enheter](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Användare

På **fliken** Användare visas alla användare som har identifierats vara en del av eller relaterade till händelsen. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exempel på en sida för användare för ett incident":::

Du kan välja bockmarkeringen för en användare om du vill se information om hot om användarkontot, exponering och kontaktinformation. Välj användarnamnet om du vill se mer information om användarkontot.

Lär dig hur du visar ytterligare användarinformation och hanterar användare av en händelse i [undersöker användare.](investigate-users.md)


## <a name="mailboxes"></a>Postlådor

På **fliken Postlådor** visas alla postlådor som har identifierats vara en del av eller relaterade till händelsen. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exempel på en postlådesida för ett incident":::

Du kan välja bockmarkeringen för en postlåda om du vill visa en lista med aktiva aviseringar. Välj postlådans namn om du vill se ytterligare information om postlådan på sidan i Utforskaren för Microsoft Defender Office 365.

## <a name="investigations"></a>Undersökningar

På **fliken Undersökningar** finns alla automatiserade undersökningar [som](m365d-autoir.md) utlösts av aviseringar om den här händelsen. Undersökningarna utför åtgärder eller väntar på att analytiker har godkänt åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exempel på en sida för undersökningar för en incident":::

Välj en undersökning för att navigera till dess informationssida för fullständig information om undersöknings- och åtgärdsstatus. Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Historik för **väntande** åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.

Det finns även fliken **Undersökningsdiagram** som visar:

- Kopplingen av aviseringar till de påverkade tillgångarna i organisationen.
- Vilka enheter är relaterade till vilka aviseringar och hur de är en del av attackens historia.
- Aviseringarna om händelsen.

Med hjälp av undersökningsdiagrammet kan du snabbt förstå den fullständiga omfattningen av attacken genom att ansluta olika misstänkta enheter som är en del av attacken till sina relaterade tillgångar, till exempel användare, enheter och postlådor. 

Mer information finns i [Automatiserad undersökning och svar i Microsoft 365 Defender](m365d-autoir.md).

## <a name="evidence-and-response"></a>Bevis och svar

På **fliken Bevis och** svar visas alla händelser som stöds och misstänkta enheter i aviseringarna för incidenten. Här är ett exempel.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exempel på en sida med bevis och svar för ett incident":::

Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga e-postmeddelanden, filer, processer, tjänster, IP-adresser med mera. På så sätt kan du snabbt identifiera och blockera potentiella hot i händelsen.

Var och en av de analyserade enheterna är markerade med en bedömning (skadlig, misstänkt, ren) och en åtgärdsstatus. På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som kan göras härnäst.

## <a name="next-steps"></a>Nästa steg

Vid behov:

- [Undersök aviseringarna om en händelse](investigate-alerts.md)
- [Undersöka användarna av ett problem](investigate-users.md)

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)

