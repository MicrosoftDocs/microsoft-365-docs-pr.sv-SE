---
title: Kom igång med appens kontroll
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430465"
---
# <a name="get-started-with-app-control"></a>Kom igång med appens kontroll

Innan du aktiverar appkontrollen i din miljö bör du granska och förstå [hur Microsoft Hanterat skrivbord](../service-description/app-control.md) implementerar den samt dina roller och ansvarsområden.

Microsoft Hanterat skrivbord förenklar appstyrningen genom att ta hand om de svårare aspekterna med att få en säker grundprincip. IT-administratörerna måste fortfarande testa apparna i testringen och granska loggarna för eventuella varningar eller fel. Om en app behöver ett undantag kan du arkivera en begäran eller välja Microsoft Hanterat skrivbord Åtgärd kan vara beroende på vem som identifierar den först.

## <a name="initial-deployment-of-apps"></a>Första distribution av appar

När du först distribuerar appar Microsoft Hanterat skrivbord utvärdera deras aktuella beteende. De exakta stegen för att aktivera appkontroll beror på om enheter redan har distribuerats i din miljö.

### <a name="devices-not-yet-in-use"></a>Enheter som ännu inte används

Om du inte redan har några enheter som används kan du öppna ett service ticket with Microsoft Hanterat skrivbord Operations och begära att vi aktiverar appkontroll. Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:

|Distributions grupp  |Typ av princip  |Tidsinställning  |
|---------|---------|---------|
|Test     |  Granskning       |  Dag 0       |
|Första     | Enforced        | Dag 1        |
|Snabbt     | Enforced        |  Dag 2       |
|Bred     | Enforced        |  Dag 3       |

Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.

### <a name="devices-already-in-use"></a>Enheter som redan används

Om du redan har minst en Microsoft Hanterat skrivbord enhet som används gör du så här:

1. Öppna ett tjänst ticket with Microsoft Hanterat skrivbord Operations requesting that we turn on app control. Åtgärder kommer att distribuera [en granskningsprincip](../service-description/app-control.md#audit-policy) på alla enheter.
2. [Testa dina program](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) för att se om några skulle blockeras. Om ett program skulle blockeras öppnar du en [undertecknarbegäran.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. När du har slutfört testningen (oavsett resultat), meddelar du Åtgärder, med information om väntande signeringsförfrågningar. Åtgärder distribuerar gradvis principer till distributionsgrupper som följer det här schemat:

|Distributions grupp  |Typ av princip  |Tidsinställning  |
|---------|---------|---------|
|Test     |  Granskning       |  Dag 0       |
|Första     | Enforced        | Dag 1        |
|Snabbt     | Enforced        |  Pausad, distribuerad på begäran       |
|Bred     | Enforced        |  Pausad, distribuerad på begäran       |

Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.



