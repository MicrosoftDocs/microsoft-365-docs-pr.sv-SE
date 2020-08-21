---
title: Den främsta statusen för domän-e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om hur du använder den främsta domänens e-postflödes status inblick i instrument panelen för e-postflöde i säkerhets & efterlevnad för att felsöka e-postproblem i samband med MX-poster i deras e-
ms.openlocfilehash: 9640d5e37932efeb7c0c8f8c56d0a15bc7f07e5b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827021"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Den främsta domänens e-postflödes status inblick i säkerhets & Compliance Center

Statusen för den **främsta domänens e-postflöde** inblickar i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center ger dig den aktuella statusen för organisationens domäner i termer av e-postflöde. Denna inblick hjälper dig att identifiera och felsöka domäner som ***påverkar problem med e-postflöde*** (till exempel att det inte går att ta emot extern e-post), särskilt upphör att gälla för domänen eller domäner med felaktiga MX-poster.

![Flödes schema för bästa domän status i instrument panelen för e-postflöde i säkerhets & Compliance Center](../../media/mfi-top-domain-mail-flow-status-widget.png)

När du klickar på **Visa information** i widgeten visas en utfällbar **domän status** som visar mer information om varje domän status:

- **Domain**
- **Föregående MX-post**
- **Aktuell MX-post**
- **Status för e-postmottagning**
- **Domän status**: en grön bock markering anger den aktuella MX-posten (när du klickade på widgeten) matchar det värde som finns på posten och att domänen har fått e-post under de två timmarna.

  Ett rött X anger att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna. Detta indikerar antagligen att din domän har upphört, eller att MX-posten har uppdaterats felaktigt. Kontrol lera med din domän registrator eller DNS-värd om domänen har upphört att gälla, eller om domänens MX-post är felaktig.

Du kan klicka på **Visa mer** om du vill se samma information för fler domäner.

![Den utfällbara informationen i den främsta domänens e-flöde-status inblick](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Relaterade ämnen

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
