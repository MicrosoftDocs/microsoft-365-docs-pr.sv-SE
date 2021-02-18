---
title: Pooler för utgående leverans
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ac11edd9-2da3-462d-8ea3-bbf9dbc6f948
ms.collection:
- M365-security-compliance
description: Lär dig hur leveranspooler används för att skydda ryktet för e-postservrar i Microsoft 365-datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 89aac1478d3e5840df4379b9f49832b79d0e133a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289811"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="f7ff5-103">Pooler för utgående leverans</span><span class="sxs-lookup"><span data-stu-id="f7ff5-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f7ff5-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f7ff5-104">**Applies to**</span></span>
- [<span data-ttu-id="f7ff5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f7ff5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f7ff5-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f7ff5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f7ff5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7ff5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="f7ff5-108">E-postservrar i Microsoft 365-datacenter kan tillfälligt skickas skräppost.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="f7ff5-109">Till exempel skadlig kod eller skadlig skräppost-attack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterat Microsoft 365-konton.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="f7ff5-110">Attacker försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365-vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="f7ff5-111">De här scenarierna kan resultera i IP-adressen för de påverkade Microsoft 365-datacenterservrarna som visas på blockeringslistor från tredje part.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party block lists.</span></span> <span data-ttu-id="f7ff5-112">De mål-e-postorganisationer som använder de här blockeringslistorna avvisar e-post från dessa meddelandekällor.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-112">Destination email organizations that use these block lists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="f7ff5-113">Högriskleveranspool</span><span class="sxs-lookup"><span data-stu-id="f7ff5-113">High-risk delivery pool</span></span>
<span data-ttu-id="f7ff5-114">För att förhindra detta skickas alla utgående meddelanden från Microsoft 365-datacenterservrar som fastställt [](configure-the-outbound-spam-policy.md) vara skräppost eller som överskrider avsändargränserna för tjänsten eller principer för utgående skräppost via högriskleveranspoolen. [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)</span><span class="sxs-lookup"><span data-stu-id="f7ff5-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="f7ff5-115">Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som bara används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost [och bakåtcatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f7ff5-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="f7ff5-116">Genom att använda högriskleveranspoolen förhindrar du att den vanliga IP-adresspoolen för utgående e-post skickar skräppost.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="f7ff5-117">Den normala IP-adresspoolen för utgående e-post upprätthåller det rykte som skickar meddelanden av "hög kvalitet", vilket minskar sannolikheten för att denna IP-adress visas på blockeringslistor för IP.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP block lists.</span></span>

<span data-ttu-id="f7ff5-118">Den verkliga risken att IP-adresser i högriskleveranspoolen placeras i listor över IP-blockeringar finns kvar, men detta är enligt design.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP block lists remains, but this is by design.</span></span> <span data-ttu-id="f7ff5-119">Leverans till de avsedda mottagarna kan inte garanteras, eftersom många e-postorganisationer inte tar emot meddelanden från högriskleveranspoolen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="f7ff5-120">Mer information finns i [Kontrollera utgående skräppost.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="f7ff5-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7ff5-121">Meddelanden där käll-e-postdomänen inte har någon A-post och ingen MX-post som definierats i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett hur många som är skräppost eller hur många som skickas.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="f7ff5-122">Studsa meddelanden</span><span class="sxs-lookup"><span data-stu-id="f7ff5-122">Bounce messages</span></span>

<span data-ttu-id="f7ff5-123">Den utgående högriskleveranspoolen hanterar leveransen för alla rapporter om utebliven leverans (kallas även NDR-rapporter, icke-leveranskaviseringar, leveransstatusmeddelanden och DSN).</span><span class="sxs-lookup"><span data-stu-id="f7ff5-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="f7ff5-124">Möjliga orsaker till en ökning av NDR-inkluderar:</span><span class="sxs-lookup"><span data-stu-id="f7ff5-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="f7ff5-125">En förfalskningskampanj som påverkar en av de kunder som använder tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="f7ff5-126">En katalogd till exempel en skördeattack.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-126">A directory harvest attack.</span></span>
- <span data-ttu-id="f7ff5-127">En skräppostattack.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-127">A spam attack.</span></span>
- <span data-ttu-id="f7ff5-128">En falsk e-postserver.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-128">A rogue email server.</span></span>

<span data-ttu-id="f7ff5-129">Alla dessa problem kan resultera i en plötsligt ökning av antalet NDR-resultat som bearbetas av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="f7ff5-130">Ofta verkar dessa NDR-meddelanden vara skräppost till andra e-postservrar och -tjänster (kallas _[även bakåtcatter).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="f7ff5-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>

## <a name="relay-pool"></a><span data-ttu-id="f7ff5-131">Reläpool</span><span class="sxs-lookup"><span data-stu-id="f7ff5-131">Relay pool</span></span>

<span data-ttu-id="f7ff5-132">Meddelanden som vidarebefordras eller vidarebefordras från Microsoft 365 skickas med en särskild reläpool, eftersom Microsoft 365 inte bör vara den faktiska avsändaren vid slutdestinationen.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-132">Messages that are forwarded or relayed out of Microsoft 365 are sent using a special relay pool, since the final destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="f7ff5-133">Det är också viktigt att isolera den här trafiken eftersom det finns legitima och ogiltiga scenarier för automatisk vidarebefordran eller e-postutskick från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-133">It's also important for us to isolate this traffic, because there are legitimate and invalid scenarios for autoforwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="f7ff5-134">På ungefär samma sätt som högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="f7ff5-135">Den här adresspoolen publiceras inte eftersom den kan ändras ofta.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-135">This address pool is not published since it can change often.</span></span>

<span data-ttu-id="f7ff5-136">Microsoft 365 behöver verifiera att den ursprungliga avsändaren är legitim så att vi kan leverera det vidarebefordrade meddelandet med säkerhet.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span> <span data-ttu-id="f7ff5-137">För att kunna göra det måste e-postautentisering (SPF, DKIM och DMARC) passera när meddelandet kommer till oss.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-137">In order to do that, email authentication (SPF, DKIM, and DMARC) needs to pass when the message comes to us.</span></span> <span data-ttu-id="f7ff5-138">I fall där vi kan autentisera avsändaren använder vi Sender Rewriting för att hjälpa mottagaren att veta att det vidarebefordrade meddelandet kommer från en betrodd källa.</span><span class="sxs-lookup"><span data-stu-id="f7ff5-138">In cases where we can authenticate the sender, we use Sender Rewriting to help the receiver know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="f7ff5-139">Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att avsändardomänen skickar autentisering i [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span><span class="sxs-lookup"><span data-stu-id="f7ff5-139">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS)](https://docs.microsoft.com/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>
