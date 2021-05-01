---
title: Incidenter i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor Microsoft 365 säkerhetscenter.
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
ms.openlocfilehash: e2e29015d4cb5e04510577118eb847b9b596a6c5
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114288"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

En incident i Microsoft 365 Defender är en samling korrelerade varningar och associerade data som utgör en attacks historia. 

Microsoft 365 och appar skapar aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet. Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack. Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor. Resultatet är flera aviseringar för flera enheter i klientorganisationen. 

Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack, sammanställer Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hur Microsoft 365 Defender korrelerar händelser från enheter till ett incident":::

Titta på den här korta översikten över incidenter i Microsoft 365 Defender (4 minuter).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Om du grupperar relaterade aviseringar i en incident får du en omfattande bild av en attack. Du kan till exempel se:

- Var attacken började.
- Vilka taktiker användes.
- Hur långt attacken har varit i din klientorganisation.
- Attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades. 
- Alla data som är associerade med attacken.

Om [den](m365d-enable.md)är aktiverad Microsoft 365 Defender undersöka och åtgärda varningar automatiskt och artificiell intelligens. Du kan också utföra ytterligare åtgärdssteg för att lösa attacken. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidenter och aviseringar på Microsoft 365 säkerhetscenter

Du hanterar incidenter **från & och > incidenter** i snabbstarten av säkerhetscentret i Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com) Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Microsoft 365 säkerhetscenter":::

När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i Microsoft 365 säkerhetscenter":::

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

  Alla automatiserade undersökningar som utlösts av aviseringar i händelsen.

- Bevis och svar

  Alla händelser som stöds och misstänkta enheter i aviseringarna om händelsen.

Här är förhållandet mellan en händelse och dess data och flikarna för en incident i Microsoft 365 säkerhetscenter.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Förhållandet mellan en incident och dess data till flikarna för en händelse i Microsoft 365 säkerhetscenter":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Exempel på arbetsflöde av incidentsvar för Microsoft 365 Defender

Här är ett exempel på ett arbetsflöde för att svara på incidenter i Microsoft 365 med Microsoft 365 säkerhetscenter.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exempel på ett arbetsflöde för incidentsvar för Microsoft 365":::

Identifiera ärenden med högsta prioritet för analys och lösning i incidentkön och gör dem redo för svar. Det här är en kombination av:

- [Prioritera till](incident-queue.md) att fastställa incidenter med högsta prioritet genom att filtrera och sortera incidentkön.
- [Hantera](manage-incidents.md) incidenter genom att ändra deras titel, tilldela dem till en analytiker och lägga till taggar och kommentarer.

1. Påbörja en analys av en attack [och avisering för varje incident:](investigate-incidents.md)
 
   a. Visa sammanfattningen av incidenten för att förstå dess omfattning och allvarlighetsgrad och vilka enheter som påverkas **(fliken** Sammanfattning).

   b. Börja analysera aviseringarna så att du förstår deras ursprung, omfattning och allvarlighetsgrad **(fliken** Aviseringar).

   c. Vid behov samlar du in information om påverkade enheter, användare och postlådor **(flikarna** **Enheter,** Användare **och Postlådor).**

   d. Se hur Microsoft 365 Defender automatiskt har löst vissa aviseringar **(fliken Undersökningar).**
   
   e. Vid behov kan du använda informationen i datauppsättningen för incidenten för mer information **(fliken Bevis och** svar).

2. Efter eller under analysen bör du utföra inneslutning för att minska eventuella ytterligare effekter av attacken och säkerhetshotet.

3. Återställ så mycket som möjligt från attacken genom att återställa klientorganisationens resurser till den status de var i innan händelsen.

4. [Lös](manage-incidents.md#resolve-incident) incidenten och ta dig tid för efter incidentinlärning att:

   - Förstå typen av attack och dess påverkan.
   - Undersöka attacken i [Hotanalys och](threat-analytics.md) säkerhets-communityn för en trend för säkerhetsattacker.
   - Återkalla det arbetsflöde som du använde för att lösa problemet och uppdatera standardarbetsflöden, processer, principer och spelböcker efter behov.
   - Avgör om ändringar i säkerhetskonfigurationen behövs och implementera dem.

Om du inte har varit [](incidents-overview.md) så bra på säkerhetsanalys kan du gå till introduktionen till att svara på din första incident för ytterligare information och gå igenom en exempelhändelse.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Exempel på säkerhetsåtgärder för Microsoft 365 Defender

Här är ett exempel på säkerhetsåtgärder för Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ett exempel på säkerhetsåtgärder för Microsoft 365 Defender":::

Dagliga uppgifter kan omfatta:

- [Hantera](manage-incidents.md) incidenter
- Granska [åtgärder för automatisk undersökning och svar (AIR)](m365d-action-center.md)
- Gå igenom de senaste [hotanalyserna](threat-analytics.md)
- [Svara på](investigate-incidents.md) ärenden

Månadsvisa uppgifter kan omfatta:

- Granska [AIR-inställningar](m365d-configure-auto-investigation-response.md)
- Granska [Secure Score](microsoft-secure-score-improvement-actions.md) och & Vulnerability [Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Rapportera till din it-säkerhetshanteringskedja

Kvartalsvisa uppgifter kan innehålla en rapport och genomgång av säkerhetsresultat för Chief Information Security Officer (CISO).

Årliga uppgifter kan omfatta att utföra större incidenter eller intrång för att testa din personal, system och processer. 

Dagliga, månatliga, kvartals- och årliga uppgifter kan användas för att uppdatera eller förfina processer, principer och säkerhetskonfigurationer.

## <a name="next-steps"></a>Nästa steg

I incidentkön på **sidan Incidenter** visas de senaste incidenterna. Härifrån kan du:

- Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer. 
- [Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldelning, klassificera och lägga till taggar och kommentarer för arbetsflödet för incidenthantering.
- Utföra en [analys](investigate-incidents.md) av en händelse.
