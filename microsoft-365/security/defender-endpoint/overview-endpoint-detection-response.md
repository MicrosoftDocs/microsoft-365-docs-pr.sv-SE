---
title: Översikt över funktioner för identifiering av slutpunkt och svar
ms.reviewer: ''
description: Läs mer om funktionerna för identifiering och svar av slutpunkter i Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 858ea0f8d46ac2489dd6ef5c10caf2ce0879e4fb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076521"
---
# <a name="overview-of-endpoint-detection-and-response"></a>Översikt över identifiering och svar av slutpunkter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender för slutpunktsidentifierings- och svarsfunktioner tillhandahåller avancerade attackidentifieringar som är nära i realtid och kan användas. Säkerhetsanalytiker kan prioritera varningar effektivt, få inblick i den fullständiga omfattningen av ett intrång och vidta åtgärder för att åtgärda hot.

När ett hot identifieras skapas aviseringar i systemet för att en analytiker ska undersöka det. Varningar med samma attacktekniker eller förser samma attack med samma attacker aggregeras i en enhet som kallas för _en incident_. Att samla aviseringar på det här sättet gör det enkelt för analytiker att gemensamt undersöka och reagera på hot.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

Med inspiration från "anta intrång" är Defender för Endpoint kontinuerligt samlad beteenderelaterad cyber telemetri. Det omfattar processinformation, nätverksaktiviteter, djupoptisk in i kernel och minneshanteraren, användarinloggningsaktiviteter, ändringar i registret och filsystem m.m. Informationen lagras i sex månader så att en analytiker kan färdas tillbaka i tiden till början av en attack. Analytikern kan sedan pivotera i olika vyer och närmar sig en undersökning genom flera vektorer.

Med svarsfunktionerna kan du snabbt åtgärda hot genom att agera på de berörda enheterna.


## <a name="related-topics"></a>Relaterade ämnen
- [Instrumentpanel för säkerhetsåtgärder](security-operations-dashboard.md)
- [Incidentkö](view-incidents-queue.md)
- [Kön Aviseringar](alerts-queue.md)
- [Listan Enheter](machines-view-overview.md)

