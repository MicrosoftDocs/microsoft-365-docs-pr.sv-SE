---
title: Zero-hour auto purge (ZAP) - retroaktivt skydd mot skräppost, skadlig kod och nätfiske.
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: Zero-hour auto purge (ZAP) är en e-postskyddsfunktion i Office 365 som identifierar skräppost, skadlig kod eller nätfiskemeddelanden som redan har levererats till Exchange Online. Hur ZAP gör detta beror på vilken typ av skadligt innehåll som upptäcks.
ms.openlocfilehash: 44bdab5d37863bc543d953a89ac3129b3530437d
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516779"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-office-365"></a><span data-ttu-id="1b4ae-104">Zero-hour auto purge (ZAP) - skydd mot skräppost och skadlig kod i Office 365</span><span class="sxs-lookup"><span data-stu-id="1b4ae-104">Zero-hour auto purge (ZAP) - protection against spam and malware in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="1b4ae-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="1b4ae-105">Overview</span></span>

<span data-ttu-id="1b4ae-106">Zero-hour auto purge (ZAP) är en e-postskyddsfunktion i Office 365 som retroaktivt identifierar och neutraliserar meddelanden om skadlig phishing, skräppost eller skadlig kod som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-106">Zero-hour auto purge (ZAP) is an email protection feature in Office 365 that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="1b4ae-107">ZAP är tillgängligt med standardprenumerationen Exchange Online Protection (EOP) som ingår i alla Office 365-prenumerationer som innehåller Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-107">ZAP is available with the default Exchange Online Protection (EOP) that's included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span> <span data-ttu-id="1b4ae-108">ZAP fungerar inte i fristående EOP-miljöer som skyddar lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-108">ZAP doesn't work in standalone EOP environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="1b4ae-109">Hur ZAP fungerar</span><span class="sxs-lookup"><span data-stu-id="1b4ae-109">How ZAP works</span></span>

<span data-ttu-id="1b4ae-110">Office 365 uppdaterar dagligen skräppost- och malwaresignaturer i realtid.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-110">Office 365 updates spam and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="1b4ae-111">Användare kan dock fortfarande ta emot skadliga meddelanden av olika skäl, bland annat om innehållet är weaponized efter att ha levererats till användare.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-111">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="1b4ae-112">ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av Office 365-signaturerna för skräppost och skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-112">ZAP addresses this issue by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="1b4ae-113">ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-113">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="1b4ae-114">ZAP-åtgärden är sömlös för användaren. De meddelas inte om ett meddelande identifieras och flyttas.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-114">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="1b4ae-115">[Säkra avsändarelistor](create-safe-sender-lists-in-office-365.md), e-postflödesregler (kallas även transportregler), inkorgsregler eller ytterligare filter har företräde framför ZAP.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-115">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="1b4ae-116">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="1b4ae-116">Malware ZAP</span></span>

<span data-ttu-id="1b4ae-117">För **lästa eller olästa meddelanden** som visar sig innehålla skadlig kod efter leverans sätter ZAP meddelandet som innehåller den bifogade koden i karantän.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-117">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="1b4ae-118">Endast administratörer kan visa och hantera meddelanden om skadlig kod från karantänen.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-118">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="1b4ae-119">Malware ZAP är aktiverat som standard i anti-malware politik.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-119">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="1b4ae-120">Mer information finns [i Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-120">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="1b4ae-121">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="1b4ae-121">Phish ZAP</span></span>

<span data-ttu-id="1b4ae-122">För **lästa eller olästa meddelanden** som identifieras som phish efter leverans beror ZAP-resultatet på vilken åtgärd som har konfigurerats för en **phishing-e-postfiltreringsdom** i tillämplig policy mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-122">For **read or unread messages** that are identified as phish after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1b4ae-123">De tillgängliga filtreringsutlåtandesåtgärderna för phish och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="1b4ae-123">The available filtering verdict actions for phish and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1b4ae-124">**Lägg till X-Header**, **Prepend ämnesrad med text:** ZAP vidtar ingen åtgärd på meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-124">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1b4ae-125">**Flytta meddelande till skräppost:** ZAP flyttar meddelandet till mappen Skräppost, så länge skräppostregeln är aktiverad i postlådan (den är aktiverad som standard).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-125">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1b4ae-126">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-126">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1b4ae-127">**Omdirigera meddelande till e-postadress**, **Ta bort meddelande**, Karantän **meddelande:** ZAP karantän meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-127">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="1b4ae-128">Endast administratörer kan visa och hantera phish karantän meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-128">Only admins can view and manage phish quarantined messages.</span></span>

<span data-ttu-id="1b4ae-129">Som standard är phish ZAP aktiverat i anti-spam-principer, och standardåtgärden för **phishing-e-postfiltreringsdomen** är **karantänmeddelande**, vilket innebär att phish ZAP sätter meddelandet i karantän som standard.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-129">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="1b4ae-130">Mer information om hur du konfigurerar domar för skräppostfiltrering finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-130">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="1b4ae-131">Spam ZAP</span><span class="sxs-lookup"><span data-stu-id="1b4ae-131">Spam ZAP</span></span>

