---
title: Zap (Zero-hour auto purge)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Administratörer kan ta reda på hur ZAP (Zero-Hour Auto Purge) retroaktivt kan flytta skickade meddelanden i en Exchange Online-postlåda till mappen Skräppost eller karantänen som retroaktivt visar sig vara skräppost eller nätfiske.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287311"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a><span data-ttu-id="f6c65-103">Zap (Zero-hour auto purge) i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f6c65-103">Zero-hour auto purge (ZAP) in Exchange Online</span></span>

<span data-ttu-id="f6c65-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f6c65-104">**Applies to**</span></span>
- [<span data-ttu-id="f6c65-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f6c65-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f6c65-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f6c65-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="f6c65-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6c65-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a><span data-ttu-id="f6c65-108">Grundläggande funktioner i ZAP</span><span class="sxs-lookup"><span data-stu-id="f6c65-108">Basic features of ZAP</span></span>

<span data-ttu-id="f6c65-109">I Microsoft 365-organisationer med postlådor i Exchange Online är ZAP (Zero-hour Auto Purge) en funktion för e-postskydd som retroaktivt identifierar och neutralerar skadliga nätfiske-, skräppost- eller skadlig programvara som redan har levererats till Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f6c65-109">In Microsoft 365 organizations with mailboxes in Exchange Online, zero-hour auto purge (ZAP) is an email protection feature that retroactively detects and neutralizes malicious phishing, spam, or malware messages that have already been delivered to Exchange Online mailboxes.</span></span>

<span data-ttu-id="f6c65-110">ZAP fungerar inte i fristående Exchange Online Protection-miljöer (EOP) som skyddar lokala Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f6c65-110">ZAP doesn't work in standalone Exchange Online Protection (EOP) environments that protect on-premises Exchange mailboxes.</span></span>

## <a name="how-zap-works"></a><span data-ttu-id="f6c65-111">Så här fungerar ZAP</span><span class="sxs-lookup"><span data-stu-id="f6c65-111">How ZAP works</span></span>

<span data-ttu-id="f6c65-112">Signaturer för skräppost och skadlig programvara uppdateras dagligen i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f6c65-112">Spam and malware signatures are updated in the service real-time on a daily basis.</span></span> <span data-ttu-id="f6c65-113">Användare kan dock fortfarande ta emot skadliga meddelanden av en mängd olika orsaker, till exempel om innehållet har lokaliserats efter att det har levererats till användarna.</span><span class="sxs-lookup"><span data-stu-id="f6c65-113">However, users can still receive malicious messages for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="f6c65-114">ZAP åtgärdar det här problemet genom att kontinuerligt övervaka uppdateringar av signaturer för skräppost och skadlig programvara i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f6c65-114">ZAP addresses this issue by continually monitoring updates to the spam and malware signatures in the service.</span></span> <span data-ttu-id="f6c65-115">ZAP kan hitta och ta bort meddelanden som redan finns i en användares postlåda.</span><span class="sxs-lookup"><span data-stu-id="f6c65-115">ZAP can find and remove messages that are already in a user's mailbox.</span></span>

<span data-ttu-id="f6c65-116">ZAP-åtgärden är smidig för användaren. De meddelas inte om ett meddelande identifieras och flyttas.</span><span class="sxs-lookup"><span data-stu-id="f6c65-116">The ZAP action is seamless for the user; they aren't notified if a message is detected and moved.</span></span>

<span data-ttu-id="f6c65-117">[Listor över betrodda](create-safe-sender-lists-in-office-365.md)avsändare, e-postflödesregler (kallas även transportregler), inkorgsregler och ytterligare filter har företräde framför ZAP.</span><span class="sxs-lookup"><span data-stu-id="f6c65-117">[Safe sender lists](create-safe-sender-lists-in-office-365.md), mail flow rules (also known as transport rules), Inbox rules, or additional filters take precedence over ZAP.</span></span> <span data-ttu-id="f6c65-118">På liknande sätt som i e-postflödet innebär det att även om tjänsten bestämmer att det levererade meddelandet behöver ZAP så ageras meddelandet inte på grund av konfigurationen betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="f6c65-118">Similar to what happens in mail flow, this means that even if the service determines the delivered message needs ZAP, the message is not acted on because of the the safe senders configuration.</span></span> <span data-ttu-id="f6c65-119">Det här är en annan orsak till att vara försiktig med att konfigurera meddelanden så att filtrering kringgås.</span><span class="sxs-lookup"><span data-stu-id="f6c65-119">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="f6c65-120">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="f6c65-120">Malware ZAP</span></span>

<span data-ttu-id="f6c65-121">För **lästa eller olästa meddelanden** som innehåller skadlig programvara efter leverans sätts det meddelande som innehåller den bifogade filen för skadlig programvara i karantän.</span><span class="sxs-lookup"><span data-stu-id="f6c65-121">For **read or unread messages** that are found to contain malware after delivery, ZAP quarantines the message that contains the malware attachment.</span></span> <span data-ttu-id="f6c65-122">Endast administratörer kan visa och hantera meddelanden om skadlig programvara från karantän.</span><span class="sxs-lookup"><span data-stu-id="f6c65-122">Only admins can view and manage malware messages from quarantine.</span></span>

<span data-ttu-id="f6c65-123">Malware ZAP är aktiverat som standard i principer för skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="f6c65-123">Malware ZAP is enabled by default in anti-malware policies.</span></span> <span data-ttu-id="f6c65-124">Mer information finns i Konfigurera [principer för skadlig programvara i EOP.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-124">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

### <a name="phish-zap"></a><span data-ttu-id="f6c65-125">Phish ZAP</span><span class="sxs-lookup"><span data-stu-id="f6c65-125">Phish ZAP</span></span>

<span data-ttu-id="f6c65-126">För **lästa eller olästa** meddelanden som identifieras som nätfiske efter leverans beror  ZAP-resultatet på den åtgärd som har konfigurerats för en filtrering av nätfiskemeddelanden i den tillämpliga principen för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f6c65-126">For **read or unread messages** that are identified as phishing after delivery, the ZAP outcome depends on the action that's configured for a **Phishing email** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="f6c65-127">Tillgängliga filtreringsåtgärder för nätfiske och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="f6c65-127">The available filtering verdict actions for phishing and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="f6c65-128">Lägg till text för **X-Header,** **Lägga till text** i den första ämnesraden: ZAP vidtar ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f6c65-128">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="f6c65-129">**Flytta meddelandet till Skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (standardinställningen är aktiverad).</span><span class="sxs-lookup"><span data-stu-id="f6c65-129">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="f6c65-130">Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-130">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="f6c65-131">**Omdirigera meddelandet till e-postadress,** **Ta bort meddelande,** **sätt meddelande** i karantän: ZAP sätt meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="f6c65-131">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span>

<span data-ttu-id="f6c65-132">Som standard är phish ZAP aktiverat i principer för skydd  mot skräppost och standardåtgärden för filtrering av nätfiskemeddelanden är karantänmeddelande, vilket innebär att zap sätts i karantänen för meddelandet som standard.</span><span class="sxs-lookup"><span data-stu-id="f6c65-132">By default, phish ZAP is enabled in anti-spam policies, and the default action for the **Phishing email** filtering verdict is **Quarantine message**, which means phish ZAP quarantines the message by default.</span></span>

<span data-ttu-id="f6c65-133">Mer information om konfigurering av skräppostfiltreringsprinciper finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-133">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="spam-zap"></a><span data-ttu-id="f6c65-134">Spam ZAP</span><span class="sxs-lookup"><span data-stu-id="f6c65-134">Spam ZAP</span></span>

<span data-ttu-id="f6c65-135">För **olästa** meddelanden som identifieras som skräppost efter leverans beror ZAP-resultatet  på den åtgärd som har konfigurerats för skräppostfiltreringens bedömning i den tillämpliga policyn för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f6c65-135">For **unread messages** that are identified as spam after delivery, the ZAP outcome depends on the action that's configured for the **Spam** filtering verdict in the applicable anti-spam policy.</span></span> <span data-ttu-id="f6c65-136">Tillgängliga filtreringsåtgärder för skräppost och deras möjliga ZAP-resultat beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="f6c65-136">The available filtering verdict actions for spam and their possible ZAP outcomes are described in the following list:</span></span>

- <span data-ttu-id="f6c65-137">Lägg till text för **X-Header,** **Lägga till text** i den första ämnesraden: ZAP vidtar ingen åtgärd för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f6c65-137">**Add X-Header**, **Prepend subject line with text**: ZAP takes no action on the message.</span></span>

- <span data-ttu-id="f6c65-138">**Flytta meddelandet till Skräppost:** ZAP flyttar meddelandet till mappen Skräppost så länge skräppostregeln är aktiverad för postlådan (standardinställningen är aktiverad).</span><span class="sxs-lookup"><span data-stu-id="f6c65-138">**Move message to Junk Email**: ZAP moves the message to the Junk Email folder, as long as the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="f6c65-139">Mer information finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor i Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-139">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

- <span data-ttu-id="f6c65-140">**Omdirigera meddelandet till e-postadress,** **Ta bort meddelande,** **sätt meddelande** i karantän: ZAP sätt meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="f6c65-140">**Redirect message to email address**, **Delete message**, **Quarantine message**: ZAP quarantines the message.</span></span> <span data-ttu-id="f6c65-141">Slutanvändarna kan visa och hantera sina egna meddelanden i karantänen för skräppost.</span><span class="sxs-lookup"><span data-stu-id="f6c65-141">End-users can view and manage their own spam quarantined messages.</span></span>

<span data-ttu-id="f6c65-142">Som standard har ZAP för skräppost aktiverats i principer  för skräppostskydd, och standardåtgärden för filtrering  av skräppost är Flytta meddelanden till mappen **Skräppost,** vilket innebär att ZAP i skräppostmappen flyttar olästa meddelanden till mappen Skräppost som standard.</span><span class="sxs-lookup"><span data-stu-id="f6c65-142">By default, spam ZAP is enabled in anti-spam policies, and the default action for the **Spam** filtering verdict is **Move message to Junk Email folder**, which means spam ZAP moves **unread** messages to the Junk Email folder by default.</span></span>

<span data-ttu-id="f6c65-143">Mer information om konfigurering av skräppostfiltreringsprinciper finns i [Konfigurera principer för skydd mot skräppost i Microsoft 365.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-143">For more information about configuring spam filtering verdicts, see [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).</span></span>

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a><span data-ttu-id="f6c65-144">ZAP-överväganden för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f6c65-144">ZAP considerations for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="f6c65-145">ZAP sätt inte i karantän ett meddelande [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) som bearbetas med dynamisk leverans vid genomsökning av säkra bifogade filer, eller där EOP-filtrering av skadlig programvara redan har ersatt den bifogade filen med Text.txt **fil.**</span><span class="sxs-lookup"><span data-stu-id="f6c65-145">ZAP will not quarantine any message that's in the process of [Dynamic Delivery](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Safe Attachments scanning, or where EOP malware filtering has already replaced the attachment with the **Malware Alert Text.txt** file.</span></span> <span data-ttu-id="f6c65-146">Om en nätfiske- eller skräppostsignal tas emot för den här typen av meddelanden, och filtreringen i skräppostprincipen är inställd på att vidta någon åtgärd för meddelandet (Flytta till Skräppost, Omdirigera, Ta bort eller Karantän) använder ZAP som standard åtgärden Flytta till skräppost.</span><span class="sxs-lookup"><span data-stu-id="f6c65-146">If a phishing or spam signal is received for these types of messages, and the filtering verdict in the anti-spam policy is set to take some action on the message (Move to Junk, Redirect, Delete, or Quarantine) then ZAP will default to a 'Move to Junk' action.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="f6c65-147">Så här ser du om ZAP har flyttat ditt meddelande</span><span class="sxs-lookup"><span data-stu-id="f6c65-147">How to see if ZAP moved your message</span></span>

<span data-ttu-id="f6c65-148">Om du vill avgöra om ZAP har [](view-email-security-reports.md#threat-protection-status-report) flyttat ditt meddelande kan du använda antingen rapporten status för skydd mot hot [eller Hotutforskaren (och identifieringar i realtid).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-148">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span> <span data-ttu-id="f6c65-149">Observera att ZAP inte loggas i granskningsloggarna för Exchange-postlådor som en systemåtgärd.</span><span class="sxs-lookup"><span data-stu-id="f6c65-149">Note that as a system action, ZAP is not logged in the Exchange mailbox audit logs.</span></span>

## <a name="zap-faq"></a><span data-ttu-id="f6c65-150">ZAP VANLIGA FRÅGOR OCH SVAR</span><span class="sxs-lookup"><span data-stu-id="f6c65-150">ZAP FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a><span data-ttu-id="f6c65-151">Vad händer om ett legitimt meddelande flyttas till mappen Skräppost?</span><span class="sxs-lookup"><span data-stu-id="f6c65-151">What happens if a legitimate message is moved to the Junk Email folder?</span></span>

<span data-ttu-id="f6c65-152">Du bör följa den vanliga rapporteringsprocessen för [falska positiva resultat.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="f6c65-152">You should follow the normal reporting process for [false positives](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="f6c65-153">Den enda orsaken till att meddelandet flyttas från Inkorgen till mappen Skräppost är att tjänsten har fastställt att meddelandet är skräppost eller skadligt.</span><span class="sxs-lookup"><span data-stu-id="f6c65-153">The only reason the message would be moved from the Inbox to the Junk Email folder would be because the service has determined that the message was spam or malicious.</span></span>

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a><span data-ttu-id="f6c65-154">Vad händer om jag använder mappen Karantän i stället för skräppostmappen?</span><span class="sxs-lookup"><span data-stu-id="f6c65-154">What if I use the Quarantine folder instead of the Junk Mail folder?</span></span>

<span data-ttu-id="f6c65-155">ZAP kommer att vidta åtgärder på ett meddelande baserat på konfigurationen av dina principer för skydd mot skräppost enligt beskrivningen tidigare i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="f6c65-155">ZAP will take action on a message based on the configuration your anti-spam policies as described earlier in this article.</span></span>

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a><span data-ttu-id="f6c65-156">Vad händer om jag använder betrodda avsändare, e-postflödesregler eller listor med tillåtna/blockerade avsändare?</span><span class="sxs-lookup"><span data-stu-id="f6c65-156">What if I'm using safe senders, mail flow rules, or allowed/blocked sender lists?</span></span>

<span data-ttu-id="f6c65-157">Betrodda avsändare, e-postflödesregler eller blockering och organisationens inställningar har företräde.</span><span class="sxs-lookup"><span data-stu-id="f6c65-157">Safe senders, mail flow rules, or block and allow organizational settings take precedence.</span></span> <span data-ttu-id="f6c65-158">Dessa meddelanden är undantagna från ZAP eftersom tjänsten gör vad du konfigurerat den för.</span><span class="sxs-lookup"><span data-stu-id="f6c65-158">These messages are excluded from ZAP since the service is doing what you configured it to do.</span></span> <span data-ttu-id="f6c65-159">Det här är en annan orsak till att vara försiktig med att konfigurera meddelanden så att filtrering kringgås.</span><span class="sxs-lookup"><span data-stu-id="f6c65-159">This is another reason to be careful about configuring messages to bypass filtering.</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a><span data-ttu-id="f6c65-160">Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregler)?</span><span class="sxs-lookup"><span data-stu-id="f6c65-160">What if a message is moved to another folder (e.g. Inbox rules)?</span></span>

<span data-ttu-id="f6c65-161">ZAP fungerar fortfarande så länge meddelandet inte har tagits bort, eller så länge samma, eller starkare, åtgärder inte redan har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="f6c65-161">ZAP still works as long as the message has not been deleted, or as long as the same, or stronger, action has not already been applied.</span></span> <span data-ttu-id="f6c65-162">Om till exempel principen för nätfiske är inställd på att sätta i karantän och meddelandet redan finns i skräpposten kommer ZAP att vidta åtgärder för att sätta meddelandet i karantän.</span><span class="sxs-lookup"><span data-stu-id="f6c65-162">For example, if the anti-phishing policy is set to quarantine and message is already in the Junk Email, then ZAP will take action to quarantine the message.</span></span>

### <a name="how-does-zap-affect-mailboxes-on-hold"></a><span data-ttu-id="f6c65-163">Hur påverkar ZAP postlådor som är väntande?</span><span class="sxs-lookup"><span data-stu-id="f6c65-163">How does ZAP affect mailboxes on hold?</span></span>

<span data-ttu-id="f6c65-164">ZAP sätts inte i karantän för meddelanden från postlådor som är väntande.</span><span class="sxs-lookup"><span data-stu-id="f6c65-164">ZAP won't quarantine messages from mailboxes on hold.</span></span> <span data-ttu-id="f6c65-165">ZAP kan flytta meddelanden till mappen Skräppost baserat på åtgärder som konfigurerats för skräppost eller nätfiskeförsök i principer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="f6c65-165">ZAP can move messages to the Junk Email folder based on the action that's configured for a spam or phishing verdict in anti-spam policies.</span></span>

<span data-ttu-id="f6c65-166">Mer information om bevarande i Exchange Online finns i Bevarande av juridiska skäl på plats i [Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)</span><span class="sxs-lookup"><span data-stu-id="f6c65-166">For more information about holds in Exchange Online, see [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).</span></span>
