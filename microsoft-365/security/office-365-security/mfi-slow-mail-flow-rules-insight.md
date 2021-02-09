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
ms.openlocfilehash: f7f084735decda922b5bcc57c029f2b384114d30
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150790"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Åtgärda information om regler för långsamt e-postflöde & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

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
