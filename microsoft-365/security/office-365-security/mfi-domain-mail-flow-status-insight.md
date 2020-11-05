---
title: Den främsta statusen för domän-e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder den främsta domänens e-postflödes status inblick i instrument panelen för e-postflöde i säkerhets & efterlevnad för att felsöka e-postproblem i samband med MX-poster.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920590"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Den främsta domänens e-postflödes status inblick i säkerhets & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Statusen för den **främsta domänens e-postflöde** inblickas i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) får du den aktuella e-postflödes statusen för din organisation

Denna inblick hjälper dig att identifiera och felsöka domäner med * *_e-postflöde_* _ problem. Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller om domänen har en felaktig MX-post.

![Flödes schema för bästa domän status i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

När du klickar på _ *Visa information* * i widgeten visas en utfällbar **domän status** som visar mer information om varje domän status:

- **Domain**
- **Föregående MX-post**
- **Aktuell MX-post**
- **Status för e-postmottagning**
- **Domän status** : en grön bock markering anger den aktuella MX-posten (när du klickade på widgeten) matchar det värde vi har på Record och domänen har fått e-post under de senaste två timmarna.

  Ett rött X anger att MX-posten har ändrats och att domänen inte har fått e-post under de senaste 6 timmarna. Detta indikerar antagligen att din domän har upphört, eller att MX-posten har uppdaterats felaktigt. Kontrol lera med din domän registrator eller DNS-värd om domänen har upphört att gälla, eller om domänens MX-post är felaktig.

Du kan klicka på **Visa mer** om du vill se samma information för fler domäner.

![Den utfällbara informationen i den främsta domänens e-flöde-status inblick](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