<span data-ttu-id="1b4ae-132">För **olästa meddelanden** som identifieras som skräppost efter leverans beror ZAP-resultatet på vilken åtgärd som har konfigurerats för spam-filtreringsdomen i tillämplig anti-spam-policy. **Spam**</span><span class="sxs-lookup"><span data-stu-id="1b4ae-132">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="1b4ae-133">De tillgängliga filtreringsutlåtandesåtgärderna för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="1b4ae-133">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="1b4ae-134">**Lägg till X-Header**, **Prepend ämnesrad med text:** ZAP vidtar ingen åtgärd på meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-134">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="1b4ae-135">**Flytta meddelande till skräppost:** ZAP flyttar meddelandet till mappen Skräppost, så länge skräppostregeln är aktiverad i postlådan (den är aktiverad som standard).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-135">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="1b4ae-136">Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-136">For more information, see [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="1b4ae-137">**Omdirigera meddelande till e-postadress**, **Ta bort meddelande**, Karantän **meddelande:** ZAP karantän meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-137">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="1b4ae-138">Slutanvändare kan visa och hantera sina egna meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-138">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="1b4ae-139">Som standard är spam ZAP aktiverat i anti-spam politik, och standardåtgärden för **spam** filtrering dom är **Flytta meddelande till skräppost mapp**, vilket innebär spam ZAP flyttar **olästa** meddelanden till skräppost mappen som standard.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-139">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="1b4ae-140">Mer information om hur du konfigurerar domar för skräppostfiltrering finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-140">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a><span data-ttu-id="1b4ae-141">ZAP-överväganden för Office 365 Advanced Threat Protection (ATP)</span><span class="sxs-lookup"><span data-stu-id="1b4ae-141">ZAP considerations for Office 365 Advanced Threat Protection (ATP)</span></span>

<span data-ttu-id="1b4ae-142">ZAP kommer inte att sätta något meddelande i karantän som håller på att [skannas](dynamic-delivery-and-previewing.md) dynamisk leverans, eller där filtrering av skadlig kod redan har ersatt den bifogade filen med filen **Malware Alert Text.txt.**</span><span class="sxs-lookup"><span data-stu-id="1b4ae-142">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](dynamic-delivery-and-previewing.md) scanning, or where malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="1b4ae-143">Om en phish eller spam signal tas emot för dessa typer av meddelanden, och filtrering dom i anti-spam politik är inställd på att vidta vissa åtgärder på meddelandet (Flytta till Skräp, Omdirigera, Ta bort, Karantän) då ZAP kommer standard till en "Flytta till Skräp" åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-143">If a phish or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="1b4ae-144">Så här ser du om ZAP har flyttat meddelandet</span><span class="sxs-lookup"><span data-stu-id="1b4ae-144">How to see if ZAP moved your message</span></span>

<span data-ttu-id="1b4ae-145">För att avgöra om ZAP har flyttat meddelandet kan du använda [antingen rapporten Status för hotskydd](view-email-security-reports.md#threat-protection-status-report) eller Hot Explorer [(och identifiering i realtid)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-145">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="1b4ae-146">Observera att ZAP som en systemåtgärd inte är inloggad i granskningsloggarna för Exchange-postlådan.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-146">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="1b4ae-147">FRÅGOR OM ZAP</span><span class="sxs-lookup"><span data-stu-id="1b4ae-147">ZAP FAQ</span></span>

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="1b4ae-148">F: Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-148">Q: What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="1b4ae-149">S: Du bör följa den normala rapporteringsprocessen för [falska positiva identifieringar](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-149">A: You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="1b4ae-150">Den enda anledningen till att meddelandet skulle flyttas från inkorgen till mappen Skräppost skulle bero på att tjänsten har fastställt att meddelandet var skräppost eller skadligt.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-150">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="q-what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="1b4ae-151">F: Vad händer om jag använder karantänen för Office 365 i stället för mappen Skräppost?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-151">Q: What if I use the Office 365 quarantine instead of the Junk Mail folder?</span></span>

<span data-ttu-id="1b4ae-152">S: ZAP vidtar åtgärder för ett meddelande baserat på konfigurationen av dina policyer mot skräppost som beskrivs tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-152">A: ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this topic.</span></span>

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="1b4ae-153">F: Vad händer om jag använder regler för e-postflöde eller tillåtna/blockerade avsändarelistor?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-153">Q: What if I'm using mail flow rules or allowed/blocked sender lists?</span></span>

<span data-ttu-id="1b4ae-154">S: Regler för e-postflöde eller blockera och tillåta organisationsinställningar har företräde.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-154">A: Mail flow rules or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="1b4ae-155">Dessa meddelanden är undantagna från ZAP.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-155">These messages are excluded from ZAP.</span></span>

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="1b4ae-156">F: Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-156">Q: What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="1b4ae-157">S: ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge som samma, eller starkare, åtgärder inte redan har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-157">A:  ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="1b4ae-158">Om phish-principen till exempel är inställd på karantän och användaren eller administratören redan har skräppost, kommer karantän att vidta åtgärder för att sätta filen i karantän.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-158">For example, if the phish policy is set to quarantine and the user or administrator has already junked the email, then quarantine will take action to quarantine the file.</span></span>

### <a name="q-does-zap-change-the-message-header"></a><span data-ttu-id="1b4ae-159">F: Har ZAP ändra meddelanderubriken?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-159">Q: Does ZAP change the message header?</span></span>

<span data-ttu-id="1b4ae-160">S: En ZAP-åtgärd gör inga ändringar i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-160">A: A ZAP action does not make any changes to the message header.</span></span>

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="1b4ae-161">F: Hur påverkar ZAP postlådor som är spärrade?</span><span class="sxs-lookup"><span data-stu-id="1b4ae-161">Q: How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="1b4ae-162">S: ZAP sätter inte meddelanden i karantän från spärrade postlådor.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-162">A: ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="1b4ae-163">ZAP kan flytta meddelanden till mappen Skräppost baserat på den åtgärd som har konfigurerats för en skräppost- eller nätfiskedom i policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="1b4ae-163">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="1b4ae-164">Mer information om spärrar i Exchange Online finns [i Hold and Litigation Hold i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span><span class="sxs-lookup"><span data-stu-id="1b4ae-164">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
