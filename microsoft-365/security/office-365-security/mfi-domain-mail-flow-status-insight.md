---
title: Statusinsikter för e-postflöde för toppdomän på instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda statusinsikten för e-postflödesstatus för toppdomänen i instrumentpanelen för e-postflöde i Säkerhets- & efterlevnadscenter för att felsöka e-postflödesproblem som rör deras MX-poster.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150213"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Den viktigaste statusen för domänflödet i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Statusinsikten för det** [](mail-flow-insights-v2.md) översta domänflödet i instrumentpanelen för e-postflöde i Säkerhets- & [efterlevnadscenter](https://protection.office.com) ger dig den aktuella e-postflödesstatusen för din organisation.

Den här insikten hjälper dig att identifiera och felsöka domäner som har problem ***med e-postflödet.*** Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller domänen har en felaktig MX-post.

![Widget för toppdomänflödesstatus i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-top-domain-mail-flow-status-widget.png)

När du klickar **på Visa** information i widgeten visas en utfällsymbol för Domänstatus som visar mer information om status för varje domän: 

- **Domain**
- **Föregående MX-post**
- **Aktuell MX-post**
- **Status för e-postmottagning**
- **Domänstatus:** En grön bockmarkering anger den aktuella MX-posten (vid den tidpunkt då du klickade på widgeten) matchar värdet vi har i posten och domänen har fått e-post under de senaste två timmarna.

  Ett rött X indikerar att MX-posten har ändrats och att domänen inte har fått någon e-post under de senaste 6 timmarna. Det här indikerar sannolikt att domänen har upphört att gälla eller att MX-posten har uppdaterats felaktigt. Kontrollera med din domänregistrator eller DNS-värd om domänen har upphört att gälla eller om domänens MX-post är felaktig.

Du kan klicka **på Visa fler** om du vill se samma information för fler domäner.

![Den utfällna informationen i statusinformation för e-postflödet för toppdomänen](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
