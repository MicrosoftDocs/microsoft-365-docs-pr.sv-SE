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
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290627"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Statusinsikter för e-postflöde i toppdomänen & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Statusinsikten för det** [](mail-flow-insights-v2.md) översta domänflödet i instrumentpanelen för e-postflöde i Säkerhets- & [efterlevnadscenter](https://protection.office.com) ger dig den aktuella e-postflödesstatusen för din organisation.

Den här insikten hjälper dig att identifiera och felsöka domäner som har problem ***med e-postflödet.*** Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller domänen har en felaktig MX-post.

![Widget för toppdomänflödesstatus i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-top-domain-mail-flow-status-widget.png)

När du klickar **på Visa** information i widgeten visas en **utfällsymbol** för Domänstatus som visar mer information om status för varje domän:

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
