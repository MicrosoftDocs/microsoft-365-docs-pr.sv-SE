---
title: Insikten E-postflödesstatus för översta domäner
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om den översta statusinformationen för domänutskicksflödet i instrumentpanelen för e-postflödet i Security & Compliance Center.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818597"
---
# <a name="top-domain-mail-flow-status-insight"></a>Insikten E-postflödesstatus för översta domäner

Statusinsikten **för toppdomänens e-postflöde** ger dig aktuell status för organisationens domäner när det gäller e-postflöde. Den här insikten hjälper dig att identifiera och felsöka domäner som upplever problem med ***e-postflödet*** (t.ex. inte kan ta emot extern e-post), särskilt domänförfall eller domäner med felaktiga MX-poster.

![Statusinsikten för toppdomänflödet i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

När du klickar på **Visa information** i insikten visas ett utfällbart utfällbart meddelande som visar mer information om status för varje domän.

En grön bock för en domän anger att den aktuella MX-posten (när du bläddrade till instrumentpanelen för e-postflödesinsikter) matchar det värde vi har på skiva och att domänen har fått e-post under de senaste två timmarna.

Ett rött x för en domän anger att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna. Detta indikerar troligen att domänen har upphört att gälla eller att MX-posten har uppdaterats felaktigt. Kontrollera med domänregistraren eller DNS-värdtjänsten om domänen har upphört att gälla eller om domänens MX-post är felaktig.

![Informationsutfällbart i statusinsikten för toppdomänflöde](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
