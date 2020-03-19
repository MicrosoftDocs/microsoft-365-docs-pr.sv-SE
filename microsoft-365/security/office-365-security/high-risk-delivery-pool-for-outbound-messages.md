---
title: Högriskleveranspool för utgående meddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/24/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: När en kunds e-postsystem har komprometterats av skadlig kod eller en skadlig skräppostattack, och den skickar utgående skräppost via den värdbaserade filtreringstjänsten, kan detta leda till att IP-adresserna till Office 365-datacenterservrarna visas på block från tredje part Listor.
ms.openlocfilehash: 19987ae74b9c78a796ddb5f13cf8291a5ed269ad
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42808608"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="48fad-103">Högriskleveranspool för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="48fad-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="48fad-104">När en kunds e-postsystem har komprometterats av skadlig kod eller en skadlig skräppostattack, och den skickar utgående skräppost via den värdbaserade filtreringstjänsten, kan detta leda till att IP-adresserna till Office 365-datacenterservrarna visas på block från tredje part Listor.</span><span class="sxs-lookup"><span data-stu-id="48fad-104">When a customer's email system has been compromised by malware or a malicious spam attack, and it's sending outbound spam through the hosted filtering service, this can result in the IP addresses of the Office 365 data center servers being listed on third-party block lists.</span></span> <span data-ttu-id="48fad-105">Målservrar som inte använder den värdbaserade filtreringstjänsten, men som använder dessa blockeringslistor, avvisar alla e-postmeddelanden som skickas från någon av de värdbaserade filtrerings-IP-adresserna som har lagts till i dessa listor.</span><span class="sxs-lookup"><span data-stu-id="48fad-105">Destination servers that do not use the hosted filtering service, but do use these block lists, reject all email sent from any of the hosted filtering IP addresses that have been added to those lists.</span></span> <span data-ttu-id="48fad-106">För att förhindra detta skickas alla utgående meddelanden som överskrider skräpposttröskeln via en leveranspool med hög risk.</span><span class="sxs-lookup"><span data-stu-id="48fad-106">To prevent this, all outbound messages that exceed the spam threshold are sent through a high-risk delivery pool.</span></span> <span data-ttu-id="48fad-107">Den här sekundära utgående e-postpoolen används endast för att skicka meddelanden som kan vara av låg kvalitet.</span><span class="sxs-lookup"><span data-stu-id="48fad-107">This secondary outbound email pool is only used to send messages that may be of low quality.</span></span> <span data-ttu-id="48fad-108">Detta hjälper till att skydda resten av nätverket från att skicka meddelanden som är mer benägna att resultera i att den sändande IP-adressen blockeras.</span><span class="sxs-lookup"><span data-stu-id="48fad-108">This helps to protect the rest of the network from sending messages that are more likely to result in the sending IP address being blocked.</span></span>
  
<span data-ttu-id="48fad-109">Användningen av en särskild högriskleveranspool säkerställer att den normala utgående poolen bara skickar meddelanden som är kända för att vara av hög kvalitet.</span><span class="sxs-lookup"><span data-stu-id="48fad-109">The use of a dedicated high-risk delivery pool helps ensure that the normal outbound pool is only sending messages that are known to be of a high-quality.</span></span> <span data-ttu-id="48fad-110">Med den här sekundära IP-poolen kan du minska sannolikheten för att den normala utgående IP-poolen läggs till i en blockerad lista.</span><span class="sxs-lookup"><span data-stu-id="48fad-110">Using this secondary IP pool helps to reduce the probability of the normal outbound-IP pool being added to a blocked list.</span></span> <span data-ttu-id="48fad-111">Möjligheten att högriskpoolen placeras på en blockerad lista är fortfarande en risk.</span><span class="sxs-lookup"><span data-stu-id="48fad-111">The possibility of the high-risk delivery pool being placed on a blocked list remains a risk.</span></span> <span data-ttu-id="48fad-112">Detta är avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="48fad-112">This is by design.</span></span>
  
<span data-ttu-id="48fad-113">Meddelanden där den sändande domänen inte har någon adresspost (A-post), som ger dig domänens IP-adress, och ingen MX-post, som hjälper direktreklam till de servrar som ska ta emot e-post för en viss domän i DNS, dirigeras alltid genom högriskleveranspool oavsett deras spamdisposition.</span><span class="sxs-lookup"><span data-stu-id="48fad-113">Messages where the sending domain has no address record (A record), which gives you the IP address of the domain, and no MX record, which helps direct mail to the servers that should receive the mail for a particular domain in the DNS, are always routed through the high-risk delivery pool regardless of their spam disposition.</span></span>
  
## <a name="understanding-delivery-status-notification-dsn-messages"></a><span data-ttu-id="48fad-114">Förstå DSN-meddelanden (Delivery Status Message)</span><span class="sxs-lookup"><span data-stu-id="48fad-114">Understanding Delivery Status Notification (DSN) messages</span></span>

<span data-ttu-id="48fad-115">Den utgående högriskleveranspoolen hanterar leveransen för alla "studsade" eller "misslyckade" (DSN) meddelanden.</span><span class="sxs-lookup"><span data-stu-id="48fad-115">The outbound high-risk delivery pool manages the delivery for all "bounced" or "failed" (DSN) messages.</span></span>
  
<span data-ttu-id="48fad-116">Möjliga orsaker till en ökning av DSN-meddelanden är följande:</span><span class="sxs-lookup"><span data-stu-id="48fad-116">Possible causes for a surge in DSN messages include the following:</span></span>
  
- <span data-ttu-id="48fad-117">En förfalskningskampanj som påverkar en av kunderna som använder tjänsten</span><span class="sxs-lookup"><span data-stu-id="48fad-117">A spoofing campaign affecting one of the customers using the service</span></span>
    
- <span data-ttu-id="48fad-118">En katalog skörd attack</span><span class="sxs-lookup"><span data-stu-id="48fad-118">A directory harvest attack</span></span>
    
- <span data-ttu-id="48fad-119">En spamattack</span><span class="sxs-lookup"><span data-stu-id="48fad-119">A spam attack</span></span>
    
- <span data-ttu-id="48fad-120">En oseriös SMTP-server</span><span class="sxs-lookup"><span data-stu-id="48fad-120">A rogue SMTP server</span></span>
    
<span data-ttu-id="48fad-121">Alla dessa problem kan resultera i en plötslig ökning av antalet DSN-meddelanden som bearbetas av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="48fad-121">All of these issues can result in a sudden increase in the number of DSN messages being processed by the service.</span></span> <span data-ttu-id="48fad-122">Många gånger verkar dessa DSN-meddelanden vara skräppost till andra e-postservrar och -tjänster.</span><span class="sxs-lookup"><span data-stu-id="48fad-122">Many times, these DSN messages appear to be spam to other email servers and services.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="48fad-123">Mer information</span><span class="sxs-lookup"><span data-stu-id="48fad-123">For more information</span></span>

[<span data-ttu-id="48fad-124">Konfigurera principen för skräppost för utgående</span><span class="sxs-lookup"><span data-stu-id="48fad-124">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="48fad-125">Vanliga frågor om skydd mot skräppost</span><span class="sxs-lookup"><span data-stu-id="48fad-125">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

