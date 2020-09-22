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
ms.openlocfilehash: 66df614700dc5f9b9938200d384cc293a51e2f3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202645"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="5f340-103">Automatisk rensning av nollor (ZAP) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5f340-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="5f340-104">Grundläggande funktioner i ZAP</span><span class="sxs-lookup"><span data-stu-id="5f340-104">Basic features of ZAP</span></span>

<span data-ttu-id="5f340-105">I Microsoft 365-organisationer med post lådor i Exchange Online, är nollställning autorensning en e-postskydds funktion som upptäcker och neutraliserar skadlig nät fiske, skräp post eller skadliga meddelanden som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="5f340-105">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="5f340-106">ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="5f340-106">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="5f340-107">Så fungerar ZAP</span><span class="sxs-lookup"><span data-stu-id="5f340-107">How ZAP works</span></span>

<span data-ttu-id="5f340-108">Alla signaturer för skräp post och skadlig program vara uppdateras i real tid per dag.</span><span class="sxs-lookup"><span data-stu-id="5f340-108">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="5f340-109">Men användare kan ändå ta emot skadliga meddelanden av olika anledningar, inklusive om innehållet är lite fritt efter att du har levererats till användarna.</span><span class="sxs-lookup"><span data-stu-id="5f340-109">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="5f340-110">ZAP löser det här problemet genom att fort löp ande övervaka uppdateringar av signaturer för skräp post och skadlig program vara i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="5f340-110">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="5f340-111">ZAP kan hitta och ta bort meddelanden som redan finns i en användares post låda.</span><span class="sxs-lookup"><span data-stu-id="5f340-111">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="5f340-112">Åtgärden ZAP är sömlös för användaren. de meddelas inte om ett meddelande identifieras och flyttas.</span><span class="sxs-lookup"><span data-stu-id="5f340-112">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="5f340-113">[Listor för betrodda avsändare](create-safe-sender-lists-in-office-365.md), regler för e-postflöde (kallas även transport regler), regler för Inkorgen eller ytterligare filter har högre prioritet än ZAP.</span><span class="sxs-lookup"><span data-stu-id="5f340-113">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="5f340-114">På samma sätt som i e-postflödet innebär det att även om tjänsten bestämmer det leverans behov som krävs för att skicka meddelandet, kan meddelandet inte aktive ras på grund av konfigurationen för betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="5f340-114">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="5f340-115">Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.</span><span class="sxs-lookup"><span data-stu-id="5f340-115">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="5f340-116">Malware, ZAP</span><span class="sxs-lookup"><span data-stu-id="5f340-116">Malware ZAP</span></span>

<span data-ttu-id="5f340-117">För **lästa och olästa meddelanden** som visar att det finns skadlig kod efter leverans får du ett meddelande som innehåller den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="5f340-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="5f340-118">Endast administratörer kan visa och hantera meddelanden om skadlig program vara från karantän.</span><span class="sxs-lookup"><span data-stu-id="5f340-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="5f340-119">Malware, ZAP är aktiverat som standard i principer mot skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="5f340-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="5f340-120">Mer information finns i [Konfigurera principer för skydd mot skadlig program vara i EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-120">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="5f340-121">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="5f340-121">Phish ZAP</span></span>

<span data-ttu-id="5f340-122">För **lästa och olästa meddelanden** som identifieras som Phish efter leverans, beror ZAP-resultatet av den åtgärd som är konfigurerad för Verdict för **e** -postfiltrering i den aktuella principen för borttagning av skräp post.</span><span class="sxs-lookup"><span data-stu-id="5f340-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="5f340-123">De tillgängliga Verdict-åtgärderna för Phish och deras eventuella ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="5f340-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="5f340-124">**Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="5f340-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="5f340-125">**Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard).</span><span class="sxs-lookup"><span data-stu-id="5f340-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="5f340-126">Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="5f340-127">**Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen.</span><span class="sxs-lookup"><span data-stu-id="5f340-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="5f340-128">Phish ZAP är som standard aktive rad i principer för skräp post och standard åtgärden för Verdict för **nät fiske** meddelanden är **karantän meddelande**, vilket innebär att Phish ZAP mellanstår meddelandet som standard.</span><span class="sxs-lookup"><span data-stu-id="5f340-128">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="5f340-129">Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-129">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="5f340-130">Spam</span><span class="sxs-lookup"><span data-stu-id="5f340-130">Spam ZAP</span></span>

