---
title: Vanliga frågor och svar om skydd mot förfalskning
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan visa vanliga frågor och svar om skydd mot förfalskning i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288915"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="83a1d-103">Vanliga frågor och svar om skydd mot förfalskning</span><span class="sxs-lookup"><span data-stu-id="83a1d-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83a1d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="83a1d-104">**Applies to**</span></span>
- [<span data-ttu-id="83a1d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="83a1d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="83a1d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="83a1d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="83a1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83a1d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="83a1d-108">Den här artikeln innehåller vanliga frågor och svar om skydd mot förfalskning för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="83a1d-108">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="83a1d-109">Frågor och svar om skydd mot skräppost finns i Vanliga frågor och svar om skydd mot [skräppost.](anti-spam-protection-faq.md)</span><span class="sxs-lookup"><span data-stu-id="83a1d-109">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="83a1d-110">Frågor och svar om skydd mot skadlig programvara finns i Vanliga frågor och svar om skydd [mot skadlig programvara](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="83a1d-110">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="83a1d-111">Varför valde Microsoft att skräppost av oautisk inkommande e-post?</span><span class="sxs-lookup"><span data-stu-id="83a1d-111">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="83a1d-112">Microsoft anser att risken för att fortsätta tillåta oauticerad inkommande e-post är högre än risken för att legitima inkommande e-postmeddelanden förloras.</span><span class="sxs-lookup"><span data-stu-id="83a1d-112">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="83a1d-113">Leder skräppost oautisk inkommande e-post till att legitim e-post markeras som skräppost?</span><span class="sxs-lookup"><span data-stu-id="83a1d-113">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="83a1d-114">När Microsoft aktiverade den här funktionen 2018 har vissa felaktiga positiva resultat inträffat (bra meddelanden markerades som dåliga).</span><span class="sxs-lookup"><span data-stu-id="83a1d-114">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="83a1d-115">Med tiden har dock avsändarna anpassat sig efter kraven.</span><span class="sxs-lookup"><span data-stu-id="83a1d-115">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="83a1d-116">Antalet meddelanden som blev felidentifierade som falska blev tillgängliga för de flesta e-postsökvägar.</span><span class="sxs-lookup"><span data-stu-id="83a1d-116">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="83a1d-117">Microsoft införde först de nya autentiseringskraven för e-post flera veckor innan de distribuerade till kunder.</span><span class="sxs-lookup"><span data-stu-id="83a1d-117">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="83a1d-118">I början förekom störningar men de minskade gradvis.</span><span class="sxs-lookup"><span data-stu-id="83a1d-118">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="83a1d-119">Är förfalskningsinformation tillgänglig för Microsoft 365-kunder utan Defender för Office 365?</span><span class="sxs-lookup"><span data-stu-id="83a1d-119">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="83a1d-120">Ja.</span><span class="sxs-lookup"><span data-stu-id="83a1d-120">Yes.</span></span> <span data-ttu-id="83a1d-121">Från och med oktober 2018 är förfalskningsinformation tillgänglig för alla organisationer med postlådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="83a1d-121">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="83a1d-122">Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?</span><span class="sxs-lookup"><span data-stu-id="83a1d-122">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="83a1d-123">Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="83a1d-123">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="83a1d-124">Jag är administratör och jag känner inte till alla källor för meddelanden i min e-postdomän!</span><span class="sxs-lookup"><span data-stu-id="83a1d-124">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="83a1d-125">Se [att du inte känner till alla källor för din e-post.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)</span><span class="sxs-lookup"><span data-stu-id="83a1d-125">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="83a1d-126">Vad händer om jag inaktiverar skydd mot förfalskning för min organisation?</span><span class="sxs-lookup"><span data-stu-id="83a1d-126">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="83a1d-127">Vi rekommenderar inte att du inaktiverar förfalskningsskydd.</span><span class="sxs-lookup"><span data-stu-id="83a1d-127">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="83a1d-128">Om du inaktiverar skyddet kan fler nätfiske- och skräppostmeddelanden levereras i organisationen.</span><span class="sxs-lookup"><span data-stu-id="83a1d-128">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="83a1d-129">Nätfiske är inte alla förfalskningsmeddelanden och du kommer inte att missa alla falska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="83a1d-129">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="83a1d-130">Din risk är dock högre.</span><span class="sxs-lookup"><span data-stu-id="83a1d-130">However, your risk will be higher.</span></span>

<span data-ttu-id="83a1d-131">Nu när Utökad filtrering för kopplingar är tillgänglig rekommenderar vi inte längre att skydd mot förfalskning inaktiveras när din e-post [dirigeras](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) genom en annan tjänst innan EOP.</span><span class="sxs-lookup"><span data-stu-id="83a1d-131">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="83a1d-132">Innebär skydd mot förfalskning att jag skyddas från all nätfiske?</span><span class="sxs-lookup"><span data-stu-id="83a1d-132">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="83a1d-133">Nej, tyvärr inte.</span><span class="sxs-lookup"><span data-stu-id="83a1d-133">Unfortunately, no.</span></span> <span data-ttu-id="83a1d-134">Attackerare kommer att anpassa sig till andra tekniker (till exempel komprometterade konton eller konton i kostnadsfria e-posttjänster).</span><span class="sxs-lookup"><span data-stu-id="83a1d-134">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="83a1d-135">Skydd mot nätfiske fungerar dock mycket bättre för att identifiera andra typer av nätfiskemetoder.</span><span class="sxs-lookup"><span data-stu-id="83a1d-135">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="83a1d-136">Skyddslageren i EOP är utformade så att de fungerar tillsammans och bygger på varandra.</span><span class="sxs-lookup"><span data-stu-id="83a1d-136">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="83a1d-137">Blockerar andra stora e-posttjänster oauticerad inkommande e-post?</span><span class="sxs-lookup"><span data-stu-id="83a1d-137">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="83a1d-138">Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM- och DMARC-kontroller.</span><span class="sxs-lookup"><span data-stu-id="83a1d-138">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="83a1d-139">Vissa tjänster har andra, striktare kontroller, men det är få som går så långt som EOP för att blockera oautisk e-post och behandla dem som falska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="83a1d-139">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="83a1d-140">Men branschen börjar bli mer medvetna om problem med oauticerad e-post, särskilt på grund av problemet med nätfiske.</span><span class="sxs-lookup"><span data-stu-id="83a1d-140">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="83a1d-141">Måste jag fortfarande aktivera inställningen Advanced Spam Filter (SPF-post: Hard Fail)_(MarkAsSpamSpfRecordHardFail)_ om jag aktiverar förfalskningskydd?</span><span class="sxs-lookup"><span data-stu-id="83a1d-141">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" (_MarkAsSpamSpfRecordHardFail_) if I enable anti-spoofing?</span></span>

<span data-ttu-id="83a1d-142">Nej.</span><span class="sxs-lookup"><span data-stu-id="83a1d-142">No.</span></span> <span data-ttu-id="83a1d-143">Den här ASF-inställningen är inte längre obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="83a1d-143">This ASF setting is no longer required.</span></span> <span data-ttu-id="83a1d-144">Skydd mot förfalskning tar hänsyn till både SPF-fel och en mycket bredare uppsättning kriterier.</span><span class="sxs-lookup"><span data-stu-id="83a1d-144">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="83a1d-145">Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** (_MarkAsSpamSpfRecordHardFail_) aktiverad kommer du antagligen att få mer falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="83a1d-145">If you have anti-spoofing enabled and the **SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="83a1d-146">Vi rekommenderar att du inaktiverar den här funktionen eftersom den nästan inte ger några ytterligare fördelar när du identifierar skräppost eller nätfiskemeddelanden, och i stället genererar huvudsakligen falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="83a1d-146">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="83a1d-147">Mer information finns i avancerade [inställningar för skräppostfilter (ASF) i EOP.](advanced-spam-filtering-asf-options.md)</span><span class="sxs-lookup"><span data-stu-id="83a1d-147">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="83a1d-148">Kan vidarebefordrad e-post åtgärdas med hjälp av avsändarschemat?</span><span class="sxs-lookup"><span data-stu-id="83a1d-148">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="83a1d-149">SRS korrigerar bara delvis problemet med vidarebefordrad e-post.</span><span class="sxs-lookup"><span data-stu-id="83a1d-149">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="83a1d-150">Genom att skriva om SMTP **MAIL FROM** kan SRS säkerställa att det vidarebefordrade meddelandet skickar SPF till nästa mål.</span><span class="sxs-lookup"><span data-stu-id="83a1d-150">By rewriting the SMTP **MAIL FROM**, SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="83a1d-151">Men eftersom antiförfalskning baseras på från-adressen i kombination med **MAIL FROM-** eller DKIM-signeringsdomänen (eller andra signaler), räcker det inte med att förhindra att vidarebefordrad SRS-e-post markeras som förfalskning. </span><span class="sxs-lookup"><span data-stu-id="83a1d-151">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
