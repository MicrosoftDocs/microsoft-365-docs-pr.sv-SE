---
title: Fixa möjlig inblick i e-postslingan
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur de kan använda korrigeringen av möjliga informationsloopar för e-post i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att identifiera och åtgärda e-postslingor i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071298"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Åtgärda möjliga insikter om e-postslingan i & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

E-postslingor är dåliga eftersom:

- De slösar på systemresurser.
- De använder organisationens e-postvolym.
- De skickar förvirrande rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) till de ursprungliga meddelandeavsändarna.

Åtgärda **möjliga insikter** om  e-postslingor [](mail-flow-insights-v2.md) i området Rekommenderas för dig på instrumentpanelen för e-postflöde i Säkerhets- och [&-efterlevnadscenter](https://protection.office.com) meddelar dig när en e-postslinga identifieras i organisationen.

Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).

![Åtgärda insikt i regler för långsamt e-postflöde i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

När du klickar **på Visa information** om widgeten visas en utfäll tillgänglig meny med mer information:

- **Domain**
- **Antal meddelanden:** Du kan klicka på Visa **exempelmeddelanden** för att se resultatet [av meddelandespårningen](message-trace-scc.md) för ett exempel på meddelanden som har påverkats av loopen.
- **Domäntyp**" Till exempel Auktoritativ eller Icke-auktoritativ.
- **MX-post:** Värden **(e-postserver)** **och prioritetsvärden** för MX-posten för domänen.
- **Looporsak** och **Hur du åtgärdar**: Vi identifierar de vanligaste e-postslingsscenarierna och tillhandahåller rekommenderade åtgärder för att åtgärda slingan.

![Information som visas när du klickar på Visa information i Åtgärda möjliga e-postslingor](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)
