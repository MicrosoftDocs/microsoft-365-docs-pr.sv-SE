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
description: Lär dig hur du hittar och använder e-postsäkerhets rapporter för organisationen. Säkerhets rapporter för e-post finns i säkerhets & Compliance Center.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944543"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="60044-104">Säkra som standard i Office 365</span><span class="sxs-lookup"><span data-stu-id="60044-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="60044-105">"Säkra som standard" är en term som används för att definiera de standardinställningar som är mest säkra.</span><span class="sxs-lookup"><span data-stu-id="60044-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="60044-106">Säkerheten måste dock bal anse ras.</span><span class="sxs-lookup"><span data-stu-id="60044-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="60044-107">Detta kan vara en balans mellan:</span><span class="sxs-lookup"><span data-stu-id="60044-107">This can include balancing across:</span></span>
- <span data-ttu-id="60044-108">Användbarhet: inställningarna ska inte komma i vägen för användar produktivitet.</span><span class="sxs-lookup"><span data-stu-id="60044-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="60044-109">Risk: säkerheten kan blockera viktiga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="60044-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="60044-110">Äldre inställningar: vissa konfigurationer för äldre produkter och funktioner kan behöva bevaras av företags skäl, även om nya, moderna inställningar förbättras.</span><span class="sxs-lookup"><span data-stu-id="60044-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="60044-111">Microsoft 365-organisationer med post lådor i Exchange Online skyddas av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="60044-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="60044-112">Detta skydd inkluderar:</span><span class="sxs-lookup"><span data-stu-id="60044-112">This  protection includes:</span></span>
1. <span data-ttu-id="60044-113">E-post med misstänkt skadlig program vara placeras automatiskt i karantän och mottagarna får ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="60044-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="60044-114">Se [Konfigurera principer för skydd mot skadlig program vara i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="60044-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="60044-115">Nät fiske meddelande som identifieras som "hög exakthet" hanteras i enlighet med åtgärd för att förhindra skräp post.</span><span class="sxs-lookup"><span data-stu-id="60044-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="60044-116">Se [Konfigurera principer för skräp post i EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="60044-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="60044-117">Eftersom Microsoft vill hålla våra kunder säkra som standard, används vissa klient organisationer inte för skadlig program vara eller Phish.</span><span class="sxs-lookup"><span data-stu-id="60044-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="60044-118">Dessa åsidosättningar inkluderar:</span><span class="sxs-lookup"><span data-stu-id="60044-118">These overrides include:</span></span>
- <span data-ttu-id="60044-119">Listan Tillåtna avsändare eller tillåtna domän listor (principer för skräp post)</span><span class="sxs-lookup"><span data-stu-id="60044-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="60044-120">Säkra avsändare i Outlook</span><span class="sxs-lookup"><span data-stu-id="60044-120">Outlook Safe senders</span></span>
- <span data-ttu-id="60044-121">Lista över tillåtna IP-adresser (anslutnings filter)</span><span class="sxs-lookup"><span data-stu-id="60044-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="60044-122">Mer information om dessa åsidosättningar finns i [skapa säkra avsändare](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="60044-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="60044-123">Alternativet säker som standard är inte en inställning som kan aktive ras eller avaktiveras, men det är så att vårt filter fungerar för att behålla potentiellt farliga eller oönskade meddelanden från dina post lådor.</span><span class="sxs-lookup"><span data-stu-id="60044-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="60044-124">Skadlig program vara och Phish med hög exakthet bör skickas till karantän.</span><span class="sxs-lookup"><span data-stu-id="60044-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="60044-125">Endast administratörer kan hantera meddelanden som satts i karantän som skadlig eller högsäker nätfiske och de kan också rapportera falska positiva positiv till Microsoft därifrån.</span><span class="sxs-lookup"><span data-stu-id="60044-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="60044-126">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="60044-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="60044-127">Undanta</span><span class="sxs-lookup"><span data-stu-id="60044-127">Exceptions</span></span>
<span data-ttu-id="60044-128">De enda åsidosättningar som kommer att kringgå alla filter är:</span><span class="sxs-lookup"><span data-stu-id="60044-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="60044-129">Regler för Exchange-Exchange (/mail).</span><span class="sxs-lookup"><span data-stu-id="60044-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="60044-130">Använd regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden i EOP.</span><span class="sxs-lookup"><span data-stu-id="60044-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="60044-131">Tillåt/blockera i klient organisation: hantera URL-adresser och filer i listan Tillåt/blockera för klient organisation.</span><span class="sxs-lookup"><span data-stu-id="60044-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="60044-132">Dessa typer av åsidosättningar är användbara för:</span><span class="sxs-lookup"><span data-stu-id="60044-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="60044-133">Phish simuleringar: simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="60044-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="60044-134">Säkerhets-SecOps post lådor: dedikerade post lådor som används av säkerhets team för att få ofiltrerad meddelanden (både bra och dåligt).</span><span class="sxs-lookup"><span data-stu-id="60044-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="60044-135">Teams kan sedan granska för att se om de innehåller skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="60044-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="60044-136">Filter från tredje part: vissa leverantörer av tredje part rekommenderar att du inaktiverar EOP (SCL =-1) när filtret för tredje part hanterar e-postfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="60044-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="60044-137">Microsoft rekommenderar inte att du inaktiverar EOP eftersom EOP krävs för Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="60044-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="60044-138">Falsk positiva uppgifter: du kanske vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörs inlämningar](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="60044-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="60044-139">Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="60044-139">As with all overrides, it is recommended that they are temporary.</span></span>
