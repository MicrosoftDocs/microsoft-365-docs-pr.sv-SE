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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="23d34-103">Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP</span><span class="sxs-lookup"><span data-stu-id="23d34-103">EOP queued, deferred, and bounced messages FAQ</span></span>

<span data-ttu-id="23d34-104">I det här avsnittet får du svar på vanliga frågor om meddelanden som har placerats i kö, skjuts upp eller studsade under Exchange Online Protection (EOP)-filtrerings processen.</span><span class="sxs-lookup"><span data-stu-id="23d34-104">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="23d34-105">Varför är e-postköer?</span><span class="sxs-lookup"><span data-stu-id="23d34-105">Why is mail queuing?</span></span>

<span data-ttu-id="23d34-106">Meddelanden köas eller är köade om tjänsten inte kan ansluta till mottagar servern för leverans.</span><span class="sxs-lookup"><span data-stu-id="23d34-106">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="23d34-107">Meddelanden skjuts inte upp om ett 500-serie fel returneras från det mottagande nätverket.</span><span class="sxs-lookup"><span data-stu-id="23d34-107">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="23d34-108">Hur skjuts ett meddelande upp?</span><span class="sxs-lookup"><span data-stu-id="23d34-108">How does a message become deferred?</span></span>

<span data-ttu-id="23d34-109">Meddelanden sparas när det inte går att ansluta till mottagar servern och mottagarens server returnerar ett tillfälligt fel, till exempel en anslutnings-timeout, anslutningen nekades eller ett 400-serie fel.</span><span class="sxs-lookup"><span data-stu-id="23d34-109">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="23d34-110">Om det finns ett permanent fel, till exempel ett 500-serie fel, returneras meddelandet till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="23d34-110">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="23d34-111">Hur länge stannar ett meddelande i uppskov och vad är återförsöksintervallet?</span><span class="sxs-lookup"><span data-stu-id="23d34-111">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="23d34-112">Meddelanden i avstängnings kön bevaras i våra köer i 1 dag.</span><span class="sxs-lookup"><span data-stu-id="23d34-112">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="23d34-113">Försök att försöka igen baseras på det fel vi får tillbaka från mottagarens e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="23d34-113">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="23d34-114">De första förskjutna samtalen är 15 minuter eller mindre, med efterföljande försök (över nästa halvtimme eller så) att öka intervallet över flera försök till högst 60 minuter.</span><span class="sxs-lookup"><span data-stu-id="23d34-114">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="23d34-115">Utökning av intervall längd är dynamisk, med hänsyn till flera variabler som kös storlek och intern meddelande prioritet.</span><span class="sxs-lookup"><span data-stu-id="23d34-115">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="23d34-116">I grundläggande fall är det 15 minuter (eller mindre) att börja och sedan expanderar vi under de närmaste timmarna till 60 minuter.</span><span class="sxs-lookup"><span data-stu-id="23d34-116">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="23d34-117">Hur distribueras köade meddelanden när e-postservern har återställts?</span><span class="sxs-lookup"><span data-stu-id="23d34-117">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="23d34-118">När e-postservern återställts bearbetas alla köade meddelanden automatiskt i den ordning de togs emot och köade när servern inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="23d34-118">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
