---
title: Säkra som standard i Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Lär dig mer om inställningen säker med standardinställningen i Exchange Online Protection (EOP)
ms.openlocfilehash: d4345134e98ae204f73dfb51a0abf5136590a24c
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126667"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="7dbc1-103">Säkra som standard i Office 365</span><span class="sxs-lookup"><span data-stu-id="7dbc1-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7dbc1-104">"Säkra som standard" är en term som används för att definiera de standardinställningar som är mest säkra.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="7dbc1-105">Säkerheten måste dock bal anse ras.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="7dbc1-106">Detta kan vara en balans mellan:</span><span class="sxs-lookup"><span data-stu-id="7dbc1-106">This can include balancing across:</span></span>

- <span data-ttu-id="7dbc1-107">Användbarhet: inställningarna ska inte komma i vägen för användar produktivitet.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="7dbc1-108">Risk: säkerheten kan blockera viktiga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="7dbc1-109">Äldre inställningar: vissa konfigurationer för äldre produkter och funktioner kan behöva bevaras av företags skäl, även om nya, moderna inställningar förbättras.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="7dbc1-110">Microsoft 365-organisationer med post lådor i Exchange Online skyddas av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="7dbc1-111">Detta skydd inkluderar:</span><span class="sxs-lookup"><span data-stu-id="7dbc1-111">This protection includes:</span></span>

1. <span data-ttu-id="7dbc1-112">E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="7dbc1-113">Se [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="7dbc1-114">Nät fiske meddelande som identifieras som "hög exakthet" hanteras i enlighet med åtgärd för att förhindra skräp post.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="7dbc1-115">Se [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="7dbc1-116">Eftersom Microsoft vill hålla våra kunder säkra som standard, används vissa klient organisationer inte för skadlig program vara eller Phish.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="7dbc1-117">Dessa åsidosättningar inkluderar:</span><span class="sxs-lookup"><span data-stu-id="7dbc1-117">These overrides include:</span></span>

- <span data-ttu-id="7dbc1-118">Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="7dbc1-119">Säkra avsändare i Outlook</span><span class="sxs-lookup"><span data-stu-id="7dbc1-119">Outlook Safe senders</span></span>
- <span data-ttu-id="7dbc1-120">Lista över tillåtna IP-adresser (anslutnings filter)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="7dbc1-121">Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="7dbc1-122">Alternativet säker som standard är inte en inställning som kan aktive ras eller avaktiveras, men det är så att vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="7dbc1-123">Malware och högkonfidens nätfiske bör skickas till karantänen.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="7dbc1-124">Endast administratörer kan hantera meddelanden som satts i karantän som skadlig eller högsäker nätfiske och de kan också rapportera falska positiva positiv till Microsoft därifrån.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="7dbc1-125">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="7dbc1-126">Undanta</span><span class="sxs-lookup"><span data-stu-id="7dbc1-126">Exceptions</span></span>

<span data-ttu-id="7dbc1-127">Den enda åsidosättning som möjliggör högsäker nät fiske meddelande för att kringgå filtrering är regler för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="7dbc1-128">Om du vill använda regler för e-postflöde för att kringgå filtrering läser du [använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="7dbc1-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="7dbc1-129">Åsidosättningar ska endast användas för:</span><span class="sxs-lookup"><span data-stu-id="7dbc1-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="7dbc1-130">Nät fiske simulering: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="7dbc1-131">Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="7dbc1-132">Teams kan sedan granska för att se om de innehåller skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="7dbc1-133">Filter från tredje part: vissa leverantörer av tredje part rekommenderar att du inaktiverar EOP (SCL =-1) när filtret för tredje part hanterar e-postfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-133">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="7dbc1-134">Microsoft rekommenderar inte att du inaktiverar EOP eftersom EOP krävs för Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="7dbc1-135">Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7dbc1-135">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="7dbc1-136">Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="7dbc1-136">As with all overrides, it is recommended that they are temporary.</span></span>
