---
title: Vanliga frågor om meddelanden i karantän
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
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Administratörer kan visa vanliga frågor och svar om meddelanden i karantän i Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cf1281338de66f54a6c4546b047259d647cc3ea
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616002"
---
# <a name="quarantined-messages-faq"></a><span data-ttu-id="5d88d-103">Vanliga frågor om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="5d88d-103">Quarantined messages FAQ</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="5d88d-104">Det här avsnittet innehåller vanliga frågor och svar om e-postmeddelanden i karantän för Microsoft 365-organisationer med post lådor i Exchange Online eller fristående organisationer för Exchange Online Protection (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="5d88d-104">This topic provides frequently asked questions and answers about quarantined email messages for Microsoft 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span>

<span data-ttu-id="5d88d-105">Frågor och svar om skydd mot skräp post finns i [vanliga frågor om skydd mot skräp post](anti-spam-protection-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-105">For questions and answers about anti-spam protection, see [Anti-spam protection FAQ](anti-spam-protection-faq.md).</span></span>

<span data-ttu-id="5d88d-106">Frågor och svar om skydd mot skadlig program vara finns i [vanliga frågor om skydd mot skadlig program vara](anti-malware-protection-faq-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-106">For questions and answers about anti-malware protection, see [Anti-malware protection FAQ](anti-malware-protection-faq-eop.md).</span></span>

<span data-ttu-id="5d88d-107">Frågor och svar om skydd mot förfalskning finns i [vanliga frågor](anti-spoofing-protection-faq.md)och svar om skydd mot förfalskning.</span><span class="sxs-lookup"><span data-stu-id="5d88d-107">For questions and answers about anti-spoofing protection, see [Anti-spoofing protection FAQ](anti-spoofing-protection-faq.md).</span></span>

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="5d88d-108">Hur hanterar jag meddelanden som satts i karantän för skadlig program vara?</span><span class="sxs-lookup"><span data-stu-id="5d88d-108">How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="5d88d-109">Endast administratörer kan hantera meddelanden som satts i karantän för skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="5d88d-109">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="5d88d-110">Mer information finns i [Hantera meddelanden och filer i karantän som administratör](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-110">For more information, see [Manage quarantined messages and files as an admin](manage-quarantined-messages-and-files.md).</span></span>

## <a name="how-do-i-quarantine-spam"></a><span data-ttu-id="5d88d-111">Hur kan jag skicka skräp post?</span><span class="sxs-lookup"><span data-stu-id="5d88d-111">How do I quarantine spam?</span></span>

<span data-ttu-id="5d88d-112">Standardinställningen är att meddelanden som klassificeras som skräp post eller Mass utskick via skräp post skickas till användarens post låda och flyttas till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="5d88d-112">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="5d88d-113">Du kan till och med skapa och konfigurera principer för skräp post till Mass utskick och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="5d88d-113">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="5d88d-114">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="5d88d-115">Hur ger jag användare åtkomst till karantänen?</span><span class="sxs-lookup"><span data-stu-id="5d88d-115">How do I give users access to the quarantine?</span></span>

<span data-ttu-id="5d88d-116">En användare måste ha ett giltigt konto för att få åtkomst till sina egna meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="5d88d-116">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="5d88d-117">Fristående EOP kräver att användarna representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalog-synkronisering).</span><span class="sxs-lookup"><span data-stu-id="5d88d-117">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="5d88d-118">Mer information om hur du hanterar användare i fristående EOP miljöer finns i [Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-118">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="5d88d-119">Vilka meddelanden kan användare få åtkomst till i karantän?</span><span class="sxs-lookup"><span data-stu-id="5d88d-119">What messages can end users access in quarantine?</span></span>

<span data-ttu-id="5d88d-120">Användare kan få åtkomst till skräp post, Mass utskick och (från april 2020) nät fiske meddelanden där de är mottagare.</span><span class="sxs-lookup"><span data-stu-id="5d88d-120">Users can access spam, bulk email, and (as of April 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="5d88d-121">Slutanvändare kan inte komma åt skadlig program vara i karantän, högsäker nät fiske eller meddelanden som satts i karantän på grund av att **meddelandet levererades till den värdbaserade karantäns** åtgärden i regler för e-postflöde (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="5d88d-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="5d88d-122">Mer information om användare som har åtkomst till karantän meddelanden finns i [hitta och släppa meddelanden i karantän som en användare](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="5d88d-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="5d88d-123">Hur länge lagras meddelanden i karantänen?</span><span class="sxs-lookup"><span data-stu-id="5d88d-123">How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="5d88d-124">Du kan konfigurera hur länge skräp post, nät fiske och Mass utskick av e-post ska sparas i karantänen genom att använda principer för skräp post.</span><span class="sxs-lookup"><span data-stu-id="5d88d-124">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="5d88d-125">Standardvärdet är 30 dagar, vilket också är det största.</span><span class="sxs-lookup"><span data-stu-id="5d88d-125">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="5d88d-126">Mer information finns i [Konfigurera principer för skräp post meddelanden i EOP](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5d88d-126">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="5d88d-127">För meddelanden som har placerats i karantän av åtgärden för e-postflödes regeln **skickas meddelandet till den värdbaserade karantänen**, men meddelandena bevaras i karantän i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="5d88d-127">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="5d88d-128">Du kan inte konfigurera varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="5d88d-128">You can't configure this duration.</span></span>

<span data-ttu-id="5d88d-129">När tids perioden går ut tas meddelanden bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="5d88d-129">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="5d88d-130">Kan jag släppa eller rapportera mer än ett meddelande i karantän åt gången?</span><span class="sxs-lookup"><span data-stu-id="5d88d-130">Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="5d88d-131">I säkerhets & Compliance Center kan du välja och släppa upp till 100 meddelanden åt gången.</span><span class="sxs-lookup"><span data-stu-id="5d88d-131">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="5d88d-132">Administratörer kan använda cmdletarna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) och [release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) i Exchange Online PowerShell eller fristående EOP PowerShell för att hitta och släppa upp insatta meddelanden i gruppen, samt för att rapportera falsk positiv identifiering i bulk.</span><span class="sxs-lookup"><span data-stu-id="5d88d-132">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone EOP PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="5d88d-133">Stöds jokertecken vid sökning efter meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="5d88d-133">Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="5d88d-134">Kan jag söka efter meddelanden i karantän för en viss domän?</span><span class="sxs-lookup"><span data-stu-id="5d88d-134">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="5d88d-135">Jokertecken stöds inte i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="5d88d-135">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="5d88d-136">Om du till exempel söker efter en avsändare måste du ange den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="5d88d-136">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="5d88d-137">Men du kan använda jokertecken i Exchange Online PowerShell eller fristående EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5d88d-137">But, you can use wildcards in Exchange Online PowerShell or standalone EOP PowerShell.</span></span>

<span data-ttu-id="5d88d-138">Kör till exempel följande kommando för att hitta skräp post i karantänen från alla avsändare i domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="5d88d-138">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="5d88d-139">Kör sedan följande kommando för att släppa dessa meddelanden till alla ursprungliga mottagare:</span><span class="sxs-lookup"><span data-stu-id="5d88d-139">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

<span data-ttu-id="5d88d-140">När du har släppt ett meddelande kan du inte frigöra det igen.</span><span class="sxs-lookup"><span data-stu-id="5d88d-140">After you release a message, you can't release it again.</span></span>
