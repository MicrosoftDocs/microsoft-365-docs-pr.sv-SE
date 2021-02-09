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
description: Administratörer kan lära sig att använda korrigeringen av möjliga e-postslingor i instrumentpanelen för e-postflöde i säkerhets- & och efterlevnadscentret för att identifiera och åtgärda e-postslingor i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150237"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Åtgärda möjliga insikter i e-postslingan i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

E-postslingor är dåliga eftersom:

- De slösar bort systemresurser.
- De använder organisationens e-postvolym.
- De skickar förvirrande rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändarmeddelanden) till de ursprungliga avsändarna.

Fix **possible mail loop** insight in the Recommended for **you** area of the Mail [flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center [notifies](https://protection.office.com) you when a mail loop isected in your organization.

Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).

![Åtgärda insikter för långsamt e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-possible-mail-loop.png)

När du klickar **på Visa** information på widgeten visas en utfäll tillgänglig meny med mer information:

- **Domain**
- **Antal meddelanden:** Du kan klicka på [](message-trace-scc.md) **Visa exempelmeddelanden** om du vill visa meddelandespårningsresultaten för ett exempel på meddelanden som har påverkats av loopen.
- **Domäntyp**" Till exempel auktoritativ eller icke-auktoritativ.
- **MX-post:** Värden **(E-postserver)** **och** prioritetsvärden för MX-posten för domänen.
- **Looporsak** **och hur du åtgärdar:** Vi identifierar de vanligaste e-postslingsscenarierna och tillhandahåller rekommenderade åtgärder för att åtgärda slingan.

![Den utfällna informationen som visas när du klickar på Visa information om åtgärda möjlig e-postslinga](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
