---
title: Fixa insikter om långsamma flödesregler
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda åtgärds reglerna för långsam e-postflöde inblick i säkerhets & Compliance Center för att identifiera och åtgärda ineffektiva eller felaktiga regler för e-postflöde (kallas även transport regler) i organisationen.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920554"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a>Åtgärda regler för långsam e-postflöde inblick i centret för säkerhets & efterlevnad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Ineffektiva regler för e-postflöde (kallas även transport regler) kan leda till fördröjning i e-postflöden för din organisation. Den här Insight rapporterar regler för e-postflöde som påverkar organisationens e-postflöde. Här följer exempel på dessa typer av regler:

- De villkor som används **är medlemmar i** för stora grupper.
- Villkor som använder regex-mönster matchning (komplext).
- Villkor som använder innehålls kontroll i bifogade filer.

Reglerna för att **åtgärda långsamma e-postflöde** är inblickade i det **rekommenderade för dig** -området i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & efterlevnaden](https://protection.office.com) meddelar dig när det tar för lång tid att slutföra en regel för e-postflöde.

Denna inblick visas bara efter det att villkoret har identifierats (om du inte har några e-postloopar visas inte inblicken).

Du kan använda det här meddelandet för att identifiera och finjustera regler för e-postflöde för att minska fördröjningar för e-postflöde.

![Åtgärda regler för långsam e-postflöde inblick i det rekommenderade för dig-området på instrument panelen för e-postflöde](../../media/mfi-fix-slow-mail-flow-rules.png)

När du klickar på **Visa information** i widgeten visas en utfällbar lista med mer information:

- **Regel** : du kan hovra över sammanfattningen för att se alla villkor, undantag och åtgärder för regeln. Du kan klicka på sammanfattningen för att redigera regeln i administrations centret för Exchange (UK).
- **Antal meddelanden som utvärderats** : du kan klicka på **Visa exempel meddelanden** [om du vill visa resultaten för](message-trace-scc.md) ett urval av de meddelanden som påverkade regeln.
- **Genomsnittlig tid som lagts ned på varje meddelande**
- **Median tid som lagts på ett meddelande** : det mittersta värdet som avgränsar den övre halvan från den nedre halvan av tidsdata.

![Den utfällbara informationen som visas när du klickar på Visa information om regler för att åtgärda långsamma e-postflöde inblick](../../media/mfi-fix-slow-mail-flow-rules-details.png)

Mer information om villkor och undantag i regler för e-postflöden finns i [villkor och undantag för e-postflödes regler (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

## <a name="see-also"></a>Se även

Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).
