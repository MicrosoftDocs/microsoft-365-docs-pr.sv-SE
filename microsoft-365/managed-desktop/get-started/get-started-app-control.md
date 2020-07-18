---
title: Komma igång med appkontroll
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170741"
---
# <a name="get-started-with-app-control"></a>Komma igång med appkontroll

Innan du aktiverar appkontroll i din miljö bör du granska och förstå [hur Microsoft Managed Desktop implementerar den](../service-description/app-control.md) och dina roller och ansvarsområden.

Microsoft Managed Desktop förenklar appkontrollen genom att ta hand om de mer utmanande aspekterna av att få en säker basprincip. IT-administratörerna måste fortfarande testa dina appar i testringen och granska loggarna för varningar eller fel. Om en app behöver ett undantag kan du lämna in en begäran eller microsoft managed desktop-drift kan, beroende på vem som identifierar den först.

## <a name="initial-deployment-of-apps"></a>Inledande distribution av appar

När du distribuerar appar första gången måste Microsoft Managed Desktop bedöma deras aktuella beteende. De exakta stegen för att aktivera appkontroll beror på om enheter redan har distribuerats i din miljö.

### <a name="devices-already-in-use"></a>Enheter som redan används

Om du redan har minst en Microsoft Managed Desktop-enhet i bruk gör du så här:

1. Öppna en tjänstbiljett med Microsoft Managed Desktop Operations som begär att vi aktiverar appkontroll. Åtgärder distribuerar en [granskningsprincip](../service-description/app-control.md#audit-policy) till alla enheter.
2. [Testa dina program](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) för att se om någon skulle blockeras. Om ett program skulle blockeras öppnar du en [undertecknarbegäran](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. När du har slutfört din testning (oavsett resultat), meddela Åtgärder, notera eventuella väntande undertecknare förfrågningar. Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:

|Distributionsgrupp  |Typ av princip  |Timing  |
|---------|---------|---------|
|Test     |  Revision       |  Dag 0       |
|Första     | Verkställas        | Dag 1        |
|Snabb     | Verkställas        |  Dag 3       |
|Bred     | Verkställas        |  Dag 7       |

Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.

### <a name="devices-not-yet-in-use"></a>Enheter som ännu inte används

Om du ännu inte har några enheter i bruk öppnar du en tjänstbiljett med Microsoft Managed Desktop Operations som begär att vi aktiverar appkontroll. Åtgärder distribuerar progressivt principer till distributionsgrupper enligt det här schemat:

|Distributionsgrupp  |Typ av princip  |Timing  |
|---------|---------|---------|
|Test     |  Revision       |  Dag 0       |
|Första     | Verkställas        | Dag 1        |
|Snabb     | Verkställas        |  Dag 3       |
|Bred     | Verkställas        |  Dag 7       |

Du kan alltid öppna en annan tjänstbegäran för att pausa eller återställa en del av den här distributionen när som helst under distributionen.

