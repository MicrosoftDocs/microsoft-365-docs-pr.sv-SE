---
title: Säkerhets nivån för skräp post
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om säkerhets nivån för skräp post (SCL) som tillämpas på meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: fbd892b0171cee71f516d7ca3b26b91da664af79
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202239"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="586d6-103">Säkerhets nivån för skräp post (SCL) i EOP</span><span class="sxs-lookup"><span data-stu-id="586d6-103">Spam confidence level (SCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="586d6-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor flyttas inkommande meddelanden via skräp post filtrering i EOP och har tilldelats ett skräp inlägg.</span><span class="sxs-lookup"><span data-stu-id="586d6-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="586d6-105">Den poängen mappas till en enskild skräp konfidensnivå (SCL) som läggs till i meddelandet i ett X-sidhuvud.</span><span class="sxs-lookup"><span data-stu-id="586d6-105">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="586d6-106">Ett högre SCL anger att ett meddelande är mer troligt för skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-106">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="586d6-107">EOP åtgärdar meddelande baserat på SCL.</span><span class="sxs-lookup"><span data-stu-id="586d6-107">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="586d6-108">Vad SCL betyder och vilka standard åtgärder som utförs på meddelanden beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="586d6-108">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="586d6-109">Mer information om vilka åtgärder du kan vidta på meddelanden baserat på Verdict för skräp post filtrering finns i [Konfigurera principer för skräp post hantering i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="586d6-109">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="586d6-110">SCL</span><span class="sxs-lookup"><span data-stu-id="586d6-110">SCL</span></span>|<span data-ttu-id="586d6-111">Definition</span><span class="sxs-lookup"><span data-stu-id="586d6-111">Definition</span></span>|<span data-ttu-id="586d6-112">Standard åtgärd</span><span class="sxs-lookup"><span data-stu-id="586d6-112">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="586d6-113">-1</span><span class="sxs-lookup"><span data-stu-id="586d6-113">-1</span></span>|<span data-ttu-id="586d6-114">Meddelandet hoppade över skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="586d6-114">The message skipped spam filtering.</span></span> <span data-ttu-id="586d6-115">Meddelandet kommer till exempel från en säker avsändare, skickades till en säker mottagare eller från en e-postserver i listan över tillåtna IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="586d6-115">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="586d6-116">Mer information finns i [skapa säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="586d6-116">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="586d6-117">Skicka meddelandet till mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="586d6-117">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="586d6-118">0, 1</span><span class="sxs-lookup"><span data-stu-id="586d6-118">0, 1</span></span>|<span data-ttu-id="586d6-119">Filtrering av skräp post avgjorde meddelandet skickades inte skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-119">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="586d6-120">Skicka meddelandet till mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="586d6-120">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="586d6-121">5,0</span><span class="sxs-lookup"><span data-stu-id="586d6-121">5, 6</span></span>|<span data-ttu-id="586d6-122">Skräp post filtrering markerade meddelandet som **skräp post**</span><span class="sxs-lookup"><span data-stu-id="586d6-122">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="586d6-123">Skicka meddelandet till mottagarens mapp för skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-123">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="586d6-124">9</span><span class="sxs-lookup"><span data-stu-id="586d6-124">9</span></span>|<span data-ttu-id="586d6-125">Skräp post filtrering markerat meddelandet som **skräp post**</span><span class="sxs-lookup"><span data-stu-id="586d6-125">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="586d6-126">Skicka meddelandet till mottagarens mapp för skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-126">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="586d6-127">Du märker att SCL 2, 3, 4, 7 och 8 inte används för filtrering av skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-127">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="586d6-128">Du kan använda regler för e-postflöde (kallas även transport regler) för att stämpla SCL på meddelanden.</span><span class="sxs-lookup"><span data-stu-id="586d6-128">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="586d6-129">Om du använder en regel för e-post för att ange SCL utlöser värdena 5 eller 6 skräp post filtrerings åtgärden för **skräp post**och värdena 7, 8 och 9 utlöser skräp post filtrerings åtgärden för **skräp post**filter.</span><span class="sxs-lookup"><span data-stu-id="586d6-129">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="586d6-130">Mer information finns i [använda regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="586d6-130">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="586d6-131">På samma sätt som i SCL (BCL) identifieras dåligt Mass utskick (kallas även _grå e-post_).</span><span class="sxs-lookup"><span data-stu-id="586d6-131">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="586d6-132">En högre BCL anger att ett Mass utskick innebär att det är mer troligt att vi skapar klagomål (och är därför förmodligen mer sannolikt att få skräp post).</span><span class="sxs-lookup"><span data-stu-id="586d6-132">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="586d6-133">Du konfigurerar tröskelvärdet för BCL i principer för skräp post.</span><span class="sxs-lookup"><span data-stu-id="586d6-133">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="586d6-134">Mer information finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md), [bulk klagomål (BCL) i EOP)](bulk-complaint-level-values.md)och [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="586d6-134">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

|<!-- -->|
|---|
|<span data-ttu-id="586d6-135">![Kort ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **som är ny för Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="586d6-135">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="586d6-136">Upptäck kostnads fria video kurser för **Microsoft 365-administratörer och IT-proffs**, som du kommer åt via LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="586d6-136">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
