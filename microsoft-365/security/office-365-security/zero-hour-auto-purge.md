---
title: Autorensning för nollor (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur nollställning av automatisk rensning (ZAP) kan flytta levererade meddelanden retroaktivt i en Exchange Online-postlåda till mappen skräp post eller karantän som kan vara skräp post eller nätfiske.
ms.openlocfilehash: 7b43fb46adacfe1e9f1e7e622122df90e747ff44
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659435"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="4f260-103">Automatisk rensning av nollor (ZAP) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4f260-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="4f260-104">Grundläggande funktioner i ZAP</span><span class="sxs-lookup"><span data-stu-id="4f260-104">Basic features of ZAP</span></span>

<span data-ttu-id="4f260-105">I Microsoft 365-organisationer med post lådor i Exchange Online, är nollställning autorensning en e-postskydds funktion som upptäcker och neutraliserar skadlig nät fiske, skräp post eller skadliga meddelanden som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="4f260-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="4f260-106">ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="4f260-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="4f260-107">Så fungerar ZAP</span><span class="sxs-lookup"><span data-stu-id="4f260-107">How ZAP works</span></span>

<span data-ttu-id="4f260-108">Alla signaturer för skräp post och skadlig program vara uppdateras i real tid per dag.</span><span class="sxs-lookup"><span data-stu-id="4f260-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="4f260-109">Men användare kan ändå ta emot skadliga meddelanden av olika anledningar, inklusive om innehållet är lite fritt efter att du har levererats till användarna.</span><span class="sxs-lookup"><span data-stu-id="4f260-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="4f260-110">ZAP löser det här problemet genom att fort löp ande övervaka uppdateringar av signaturer för skräp post och skadlig program vara i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4f260-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="4f260-111">ZAP kan hitta och ta bort meddelanden som redan finns i en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="4f260-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="4f260-112">Åtgärden ZAP är sömlös för användaren. de meddelas inte om ett meddelande identifieras och flyttas.</span><span class="sxs-lookup"><span data-stu-id="4f260-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="4f260-113">[Listor för betrodda avsändare](create-safe-sender-lists-in-office-365.md), regler för e-postflöde (kallas även transport regler), regler för Inkorgen eller ytterligare filter har högre prioritet än ZAP.</span><span class="sxs-lookup"><span data-stu-id="4f260-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="4f260-114">På samma sätt som i e-postflödet innebär det att även om tjänsten bestämmer det leverans behov som krävs för att skicka meddelandet, kan meddelandet inte aktive ras på grund av konfigurationen för betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="4f260-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="4f260-115">Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.</span><span class="sxs-lookup"><span data-stu-id="4f260-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="4f260-116">Malware, ZAP</span><span class="sxs-lookup"><span data-stu-id="4f260-116">Malware ZAP</span></span>

<span data-ttu-id="4f260-117">För **lästa och olästa meddelanden** som visar att det finns skadlig kod efter leverans får du ett meddelande som innehåller den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="4f260-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="4f260-118">Endast administratörer kan visa och hantera meddelanden om skadlig program vara från karantän.</span><span class="sxs-lookup"><span data-stu-id="4f260-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="4f260-119">Malware, ZAP är aktiverat som standard i principer mot skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="4f260-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="4f260-120">Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="4f260-121">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="4f260-121">Phish ZAP</span></span>

<span data-ttu-id="4f260-122">För **lästa och olästa meddelanden** som identifieras som nätfiske efter leveransen beror ZAP-resultatet av den åtgärd som är konfigurerad för en Verdict för **nätfiske** .</span><span class="sxs-lookup"><span data-stu-id="4f260-122">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="4f260-123">De tillgängliga Verdict-åtgärderna för filtrering för nätfiske och deras potentiella ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="4f260-123">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="4f260-124">**Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f260-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="4f260-125">**Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard).</span><span class="sxs-lookup"><span data-stu-id="4f260-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="4f260-126">Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="4f260-127">**Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen.</span><span class="sxs-lookup"><span data-stu-id="4f260-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="4f260-128">Phish ZAP är som standard aktive rad i principer för skräp post och standard åtgärden för Verdict för **nät fiske** meddelanden är **karantän meddelande**, vilket innebär att Phish ZAP mellanstår meddelandet som standard.</span><span class="sxs-lookup"><span data-stu-id="4f260-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="4f260-129">Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="4f260-130">Spam</span><span class="sxs-lookup"><span data-stu-id="4f260-130">Spam ZAP</span></span>

