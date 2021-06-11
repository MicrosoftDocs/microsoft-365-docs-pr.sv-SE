---
title: Statusinsikt för domän-e-postflöde på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig att använda statusinsikten för e-postflödesstatus för toppdomänen i instrumentpanelen för e-postflöde i Säkerhets- och efterlevnadscenter för & för att felsöka problem i e-postflödet som är relaterade till MX-posterna.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207552"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Statusinsikter för e-postflöde i toppdomänen i & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Statusinsikten för** e-postflödet för toppdomänen i instrumentpanelen för e-postflöde i säkerhets- & [efterlevnadscenter](https://protection.office.com) ger dig den aktuella statusen för e-postflödet för din organisation. [](mail-flow-insights-v2.md)

Med den här insikten kan du identifiera och felsöka domäner som har problem ***med e-postflödet.*** Domänen kan till exempel inte ta emot extern e-post eftersom domänen har upphört att gälla eller domänen har en felaktig MX-post.

![Widgeten för toppdomänflödesstatus på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-top-domain-mail-flow-status-widget.png)

När du klickar **på Visa** information i widgeten visas den utfällsymbolen Domänstatus med mer information om varje domäns status: 

- **Domän**
- **Föregående MX-post**
- **Aktuell MX-post**
- **Status för e-post som tas emot**
- **Domänstatus:** En grön bockmarkering anger den aktuella MX-posten (vid den tidpunkt då du klickade på widgeten) matchar värdet vi har på posten och domänen har fått e-post under de senaste två timmarna.

  Ett rött X indikerar att MX-posten har ändrats och att domänen inte har fått något e-postmeddelande under de senaste 6 timmarna. Det här indikerar förmodligen att din domän har upphört att gälla eller att MX-posten har uppdaterats felaktigt. Kontrollera med din domänregistrator eller DNS-värd om domänen har upphört att gälla eller om domänens MX-post är felaktig.

Du kan klicka **på Visa fler** om du vill se samma information för fler domäner.

![Information som visas i statusinsikten för e-postflödet för toppdomänen](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
