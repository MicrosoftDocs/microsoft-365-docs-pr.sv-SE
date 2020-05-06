---
title: Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hitta svar på vanliga frågor om meddelanden som har köats, skjutits upp eller studsat under filtreringsprocessen för Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: f7a7c8b5466e02353ca114d6c7ed44f37bed5592
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036554"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a>Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP

Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har köats, skjutits upp eller studsat under filtreringsprocessen för Microsoft Exchange Online Protection (EOP).

**F. Varför köar post?**

A. Meddelanden köas eller skjuts upp om tjänsten inte kan ansluta till mottagarservern för leverans. Meddelanden kommer inte att skjuta upp meddelanden om ett fel i 500-serien returneras från mottagarnätverket.

**F. Hur skjuts ett meddelande upp?**

A. Meddelanden lagras när en anslutning till mottagarservern inte kan upprättas och mottagarens server returnerar ett "tillfälligt fel" som en anslutningstidsgräns, anslutning som har avslagits eller ett fel i 400-serien. Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.

**F. Hur länge förblir ett meddelande i uppskov och vad är återförsöksintervallet?**

A. Meddelanden i uppskov kommer att finnas kvar i våra köer i 1 dag. Försök att skicka meddelanden baseras på felet vi får tillbaka från mottagarens e-postsystem. De första uppskoven är 15 minuter eller mindre, med efterföljande återförsök (under nästa halv dussin eller så) ökar intervallet över flera försök till högst 60 minuter. Intervallvaraktighetsexpansionen är dynamisk, med beaktande av flera variabler som köstorlekar och intern meddelandeprioritet. I grund och botten är det 15 minuter (eller mindre) att starta, sedan expandera därifrån under de närmaste timmarna till 60 minuter max.

**F. När e-postservern har återställts, hur distribueras meddelanden i kö?**

A. När e-postservern har återställts bearbetas alla meddelanden i kö automatiskt i den ordning de togs emot och köade när servern blev otillgänglig.
