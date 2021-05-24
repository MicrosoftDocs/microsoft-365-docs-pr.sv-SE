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
description: Läs mer om inställningen säker som standard i Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d5cdc8f8faa9c2d5772fd1572134ea49cdd77da
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624055"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="707ee-103">Säker som standard i Office 365</span><span class="sxs-lookup"><span data-stu-id="707ee-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="707ee-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="707ee-104">**Applies to**</span></span>
- [<span data-ttu-id="707ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="707ee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="707ee-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="707ee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="707ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="707ee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="707ee-108">"Säker som standard" är en term som används för att definiera de standardinställningar som är säkrast möjliga.</span><span class="sxs-lookup"><span data-stu-id="707ee-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="707ee-109">Säkerheten måste dock balanseras med produktiviteten.</span><span class="sxs-lookup"><span data-stu-id="707ee-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="707ee-110">Det kan till exempel vara balansering över:</span><span class="sxs-lookup"><span data-stu-id="707ee-110">This can include balancing across:</span></span>

- <span data-ttu-id="707ee-111">**Användbarhet:** Inställningar bör inte vara i vägen för användarnas produktivitet.</span><span class="sxs-lookup"><span data-stu-id="707ee-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="707ee-112">**Risk:** Säkerheten kan blockera viktiga aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="707ee-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="707ee-113">**Äldre inställningar:** Vissa konfigurationer för äldre produkter och funktioner kan behöva underhållas av företagsskäl, även om nya, moderna inställningar har förbättrats.</span><span class="sxs-lookup"><span data-stu-id="707ee-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="707ee-114">Microsoft 365 organisationer med postlådor i Exchange Online skyddas av Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="707ee-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="707ee-115">Det här skyddet omfattar:</span><span class="sxs-lookup"><span data-stu-id="707ee-115">This protection includes:</span></span>

- <span data-ttu-id="707ee-116">E-post med misstänkt skadlig programvara sätts automatiskt i karantän och mottagare meddelas.</span><span class="sxs-lookup"><span data-stu-id="707ee-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="707ee-117">Se [Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="707ee-118">E-post som identifieras som nätfiske hanteras i enlighet med policyåtgärden mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="707ee-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="707ee-119">Se [Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="707ee-120">Mer information om EOP finns i Exchange Online Protection [översikt.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="707ee-121">Eftersom Microsoft vill att våra kunder ska vara säkra som standard används inte vissa klientorganisations åsidosättningar för skadlig programvara eller nätfiske med hög säkerhet.</span><span class="sxs-lookup"><span data-stu-id="707ee-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="707ee-122">Dessa åsidosättningar omfattar:</span><span class="sxs-lookup"><span data-stu-id="707ee-122">These overrides include:</span></span>

- <span data-ttu-id="707ee-123">Listor över tillåtna avsändare eller tillåtna domäner (principer som skydda mot skräppost)</span><span class="sxs-lookup"><span data-stu-id="707ee-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="707ee-124">Outlook Valv avsändare</span><span class="sxs-lookup"><span data-stu-id="707ee-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="707ee-125">Lista över tillåtna IP-adresser (anslutningsfiltrering)</span><span class="sxs-lookup"><span data-stu-id="707ee-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="707ee-126">Mer information om dessa åsidosättningar finns i Skapa [listor över betrodda avsändare.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="707ee-127">Vi håller på att ta bort  åtgärden Flytta meddelandet till skräppostmappen för nätfiskeuttryck i EOP:s principer för skräppost. </span><span class="sxs-lookup"><span data-stu-id="707ee-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="707ee-128">Principer för skydd mot skräppost som använder den här åtgärden för nätfiskemeddelanden med hög säkerhet konverteras till **karantänmeddelanden.**</span><span class="sxs-lookup"><span data-stu-id="707ee-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="707ee-129">Åtgärden **Omdirigera meddelandet till e-postadress** för nätfiskemeddelanden med hög säkerhet påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="707ee-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="707ee-130">Säker som standard är inte en inställning som kan aktiveras eller inaktiveras, men är det sätt som vår filtrering fungerar för att hålla potentiellt skadliga eller oönskade meddelanden från dina postlådor.</span><span class="sxs-lookup"><span data-stu-id="707ee-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="707ee-131">Skadlig programvara och nätfiskemeddelanden med hög konfidens bör ha satts i karantän.</span><span class="sxs-lookup"><span data-stu-id="707ee-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="707ee-132">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod eller nätfiske med hög konfidens, och de kan också rapportera falska positiva meddelanden till Microsoft därifrån.</span><span class="sxs-lookup"><span data-stu-id="707ee-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="707ee-133">Mer information finns i [Hantera meddelanden i karantän och filer som administratör i EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="707ee-134">Mer information om varför vi gör detta</span><span class="sxs-lookup"><span data-stu-id="707ee-134">More on why we're doing this</span></span>

<span data-ttu-id="707ee-135">Andan med att vara säker som standard är: vi vidtar samma åtgärd för meddelandet som du skulle vidta om du visste att meddelandet var skadligt, även om ett konfigurerat undantag annars skulle tillåta att meddelandet levereras.</span><span class="sxs-lookup"><span data-stu-id="707ee-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="707ee-136">Det här är samma metod som vi alltid har använt när vi använder skadlig programvara, och nu utökar vi denna funktion till att ge nätfiskemeddelanden med hög säkerhet.</span><span class="sxs-lookup"><span data-stu-id="707ee-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="707ee-137">Våra data anger att en användare är 30 gånger mer trolig att klicka på en skadlig länk i meddelanden i mappen Skräppost kontra Karantän.</span><span class="sxs-lookup"><span data-stu-id="707ee-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="707ee-138">Våra data anger också att den falska positiva hastigheten (bra meddelanden som markerats som dåliga) för nätfiskemeddelanden är mycket låg och administratörer kan lösa alla falska positiva resultat med administratörsinskick.</span><span class="sxs-lookup"><span data-stu-id="707ee-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="707ee-139">Vi har också fastställt att listorna med tillåtna avsändare och tillåtna domäner i principer för skräppostskydd och Valv-avsändare i Outlook var för breda och orsakar mer skada än nytta.</span><span class="sxs-lookup"><span data-stu-id="707ee-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="707ee-140">Till att uttrycka det på ett annat sätt: som en säkerhetstjänst arbetar vi åt dig för att förhindra att dina användare komprometteras.</span><span class="sxs-lookup"><span data-stu-id="707ee-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span>

## <a name="exceptions"></a><span data-ttu-id="707ee-141">Undantag</span><span class="sxs-lookup"><span data-stu-id="707ee-141">Exceptions</span></span>

> [!NOTE]
> <span data-ttu-id="707ee-142">I juli 2021 utökas säkerhet som standard till att Exchange till e-postflödesregler (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="707ee-142">In July 2021, secure by default will be extended to Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="707ee-143">Om du använder e-postflödesregler för att tillåta nätfiskebedrägerier eller ofiltrerad leverans till postlådor för [](configure-advanced-delivery.md) säkerhetsåtgärd måste du så småningom eliminera dessa regler och byta till att använda den avancerade leveransprincipen när funktionen är tillgänglig för _dig._</span><span class="sxs-lookup"><span data-stu-id="707ee-143">If you use mail flow rules to allow third-party phishing simulations or unfiltered delivery to security operation mailboxes, you eventually need to eliminate these rules and switch to using the [advanced delivery policy](configure-advanced-delivery.md) _when the feature is available to you_.</span></span>

<span data-ttu-id="707ee-144">Den enda åsidosättningen som tillåter nätfiskemeddelande med hög säkerhet att kringgå filtrering är e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="707ee-144">The only override that allows high confidence phishing message to bypass filtering is mail flow rules.</span></span> <span data-ttu-id="707ee-145">Information om hur du använder e-postflödesregler för att kringgå filtrering finns i [Använda e-postflödesregler för att ange SCL i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="707ee-145">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="707ee-146">Du bör endast använda åsidosättningar i följande fall:</span><span class="sxs-lookup"><span data-stu-id="707ee-146">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="707ee-147">Nätfiskebedrägerier: Simulerade attacker kan hjälpa dig att identifiera sårbara användare innan en verklig attack påverkar din organisation.</span><span class="sxs-lookup"><span data-stu-id="707ee-147">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="707ee-148">Säkerhet/SecOps-postlådor: Dedikerade postlådor som används av säkerhetsteam för att få ofiltrerade meddelanden (både bra och dåliga).</span><span class="sxs-lookup"><span data-stu-id="707ee-148">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="707ee-149">Teams kan sedan granska för att se om de innehåller skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="707ee-149">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="707ee-150">Filter från tredje part: Säker som standard gäller inte när domänens MX-post inte pekar på Office 365.</span><span class="sxs-lookup"><span data-stu-id="707ee-150">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="707ee-151">Falska positiva resultat: Du kanske tillfälligt vill tillåta vissa meddelanden som fortfarande analyseras av Microsoft [via administratörsinskick.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="707ee-151">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="707ee-152">Som med alla åsidosättningar rekommenderar vi att de är tillfälliga.</span><span class="sxs-lookup"><span data-stu-id="707ee-152">As with all overrides, it is recommended that they are temporary.</span></span>
