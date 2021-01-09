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
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787979"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="0e4ca-103">Säkra som standard i Office 365</span><span class="sxs-lookup"><span data-stu-id="0e4ca-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0e4ca-104">"Säkra som standard" är en term som används för att definiera de standardinställningar som är mest säkra.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="0e4ca-105">Säkerheten måste dock bal anse ras.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="0e4ca-106">Detta kan vara en balans mellan:</span><span class="sxs-lookup"><span data-stu-id="0e4ca-106">This can include balancing across:</span></span>

- <span data-ttu-id="0e4ca-107">**Användbarhet**: inställningarna ska inte komma i vägen för användar produktivitet.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-107">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="0e4ca-108">**Risk**: säkerheten kan blockera viktiga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-108">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="0e4ca-109">**Äldre inställningar**: vissa konfigurationer för äldre produkter och funktioner kan behöva bevaras av företags skäl, även om nya, moderna inställningar förbättras.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-109">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="0e4ca-110">Microsoft 365-organisationer med post lådor i Exchange Online skyddas av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="0e4ca-111">Detta skydd inkluderar:</span><span class="sxs-lookup"><span data-stu-id="0e4ca-111">This protection includes:</span></span>

- <span data-ttu-id="0e4ca-112">E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="0e4ca-113">Se [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="0e4ca-114">E-postmeddelanden som identifieras som ett högkonfidens nät fiske hanteras enligt policyn för skydd mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-114">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="0e4ca-115">Se [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="0e4ca-116">Mer information om EOP finns i [Översikt över Exchange Online-skydd](exchange-online-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-116">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="0e4ca-117">Eftersom Microsoft vill hålla våra kunder säkra som standard, tillämpas vissa klient organisationer inte på skadlig program vara eller nätfiske med hög exakthet.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="0e4ca-118">Dessa åsidosättningar inkluderar:</span><span class="sxs-lookup"><span data-stu-id="0e4ca-118">These overrides include:</span></span>

- <span data-ttu-id="0e4ca-119">Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)</span><span class="sxs-lookup"><span data-stu-id="0e4ca-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="0e4ca-120">Säkra avsändare i Outlook</span><span class="sxs-lookup"><span data-stu-id="0e4ca-120">Outlook Safe Senders</span></span>
- <span data-ttu-id="0e4ca-121">Lista över tillåtna IP-adresser (anslutnings filter)</span><span class="sxs-lookup"><span data-stu-id="0e4ca-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="0e4ca-122">Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-122">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="0e4ca-123">Säkra som standard är inte en inställning som kan sättas på eller av, men är det sätt på vilket vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-123">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="0e4ca-124">Nätfiske och högsäker nät fiske meddelanden bör vara i karantän.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-124">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="0e4ca-125">Endast administratörer kan hantera meddelanden som är i karantän som skadlig eller högkonfidens nätfiske, och de kan också rapportera falska positiva positiv till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-125">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="0e4ca-126">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="0e4ca-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="0e4ca-127">Mer om varför vi gör detta</span><span class="sxs-lookup"><span data-stu-id="0e4ca-127">More on why we're doing this</span></span>

<span data-ttu-id="0e4ca-128">Den anda som är säker som standard är: Vi utför samma åtgärd på meddelandet som du skulle vidta om du kände till att meddelandet är skadligt, även om det var något möjligt.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-128">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even if there was an allow in place.</span></span> <span data-ttu-id="0e4ca-129">Det här är samma metod som vi har använt på skadlig program vara och nu utökas samma sak med högsäker nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-129">This is the same approach that we've used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span> <span data-ttu-id="0e4ca-130">I våra data anges att den felaktiga positiva taxan för nät fiske samtal är väldigt svag och administratörer kan lösa eventuella falska positiva godkännanden med administratörs inlämningar.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-130">Our data indicates that the false positive rate for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span> <span data-ttu-id="0e4ca-131">I våra data anges också att listan Tillåtna avsändare och tillåtna domän listor i principer för skräp post och betrodda avsändare i Outlook var för omfattande och vållar mindre skada.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-131">Our data also indicates that the allowed sender lists and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and causing more harm than good.</span></span>

<span data-ttu-id="0e4ca-132">Så här lägger du till det på ett annat sätt: som en säkerhets tjänst, agerar vi för din räkning för att förhindra att användarna angrips.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-132">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> <span data-ttu-id="0e4ca-133">Dessutom är säkra som standard inte ett fullständigt övertag ande av dina tillgängliga alternativ för nät fiske meddelanden med skydd mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-133">In addition, secure by default is not a full takeover of your available options for high confidence phishing messages in anti-spam policies.</span></span> <span data-ttu-id="0e4ca-134">Även om vi rekommenderar karantän är de andra åtgärderna som alltid är tillgängliga fortfarande tillgängliga (flytta till mappen skräp post eller omdirigera till en e-postadress).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-134">Although we recommend Quarantine, the other actions that have always been available are still available (Move to Junk Email folder or Redirect to an email address).</span></span>

## <a name="exceptions"></a><span data-ttu-id="0e4ca-135">Undanta</span><span class="sxs-lookup"><span data-stu-id="0e4ca-135">Exceptions</span></span>

<span data-ttu-id="0e4ca-136">Den enda åsidosättning som möjliggör högsäker nät fiske meddelande för att kringgå filtrering är regler för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-136">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="0e4ca-137">Om du vill använda regler för e-postflöde för att kringgå filtrering läser du [använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="0e4ca-137">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="0e4ca-138">Du bör bara använda åsidosättningar i följande fall:</span><span class="sxs-lookup"><span data-stu-id="0e4ca-138">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="0e4ca-139">Nät fiske simulering: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-139">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="0e4ca-140">Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-140">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="0e4ca-141">Teams kan sedan granska för att se om de innehåller skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-141">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="0e4ca-142">Filter från tredje part är säkert som standard gäller inte när domänens MX-post inte pekar på Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-142">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="0e4ca-143">Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="0e4ca-143">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="0e4ca-144">Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="0e4ca-144">As with all overrides, it is recommended that they are temporary.</span></span>
