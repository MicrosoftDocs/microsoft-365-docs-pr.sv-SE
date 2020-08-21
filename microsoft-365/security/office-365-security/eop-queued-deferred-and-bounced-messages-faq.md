---
title: Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Få svar på de vanligaste frågorna om meddelanden som har placerats i kö, skjuts upp eller studsade under Exchange Online Protection (EOP)-filtrerings processen.
ms.openlocfilehash: 76fe08f3a83321b6c0549dae5f1382ead5f0b3ae
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827755"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP

I det här avsnittet får du svar på vanliga frågor om meddelanden som har placerats i kö, skjuts upp eller studsade under Exchange Online Protection (EOP)-filtrerings processen.

## <a name="why-is-mail-queuing"></a>Varför är e-postköer?

Meddelanden köas eller är köade om tjänsten inte kan ansluta till mottagar servern för leverans. Meddelanden skjuts inte upp om ett 500-serie fel returneras från det mottagande nätverket.

## <a name="how-does-a-message-become-deferred"></a>Hur skjuts ett meddelande upp?

Meddelanden sparas när det inte går att ansluta till mottagar servern och mottagarens server returnerar ett tillfälligt fel, till exempel en anslutnings-timeout, anslutningen nekades eller ett 400-serie fel. Om det finns ett permanent fel, till exempel ett 500-serie fel, returneras meddelandet till avsändaren.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hur länge stannar ett meddelande i uppskov och vad är återförsöksintervallet?

Meddelanden i avstängnings kön bevaras i våra köer i 1 dag. Försök att försöka igen baseras på det fel vi får tillbaka från mottagarens e-postsystem. De första förskjutna samtalen är 15 minuter eller mindre, med efterföljande försök (över nästa halvtimme eller så) att öka intervallet över flera försök till högst 60 minuter. Utökning av intervall längd är dynamisk, med hänsyn till flera variabler som kös storlek och intern meddelande prioritet. I grundläggande fall är det 15 minuter (eller mindre) att börja och sedan expanderar vi under de närmaste timmarna till 60 minuter.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hur distribueras köade meddelanden när e-postservern har återställts?

När e-postservern återställts bearbetas alla köade meddelanden automatiskt i den ordning de togs emot och köade när servern inte är tillgänglig.
