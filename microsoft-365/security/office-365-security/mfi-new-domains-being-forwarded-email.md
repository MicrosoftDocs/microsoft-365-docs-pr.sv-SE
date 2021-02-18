---
title: Nya domäner som vidarebefordras via e-post
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Administratörer kan lära sig att använda de nya domänerna som vidarebefordras e-postinsikter i instrumentpanelen för e-postflöde i säkerhets- & efterlevnadscenter för att undersöka när användarna vidarebefordrar meddelanden till externa domäner som aldrig har vidarebefordrats till.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd026b31b7cb678ff1f091579c67a3958b159c09
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289467"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Nya domäner som vidarebefordras e-postinsikter i Säkerhets- & Efterlevnadscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Det finns giltiga affärsorsaker till att vidarebefordra e-postmeddelanden till externa mottagare i specifika domäner. Det är dock misstänkt när användare i organisationen plötsligt börjar vidarebefordra meddelanden till en domän där ingen i organisationen har vidarebefordrat meddelanden till (en ny domän).

Det här villkoret kan ange att användarkontona har komprometterats. Om du misstänker att kontona har komprometterats kan du gå till [Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)

De **nya domäner som vidarebefordras i** Säkerhets- & [och](https://protection.office.com) efterlevnadscenter meddelar dig när användare i organisationen vidarebefordrar meddelanden till nya domäner.

Den här insikten visas bara när problemet identifieras och visas på [sidan Med vidarebefordransrapport.](view-mail-flow-reports.md#forwarding-report)

![Nya domäner som vidarebefordras via e-post](../../media/mfi-new-domains-being-forwarded.png)

När du klickar på widgeten visas en utfällig meny där du kan hitta mer information om vidarebefordrade meddelanden, inklusive en länk tillbaka till [vidarebefordransrapporten.](view-mail-flow-reports.md#forwarding-report)

![Information som visas när du klickar på den nya domän som vidarebefordras e-postinsikt](../../media/mfi-new-domains-being-forwarded-details.png)

Du kan också gå till den här informationssidan  när du väljer insikten när du har klickat på Visa allt i området **& rekommendationer** **på** (Instrumentpanelen rapporter \>  <https://protection.office.com/insightdashboard> eller).

Om du vill förhindra automatisk vidarebefordran av meddelanden till externa domäner konfigurerar du en fjärrdomän för vissa eller alla externa domäner. Mer information finns i Hantera [fjärrdomäner i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Relaterade ämnen

Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)
