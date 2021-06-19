---
title: Ärenden i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor i Microsoft 365 Defender portalen.
keywords: incidenter, aviseringar, undersöker, analyserar, svar, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365, incidentsvar, cyberattack
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028529"
---
# <a name="incidents-in-microsoft-365-defender"></a>Ärenden i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör storyn av en attack. 

Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet. Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack. Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor. Resultatet är flera aviseringar för flera enheter i klientorganisationen. 

Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

Titta på den här korta översikten över incidenter om Microsoft 365 Defender (4 minuter).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack. Du kan till exempel se:

- Var attacken började.
- Vilka taktiker användes.
- Hur långt attacken har varit i din klientorganisation.
- Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades. 
- Alla data som är associerade med attacken.

Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender automatiskt [undersöka och åtgärda](m365d-autoir.md) varningar med hjälp av automatisering och artificiell intelligens. Du kan också utföra ytterligare åtgärdssteg för att lösa attacken. 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a>Incidenter och aviseringar i Microsoft 365 Defender portalen

Du hanterar incidenter **från & och > incidenter** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com) Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 Defender portalen":::

När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 Defender portalen":::

Ytterligare flikar för en händelse är:

- Varningar 

  Alla aviseringar som rör händelsen och deras information.

- Enheter

  Alla enheter som har identifierats vara en del av eller relaterade till händelsen.

- Användare

  Alla användare som har identifierats vara en del av eller relaterade till händelsen.

- Postlådor

  Alla postlådor som har identifierats vara en del av eller relaterade till händelsen.

- Undersökningar

  Alla automatiserade [undersökningar som](m365d-autoir.md) utlösts av aviseringar i händelsen.

- Bevis och svar

  Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.

- Graph (i förhandsgranskning)

  En bild som visar kopplingen av aviseringar till de påverkade tillgångarna i organisationen.

Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 Defender portalen.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en händelse och dess data till flikarna för en händelse i Microsoft 365 Defender portalen":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender

Här är ett exempel på ett arbetsflöde för att svara på incidenter Microsoft 365 med Microsoft 365 Defender portalen.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar. Det här är en kombination av:

- [Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.
- [Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.

1. Påbörja en attack och aviseringsundersökning och analys [för varje händelse:](investigate-incidents.md)
 
   1. Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).

   1. Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).

   1. Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**

   1. Se hur Microsoft 365 Defender har [löst vissa aviseringar](m365d-autoir.md) automatiskt **(fliken Undersökningar).**
   
   1. Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).

2. Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.

3. Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.

4. [Lös](manage-incidents.md#resolve-an-incident) incidenten och ta dig tid för efter incidentinlärning att:

   - Förstå typen av attack och dess påverkan.
   - Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.
   - Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.
   - Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.

Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.

Mer information om åtgärder vid incidenter i microsoft-produkter finns i [den här artikeln.](/security/compass/incident-response-overview)

## <a name="example-security-operations-for-microsoft-365-defender"></a>Exempel på säkerhetsåtgärder för Microsoft 365 Defender

Här är ett exempel på säkerhetsåtgärder (SecOps) för Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

Dagliga uppgifter kan omfatta:

- [Hantera](manage-incidents.md) incidenter
- Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md) i Åtgärdscenter
- Gå igenom de senaste [hotanalyserna](threat-analytics.md)
- [Svara på](investigate-incidents.md) ärenden

Månadsvisa uppgifter kan omfatta:

- Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)
- Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Rapportera till din it-säkerhetshanteringskedja

Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).

Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer. 

Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.

### <a name="secops-resources-across-microsoft-products"></a>SecOps-resurser i alla Microsoft-produkter

Mer information om SecOps i Microsofts produkter finns i följande resurser:

- [Kapaciteter](/security/compass/security-operations-capabilities)
- [Metodtips](/security/compass/security-operations)
- [Videor och bilder](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a>Nästa steg

**Om du inte har angående** säkerhetsanalys och incidentsvar:

- I [genomgången](first-incident-overview.md) Svara på din första incident finns en guidad genomgång av en typisk process av analys, åtgärder och granskning efter incident i Microsoft 365 Defender-portalen med ett exempel på en attack.

**Om du har erfarenhet av** säkerhetsanalys och incidentsvar:

- Kom igång med incidentkön på sidan **Incidenter** i Microsoft 365 Defender portalen. Härifrån kan du:

  - Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer. 

  - [Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldela, klassificera och lägga till taggar och kommentarer baserat på arbetsflödet för hantering av incidenter.

  - Utföra [undersökningar](investigate-incidents.md) av incidenter.

- I de här [spelböckerna för incidenter](/security/compass/incident-response-playbooks) finns detaljerad vägledning för attacker för nätfiske, lösenordsförsök och att bevilja åtkomst till appar.

