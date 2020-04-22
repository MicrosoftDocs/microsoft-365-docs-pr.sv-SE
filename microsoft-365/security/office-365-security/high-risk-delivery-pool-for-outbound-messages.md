---
title: Leveranspool med hög risk för utgående meddelanden
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
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur högriskleveranspoolen används för att skydda ryktet för e-postservrar i Microsoft 365-datacenter.
ms.openlocfilehash: 7fb4788361534335be1e07bae44ed7511bebe434
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638040"
---
# <a name="high-risk-delivery-pool-for-outbound-messages"></a><span data-ttu-id="74227-103">Leveranspool med hög risk för utgående meddelanden</span><span class="sxs-lookup"><span data-stu-id="74227-103">High-risk delivery pool for outbound messages</span></span>

<span data-ttu-id="74227-104">E-postservrar i Microsoft 365 datacenter kan vara tillfälligt skyldiga till att skicka skräppost.</span><span class="sxs-lookup"><span data-stu-id="74227-104">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="74227-105">Till exempel en skadlig kod eller skadlig skräppostattack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterade Microsoft 365-konton.</span><span class="sxs-lookup"><span data-stu-id="74227-105">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="74227-106">Dessa scenarier kan resultera i IP-adressen för de berörda Microsoft 365 datacenterservrar som visas på tredje parts blocklistor.</span><span class="sxs-lookup"><span data-stu-id="74227-106">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="74227-107">Mål e-postorganisationer som använder dessa blocklistor kommer att avvisa e-post från dessa meddelanden källor.</span><span class="sxs-lookup"><span data-stu-id="74227-107">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

<span data-ttu-id="74227-108">För att förhindra detta skickas alla utgående meddelanden från Microsoft 365 datacenterservrar som är fast beslutna att vara skräppost eller som överskrider sändningsgränserna för [tjänsten](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) eller [utgående skräppostpolicyer](configure-the-outbound-spam-policy.md) via _högriskleveranspoolen_.</span><span class="sxs-lookup"><span data-stu-id="74227-108">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="74227-109">Högriskleveranspoolen är en sekundär IP-adresspool för utgående e-post som endast används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost och [backscatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="74227-109">The high risk delivery pool is a secondary IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="74227-110">Med hjälp av hög risk leveranspoolen hjälper till att förhindra den normala IP-adresspoolen för utgående e-post från att skicka skräppost.</span><span class="sxs-lookup"><span data-stu-id="74227-110">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="74227-111">Den normala IP-adresspoolen för utgående e-post upprätthåller ryktet att skicka "högkvalitativa" meddelanden, vilket minskar sannolikheten för att dessa IP-adresser visas på IP-blockeringslistor.</span><span class="sxs-lookup"><span data-stu-id="74227-111">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="74227-112">Den mycket verkliga möjligheten att IP-adresser i högriskleveranspoolen kommer att placeras på IP-blocklistor kvarstår, men detta är avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="74227-112">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="74227-113">Leverans till de avsedda mottagarna är inte garanterad, eftersom många e-postorganisationer inte accepterar meddelanden från högriskleveranspoolen.</span><span class="sxs-lookup"><span data-stu-id="74227-113">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="74227-114">Mer information finns i [Kontrollera utgående skräppost](outbound-spam-controls.md).</span><span class="sxs-lookup"><span data-stu-id="74227-114">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="74227-115">Meddelanden där källe-domänen inte har någon A-post och ingen MX-post som definieras i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett deras spam eller skicka gränsdisposition.</span><span class="sxs-lookup"><span data-stu-id="74227-115">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

## <a name="bounce-messages"></a><span data-ttu-id="74227-116">Studsa meddelanden</span><span class="sxs-lookup"><span data-stu-id="74227-116">Bounce messages</span></span>

<span data-ttu-id="74227-117">Den utgående högriskleveranspoolen hanterar leveransen för alla rapporter som inte levereras (kallas även NDRs, avstudsmeddelanden, leveransstatusmeddelanden eller DSN-nätverk).</span><span class="sxs-lookup"><span data-stu-id="74227-117">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="74227-118">Möjliga orsaker till en ökning av NDR inkluderar:</span><span class="sxs-lookup"><span data-stu-id="74227-118">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="74227-119">En förfalskningskampanj som påverkar en av kunderna som använder tjänsten.</span><span class="sxs-lookup"><span data-stu-id="74227-119">A spoofing campaign that affects one of the customers using the service.</span></span>

- <span data-ttu-id="74227-120">En katalog skörd attack.</span><span class="sxs-lookup"><span data-stu-id="74227-120">A directory harvest attack.</span></span>

- <span data-ttu-id="74227-121">En spamattack.</span><span class="sxs-lookup"><span data-stu-id="74227-121">A spam attack.</span></span>

- <span data-ttu-id="74227-122">En oseriös e-postserver.</span><span class="sxs-lookup"><span data-stu-id="74227-122">A rogue email server.</span></span>

<span data-ttu-id="74227-123">Alla dessa problem kan resultera i en plötslig ökning av antalet NDR som behandlas av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="74227-123">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="74227-124">Många gånger, dessa NDRs verkar vara spam till andra e-postservrar och tjänster (även känd som _[backscatter).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="74227-124">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>
