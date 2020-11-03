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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan se vanliga frågor och svar om skydd mot förfalskning i Exchange Online Protection (EOP).
ms.openlocfilehash: a5b0484e41e3df7a7b6ad16e69a4f7062b19b554
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844398"
---
# <a name="anti-spoofing-protection-faq"></a><span data-ttu-id="d5917-103">Vanliga frågor och svar om skydd mot förfalskning</span><span class="sxs-lookup"><span data-stu-id="d5917-103">Anti-spoofing protection FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d5917-104">Den här artikeln innehåller vanliga frågor och svar om skydd mot förfalskning för Microsoft 365-organisationer med post lådor i Exchange Online eller fristående organisationer för Exchange Online Protection (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="d5917-104">This article provides frequently asked questions and answers about anti-spoofing protection for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="d5917-105">Frågor och svar om skydd mot skräp post finns i [vanliga frågor om skydd mot skräp post](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="d5917-106">Frågor och svar om skydd mot skadlig program vara finns i [vanliga frågor om skydd mot skadlig program vara](anti-malware-protection-faq-eop.md)</span><span class="sxs-lookup"><span data-stu-id="d5917-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md)</span></span>

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a><span data-ttu-id="d5917-107">Varför väljer Microsoft att skicka skräp post som inte verifierats som overifierat?</span><span class="sxs-lookup"><span data-stu-id="d5917-107">Why did Microsoft choose to junk unauthenticated inbound email?</span></span>

<span data-ttu-id="d5917-108">Microsoft anser att risken för att overifierad inkommande e-post tillåts vara högre än risken att du förlorar legitim inkommande e-post.</span><span class="sxs-lookup"><span data-stu-id="d5917-108">Microsoft believes that the risk of continuing to allow unauthenticated inbound email is higher than the risk of losing legitimate inbound email.</span></span>

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a><span data-ttu-id="d5917-109">Orsakar skräp post av oautentiserad e-post att legitim e-post markeras som skräp post?</span><span class="sxs-lookup"><span data-stu-id="d5917-109">Does junking unauthenticated inbound email cause legitimate email to be marked as spam?</span></span>

<span data-ttu-id="d5917-110">När Microsoft aktiverade den här funktionen i 2018 skedde vissa falska positiva (goda meddelanden).</span><span class="sxs-lookup"><span data-stu-id="d5917-110">When Microsoft enabled this feature in 2018, some false positives happened (good messages were marked as bad).</span></span> <span data-ttu-id="d5917-111">Men över tiden har avsändare justerats efter kraven.</span><span class="sxs-lookup"><span data-stu-id="d5917-111">However, over time, senders adjusted to the requirements.</span></span> <span data-ttu-id="d5917-112">Antalet meddelanden som identifierats som falsk är försumbart för de flesta e-postsök vägar.</span><span class="sxs-lookup"><span data-stu-id="d5917-112">The number of messages that were misidentified as spoofed became negligible for most email paths.</span></span>

<span data-ttu-id="d5917-113">Microsoft antog först de nya e-postautentiseringskravna flera veckor innan de distribueras till kunderna.</span><span class="sxs-lookup"><span data-stu-id="d5917-113">Microsoft itself first adopted the new email authentication requirements several weeks before deploying it to customers.</span></span> <span data-ttu-id="d5917-114">I början förekom störningar men de minskade gradvis.</span><span class="sxs-lookup"><span data-stu-id="d5917-114">While there was disruption at first, it gradually declined.</span></span>

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a><span data-ttu-id="d5917-115">Är Spoof-intelligens tillgänglig för Microsoft 365-kunder utan Defender för Office 365?</span><span class="sxs-lookup"><span data-stu-id="d5917-115">Is spoof intelligence available to Microsoft 365 customers without Defender for Office 365?</span></span>

<span data-ttu-id="d5917-116">Ja.</span><span class="sxs-lookup"><span data-stu-id="d5917-116">Yes.</span></span> <span data-ttu-id="d5917-117">Från och med oktober 2018 är Spoof-intelligens tillgänglig för alla organisationer med post lådor i Exchange Online och fristående EOP-organisationer utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="d5917-117">As of October 2018, spoof intelligence is available to all organizations with mailboxes in Exchange Online, and standalone EOP organizations without Exchange Online mailboxes.</span></span>

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a><span data-ttu-id="d5917-118">Hur kan jag rapportera spam eller inte spam-meddelanden tillbaka till Microsoft?</span><span class="sxs-lookup"><span data-stu-id="d5917-118">How can I report spam or non-spam messages back to Microsoft?</span></span>

