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
description: Administratörer kan lära sig hur attack simuleringsutbildning i Microsoft 365 säkerhetscenter påverkar anställda och kan få insikter från simulering och utbildningsresultat.
ms.technology: mdo
ms.openlocfilehash: 0fcb88406558f73b587d8452375c33dbbec1c78b
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51600013"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Få insikter genom att träna på attacksimulering

I simuleringen av attacker ger Microsoft dig insikter baserade på resultat av simuleringar och utbildningar som anställda gick igenom. De här insikterna hjälper dig att hålla dig informerad om dina anställdas beredskapsstatus och rekommenderar nästa steg för att bättre förbereda de anställda och din miljö för attacker.

Vi arbetar kontinuerligt med att expandera de insikter som är tillgängliga för dig. Funktionens påverkan och rekommenderade åtgärder är tillgängliga för närvarande. Börja med att gå till [simuleringsutbildning för attack i Microsoft 365 säkerhetscenter](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Påverkan på kompromettränta

På fliken **Översikt** över attack simuleringsutbildning ser du hur beteendet **påverkar komprometteringsräntan.** Det här kortet visar hur anställda tagit itu med de simuleringar du körde i motsats till den **förutsagda komprometteringen**. Du kan använda de här insikterna för att följa utvecklingen av medarbetarnas hotberedskap genom att köra flera simuleringar mot samma grupper av anställda.

I diagrammet kan du se:

- **Förutsagd komprometteringshastighet** som återspeglar den genomsnittliga komprometteringen för simuleringar som använder samma typ av nyttolast i andra Microsoft 365-klientorganisationen som använder utbildning av attack simulering.
- **Den faktiska komprometteringen** återspeglar procentandelen anställda som avar sig för simuleringen.

Återspeglar dessutom `<number> less susceptible to phishing` skillnaden mellan det faktiska antalet anställda som komprometterats av attacken och den förutsagda komprometterats. Antalet anställda är mindre sannolikt att bli komprometterade av liknande attacker i framtiden, samtidigt som det visar hur anställda gjorde generellt i motsats till `<percent%> better than predicted rate` den förutsagda komprometterat lönen.

> [!div class="mx-imgBorder"]
> ![Kort som påverkar beteendet på översikt över attack simuleringsutbildning](../../media/attack-sim-preview-behavior-impact-card.png)

Om du vill se en mer detaljerad rapport klickar du **på Visa simuleringar och effektivhetsrapport för utbildning**. Den här rapporten innehåller samma information med ytterligare kontext från själva simuleringen (till exempel simuleringsteknik och den totala användarens riktade).

## <a name="recommended-actions"></a>Rekommenderade åtgärder

På fliken Simuleringar väljer du en simulering för att gå till [ **simuleringsinformationen,**](https://security.microsoft.com/attacksimulator?viewid=simulations)där du hittar **avsnittet Rekommenderade** åtgärder.

Avsnittet med rekommenderade åtgärder innehåller information om rekommendationer som finns [i Microsoft Secure Score.](../defender/microsoft-secure-score.md) De här rekommendationerna baseras på den nyttolast som användes i simuleringen och hjälper dig att skydda dina anställda och din miljö. Om du klickar på varje förbättringsåtgärd visas information om den.

> [!div class="mx-imgBorder"]
> ![Avsnittet Rekommendationsåtgärder på simulering av attack](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Relaterade länkar

[Kom igång med Attack simuleringsträning](attack-simulation-training-get-started.md)

[Skapa en simulering av nätfiskeattacker](attack-simulation-training.md)

[skapa en nyttolast för utbildning av dina användare](attack-simulation-training-payloads.md)
