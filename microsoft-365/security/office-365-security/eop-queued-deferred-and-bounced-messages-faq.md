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
# <a name="eop-queued-deferred-and-bounced-messages-faq"></a><span data-ttu-id="3ce18-103">Vanliga frågor och svar om köade, uppskjutna och studsade meddelanden i EOP</span><span class="sxs-lookup"><span data-stu-id="3ce18-103">EOP queued, deferred, and bounced messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ce18-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="3ce18-104">**Applies to**</span></span>
- [<span data-ttu-id="3ce18-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ce18-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3ce18-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="3ce18-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3ce18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ce18-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3ce18-108">Det här avsnittet innehåller svar på vanliga frågor om meddelanden som har lagts i kö, skjutits upp eller studsats under filtreringsprocessen För Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3ce18-108">This topic provides answers to frequently asked questions about messages that have been queued, deferred, or bounced during the Exchange Online Protection (EOP) filtering process.</span></span>

## <a name="why-is-mail-queuing"></a><span data-ttu-id="3ce18-109">Varför köar e-post?</span><span class="sxs-lookup"><span data-stu-id="3ce18-109">Why is mail queuing?</span></span>

<span data-ttu-id="3ce18-110">Meddelanden köas eller skjutits upp om tjänsten inte kan upprätta en anslutning till mottagarservern för leverans.</span><span class="sxs-lookup"><span data-stu-id="3ce18-110">Messages are queued or deferred if the service is unable to make a connection to the recipient server for delivery.</span></span> <span data-ttu-id="3ce18-111">Meddelandet skjuter inte upp meddelanden om ett 500-seriefel returneras från mottagarnätverket.</span><span class="sxs-lookup"><span data-stu-id="3ce18-111">It will not defer messages if a 500-series error is returned from the recipient network.</span></span>

## <a name="how-does-a-message-become-deferred"></a><span data-ttu-id="3ce18-112">Hur uppskjuts ett meddelande?</span><span class="sxs-lookup"><span data-stu-id="3ce18-112">How does a message become deferred?</span></span>

<span data-ttu-id="3ce18-113">Meddelanden hålls kvar om det inte går att upprätta en anslutning till mottagarservern och mottagarens server returnerar ett "tillfälligt fel" som att anslutningens time out, anslutningen är misslyckad eller ett 400-seriefel.</span><span class="sxs-lookup"><span data-stu-id="3ce18-113">Messages will be held when a connection to the recipient server cannot be made and the recipient's server is returning a "temporary failure" such as a connection time-out, connection refused, or a 400-series error.</span></span> <span data-ttu-id="3ce18-114">Om det finns ett permanent fel, till exempel ett 500-seriefel, returneras meddelandet till avsändaren.</span><span class="sxs-lookup"><span data-stu-id="3ce18-114">If there is a permanent failure, such as a 500-series error, then the message will be returned to the sender.</span></span>

## <a name="how-long-does-a-message-remain-in-deferral-and-what-is-the-retry-interval"></a><span data-ttu-id="3ce18-115">Hur länge kan meddelandet skjutas upp och vad är försöksintervallet?</span><span class="sxs-lookup"><span data-stu-id="3ce18-115">How long does a message remain in deferral and what is the retry interval?</span></span>

<span data-ttu-id="3ce18-116">Meddelanden med uppsegen post finns kvar i våra köer i 1 dag.</span><span class="sxs-lookup"><span data-stu-id="3ce18-116">Messages in deferral will remain in our queues for 1 day.</span></span> <span data-ttu-id="3ce18-117">Försök att göra om meddelanden beror på felet vi får tillbaka från mottagarens e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="3ce18-117">Message retry attempts are based on the error we get back from the recipient's mail system.</span></span> <span data-ttu-id="3ce18-118">De första upp skjutas upp är 15 minuter eller mindre, med efterföljande försök (över det närmaste halvtimmen) och ökar intervallet över flera försök till högst 60 minuter.</span><span class="sxs-lookup"><span data-stu-id="3ce18-118">The first few deferrals are 15 minutes or less, with subsequent retries (over the next half dozen or so) increasing the interval over multiple retries to a max of 60 minutes.</span></span> <span data-ttu-id="3ce18-119">Intervallvaraktighetsexpansionen är dynamisk och du tas hänsyn till flera variabler som köstorlekar och intern meddelandeprioritet.</span><span class="sxs-lookup"><span data-stu-id="3ce18-119">The interval duration expansion is dynamic, taking into consideration multiple variables like queue sizes and internal message priority.</span></span> <span data-ttu-id="3ce18-120">In basic, it's 15 minutes (or less) to start, then expand from there over the next few hours to 60 mins max.</span><span class="sxs-lookup"><span data-stu-id="3ce18-120">In basic, it's 15 minutes (or less) to start, then expanding from there over the next few hours to 60 mins max.</span></span>

## <a name="after-your-email-server-is-restored-how-are-queued-messages-distributed"></a><span data-ttu-id="3ce18-121">Hur distribueras meddelanden i kö när e-postservern har återställts?</span><span class="sxs-lookup"><span data-stu-id="3ce18-121">After your email server is restored, how are queued messages distributed?</span></span>

<span data-ttu-id="3ce18-122">När e-postservern har återställts bearbetas alla i köade meddelanden automatiskt i den ordning som de togs emot och i kö när servern blev otillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3ce18-122">After your email server is restored, all queued messages are automatically processed in the order in which they were received and queued when the server became unavailable.</span></span>