<span data-ttu-id="d5917-119">Se [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-119">See [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a><span data-ttu-id="d5917-120">Jag är administratör och jag känner inte till alla källor för meddelanden i min e-post-domän!</span><span class="sxs-lookup"><span data-stu-id="d5917-120">I'm an admin and I don't know all of sources for messages in my email domain!</span></span>

<span data-ttu-id="d5917-121">Se [att du inte känner till alla källor för din e-post](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span><span class="sxs-lookup"><span data-stu-id="d5917-121">See [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).</span></span>

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a><span data-ttu-id="d5917-122">Vad händer om jag inaktiverar skydd mot förfalskning för min organisation?</span><span class="sxs-lookup"><span data-stu-id="d5917-122">What happens if I disable anti-spoofing protection for my organization?</span></span>

<span data-ttu-id="d5917-123">Vi rekommenderar inte att du inaktiverar skydd mot förfalskning.</span><span class="sxs-lookup"><span data-stu-id="d5917-123">We do not recommend disabling anti-spoofing protection.</span></span> <span data-ttu-id="d5917-124">Om du inaktiverar skyddet kan fler nätfiske och skräp post skickas till din organisation.</span><span class="sxs-lookup"><span data-stu-id="d5917-124">Disabling the protection will allow more phishing and spam messages to be delivered in your organization.</span></span> <span data-ttu-id="d5917-125">Alla nätfiske är inte falska och alla falska meddelanden kommer inte att missas.</span><span class="sxs-lookup"><span data-stu-id="d5917-125">Not all phishing is spoofing, and not all spoofed messages will be missed.</span></span> <span data-ttu-id="d5917-126">Men din risk är högre.</span><span class="sxs-lookup"><span data-stu-id="d5917-126">However, your risk will be higher.</span></span>

<span data-ttu-id="d5917-127">Nu när det finns [förbättrade filter för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) är det inte längre möjligt att stänga av skyddet mot förfalskning när din e-post dirigeras via en annan tjänst före EOP.</span><span class="sxs-lookup"><span data-stu-id="d5917-127">Now that [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) is available, we no longer recommended turning off anti-spoofing protection when your email is routed through another service before EOP.</span></span>

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a><span data-ttu-id="d5917-128">Innebär skydd mot förfalskning att jag skyddas från alla nätfiske?</span><span class="sxs-lookup"><span data-stu-id="d5917-128">Does anti-spoofing protection mean I will be protected from all phishing?</span></span>

<span data-ttu-id="d5917-129">Tyvärr, nej.</span><span class="sxs-lookup"><span data-stu-id="d5917-129">Unfortunately, no.</span></span> <span data-ttu-id="d5917-130">Angripare anpassas till Använd annan teknik (till exempel äventyrade konton eller konton i gratis e-posttjänster).</span><span class="sxs-lookup"><span data-stu-id="d5917-130">Attackers will adapt to use other techniques (for example, compromised accounts or accounts in free email services).</span></span> <span data-ttu-id="d5917-131">Skydd mot nätfiske fungerar dock bättre för att upptäcka dessa andra typer av nät fiske metoder.</span><span class="sxs-lookup"><span data-stu-id="d5917-131">However, anti-phishing protection works much better to detect these other types of phishing methods.</span></span> <span data-ttu-id="d5917-132">Skydds lagren i EOP är utformade för att fungera tillsammans och bygga ovanpå varandra.</span><span class="sxs-lookup"><span data-stu-id="d5917-132">The protection layers in EOP are designed work together and build on top of each other.</span></span>

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a><span data-ttu-id="d5917-133">Blockerar andra stora e-posttjänster oautentiserad e-post?</span><span class="sxs-lookup"><span data-stu-id="d5917-133">Do other large email services block unauthenticated inbound email?</span></span>

<span data-ttu-id="d5917-134">Nästan alla stora e-posttjänster implementerar traditionella SPF-, DKIM-och DMARC-kontroller.</span><span class="sxs-lookup"><span data-stu-id="d5917-134">Nearly all large email services implement traditional SPF, DKIM, and DMARC checks.</span></span> <span data-ttu-id="d5917-135">Vissa tjänster har andra, mer strikta kontroller, men få lika mycket som EOP för att blockera overifierad e-post och behandla dem som falska meddelanden.</span><span class="sxs-lookup"><span data-stu-id="d5917-135">Some services have other, more strict checks, but few go as far as EOP to block unauthenticated email and treat them as spoofed messages.</span></span> <span data-ttu-id="d5917-136">Men industrin blir mer medveten om problem med overifierad e-post, särskilt på grund av problemet med nätfiske.</span><span class="sxs-lookup"><span data-stu-id="d5917-136">However, the industry is becoming more aware about issues with unauthenticated email, particularly because of the problem of phishing.</span></span>

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a><span data-ttu-id="d5917-137">Måste jag ändå aktivera avancerade inställningar för skräp post filtret "SPF record: hårda fail" ( _MarkAsSpamSpfRecordHardFail_ ) om jag aktiverar mot förfalskning?</span><span class="sxs-lookup"><span data-stu-id="d5917-137">Do I still need to enable the Advanced Spam Filter setting "SPF record: hard fail" ( _MarkAsSpamSpfRecordHardFail_ ) if I enable anti-spoofing?</span></span>

<span data-ttu-id="d5917-138">Nej.</span><span class="sxs-lookup"><span data-stu-id="d5917-138">No.</span></span> <span data-ttu-id="d5917-139">Den här ASF-inställningen behövs inte längre.</span><span class="sxs-lookup"><span data-stu-id="d5917-139">This ASF setting is no longer required.</span></span> <span data-ttu-id="d5917-140">Skydd mot förfalskningar betraktar både SPF-hårda fel och en större uppsättning villkor.</span><span class="sxs-lookup"><span data-stu-id="d5917-140">Anti-spoofing protection considers both SPF hard fails and a much wider set of criteria.</span></span> <span data-ttu-id="d5917-141">Om du har aktiverat skydd mot förfalskning och **SPF-post: Hard Fail** ( _MarkAsSpamSpfRecordHardFail_ ) aktiverad kommer du antagligen att få mer falska positiva identifieringar.</span><span class="sxs-lookup"><span data-stu-id="d5917-141">If you have anti-spoofing enabled and the **SPF record: hard fail** ( _MarkAsSpamSpfRecordHardFail_ ) turned on, you will probably get more false positives.</span></span>

<span data-ttu-id="d5917-142">Vi rekommenderar att du inaktiverar den här funktionen eftersom den inte har någon ytterligare förmån för att upptäcka skräp post eller nätfiske och skulle i stället generera mest falska positiva positiv.</span><span class="sxs-lookup"><span data-stu-id="d5917-142">We recommend that you disable this feature as it provides almost no additional benefit for detecting spam or phishing message, and would instead generate mostly false positives.</span></span> <span data-ttu-id="d5917-143">Mer information finns i [Avancerade inställningar för skräp post filter (ASF) i EOP](advanced-spam-filtering-asf-options.md).</span><span class="sxs-lookup"><span data-stu-id="d5917-143">For more information, see [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).</span></span>

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a><span data-ttu-id="d5917-144">Hjälper avsändarens schema att åtgärda vidarebefordrade e-postmeddelanden?</span><span class="sxs-lookup"><span data-stu-id="d5917-144">Does Sender Rewriting Scheme help fix forwarded email?</span></span>

<span data-ttu-id="d5917-145">SRS korrigerar bara delvis problemet med vidarebefordrad e-post.</span><span class="sxs-lookup"><span data-stu-id="d5917-145">SRS only partially fixes the problem of forwarded email.</span></span> <span data-ttu-id="d5917-146">Genom att skriva om SMTP **-e-post från** kan SRS säkerställa att det vidarebefordrade meddelandet skickar SPF vid nästa destination.</span><span class="sxs-lookup"><span data-stu-id="d5917-146">By rewriting the SMTP **MAIL FROM** , SRS can ensure that the forwarded message passes SPF at the next destination.</span></span> <span data-ttu-id="d5917-147">Eftersom anti-förfalskning är baserat på **från** -adressen i kombination med **e-post från** eller DKIM (eller andra signaler) är det emellertid inte tillräckligt för att förhindra att e-post med SRS-meddelanden markeras som falsk.</span><span class="sxs-lookup"><span data-stu-id="d5917-147">However, because anti-spoofing is based upon the **From** address in combination with the **MAIL FROM** or DKIM-signing domain (or other signals), it's not enough to prevent SRS forwarded email from being marked as spoofed.</span></span>