<span data-ttu-id="5f340-131">För **olästa meddelanden** som identifieras som skräp post efter leverans beror ZAP-resultatet av den åtgärd som är konfigurerad för filtrering av **skräp post** filter i den aktuella principen för skräp post Verdict.</span><span class="sxs-lookup"><span data-stu-id="5f340-131">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="5f340-132">De tillgängliga Verdict-åtgärderna för filtrering av skräp post och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="5f340-132">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="5f340-133">**Lägga till X-rubrik**, **före ämnesrad med text**: ZAP gör ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="5f340-133">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="5f340-134">**Flytta meddelande till skräp post**: ZAP flyttar meddelandet till mappen skräp post så länge skräp post regeln är aktive rad på post lådan (den är aktive rad som standard).</span><span class="sxs-lookup"><span data-stu-id="5f340-134">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="5f340-135">Mer information finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor i Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-135">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="5f340-136">**Omdirigera meddelande till e-postadress**, **ta bort meddelande**, **karantän meddelande**: ZAP karantänen.</span><span class="sxs-lookup"><span data-stu-id="5f340-136">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="5f340-137">Slutanvändare kan visa och hantera sina egna meddelanden i Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="5f340-137">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="5f340-138">Som standard är skräppost-ZAP aktiverat i principer för skräp post, och standard åtgärden för **skräp** post filtrering Verdict är **att flytta meddelandet till mappen skräp post**, vilket innebär att skräp posten är som standard **avläst** meddelanden till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="5f340-138">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="5f340-139">Mer information om hur du konfigurerar verdicts för skräp post finns i [Konfigurera principer för skräp post filtrering i Microsoft 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-139">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a><span data-ttu-id="5f340-140">ZAP-överväganden för Office 365 Avancerat skydd (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="5f340-140">ZAP considerations for Office 365 Advanced Threat Protection (Office 365 ATP)</span></span>

<span data-ttu-id="5f340-141">ZAP kommer inte att placera något meddelande i processen för [dynamisk leverans](dynamic-delivery-and-previewing.md) genomsökning, eller så att filtret för skadlig program vara redan har ersatt bilagan med **varnings meddelandet Text.txt** -filen.</span><span class="sxs-lookup"><span data-stu-id="5f340-141">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="5f340-142">Om en Phish eller spam signal tas emot för dessa typer av meddelanden och filtrerings Verdict i principen mot skräp post är inställt på att få en åtgärd på meddelandet (flytta till skräp post, omdirigering, ta bort, karantän) och standardvärdet för "flytta till skräp post".</span><span class="sxs-lookup"><span data-stu-id="5f340-142">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="5f340-143">Så här ser du om ZAP har flyttat ditt meddelande</span><span class="sxs-lookup"><span data-stu-id="5f340-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="5f340-144">Om du vill ta reda på om ZAP har flyttat ditt meddelande kan du använda antingen [status rapport](view-email-security-reports.md#threat-protection-status-report) eller hot kontroll i [real tid](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="5f340-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="5f340-145">Observera att ZAP inte loggas i gransknings loggarna för Exchange-postlådan.</span><span class="sxs-lookup"><span data-stu-id="5f340-145">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="5f340-146">VANLIGA FRÅGOR OM ZAP</span><span class="sxs-lookup"><span data-stu-id="5f340-146">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="5f340-147">Vad händer om ett legitimt meddelande flyttas till mappen skräp post?</span><span class="sxs-lookup"><span data-stu-id="5f340-147">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="5f340-148">Du bör följa den vanliga rapporterings processen för [falska positiva](report-junk-email-messages-to-microsoft.md)verifieringar.</span><span class="sxs-lookup"><span data-stu-id="5f340-148">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="5f340-149">Det enda skälet till att meddelandet flyttas från inkorgen till mappen skräp post, eftersom tjänsten har fastställt att meddelandet har tagits bort eller är skadligt.</span><span class="sxs-lookup"><span data-stu-id="5f340-149">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="5f340-150">Vad händer om jag använder mappen karantän i stället för mappen skräp post?</span><span class="sxs-lookup"><span data-stu-id="5f340-150">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="5f340-151">ZAP utför en åtgärd på ett meddelande baserat på konfigurationen för skydd mot skräp post enligt beskrivningen ovan.</span><span class="sxs-lookup"><span data-stu-id="5f340-151">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="5f340-152">Vad händer om jag använder betrodda avsändare, e-postflödes regler eller tillåtna/blockerade avsändar listor?</span><span class="sxs-lookup"><span data-stu-id="5f340-152">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="5f340-153">Säkra avsändare, regler för e-postflöde eller blockering och Tillåt organisations inställningar gäller.</span><span class="sxs-lookup"><span data-stu-id="5f340-153">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="5f340-154">Dessa meddelanden är exkluderade från ZAP eftersom tjänsten gör det du konfigurerade att göra.</span><span class="sxs-lookup"><span data-stu-id="5f340-154">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="5f340-155">Det här är en annan anledning till att vara försiktig när du konfigurerar meddelanden för att kringgå filtrering.</span><span class="sxs-lookup"><span data-stu-id="5f340-155">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="5f340-156">Vad händer om ett meddelande flyttas till en annan mapp (till exempel regler för Inkorgen)?</span><span class="sxs-lookup"><span data-stu-id="5f340-156">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="5f340-157">ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge det finns en åtgärd som inte redan har använts.</span><span class="sxs-lookup"><span data-stu-id="5f340-157">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="5f340-158">Om till exempel Phish-principen är inställd på Quarantine och användaren eller administratören har fördelat e-postmeddelandet, vidtar en åtgärd för att placera filen i karantänen.</span><span class="sxs-lookup"><span data-stu-id="5f340-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="5f340-159">Hur påverkar ZAP post lådor?</span><span class="sxs-lookup"><span data-stu-id="5f340-159">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="5f340-160">ZAP startar inte karantän meddelanden från post lådor med undantag.</span><span class="sxs-lookup"><span data-stu-id="5f340-160">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="5f340-161">ZAP kan flytta meddelanden till mappen skräp post baserat på den åtgärd som har kon figurer ATS för skräp post eller nätfiske-Verdict i policyer för borttagning.</span><span class="sxs-lookup"><span data-stu-id="5f340-161">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="5f340-162">Mer information om undantag i Exchange Online finns [i-platsens undantag och rättsliga undantag i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span><span class="sxs-lookup"><span data-stu-id="5f340-162">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
