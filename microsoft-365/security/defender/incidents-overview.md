---
title: Översikt över incidenter i Microsoft 365 Defender
description: Undersök incidenter som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
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
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068923"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Översikt över incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera den i en labbmiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller köra [pilotprojektet i produktion.](m365d-pilot.md?ocid=cx-evalpilot)
>


Incidenterna baseras på relaterade aviseringar. Aviseringar skapas när en skadlig händelse eller aktivitet visas i nätverket. Enskilda aviseringar ger värdefulla ledtrådar om en 1:e attack. Men attacker använder vanligtvis olika vektorer och tekniker för att utföra ett intrång. Det kan vara svårt och tidskrävande att samla enskilda ledtrådar.

Den här korta videon ger en översikt över incidenter i Microsoft 365 Defender.
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

En incident är en samling korrelerade varningar som utgör berättelse om en attack. Skadliga och misstänkta händelser som hittas på olika enheter, användare och postlådeenheter i nätverket aggregeras automatiskt av Microsoft 365 Defender. Att gruppera relaterade aviseringar till en händelse ger säkerhetssäkerhet en omfattande bild av en attack. 

Säkerhetsvakten kan till exempel se var attacken började, vilka taktiker som användes och hur långt attacken har varit i nätverket. De kan också se attackens omfattning, till exempel hur många enheter, användare och postlådor som påverkades, hur allvarligt påverkan det var och annan information om berörda enheter.

Om den är aktiverad kan Microsoft 365 Defender automatiskt undersöka och lösa enskilda aviseringar via automatisering och artificiell intelligens. Säkerhetshändelser kan också utföra ytterligare åtgärdsåtgärder för att lösa attacken direkt från händelsevyn. 

Incidenter från de senaste 30 dagarna visas i incidentkön. Säkerhetsärenden kan direkt se vilka ärenden som ska prioriteras utifrån risknivå och andra faktorer. 

Säkerhetsärenden kan också byta namn på incidenter, tilldela dem till enskilda analytiker, klassificera och lägga till taggar i incidenter för att få en bättre och mer anpassad upplevelse med incidenthantering.



## <a name="see-also"></a>Se även
- [Prioritera incidenter](incident-queue.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)