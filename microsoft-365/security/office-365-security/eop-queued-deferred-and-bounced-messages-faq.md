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
description: Hitta svar på de vanligaste frågorna om meddelanden som har lagts i kö, skjutits upp eller studsats under filtreringsprocessen För Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7b5ba595e9a6401efd1b733c9e5a11c8a966037
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207480"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har lagts i kö, skjutits upp eller studsats under filtreringsprocessen För Exchange Online Protection (EOP).

## <a name="why-is-mail-queuing"></a>Varför köar e-post?

Meddelanden köas eller skjutits upp om tjänsten inte kan upprätta en anslutning till mottagarservern för leverans. Meddelandet skjuter inte upp meddelanden om ett 500-seriefel returneras från mottagarnätverket.

## <a name="how-does-a-message-become-deferred"></a>Hur uppskjuts ett meddelande?

Meddelanden hålls kvar om det inte går att upprätta en anslutning till mottagarservern och mottagarens server returnerar ett "tillfälligt fel" som att anslutningens time out, anslutningen är misslyckad eller ett 400-seriefel. Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a>Hur länge kan meddelandet skjutas upp och vad är försöksintervallet?

Meddelanden med uppsegen post finns kvar i våra köer i 1 dag. Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem. De första upp skjutas upp är 15 minuter eller mindre, med efterföljande försök (över det närmaste halvtimmen) och ökar intervallet över flera försök till högst 60 minuter. Intervallvaraktighetsexpansionen är dynamisk och du tas hänsyn till flera variabler som köstorlekar och intern meddelandeprioritet. In basic, it's 15 minutes (or less) to start, then expand from there over the next few hours to 60 mins max.

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a>Hur distribueras meddelanden i kö när e-postservern har återställts?

När e-postservern har återställts bearbetas alla i köade meddelanden automatiskt i den ordning som de togs emot och i kö när servern blev otillgänglig.
