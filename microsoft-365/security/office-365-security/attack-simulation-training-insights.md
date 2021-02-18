---
title: Få insikter genom att träna på attacksimulering
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur utbildningskurser för attacker i Säkerhetscenter i Microsoft 365 påverkar anställda och kan få insikter från simulering och utbildningsresultat.
ms.technology: mdo
ms.openlocfilehash: 43319089f604d32bf295392dd223cf65af8bd4be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288663"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Få insikter genom att träna på attacksimulering

I utbildning av attacksimulering ger Microsoft dig insikter baserade på resultat av simuleringar och utbildningar som anställda har gått igenom. De här insikterna hjälper dig att hålla dig informerad om dina anställdas beredskapsnivå och rekommenderar nästa steg för att bättre förbereda anställda och din miljö för attacker.

Vi arbetar kontinuerligt med att utöka de insikter som är tillgängliga för dig. Funktionens påverkan och rekommenderade åtgärder är tillgängliga för närvarande. Börja med att gå till [attackutbildningen i Säkerhetscenter i Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Påverkan på kompromettens

På fliken **Översikt** över attacksimuleringsutbildning ser du hur **beteendet påverkar komprometteringskortet.** Det här kortet visar hur anställda har hanterat de simuleringar du körde i motsats till **den förutsagda komprometteringen.** Du kan använda de här insikterna för att följa utvecklingen av medarbetarnas hotberedskap genom att köra flera simuleringar mot samma grupper av anställda.

I diagrammet kan du se:

- **Förutsagd** komprometteringshastighet som återspeglar den genomsnittliga komprometteringen för simuleringar som använder samma typ av nyttolast i andra Microsoft 365-klientorganisationar som använder attacksimuleringsutbildning.
- **Den faktiska komprometteringen** återspeglar procentandelen anställda som var med i simuleringen.

Återspeglar dessutom `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som komprometterats av attacken och den förutsagda komprometteras. Antalet anställda är mindre sannolikt att bli komprometterade av liknande angrepp i framtiden, samtidigt som det visar hur anställda gjorde generellt i motsats till den `<percent%> better than predicted rate` förutsagda komprometterande räntan.

> [!div class="mx-imgBorder"]
> ![Kortet Påverkar beteendet på översikt över attacksimulering](../../media/attack-sim-preview-behavior-impact-card.png)

Om du vill se en mer detaljerad rapport klickar du **på Visa simuleringar och övningsresultat.** Den här rapporten innehåller samma information med ytterligare kontext från själva simuleringen (till exempel simuleringsteknik och totalt antal användare som är riktade).

## <a name="recommended-actions"></a>Rekommenderade åtgärder

På [ **fliken Simuleringar**](https://security.microsoft.com/attacksimulator?viewid=simulations)kommer du till simuleringsinformationen där du hittar avsnittet Rekommenderade **åtgärder** när du väljer en simulering.

Avsnitten med rekommenderade åtgärder innehåller information om rekommendationer som finns [i Microsoft Secure Score.](../mtp/microsoft-secure-score.md) De här rekommendationerna baseras på den nyttolast som användes i simuleringen och hjälper dig att skydda dina anställda och din miljö. Om du klickar på varje förbättringsåtgärd visas information om den.

> [!div class="mx-imgBorder"]
> ![Avsnittet Rekommendationsåtgärder på attacksimuleringsutbildning](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Relaterade länkar

[Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)

[Skapa en simulering av nätfiskeattack](attack-simulation-training.md)

[skapa ett nyttolast för att utbilda dina användare](attack-simulation-training-payloads.md)
