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
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290567"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a>Åtgärda möjliga insikter i e-postslingan i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

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