<span data-ttu-id="4f260-131">För **olästa meddelanden** som identifieras som skräp post efter leverans beror ZAP-resultatet av den åtgärd som är konfigurerad för filtrering av **skräp post** filter i den aktuella principen för skräp post Verdict.</span><span class="sxs-lookup"><span data-stu-id="4f260-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="4f260-132">De tillgängliga Verdict-åtgärderna för filtrering av skräp post och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="4f260-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="4f260-133">**Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="4f260-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="4f260-134">**Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard).</span><span class="sxs-lookup"><span data-stu-id="4f260-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="4f260-135">Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="4f260-136">**Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen.</span><span class="sxs-lookup"><span data-stu-id="4f260-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="4f260-137">Slutanvändare kan visa och hantera sina egna meddelanden i Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="4f260-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="4f260-138">Som standard är skräppost-ZAP aktiverat i principer för skräp post, och standard åtgärden för **skräp** post filtrering Verdict är **att flytta meddelandet till mappen skräp post**, vilket innebär att skräp posten är som standard **avläst** meddelanden till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="4f260-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="4f260-139">Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="4f260-140">ZAP-överväganden för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4f260-140">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="4f260-141">ZAP kommer inte att placera något meddelande som bearbetas i processen för [dynamisk leverans](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) i den säkra bilage genomsökningen eller där EOP malware filter redan har ersatt bilagan med **varnings meddelandet Text.txt** -filen.</span><span class="sxs-lookup"><span data-stu-id="4f260-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="4f260-142">Om en nätfiske eller skräp post tas emot för dessa typer av meddelanden och filtrerings Verdict i policyn för skräp post är inställd på att vidta vissa åtgärder på meddelandet (flytta till skräp post, omdirigering, ta bort eller karantän) återställs den till åtgärden "flytta till skräp post".</span><span class="sxs-lookup"><span data-stu-id="4f260-142">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="4f260-143">Så här ser du om ZAP har flyttat ditt meddelande</span><span class="sxs-lookup"><span data-stu-id="4f260-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="4f260-144">Om du vill ta reda på om ZAP har flyttat ditt meddelande kan du använda antingen [status rapport](view-email-security-reports.md#threat-protection-status-report) eller hot kontroll i [real tid](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="4f260-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="4f260-145">Observera att ZAP inte loggas i gransknings loggarna för Exchange-postlådan.</span><span class="sxs-lookup"><span data-stu-id="4f260-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="4f260-146">VANLIGA FRÅGOR OM ZAP</span><span class="sxs-lookup"><span data-stu-id="4f260-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="4f260-147">Vad händer om ett legitimt meddelande flyttas till mappen skräp post?</span><span class="sxs-lookup"><span data-stu-id="4f260-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="4f260-148">Du bör följa den vanliga rapporterings processen för [falska positiva](report-junk-email-messages-to-microsoft.md)verifieringar.</span><span class="sxs-lookup"><span data-stu-id="4f260-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="4f260-149">Det enda skälet till att meddelandet flyttas från inkorgen till mappen skräp post, eftersom tjänsten har fastställt att meddelandet har tagits bort eller är skadligt.</span><span class="sxs-lookup"><span data-stu-id="4f260-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="4f260-150">Vad händer om jag använder mappen karantän i stället för mappen skräp post?</span><span class="sxs-lookup"><span data-stu-id="4f260-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="4f260-151">ZAP utför en åtgärd på ett meddelande baserat på konfigurationen för skydd mot skräp post enligt beskrivningen ovan.</span><span class="sxs-lookup"><span data-stu-id="4f260-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="4f260-152">Vad händer om jag använder betrodda avsändare, e-postflödes regler eller tillåtna/blockerade avsändar listor?</span><span class="sxs-lookup"><span data-stu-id="4f260-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="4f260-153">Säkra avsändare, regler för e-postflöde eller blockering och Tillåt organisations inställningar gäller.</span><span class="sxs-lookup"><span data-stu-id="4f260-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="4f260-154">Dessa meddelanden är exkluderade från ZAP eftersom tjänsten gör det du konfigurerade att göra.</span><span class="sxs-lookup"><span data-stu-id="4f260-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="4f260-155">Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.</span><span class="sxs-lookup"><span data-stu-id="4f260-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="4f260-156">Vad händer om ett meddelande flyttas till en annan mapp (till exempel regler för Inkorgen)?</span><span class="sxs-lookup"><span data-stu-id="4f260-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="4f260-157">ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge det finns en åtgärd som inte redan har använts.</span><span class="sxs-lookup"><span data-stu-id="4f260-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="4f260-158">Om du till exempel har ställt in en karantän och ett meddelande redan finns i skräp posten vidtar ZAP åtgärd för att sätta in ett karantän meddelande.</span><span class="sxs-lookup"><span data-stu-id="4f260-158">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="4f260-159">Hur påverkar ZAP post lådor?</span><span class="sxs-lookup"><span data-stu-id="4f260-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="4f260-160">ZAP startar inte karantän meddelanden från post lådor med undantag.</span><span class="sxs-lookup"><span data-stu-id="4f260-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="4f260-161">ZAP kan flytta meddelanden till mappen skräp post baserat på den åtgärd som har kon figurer ATS för skräp post eller nätfiske-Verdict i policyer för borttagning.</span><span class="sxs-lookup"><span data-stu-id="4f260-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="4f260-162">Mer information om undantag i Exchange Online finns [i-platsens undantag och rättsliga undantag i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span><span class="sxs-lookup"><span data-stu-id="4f260-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
