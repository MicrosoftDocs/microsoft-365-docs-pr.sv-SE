---
title: Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d015a0d-52a0-484d-9a08-121d04f973d3
ms.custom:
- seo-marvel-apr2020
description: Hitta svar på de vanligaste frågorna om meddelanden som har köats, skjutits upp eller studsat under filtreringsprocessen för Exchange Online Protection (EOP).
ms.openlocfilehash: 38e72a04e855862c621bd2b170c11407e0d22af3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206598"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="c014d-103">Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP</span><span class="sxs-lookup"><span data-stu-id="c014d-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="c014d-104">Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har köats, skjutits upp eller studsats under filtreringsprocessen för Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c014d-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="c014d-105">Varför köar post?</span><span class="sxs-lookup"><span data-stu-id="c014d-105">Why is mail queuing?</span></span>

<span data-ttu-id="c014d-106">Meddelanden köas eller skjuts upp om tjänsten inte kan ansluta till mottagarservern för leverans.</span><span class="sxs-lookup"><span data-stu-id="c014d-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="c014d-107">Meddelanden kommer inte att skjuta upp meddelanden om ett fel i 500-serien returneras från mottagarnätverket.</span><span class="sxs-lookup"><span data-stu-id="c014d-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="c014d-108">Hur skjuts ett meddelande upp?</span><span class="sxs-lookup"><span data-stu-id="c014d-108">How does a message become deferred?</span></span>

<span data-ttu-id="c014d-109">Meddelanden lagras när en anslutning till mottagarservern inte kan upprättas och mottagarens server returnerar ett "tillfälligt fel" som en anslutningstidsgräns, anslutning som har avslagits eller ett fel i 400-serien.</span><span class="sxs-lookup"><span data-stu-id="c014d-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="c014d-110">Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="c014d-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="c014d-111">Hur länge förblir ett meddelande i uppskov och vad är återförsöksintervallet?</span><span class="sxs-lookup"><span data-stu-id="c014d-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="c014d-112">Meddelanden i uppskov kommer att finnas kvar i våra köer i 1 dag.</span><span class="sxs-lookup"><span data-stu-id="c014d-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="c014d-113">Försök att skicka meddelanden baseras på felet vi får tillbaka från mottagarens e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="c014d-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="c014d-114">De första uppskoven är 15 minuter eller mindre, med efterföljande återförsök (under nästa halv dussin eller så) ökar intervallet över flera försök till högst 60 minuter.</span><span class="sxs-lookup"><span data-stu-id="c014d-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="c014d-115">Intervallvaraktighetsexpansionen är dynamisk, med beaktande av flera variabler som köstorlekar och intern meddelandeprioritet.</span><span class="sxs-lookup"><span data-stu-id="c014d-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="c014d-116">I grund och botten är det 15 minuter (eller mindre) att starta, sedan expandera därifrån under de närmaste timmarna till 60 minuter max.</span><span class="sxs-lookup"><span data-stu-id="c014d-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="c014d-117">När e-postservern har återställts, hur distribueras meddelanden i kö?</span><span class="sxs-lookup"><span data-stu-id="c014d-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="c014d-118">När e-postservern har återställts bearbetas alla meddelanden i kö automatiskt i den ordning de togs emot och köade när servern blev otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c014d-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
