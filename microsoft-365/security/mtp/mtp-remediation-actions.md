---
title: Reparationsåtgärder efter automatiserade undersökningar i Microsoft Threat Protection
description: Få en översikt över åtgärder för reparation som följer automatiserade undersökningar i Microsoft Threat Protection
keywords: automatiserad, utredning, alert, utlösa, åtgärder, sanering
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ca0c557de24320692d903a1136fc434d635f0507
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955597"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Reparationsåtgärder efter automatiserade undersökningar i Microsoft Threat Protection

**Gäller:**
- Microsofts hotskydd


## <a name="remediation-actions"></a>Åtgärder för reparation

Under och efter en automatisk undersökning i Microsoft Threat Protection identifieras reparationsåtgärder för skadliga eller misstänkta objekt. Vissa typer av åtgärder för reparation vidtas på enheter, även kallade slutpunkter. Andra åtgärder för reparation vidtas på e-postinnehåll. Automatiserade undersökningar slutförs efter att reparationsåtgärder har vidtagits, godkänts eller avvisats.

I följande tabell sammanfattas åtgärder för reparation som för närvarande stöds i Microsoft Threat Protection: 

|Åtgärdsåtgärder för enhet (slutpunkt)  |Åtgärder för reparation av e-post  |
|---------|---------|
|Karantänfil<br/>Ta bort registernyckel<br/>Döda process <br/>Stoppa tjänsten <br/>Inaktivera drivrutin <br/>Ta bort schemalagd aktivitet      |E-postmeddelanden eller kluster för mjuk borttagning<br/>Blockera URL (tid för klick)<br/>Inaktivera vidarebefordran av extern e-post          |

Reparationsåtgärder, oavsett om de väntar på godkännande eller redan är slutförda, kan visas i [Åtgärdscenter](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Saneringsåtgärder följer på automatiserade utredningar

När en automatiserad undersökning är klar, en dom nås för varje del av bevis inblandade, och saneringsåtgärder identifieras. I vissa fall vidtas åtgärder för att åtgärda dem automatiskt. I andra fall väntar saneringsåtgärder på godkännande. I följande tabell listas möjliga domar och resultat:

|Dom    |Området    |Resultat|
|------|------|------|
|Skadlig    |Enheter (slutpunkter)    |Reparationsåtgärder vidtas automatiskt|
|Skadlig    |E-postinnehåll (webbadresser eller bilagor) | Rekommenderade åtgärder väntar på godkännande|
|Misstänkta    |Enheter eller e-postinnehåll |Rekommenderade åtgärder väntar på godkännande|
|Inga hot hittades    |Enheter eller e-postinnehåll    |Inga saneringsåtgärder behövs|

[Granska en väntande åtgärd i åtgärdscentret](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Om du tror att något har missats eller felaktigt upptäckts av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta! [Rapportera falska positiva identifieringar/negativ](mtp-autoir-report-false-positives-negatives.md).

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [Läs mer om Åtgärdscentret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
