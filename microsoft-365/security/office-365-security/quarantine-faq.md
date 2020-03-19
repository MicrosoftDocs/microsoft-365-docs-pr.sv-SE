---
title: Vanliga frågor om karantän
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
description: Svar på vanliga frågor om karantän i Office 365.
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856911"
---
# <a name="quarantine-faq-in-office-365"></a><span data-ttu-id="ec213-103">Vanliga frågor om karantän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ec213-103">Quarantine FAQ in Office 365</span></span>

<span data-ttu-id="ec213-104">Det här avsnittet innehåller vanliga frågor och svar om karantän för Office 365-kunder med postlådor i Exchange Online eller fristående Exchange Online Protection -kunder (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="ec213-104">This topic provides frequently asked questions and answers about quarantine for Office 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes.</span></span>

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a><span data-ttu-id="ec213-105">F: Hur hanterar jag meddelanden som har satts i karantän för skadlig kod?</span><span class="sxs-lookup"><span data-stu-id="ec213-105">Q: How do I manage messages that were quarantined for malware?</span></span>

<span data-ttu-id="ec213-106">Endast administratörer kan hantera meddelanden som har satts i karantän för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="ec213-106">Only admins can manage messages that were quarantined for malware.</span></span> <span data-ttu-id="ec213-107">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ec213-107">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

## <a name="q-how-do-i-quarantine-spam"></a><span data-ttu-id="ec213-108">F: Hur sätter jag skräppost i karantän?</span><span class="sxs-lookup"><span data-stu-id="ec213-108">Q: How do I quarantine spam?</span></span>

<span data-ttu-id="ec213-109">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-109">A.</span></span> <span data-ttu-id="ec213-110">Som standard levereras meddelanden som klassificeras som skräppost eller massutskick via skräppostfiltrering till användarens postlåda och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="ec213-110">By default, messages that are classified as spam or bulk email by spam filtering are delivered to the user's mailbox, and are moved to the Junk Email folder.</span></span> <span data-ttu-id="ec213-111">Men du kan skapa och konfigurera anti-spam-principer för att sätta skräppost eller massmeddelanden i karantän i stället.</span><span class="sxs-lookup"><span data-stu-id="ec213-111">But you can create and configure anti-spam policies to quarantine spam or bulk email messages instead.</span></span> <span data-ttu-id="ec213-112">Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ec213-112">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a><span data-ttu-id="ec213-113">F: Hur ger jag användarna åtkomst till karantänen?</span><span class="sxs-lookup"><span data-stu-id="ec213-113">Q: How do I give users access to the quarantine?</span></span>

<span data-ttu-id="ec213-114">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-114">A.</span></span> <span data-ttu-id="ec213-115">En användare måste ha ett giltigt konto för att få åtkomst till sina egna meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="ec213-115">A user must have a valid account to access their own messages in quarantine.</span></span> <span data-ttu-id="ec213-116">Fristående EOP kräver att användare representeras som e-postanvändare i EOP (skapas eller skapas manuellt via katalogsynkronisering).</span><span class="sxs-lookup"><span data-stu-id="ec213-116">Standalone EOP requires that users are represented as mail users in EOP (manually created or created via directory synchronization).</span></span> <span data-ttu-id="ec213-117">Mer information om hur du hanterar användare i fristående EOP-miljöer finns [i Hantera e-postanvändare i EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ec213-117">For more information about managing users in standalone EOP environments, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a><span data-ttu-id="ec213-118">F: Vilka meddelanden kan slutanvändare komma åt i karantän?</span><span class="sxs-lookup"><span data-stu-id="ec213-118">Q: What messages can end users access in quarantine?</span></span>

<span data-ttu-id="ec213-119">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-119">A.</span></span> <span data-ttu-id="ec213-120">Användare kan komma åt skräppost, massmeddelanden och (från och med april 2020) nätfiskemeddelanden där de är mottagare.</span><span class="sxs-lookup"><span data-stu-id="ec213-120">Users can access spam, bulk email, and (as of April, 2020) phishing messages where they are a recipient.</span></span> <span data-ttu-id="ec213-121">Slutanvändare kan inte komma åt skadlig kod i karantän, nätfiske med högt förtroende eller meddelanden som har satts i karantän på grund av **meddelandet Leverera meddelandet till den värdbaserade karantänåtgärden** i regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="ec213-121">End users can't access quarantined malware, high confidence phishing or messages that were quarantined because of the **Deliver the message to the hosted quarantine** action in mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="ec213-122">Mer information om användare som använder meddelanden i karantän finns i [Hitta och släppa meddelanden i karantän som användare i Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="ec213-122">For more information about users accessing quarantined messages, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a><span data-ttu-id="ec213-123">F: Hur länge hålls meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="ec213-123">Q: How long are messages kept in the quarantine?</span></span>

<span data-ttu-id="ec213-124">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-124">A.</span></span> <span data-ttu-id="ec213-125">Du kan konfigurera hur länge skräppost, nätfiske och massmeddelanden hålls i karantän med hjälp av policyer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="ec213-125">You configure how long spam, phishing, and bulk email messages are kept in the quarantine by using anti-spam policies.</span></span> <span data-ttu-id="ec213-126">Standardvärdet är 30 dagar, vilket också är det maximala.</span><span class="sxs-lookup"><span data-stu-id="ec213-126">The default is 30 days, which is also the maximum.</span></span> <span data-ttu-id="ec213-127">Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ec213-127">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md)</span></span>

