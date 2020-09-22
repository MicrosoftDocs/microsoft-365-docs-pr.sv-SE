---
title: Reparations åtgärder efter automatiserade utredningar av skydd mot Microsoft Threat
description: Få en översikt över reparations åtgärder som följer automatiska utredningar av Microsoft Threat Protection
keywords: automatiserad, undersökning, avisering, utlösare, åtgärd, reparation
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201057"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Reparations åtgärder efter automatiserade utredningar av skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Hotskydd


## <a name="remediation-actions"></a>Reparationsåtgärder

Under och efter en automatisk undersökning av Microsoft Threat Protection identifieras åtgärds åtgärder för skadliga eller misstänkta objekt. Vissa typer av reparations åtgärder utförs på enheter, som även kallas slut punkter. Andra reparations åtgärder vidtas på e-postinnehållet. Automatiserade undersökningar slutfört efter att reparations åtgärder vidtogs, godkännts eller avvisats.

I följande tabell sammanfattas de reparations åtgärder som stöds för närvarande i Microsoft Threat Protection: 

|Reparations åtgärder för enheter (slut punkter)  |Åtgärder för e-postreparation  |
|---------|---------|
|-Samla in undersöknings paket <br/>-Isolera enheter (denna åtgärd kan ångras)<br/>-Ta bort dator <br/>-Lansering av kod <br/>-Släpp från karantän <br/>-Begäran-exempel <br/>-Begränsa kod körning (denna åtgärd kan ångras) <br/>-Kör antivirus genomsökning <br/>-Stopp och karantän      |-Block-URL (tid för klick)<br/>-Mjuka ta bort e-postmeddelanden eller kluster<br/>-Karantän-e-postadress<br/>-Quarantine a e-postbilaga<br/>-Inaktivera vidarebefordran av externa e-post          |

Reparations åtgärder som väntar på godkännande eller redan är avslutade kan visas i [Åtgärds centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Reparations åtgärder utför automatiserade utredningar

När en automatiserad undersökning är klar är en Verdict nådd för varje del av beviset. Beroende på Verdict identifieras åtgärds åtgärder. I vissa fall vidtas reparations åtgärder automatiskt. i andra fall väntar reparations åtgärder på godkännande. Det beror på hur [Automatisk undersökning och svar är konfigurerat](mtp-configure-auto-investigation-response.md).

I följande tabell visas möjliga verdicts och resultat:

|Verdict    |Under    |Resultat|
|------|------|------|
|Skadliga    |Enheter (slut punkter)    |Reparations åtgärder vidtas automatiskt (förutsatt att organisationens [enhets grupper](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) är inställda på att **automatiskt åtgärda hot**)|
|Skadliga    |E-postinnehåll (URL: er eller bifogade filer) | Rekommenderade reparations åtgärder väntar på godkännande|
|Misstänkt    |Enheter eller e-postinnehåll |Rekommenderade reparations åtgärder väntar på godkännande|
|Inga hot hittades    |Enheter eller e-postinnehåll    |Inga reparations åtgärder behövs|

> [!IMPORTANT]
> Om reparations åtgärder vidtas automatiskt eller bara vid godkännande beror på vissa inställningar, till exempel organisationens enhets grup principer. Mer information finns i följande artiklar:
> - [Konfigurera automatisk granskning och svars funktioner i Microsoft Threat Protection](mtp-configure-auto-investigation-response.md)
> - [Hur hot åtgärdas på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Nästa steg

- [Besök åtgärden centret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Godkänna eller avvisa väntande åtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Hantera felaktiga positiva/negativa negativ i automatiserade undersökningar och svars funktioner](mtp-autoir-report-false-positives-negatives.md)
