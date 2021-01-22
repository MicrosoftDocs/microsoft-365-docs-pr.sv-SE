---
title: Översikt över incidenter i Microsoft 365 Defender
description: Undersök incidenter som kan visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929288"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Översikt över incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)
>


Incidenter baseras på relaterade aviseringar. Aviseringar skapas när en skadlig händelse eller aktivitet visas på nätverket. Enskilda varningar ger värdefulla ledtrådar om en going attack. Attacker använder emellertid vanligtvis olika vektorer och tekniker för att utföra ett intrång. Det kan vara svårt och tidskrävande att skapa cirkeldiagram för enskilda ledtrådar tillsammans.

Den här korta videon ger en översikt över incidenter i Microsoft 365 Defender.
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

En incident är en samling korrelerade varningar som utgör en berättelse om en attack. Skadliga och misstänkta händelser som hittas på olika enheter, användare och postlådeenheter i nätverket aggregeras automatiskt av Microsoft 365 Defender. Om du grupperar relaterade aviseringar till en händelse får säkerhetsvarningen en omfattande översikt över en attack. 

Säkerhetssäkerhet kan till exempel se var attacken började, vilka taktiker som användes och hur långt attacken har varit i nätverket. De kan också se attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades, hur allvarligt påverkan det var och annan information om berörda enheter.

Om den är aktiverad kan Microsoft 365 Defender automatiskt undersöka och lösa enskilda varningar genom automatisering och artificiell intelligens. Säkerhetsärenden kan också vidta ytterligare åtgärder för att lösa attacken direkt från händelsevyn. 

Incidenter från de senaste 30 dagarna visas i incidentkön. Härifrån kan säkerhetsärenden se vilka ärenden som ska prioriteras baserat på risknivå och andra faktorer. 

Säkerhetsärenden kan också byta namn på incidenter, tilldela dem till enskilda analytiker, klassificera och lägga till taggar i incidenter för att få en bättre och mer anpassad upplevelse för incidenthantering.



## <a name="see-also"></a>Se även
- [Prioritera incidenter](incident-queue.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
