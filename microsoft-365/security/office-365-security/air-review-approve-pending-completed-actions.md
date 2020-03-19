---
title: Granska och godkänna väntande reparationsåtgärder i Office 365 automatisk undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Lär dig mer om reparationsåtgärder i automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d2b617e29fc36d1f39ab6c9ef6f708d5f608b206
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826463"
---
# <a name="view-pending-or-completed-remediation-actions-following-an-automated-investigation-in-office-365"></a>Visa väntande eller slutförda reparationsåtgärder efter en automatisk undersökning i Office 365

## <a name="approve-or-reject-pending-actions"></a>Godkänna (eller avvisa) väntande åtgärder

![ÅTGÄRDssida för AIR-utredningar](../../media/air-investigationactionspage.png)

När du visar [information om en undersökning](air-view-investigation-results.md)kan du godkänna eller avvisa eventuella väntande reparationsåtgärder. Vi rekommenderar att du gör detta så snart som möjligt så att dina automatiserade undersökningar slutförs.

> [!IMPORTANT]
> Lämpliga behörigheter krävs för att godkänna eller avvisa åtgärder för reparation. Se [Behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities).

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in. Detta tar dig till Security & Compliance Center.

2. Gå till **Threat management** > **Investigations**.

3. Välj ett objekt i **ID-kolumnen** i listan över undersökningar. 

4. Välj fliken **Åtgärder.**

5. Markera ett objekt i listan. (Detta aktiverar knapparna Godkänn och Avvisa.)

6. Granska tillgänglig information för de objekt du har markerat och godkänn eller avvisa åtgärden/åtgärderna. 
 - **Godkänn** tillåter reparation att börja.
 - **Avvisa** vidtar inga ytterligare åtgärder

## <a name="next-steps"></a>Nästa steg

- [Information och resultat av en automatiserad undersökning i Office 365](air-view-investigation-results.md)

- [Använda Threat Explorer](threat-explorer.md)