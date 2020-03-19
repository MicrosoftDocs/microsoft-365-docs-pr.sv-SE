---
title: Insikt om långsamma regler för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 5/3/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
description: Administratörer kan lära sig mer om insikten om långsamma regler för e-postflöde i instrumentpanelen för säkerhets- & compliance.
ms.openlocfilehash: d5317f2d45aacb91e51131bc5b8aa6e67d3ae4c7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806811"
---
# <a name="slow-mail-flow-rules-insight"></a>Insikt om långsamma regler för e-postflöde

Ineffektiva regler för e-postflöde (kallas även transportregler) kan leda till fördröjningar i e-postflödet för din organisation. Den här insikten rapporterar regler för e-postflöde som påverkar organisationens e-postflöde. Exempel på dessa typer av regler är:

- Villkor som används **Är medlem i** för stora grupper.

- Villkor som använder komplexa reguljära uttryck (regex) mönster matchning.

- Villkor som använder innehållskontroll i bifogade filer.

Insikten hjälper dig att identifiera och finjustera regler för e-postflöde för att minska fördröjningar i e-postflödet.

![En långsam insikt om e-postflödesregler i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

När du klickar på **Visa information**visas ett utfällbart fönster där du kan granska regeln. I det utfällbara fönstret kan du även klicka på **Visa exempelmeddelanden** för att se vilken typ av meddelanden som påverkas av regeln.

![Utfällbart fönster efter att ha klickat på Visa information i en långsam insikt om e-postflödesregler i instrumentpanelen för e-postflödet](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="see-also"></a>Se även

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
