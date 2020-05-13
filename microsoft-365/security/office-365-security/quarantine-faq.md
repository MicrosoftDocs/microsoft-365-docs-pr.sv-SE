---
title: Vanliga frågor och svar om meddelanden i karantän
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Administratörer kan visa vanliga frågor och svar om meddelanden i karantän i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2022a43f1dd89d47fdb4f3898f8f481419962c0
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213110"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="56509-103">Vanliga frågor och svar om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="56509-103">Quarantined messages FAQ</span></span>

<span data-ttu-id="56509-104">Det här avsnittet innehåller vanliga frågor och svar om e-postmeddelanden i karantän för Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="56509-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="56509-105">Frågor och svar om skydd mot skräppost finns i [Vanliga frågor om skydd mot skräppost](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="56509-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="56509-106">Frågor och svar om skydd mot skadlig kod finns i [Vanliga frågor om skydd mot skadlig kod](anti-malware-protection-faq-eop.md).</span><span class="sxs-lookup"><span data-stu-id="56509-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="56509-107">För frågor och svar om anti-spoofing skydd, se [Anti-spoofing skydd FAQ](anti-spoofing-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="56509-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="56509-108">Hur hanterar jag meddelanden som har satts i karantän för skadlig kod?</span><span class="sxs-lookup"><span data-stu-id="56509-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="56509-109">Endast administratörer kan hantera meddelanden som har satts i karantän för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="56509-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="56509-110">Mer information finns i [Hantera meddelanden och filer i karantän som administratör](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="56509-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="56509-111">Hur sätter jag skräppost i karantän?</span><span class="sxs-lookup"><span data-stu-id="56509-111">How do I quarantine spam?</span></span>

<span data-ttu-id="56509-112">Som standard levereras meddelanden som klassificeras som skräppost eller massutskick via skräppostfiltrering till användarens postlåda och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="56509-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="56509-113">Men du kan skapa och konfigurera anti-spam-principer för att sätta skräppost eller massmeddelanden i karantän i stället.</span><span class="sxs-lookup"><span data-stu-id="56509-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="56509-114">Mer information finns [i Konfigurera principer mot skräppost i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56509-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="56509-115">Hur ger jag användarna åtkomst till karantänen?</span><span class="sxs-lookup"><span data-stu-id="56509-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="56509-116">En användare måste ha ett giltigt konto för att få åtkomst till sina egna meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="56509-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="56509-117">Fristående EOP kräver att användare representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalogsynkronisering).</span><span class="sxs-lookup"><span data-stu-id="56509-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="56509-118">Mer information om hur du hanterar användare i fristående EOP-miljöer finns [i Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="56509-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="56509-119">Vilka meddelanden kan slutanvändare komma åt i karantän?</span><span class="sxs-lookup"><span data-stu-id="56509-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="56509-120">Användare kan komma åt skräppost, massmeddelanden och (från och med april 2020) nätfiskemeddelanden där de är mottagare.</span><span class="sxs-lookup"><span data-stu-id="56509-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="56509-121">Slutanvändare kan inte komma åt skadlig kod i karantän, nätfiske med högt förtroende eller meddelanden som har satts i karantän på grund av **meddelandet Leverera meddelandet till den värdbaserade karantänåtgärden** i regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="56509-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="56509-122">Mer information om användare som använder meddelanden i karantän finns i [Hitta och släppa meddelanden i karantän som användare](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="56509-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="56509-123">Hur länge förvaras meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="56509-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="56509-124">Du kan konfigurera hur länge skräppost, nätfiske och massmeddelanden hålls i karantän med hjälp av policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="56509-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="56509-125">Standardvärdet är 30 dagar, vilket också är det maximala.</span><span class="sxs-lookup"><span data-stu-id="56509-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="56509-126">Mer information finns [i Konfigurera policyer mot skräppost i EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="56509-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="56509-127">För meddelanden som har satts i karantän av e-postflödesregelåtgärden **Leverera meddelandet till den värdbaserade karantänen**hålls meddelandena i karantän i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="56509-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="56509-128">Du kan inte konfigurera den här varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="56509-128">You can't configure this duration.</span></span>

<span data-ttu-id="56509-129">När tidsperioden har gått ut tas meddelandena bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="56509-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="56509-130">Kan jag släppa eller rapportera mer än ett meddelande i karantän åt gången?</span><span class="sxs-lookup"><span data-stu-id="56509-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="56509-131">I Security & Compliance Center kan du välja och släppa upp till 100 meddelanden åt gången.</span><span class="sxs-lookup"><span data-stu-id="56509-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="56509-132">Administratörer kan använda cmdleterna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) och [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) i Exchange Online PowerShell eller fristående EOP PowerShell för att hitta och släppa meddelanden i karantän i grupp och för att rapportera falska positiva identifieringar i grupp.</span><span class="sxs-lookup"><span data-stu-id="56509-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="56509-133">Stöds jokertecken när du söker efter meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="56509-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="56509-134">Kan jag söka efter meddelanden i karantän för en viss domän?</span><span class="sxs-lookup"><span data-stu-id="56509-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="56509-135">Jokertecken stöds inte i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="56509-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="56509-136">När du till exempel söker efter en avsändare måste du ange den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="56509-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="56509-137">Men du kan använda jokertecken i Exchange Online PowerShell eller fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56509-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="56509-138">Kör till exempel följande kommando för att hitta skräppostmeddelanden i karantän från alla avsändare i domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="56509-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="56509-139">Kör sedan följande kommando för att släppa dessa meddelanden till alla ursprungliga mottagare:</span><span class="sxs-lookup"><span data-stu-id="56509-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="56509-140">När du har släppt ett meddelande kan du inte släppa det igen.</span><span class="sxs-lookup"><span data-stu-id="56509-140">After you release a message, you can't release it again.</span></span>