<span data-ttu-id="ec213-128">För meddelanden som har satts i karantän av e-postflödesregelåtgärden **Leverera meddelandet till den värdbaserade karantänen**hålls meddelandena i karantän i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="ec213-128">For messages that were quarantined by the mail flow rule action **Deliver the message to the hosted quarantine**, the messages are kept in quarantine for 30 days.</span></span> <span data-ttu-id="ec213-129">Du kan inte konfigurera den här varaktigheten.</span><span class="sxs-lookup"><span data-stu-id="ec213-129">You can't configure this duration.</span></span>

<span data-ttu-id="ec213-130">När tidsperioden har gått ut tas meddelandena bort och kan inte återställas.</span><span class="sxs-lookup"><span data-stu-id="ec213-130">After the time period expires, the messages are deleted and are not recoverable.</span></span>

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a><span data-ttu-id="ec213-131">F: Kan jag släppa eller rapportera mer än ett meddelande i karantän åt gången?</span><span class="sxs-lookup"><span data-stu-id="ec213-131">Q: Can I release or report more than one quarantined message at a time?</span></span>

<span data-ttu-id="ec213-132">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-132">A.</span></span> <span data-ttu-id="ec213-133">I Security & Compliance Center kan du välja och släppa upp till 100 meddelanden åt gången.</span><span class="sxs-lookup"><span data-stu-id="ec213-133">In the Security & Compliance Center, you can select and release up to 100 messages at a time.</span></span>

<span data-ttu-id="ec213-134">Administratörer kan använda cmdleterna [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) och [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) i Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att hitta och släppa meddelanden i karantän i grupp och för att rapportera falska positiva identifieringar i grupp.</span><span class="sxs-lookup"><span data-stu-id="ec213-134">Admins can use the the [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) and [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) cmdlets in Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to find and release quarantined messages in bulk, and to report false positives in bulk.</span></span>

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a><span data-ttu-id="ec213-135">F: Stöds jokertecken när du söker efter meddelanden i karantän?</span><span class="sxs-lookup"><span data-stu-id="ec213-135">Q: Are wildcards supported when searching for quarantined messages?</span></span> <span data-ttu-id="ec213-136">Kan jag söka efter meddelanden i karantän för en viss domän?</span><span class="sxs-lookup"><span data-stu-id="ec213-136">Can I search for quarantined messages for a specific domain?</span></span>

<span data-ttu-id="ec213-137">A.</span><span class="sxs-lookup"><span data-stu-id="ec213-137">A.</span></span> <span data-ttu-id="ec213-138">Jokertecken stöds inte i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="ec213-138">Wildcards aren't supported in the Security & Compliance Center.</span></span> <span data-ttu-id="ec213-139">När du till exempel söker efter en avsändare måste du ange den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="ec213-139">For example, when searching for a sender, you need to specify the full email address.</span></span> <span data-ttu-id="ec213-140">Men du kan använda jokertecken i Exchange Online PowerShell eller Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec213-140">But, you can use wildcards in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

<span data-ttu-id="ec213-141">Kör till exempel följande kommando för att hitta skräppostmeddelanden i karantän från alla avsändare i domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ec213-141">For example, run the following command to find spam quarantined messages from all senders in the domain contoso.com:</span></span>

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

<span data-ttu-id="ec213-142">Kör sedan följande kommando för att släppa dessa meddelanden till alla ursprungliga mottagare:</span><span class="sxs-lookup"><span data-stu-id="ec213-142">Then, run the following command to release those messages to all original recipients:</span></span>

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

<span data-ttu-id="ec213-143">När du har släppt ett meddelande kan du inte släppa det igen.</span><span class="sxs-lookup"><span data-stu-id="ec213-143">After you release a message, you can't release it again.</span></span>
