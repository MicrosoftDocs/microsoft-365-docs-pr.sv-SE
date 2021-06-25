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
description: Lär dig hur leveranspoolerna används för att skydda ryktet för e-postservrar i Microsoft 365 datacenter.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85f200cf226a050762db4ea37255f71241d1f98c
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137733"
---
# <a name="outbound-delivery-pools"></a><span data-ttu-id="04049-103">Pooler för utgående leverans</span><span class="sxs-lookup"><span data-stu-id="04049-103">Outbound delivery pools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04049-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="04049-104">**Applies to**</span></span>
- [<span data-ttu-id="04049-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="04049-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04049-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="04049-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04049-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04049-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04049-108">E-postservrar i Microsoft 365 datacenter kan tillfälligt bli av med att skicka skräppost.</span><span class="sxs-lookup"><span data-stu-id="04049-108">Email servers in the Microsoft 365 datacenters might be temporarily guilty of sending spam.</span></span> <span data-ttu-id="04049-109">Till exempel en skadlig programvara eller skadlig skräppost-attack i en lokal e-postorganisation som skickar utgående e-post via Microsoft 365 eller komprometterat Microsoft 365 konton.</span><span class="sxs-lookup"><span data-stu-id="04049-109">For example, a malware or malicious spam attack in an on-premises email organization that sends outbound mail through Microsoft 365, or compromised Microsoft 365 accounts.</span></span> <span data-ttu-id="04049-110">Attacker försöker också undvika identifiering genom att vidarebefordra meddelanden via Microsoft 365 vidarebefordran.</span><span class="sxs-lookup"><span data-stu-id="04049-110">Attackers also try to avoid detection by relaying messages through Microsoft 365 forwarding.</span></span>

<span data-ttu-id="04049-111">De här scenarierna kan resultera i IP-adressen för Microsoft 365 datacenterservrar som visas på blockeringslistor från tredje part.</span><span class="sxs-lookup"><span data-stu-id="04049-111">These scenarios can result in the IP address of the affected Microsoft 365 datacenter servers appearing on third-party blocklists.</span></span> <span data-ttu-id="04049-112">Mål-e-postorganisationer som använder dessa blockeringslistor avvisar e-post från dessa meddelandekällor.</span><span class="sxs-lookup"><span data-stu-id="04049-112">Destination email organizations that use these blocklists will reject email from those messages sources.</span></span>

## <a name="high-risk-delivery-pool"></a><span data-ttu-id="04049-113">Högriskleveranspool</span><span class="sxs-lookup"><span data-stu-id="04049-113">High-risk delivery pool</span></span>
<span data-ttu-id="04049-114">För att förhindra detta skickas alla utgående meddelanden från Microsoft 365 datacenterservrar som fastställt vara [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) skräppost [](configure-the-outbound-spam-policy.md) eller som överskrider gränserna för att skicka ut tjänster eller utgående skräppost via _högriskleveranspoolen._</span><span class="sxs-lookup"><span data-stu-id="04049-114">To prevent this, all outbound messages from Microsoft 365 datacenter servers that's determined to be spam or that exceeds the sending limits of [the service](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or [outbound spam policies](configure-the-outbound-spam-policy.md) are sent through the _high-risk delivery pool_.</span></span>

<span data-ttu-id="04049-115">Högriskleveranspoolen är en separat IP-adresspool för utgående e-post som bara används för att skicka meddelanden av "låg kvalitet" (till exempel skräppost [och bakåtcatter).](backscatter-messages-and-eop.md)</span><span class="sxs-lookup"><span data-stu-id="04049-115">The high risk delivery pool is a separate IP address pool for outbound email that's only used to send "low quality" messages (for example, spam and [backscatter](backscatter-messages-and-eop.md)).</span></span> <span data-ttu-id="04049-116">Användning av högriskleveranspoolen förhindrar att den vanliga IP-adresspoolen för utgående e-post skickas som skräppost.</span><span class="sxs-lookup"><span data-stu-id="04049-116">Using the high risk delivery pool helps prevent the normal IP address pool for outbound email from sending spam.</span></span> <span data-ttu-id="04049-117">Den normala IP-adresspoolen för utgående e-post behåller det rykte som skickar meddelanden av "hög kvalitet", vilket minskar sannolikheten att denna IP-adress visas på IP-blockeringslistor.</span><span class="sxs-lookup"><span data-stu-id="04049-117">The normal IP address pool for outbound email maintains the reputation sending "high quality" messages, which reduces the likelihood that these IP address will appear on IP blocklists.</span></span>

<span data-ttu-id="04049-118">Den mycket stora risken att IP-adresser i högriskpoolen placeras i IP-blockeringslistor finns kvar, men detta är enligt design.</span><span class="sxs-lookup"><span data-stu-id="04049-118">The very real possibility that IP addresses in the high-risk delivery pool will be placed on IP blocklists remains, but this is by design.</span></span> <span data-ttu-id="04049-119">Leverans till de avsedda mottagarna är inte garanterad, eftersom många e-postorganisationer inte tar emot meddelanden från högriskleveranspoolen.</span><span class="sxs-lookup"><span data-stu-id="04049-119">Delivery to the intended recipients isn't guaranteed, because many email organizations won't accept messages from the high risk delivery pool.</span></span>

<span data-ttu-id="04049-120">Mer information finns i [Kontrollera utgående skräppost.](outbound-spam-controls.md)</span><span class="sxs-lookup"><span data-stu-id="04049-120">For more information, see [Control outbound spam](outbound-spam-controls.md).</span></span>

> [!NOTE]
> <span data-ttu-id="04049-121">Meddelanden där käll-e-postdomänen inte har någon A-post och ingen MX-post som definierats i offentlig DNS dirigeras alltid genom högriskleveranspoolen, oavsett deras disposition av skräppost eller sändningsgräns.</span><span class="sxs-lookup"><span data-stu-id="04049-121">Messages where the source email domain has no A record and no MX record defined in public DNS are always routed through the high-risk delivery pool, regardless of their spam or sending limit disposition.</span></span>

### <a name="bounce-messages"></a><span data-ttu-id="04049-122">Studsande meddelanden</span><span class="sxs-lookup"><span data-stu-id="04049-122">Bounce messages</span></span>

<span data-ttu-id="04049-123">Leveranspoolen för utgående högriskleverans hanterar leveransen för alla rapporter om utebliven leverans (kallas även NDR-rapporter, icke-leveranskaviseringar, leveransstatusmeddelanden och DSN-meddelanden).</span><span class="sxs-lookup"><span data-stu-id="04049-123">The outbound high-risk delivery pool manages the delivery for all non-delivery reports (also known as NDRs, bounce messages, delivery status notifications, or DSNs).</span></span>

<span data-ttu-id="04049-124">Möjliga orsaker till en ökning av NDR-fel är:</span><span class="sxs-lookup"><span data-stu-id="04049-124">Possible causes for a surge in NDRs include:</span></span>

- <span data-ttu-id="04049-125">En förfalskningskampanj som påverkar en av kunderna som använder tjänsten.</span><span class="sxs-lookup"><span data-stu-id="04049-125">A spoofing campaign that affects one of the customers using the service.</span></span>
- <span data-ttu-id="04049-126">En katalogd till-skördeattack.</span><span class="sxs-lookup"><span data-stu-id="04049-126">A directory harvest attack.</span></span>
- <span data-ttu-id="04049-127">En skräppostattack.</span><span class="sxs-lookup"><span data-stu-id="04049-127">A spam attack.</span></span>
- <span data-ttu-id="04049-128">En falsk e-postserver.</span><span class="sxs-lookup"><span data-stu-id="04049-128">A rogue email server.</span></span>

<span data-ttu-id="04049-129">Alla dessa problem kan resultera i en plötsligt ökning av antalet NDR-resultat som bearbetas av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="04049-129">All of these issues can result in a sudden increase in the number of NDRs being processed by the service.</span></span> <span data-ttu-id="04049-130">Ofta verkar dessa NDR-meddelanden vara skräppost till andra e-postservrar och -tjänster (kallas även _[bakåtcatter).](backscatter-messages-and-eop.md)_</span><span class="sxs-lookup"><span data-stu-id="04049-130">Many times, these NDRs appear to be spam to other email servers and services (also known as _[backscatter](backscatter-messages-and-eop.md)_).</span></span>


### <a name="relay-pool"></a><span data-ttu-id="04049-131">Reläpool</span><span class="sxs-lookup"><span data-stu-id="04049-131">Relay pool</span></span>

<span data-ttu-id="04049-132">Meddelanden som vidarebefordras eller vidarebefordras via Microsoft 365 i vissa fall skickas med en särskild reläpool, eftersom målet inte bör överväga Microsoft 365 som den faktiska avsändaren.</span><span class="sxs-lookup"><span data-stu-id="04049-132">Messages that are forwarded or relayed via Microsoft 365 in certain scenarios will be sent using a special relay pool, because the destination should not consider Microsoft 365 as the actual sender.</span></span> <span data-ttu-id="04049-133">Det är viktigt att vi isolerar den här e-posttrafiken eftersom det finns legitima och ogiltiga scenarier för automatisk vidarebefordran eller vidarebefordra e-Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04049-133">It's important for us to isolate this email traffic, because there are legitimate and invalid scenarios for auto forwarding or relaying email out of Microsoft 365.</span></span> <span data-ttu-id="04049-134">På ungefär samma sätt som högriskleveranspoolen används en separat IP-adresspool för vidarebefordrad e-post.</span><span class="sxs-lookup"><span data-stu-id="04049-134">Similar to the high-risk delivery pool, a separate IP address pool is used for relayed mail.</span></span> <span data-ttu-id="04049-135">Den här adresspoolen publiceras inte eftersom den kan ändras ofta, och den är inte en del av den publicerade SPF-posten för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04049-135">This address pool is not published because it can change often, and it's not part of published SPF record for Microsoft 365.</span></span>

<span data-ttu-id="04049-136">Microsoft 365 att verifiera att den ursprungliga avsändaren är legitim så att vi kan leverera det vidarebefordrade meddelandet med tillförsikt.</span><span class="sxs-lookup"><span data-stu-id="04049-136">Microsoft 365 needs to verify that the original sender is legitimate so we can confidently deliver the forwarded message.</span></span>

<span data-ttu-id="04049-137">Det vidarebefordrade/vidarebefordrade meddelandet bör uppfylla något av följande kriterier för att undvika att använda reläpoolen:</span><span class="sxs-lookup"><span data-stu-id="04049-137">The forwarded/relayed message should meet one of the following criteria to avoid using the relay pool:</span></span>

- <span data-ttu-id="04049-138">Den utgående avsändaren finns i en [godkänd domän.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="04049-138">The outbound sender is in an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
- <span data-ttu-id="04049-139">SPF passerar när meddelandet kommer till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04049-139">SPF passes when the message comes to Microsoft 365.</span></span>
- <span data-ttu-id="04049-140">DKIM för avsändardomänen passeras när meddelandet kommer till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04049-140">DKIM on the sender domain passes when the message comes to Microsoft 365.</span></span>
 
<span data-ttu-id="04049-141">Du kan se att ett meddelande har skickats via reläpoolen genom att titta på den utgående server-IP:n (reläpoolen finns i intervallet 40.95.0.0/16), eller genom att titta på den utgående servernamnet (har "rly" i namnet).</span><span class="sxs-lookup"><span data-stu-id="04049-141">You can tell that a message was sent via the relay pool by looking at the outbound server IP (the relay pool will be in the 40.95.0.0/16 range), or by looking at the outbound server name (will have "rly" in the name).</span></span>

<span data-ttu-id="04049-142">I fall där vi kan autentisera avsändaren använder vi SRS (Sender Rewriting Scheme) för att hjälpa mottagarens e-postsystem att veta att det vidarebefordrade meddelandet kommer från en betrodd källa.</span><span class="sxs-lookup"><span data-stu-id="04049-142">In cases where we can authenticate the sender, we use Sender Rewriting Scheme (SRS) to help the recipient email system know that the forwarded message is from a trusted source.</span></span> <span data-ttu-id="04049-143">Du kan läsa mer om hur det fungerar och vad du kan göra för att se till att sändningsdomänen skickar autentisering i [SRS (Sender Rewriting Scheme) i Office 365.](/office365/troubleshoot/antispam/sender-rewriting-scheme)</span><span class="sxs-lookup"><span data-stu-id="04049-143">You can read more about how that works and what you can do to help make sure the sending domain passes authentication in [Sender Rewriting Scheme (SRS) in Office 365](/office365/troubleshoot/antispam/sender-rewriting-scheme).</span></span>

<span data-ttu-id="04049-144">För att DKIM ska fungera måste du aktivera DKIM för att skicka domän.</span><span class="sxs-lookup"><span data-stu-id="04049-144">For DKIM to work, make sure you enable DKIM for sending domain.</span></span> <span data-ttu-id="04049-145">Till exempel fabrikam.com en del av contoso.com och definieras i organisationens godkända domäner.</span><span class="sxs-lookup"><span data-stu-id="04049-145">For example, fabrikam.com is part of contoso.com and is defined in the accepted domains of the organization.</span></span> <span data-ttu-id="04049-146">Om meddelandets avsändare är sender@fabrikam.com, måste DKIM aktiveras för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="04049-146">If the message sender is sender@fabrikam.com, DKIM needs to be enabled for fabrikam.com.</span></span> <span data-ttu-id="04049-147">du kan läsa om hur du aktiverar i [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="04049-147">you can read on how to enable at [Use DKIM to validate outbound email sent from your custom domain](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="04049-148">Om du vill lägga till en egen domän följer du stegen [i Lägga till en domän i Microsoft 365](../../admin/setup/add-domain.md).</span><span class="sxs-lookup"><span data-stu-id="04049-148">To add a custom domains follow the steps in [Add a domain to Microsoft 365](../../admin/setup/add-domain.md).</span></span>
