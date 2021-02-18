---
title: Säker som standard i Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Läs mer om den säkra inställningen som standard i Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a507abce8c18657794b56570241570e5048b89d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288519"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="ff645-103">Säker som standard i Office 365</span><span class="sxs-lookup"><span data-stu-id="ff645-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ff645-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ff645-104">**Applies to**</span></span>
- [<span data-ttu-id="ff645-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ff645-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ff645-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ff645-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="ff645-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff645-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="ff645-108">"Säker som standard" är en term som används för att definiera vilka standardinställningar som är säkrast som möjligt.</span><span class="sxs-lookup"><span data-stu-id="ff645-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="ff645-109">Säkerheten måste dock balanseras med produktiviteten.</span><span class="sxs-lookup"><span data-stu-id="ff645-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="ff645-110">Detta kan innefatta balans mellan:</span><span class="sxs-lookup"><span data-stu-id="ff645-110">This can include balancing across:</span></span>

- <span data-ttu-id="ff645-111">**Användbarhet:** Inställningar bör inte vara i vägen för användarnas produktivitet.</span><span class="sxs-lookup"><span data-stu-id="ff645-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="ff645-112">**Risk:** Säkerheten kan blockera viktiga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="ff645-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="ff645-113">**Äldre inställningar:** Vissa konfigurationer för äldre produkter och funktioner kan behöva underhållas av företagsskäl, även om nya, moderna inställningar förbättras.</span><span class="sxs-lookup"><span data-stu-id="ff645-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="ff645-114">Microsoft 365-organisationer med postlådor i Exchange Online skyddas av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="ff645-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="ff645-115">Skyddet omfattar:</span><span class="sxs-lookup"><span data-stu-id="ff645-115">This protection includes:</span></span>

- <span data-ttu-id="ff645-116">E-post med misstänkt skadlig programvara sätts automatiskt i karantän och mottagare meddelas.</span><span class="sxs-lookup"><span data-stu-id="ff645-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="ff645-117">Se [Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="ff645-118">E-post som identifieras som nätfiske hanteras i enlighet med policyåtgärden mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="ff645-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="ff645-119">Se [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ff645-120">Mer information om EOP finns i [Översikt över Exchange Online Protection.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="ff645-121">Eftersom Microsoft vill att våra kunder ska vara säkra som standard tillämpas inte vissa åsidosättningar av klientorganisationen för skadlig programvara eller nätfiske med hög konfidens.</span><span class="sxs-lookup"><span data-stu-id="ff645-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="ff645-122">Dessa åsidosättningar omfattar:</span><span class="sxs-lookup"><span data-stu-id="ff645-122">These overrides include:</span></span>

- <span data-ttu-id="ff645-123">Tillåtna avsändarlistor eller listor över tillåtna domäner (principer för skydd mot skräppost)</span><span class="sxs-lookup"><span data-stu-id="ff645-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="ff645-124">Betrodda avsändare i Outlook</span><span class="sxs-lookup"><span data-stu-id="ff645-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="ff645-125">IP-lista över tillåtna (anslutningsfiltrering)</span><span class="sxs-lookup"><span data-stu-id="ff645-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="ff645-126">Mer information om dessa åsidosättningar finns i skapa [listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ff645-127">Vi håller på att ta bort  åtgärden Flytta meddelandet till mappen  Skräppost för nätfiskeuttryck i EOP:s principer för skräppost.</span><span class="sxs-lookup"><span data-stu-id="ff645-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="ff645-128">Principer för skydd mot skräppost som använder den här åtgärden för nätfiskemeddelanden med hög förtroende konverteras till **karantänmeddelande.**</span><span class="sxs-lookup"><span data-stu-id="ff645-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="ff645-129">Åtgärden **Omdirigera meddelande till e-postadress** för nätfiskemeddelanden med hög konfidens påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="ff645-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="ff645-130">Säker är som standard inte en inställning som kan aktiveras eller inaktiveras, men det är så filtreringen fungerar för att hålla potentiellt skadliga eller oönskade meddelanden borta från dina postlådor.</span><span class="sxs-lookup"><span data-stu-id="ff645-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="ff645-131">Skadlig programvara och nätfiskemeddelanden med hög konfidens ska ha karantän.</span><span class="sxs-lookup"><span data-stu-id="ff645-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="ff645-132">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod eller nätfiske och de kan också rapportera falska positiva meddelanden till Microsoft därifrån.</span><span class="sxs-lookup"><span data-stu-id="ff645-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="ff645-133">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="ff645-134">Mer information om varför vi gör det här</span><span class="sxs-lookup"><span data-stu-id="ff645-134">More on why we're doing this</span></span>

<span data-ttu-id="ff645-135">Andan för att vara säker som standard är att vi vidtar samma åtgärd för meddelandet du skulle vidta om du visste att meddelandet var skadligt, även om ett konfigurerat undantag annars skulle tillåta att meddelandet levereras.</span><span class="sxs-lookup"><span data-stu-id="ff645-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="ff645-136">Det här är samma metod som vi alltid använt för skadlig programvara, och nu utökar vi den här funktionen till nätfiskemeddelanden med hög säkerhet.</span><span class="sxs-lookup"><span data-stu-id="ff645-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="ff645-137">Våra data anger att en användare är 30 gånger mer sannolikt att klicka på en skadlig länk i meddelanden i mappen Skräppost kontra karantän.</span><span class="sxs-lookup"><span data-stu-id="ff645-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="ff645-138">Våra data visar också att den falska positiva hastigheten (bra meddelanden som markerats som dåliga) för nätfiskemeddelanden med hög förtroende är mycket låg och administratörer kan lösa alla falska positiva resultat med administratörsinskickningar.</span><span class="sxs-lookup"><span data-stu-id="ff645-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="ff645-139">Vi kom också fram till att listorna för tillåtna avsändare och tillåtna domäner i principerna för skräppostskydd och Betrodda avsändare i Outlook var för breda och orsakade mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="ff645-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="ff645-140">För att uttrycka det på ett annat sätt: som en säkerhetstjänst arbetar vi för att förhindra att dina användare komprometteras.</span><span class="sxs-lookup"><span data-stu-id="ff645-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="ff645-141">Undantag</span><span class="sxs-lookup"><span data-stu-id="ff645-141">Exceptions</span></span>

<span data-ttu-id="ff645-142">Den enda åsidosättningen som tillåter nätfiskemeddelanden att kringgå filtrering är Exchange-e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="ff645-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ff645-143">Information om hur du använder e-postflödesregler för att kringgå filtrering finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="ff645-144">Du bör endast överväga att använda åsidosättningar i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="ff645-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="ff645-145">Nätfiskebedrägerier: Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar organisationen.</span><span class="sxs-lookup"><span data-stu-id="ff645-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="ff645-146">Säkerhet/SecOps-postlådor: Dedikerade postlådor som används av säkerhetsgrupper för att få ofiltrerade meddelanden (både bra och dåliga).</span><span class="sxs-lookup"><span data-stu-id="ff645-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="ff645-147">Teams kan sedan granska dem för att se om de innehåller skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="ff645-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="ff645-148">Filter från tredje part: Säker som standard gäller inte när domänens MX-post inte pekar på Office 365.</span><span class="sxs-lookup"><span data-stu-id="ff645-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="ff645-149">Falska positiva resultat: Du kanske tillfälligt vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörsinskickningar.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="ff645-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="ff645-150">Precis som med alla åsidosättningar rekommenderar vi att de är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="ff645-150">As with all overrides, it is recommended that they are temporary.</span></span>
