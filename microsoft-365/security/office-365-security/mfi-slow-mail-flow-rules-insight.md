---
title: Fixa insikter om långsamma flödesregler
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de kan använda information om åtgärda långsam e-postflödesregler i Säkerhets- & och efterlevnadscenter för att identifiera och åtgärda ineffektiva eller trasiga e-postflödesregler (kallas även transportregler) i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290699"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Åtgärda information om regler för långsamt e-postflöde & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Ineffektiva e-postflödesregler (kallas även transportregler) kan leda till e-postflödesfördröjningar för organisationen. Den här insikten rapporterar e-postflödesregler som påverkar organisationens e-postflöde. Exempel på dessa typer av regler är:

- Villkor som använder **Är medlem i** stora grupper.
- Villkor som använder komplexa reguljära uttryck (regex) mönstermatchning.
- Villkor som använder innehåll som checkar in bifogade filer.

Insikten **för Åtgärda** långsamt  e-postflödesregler [](mail-flow-insights-v2.md) i området Rekommenderas för dig på instrumentpanelen för e-postflöde i Säkerhets- [& och](https://protection.office.com) efterlevnadscenter meddelar dig när en e-postflödesregel tar för lång tid att slutföra.

Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).

Du kan använda det här meddelandet för att identifiera och finjustera e-postflödesregler för att minska e-postflödesfördröjningar.

![Åtgärda insikter för långsamt e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

När du klickar **på Visa** information på widgeten visas en utfäll tillgänglig meny med mer information:

- **Regel:** Du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln. Klicka på sammanfattningen om du vill redigera regeln i administrationscentret för Exchange (EAC).
- **Antal meddelanden som utvärderats**  : Du kan [](message-trace-scc.md) klicka på Visa exempelmeddelanden för att visa meddelandespårningsresultaten för ett exempel på meddelanden som har påverkats av regeln.
- **Genomsnittlig tid för varje meddelande**
- **Mediantiden för ett meddelande:** Det mittersta värdet som separerar den övre halvan från den nedre halvan av tidsdata.

![Information som visas när du klickar på Visa information på insikten Åtgärda långsam e-postflödesregler](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Mer information om villkor och undantag i e-postflödesregler finns i Villkoren för e-postflödesregel och undantag [(predikat) i Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
