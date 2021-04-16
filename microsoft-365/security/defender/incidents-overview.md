---
title: Incidenter i Microsoft 365 Defender
description: Undersök incidenter som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861629"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

En incident i Microsoft 365 Defender är en samling korrelerade aviseringar och associerade data som utgör attackens historia. 

I Microsoft 365-tjänster och -appar skapas aviseringar när de upptäcker misstänkt eller skadlig händelse eller aktivitet. Enskilda aviseringar ger värdefulla ledtrådar om en slutförd eller pågående attack. Men attacker använder vanligtvis olika tekniker mot olika typer av enheter, till exempel enheter, användare och postlådor. Resultatet är flera aviseringar för flera enheter i klientorganisationen. 

Eftersom det kan vara svårt och tidskrävande att samla ihop enskilda aviseringar för att få insikter i en attack aggregerar Microsoft 365 Defender automatiskt aviseringarna och deras tillhörande information till en incident.

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

Om [den](m365d-enable.md)är aktiverad kan Microsoft 365 Defender automatiskt undersöka och åtgärda varningar med hjälp av automatisering och artificiell intelligens. Du kan också utföra ytterligare åtgärdssteg för att lösa attacken. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidenter och aviseringar i Säkerhetscenter för Microsoft 365

Du hanterar incidenter **från & och > incidenter** i snabbstarten av Säkerhetscenter för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com) Här är ett exempel.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Sidan Incidenter i Säkerhetscenter för Microsoft 365":::

När du väljer ett namn på incidenten visas en sammanfattning av händelsen och det ger tillgång till flikar med ytterligare information.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exempel på sidan Sammanfattning för en incident i säkerhetscentret i Microsoft 365":::

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

Här är förhållandet mellan en incident och dess data och flikarna för ett incident i Säkerhetscenter i Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Relationen mellan en händelse och dess data till flikarna för en händelse i Säkerhetscenter i Microsoft 365":::

## <a name="next-step"></a>Nästa steg

I incidentkön på **sidan Incidenter** visas de senaste incidenterna. Härifrån kan du:

- Se vilka incidenter som [ska prioriteras](incident-queue.md) utifrån allvarlighetsgrad och andra faktorer. 
- Undersöka [en](investigate-incidents.md) händelse.
- [Hantera incidenter,](manage-incidents.md)som omfattar att byta namn på, tilldela dem, klassificera och lägga till taggar för arbetsflödet för incidenthantering.
