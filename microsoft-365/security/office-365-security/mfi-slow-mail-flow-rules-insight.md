---
title: Insikt om långsamma e-postflödesregler
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
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om insikten om långsamma regler för e-postflöde i instrumentpanelen för säkerhets- & compliance.
ms.openlocfilehash: 52ddb6bf5ab6998309fd3122c59636c14b3da1dd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819370"
---
# <a name="slow-mail-flow-rules-insight"></a>Insikt om långsamma e-postflödesregler

Ineffektiva regler för e-postflöde (kallas även transportregler) kan leda till fördröjningar i e-postflödet för din organisation. Den här insikten rapporterar regler för e-postflöde som påverkar organisationens e-postflöde. Exempel på dessa typer av regler är:

- Villkor som används **Är medlem i** för stora grupper.

- Villkor som använder komplexa reguljära uttryck (regex) mönster matchning.

- Villkor som använder innehållskontroll i bifogade filer.

Insikten hjälper dig att identifiera och finjustera regler för e-postflöde för att minska fördröjningar i e-postflödet.

![En långsam insikt om e-postflödesregler i instrumentpanelen för e-postflödet i Security & Compliance Center](../../media/1dd90faa-f065-4b10-8b47-d35dc127fc26.png)

När du klickar på **Visa information**visas ett utfällbart fönster där du kan granska regeln. I det utfällbara fönstret kan du även klicka på **Visa exempelmeddelanden** för att se vilken typ av meddelanden som påverkas av regeln.

![Utfällbart fönster efter att ha klickat på Visa information i en långsam insikt om regler för e-postflöde i instrumentpanelen för e-postflödet](../../media/2cbd43b7-1f21-4338-a70c-7b50de5c69cd.png)

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter om e-postflöde i instrumentpanelen för e-postflödet finns [i Insikterna för e-postflöde i Security & Compliance Center](mail-flow-insights-v2.md).
