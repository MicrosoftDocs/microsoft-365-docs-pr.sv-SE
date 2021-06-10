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
description: Administratörer kan ta reda på hur de kan använda insikter i artikeln om långsamma e-postflödesregler i Säkerhets- och efterlevnadscenter för & för att identifiera och åtgärda ineffektiva eller bryta e-postflödesregler (kallas även transportregler) i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 51ffa92402fd3e7c9e76115642426d3cce0a9e19
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207070"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Åtgärda insikter om långsamt e-postflödesregler i & Säkerhets- och efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Ineffektiva e-postflödesregler (kallas även transportregler) kan leda till fördröjningar i e-postflödet för din organisation. Den här insikten rapporterar e-postflödesregler som påverkar organisationens e-postflöde. Exempel på sådana typer av regler är:

- Villkor som används **Är medlem i** stora grupper.
- Villkor som använder komplexa reguljära uttryck (regex) mönstermatchning.
- Villkor som använder innehållskontrollen i bifogade filer.

Insikten **åtgärda problem med**  långsamma e-postflödesregler i området Rekommenderas för dig på instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) meddelar dig när en e-postflödesregel tar för lång tid att slutföra. [](mail-flow-insights-v2.md)

Den här insikten visas bara när villkoret har upptäckts (om du inte har några e-postslingor kan du inte se insikten).

Du kan använda det här meddelandet för att identifiera och finjustera e-postflödesregler för att minska e-postflödesfördröjningar.

![Åtgärda insikt i regler för långsamt e-postflöde i området Rekommenderas för dig på instrumentpanelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

När du klickar **på Visa information** om widgeten visas en utfäll tillgänglig meny med mer information:

- **Regel:** Du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln. Du kan klicka på sammanfattningen för att redigera regeln i Exchange (EAC).
- **Antal meddelanden som utvärderats**  : Du kan [](message-trace-scc.md) klicka på Visa exempelmeddelanden för att visa meddelandespårningsresultaten för ett exempel på meddelanden som påverkades av regeln.
- **Genomsnittlig tid för varje meddelande**
- **Mediantid i ett meddelande**: Det mittersta värdet som separerar den övre halvan från den nedre halvan av tidsdata.

![Information som visas när du klickar på Visa information på åtgärda information för långsamt e-postflödesregler](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Mer information om villkor och undantag i e-postflödesregler finns i Villkor för e-postflödesregel och undantag [(predikat) i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

## <a name="see-also"></a>Se även

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)