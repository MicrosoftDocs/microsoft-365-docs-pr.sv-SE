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
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hitta svar på de vanligaste frågorna om meddelanden som har lagts i kö, skjutits upp eller studsats under filtreringsprocessen för Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 854e954e3ebb995ba23db2afc6f2ca9ab19de508
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165433"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I det här avsnittet finns svar på vanliga frågor om meddelanden som har lagts i kö, skjutits upp eller studsats under filtreringsprocessen för Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Varför är köer av e-post?

Meddelanden köas eller uppskjuts om tjänsten inte kan upprätta en anslutning till mottagarservern för leverans. Meddelandet skjuter inte upp meddelanden om ett 500-seriefel returneras från mottagarnätverket.

## <a name="how-does-a-message-become-deferred"></a>Hur uppskjuts ett meddelande?

Meddelanden hålls kvar om det inte går att upprätta en anslutning till mottagarservern och mottagarens server returnerar ett "tillfälligt fel" som en time out för anslutning, anslutning som inte är upprättad eller ett 400-seriesfel. Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hur lång tid tar det att skjuta upp ett meddelande och vad är försöksintervallet?

Meddelanden vid upp skjutas upp kommer att finnas kvar i våra köer i 1 dag. Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem. De första uppvaktarna är 15 minuter eller mindre, med efterföljande försök (under de kommande sex) som ökar intervallet över flera försök till maximalt 60 minuter. Utökningen av intervallets varaktighet är dynamisk, med hänsyn till flera variabler som köstorlekar och intern meddelandeprioritet. I grundläggande fall är det 15 minuter (eller mindre) att börja och sedan expandera därifrån under de kommande timmarna till 60 min max.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hur distribueras meddelanden i kö när e-postservern har återställts?

När e-postservern har återställts bearbetas alla i köade meddelanden automatiskt i den ordning som de togs emot och i kö när servern blev otillgänglig.
