---
title: Vanliga frågor och svar om EOP-köade, uppskjutna och studsade meddelanden
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
description: Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har köats, skjutits upp eller studsat under filtreringsprocessen för Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 05993e8d0e9af69dd1ac35b588c4e8ec731642f7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810391"
---
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="00de5-103">Vanliga frågor och svar om EOP-köade, uppskjutna och studsade meddelanden</span><span class="sxs-lookup"><span data-stu-id="00de5-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="00de5-104">Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har köats, skjutits upp eller studsat under filtreringsprocessen för Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="00de5-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Microsoft Exchange Online Protection (EOP) filtering process.</span></span>

<span data-ttu-id="00de5-105">**F. Varför köar post?**</span><span class="sxs-lookup"><span data-stu-id="00de5-105">**Q. Why is mail queuing?**</span></span>

<span data-ttu-id="00de5-106">A.</span><span class="sxs-lookup"><span data-stu-id="00de5-106">A.</span></span> <span data-ttu-id="00de5-107">Meddelanden köas eller skjuts upp om tjänsten inte kan ansluta till mottagarservern för leverans.</span><span class="sxs-lookup"><span data-stu-id="00de5-107">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="00de5-108">Meddelanden kommer inte att skjuta upp meddelanden om ett fel i 500-serien returneras från mottagarnätverket.</span><span class="sxs-lookup"><span data-stu-id="00de5-108">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

<span data-ttu-id="00de5-109">**F. Hur skjuts ett meddelande upp?**</span><span class="sxs-lookup"><span data-stu-id="00de5-109">**Q. How does a message become deferred?**</span></span>

<span data-ttu-id="00de5-110">A.</span><span class="sxs-lookup"><span data-stu-id="00de5-110">A.</span></span> <span data-ttu-id="00de5-111">Meddelanden lagras när en anslutning till mottagarservern inte kan upprättas och mottagarens server returnerar ett "tillfälligt fel" som en anslutningstidsgräns, anslutning som har avslagits eller ett fel i 400-serien.</span><span class="sxs-lookup"><span data-stu-id="00de5-111">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="00de5-112">Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="00de5-112">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

<span data-ttu-id="00de5-113">**F. Hur länge förblir ett meddelande i uppskov och vad är återförsöksintervallet?**</span><span class="sxs-lookup"><span data-stu-id="00de5-113">**Q. How long does a message remain in deferral and what is the retry interval?**</span></span>

<span data-ttu-id="00de5-114">A.</span><span class="sxs-lookup"><span data-stu-id="00de5-114">A.</span></span> <span data-ttu-id="00de5-115">Meddelanden i uppskov kommer att finnas kvar i våra köer i 1 dag.</span><span class="sxs-lookup"><span data-stu-id="00de5-115">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="00de5-116">Försök att skicka meddelanden baseras på felet vi får tillbaka från mottagarens e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="00de5-116">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="00de5-117">De första uppskoven är 15 minuter eller mindre, med efterföljande återförsök (under nästa halv dussin eller så) ökar intervallet över flera försök till högst 60 minuter.</span><span class="sxs-lookup"><span data-stu-id="00de5-117">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="00de5-118">Intervallvaraktighetsexpansionen är dynamisk, med beaktande av flera variabler som köstorlekar och intern meddelandeprioritet.</span><span class="sxs-lookup"><span data-stu-id="00de5-118">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="00de5-119">I grund och botten är det 15 minuter (eller mindre) att starta, sedan expandera därifrån under de närmaste timmarna till 60 minuter max.</span><span class="sxs-lookup"><span data-stu-id="00de5-119">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

<span data-ttu-id="00de5-120">**F. När e-postservern har återställts, hur distribueras meddelanden i kö?**</span><span class="sxs-lookup"><span data-stu-id="00de5-120">**Q. After your email server is restored, how are queued messages distributed?**</span></span>

<span data-ttu-id="00de5-121">A.</span><span class="sxs-lookup"><span data-stu-id="00de5-121">A.</span></span> <span data-ttu-id="00de5-122">När e-postservern har återställts bearbetas alla meddelanden i kö automatiskt i den ordning de togs emot och köade när servern blev otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="00de5-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
