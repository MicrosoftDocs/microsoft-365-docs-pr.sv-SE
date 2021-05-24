---
title: Konfidensnivå för skräppost
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om konfidensnivån för skräppost (SCL) som används för meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55e64c72cc472e98baa8eb71e23dafb6b276ba01
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625287"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="f3185-103">SCL (Spam Confidence Level) i EOP</span><span class="sxs-lookup"><span data-stu-id="f3185-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="f3185-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f3185-104">**Applies to**</span></span>
- [<span data-ttu-id="f3185-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f3185-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f3185-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f3185-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f3185-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3185-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3185-108">I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, används filtrering av inkommande meddelanden i EOP och tilldelas en poäng för skräppost.</span><span class="sxs-lookup"><span data-stu-id="f3185-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="f3185-109">Poängen mappas till en enskild SCL-nivå (Spam Confidence Level) som läggs till i meddelandet i ett X-sidhuvud.</span><span class="sxs-lookup"><span data-stu-id="f3185-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="f3185-110">Ett högre SCL-tecken anger att ett meddelande är mer troligt som skräppost.</span><span class="sxs-lookup"><span data-stu-id="f3185-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="f3185-111">EOP vidtar åtgärder på meddelandet baserat på SCL.</span><span class="sxs-lookup"><span data-stu-id="f3185-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="f3185-112">Vad SCL innebär och de standardåtgärder som vidtas på meddelanden beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="f3185-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="f3185-113">Mer information om åtgärder du kan vidta på meddelanden baserat på skräppostfiltrering av bedömning finns i Konfigurera principer för skydd mot [skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f3185-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="f3185-114">SCL</span><span class="sxs-lookup"><span data-stu-id="f3185-114">SCL</span></span>|<span data-ttu-id="f3185-115">Definition</span><span class="sxs-lookup"><span data-stu-id="f3185-115">Definition</span></span>|<span data-ttu-id="f3185-116">Standardåtgärd</span><span class="sxs-lookup"><span data-stu-id="f3185-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="f3185-117">-1</span><span class="sxs-lookup"><span data-stu-id="f3185-117">-1</span></span>|<span data-ttu-id="f3185-118">Meddelandet hoppade över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="f3185-118">The message skipped spam filtering.</span></span> <span data-ttu-id="f3185-119">Meddelandet kommer till exempel från en betrodd avsändare, har skickats till en betrodd mottagare eller kommer från en server för e-postkälla på listan över tillåtna IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="f3185-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="f3185-120">Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f3185-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="f3185-121">Skicka meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="f3185-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f3185-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="f3185-122">0, 1</span></span>|<span data-ttu-id="f3185-123">Filtrering av skräppost gjorde att meddelandet inte var skräppost.</span><span class="sxs-lookup"><span data-stu-id="f3185-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="f3185-124">Skicka meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="f3185-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="f3185-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="f3185-125">5, 6</span></span>|<span data-ttu-id="f3185-126">Skräppostfiltrering markerade meddelandet som **skräppost**</span><span class="sxs-lookup"><span data-stu-id="f3185-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="f3185-127">Skicka meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="f3185-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="f3185-128">9</span><span class="sxs-lookup"><span data-stu-id="f3185-128">9</span></span>|<span data-ttu-id="f3185-129">Skräppostfiltrering markerade meddelandet som **Skräppost med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="f3185-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="f3185-130">Skicka meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="f3185-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="f3185-131">Du kommer att märka att SCL 2, 3, 4, 7 och 8 inte används genom skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="f3185-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="f3185-132">Du kan använda e-postflödesregler (kallas även transportregler) för att stämpla SCL på meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f3185-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="f3185-133">Om du använder en e-postflödesregel för att ange SCL utlöser värdena 5 eller 6 filtreringsåtgärden för **skräppost,** och värdena 7, 8 eller 9 utlöser skräppostfiltrering för skräppost med hög konfidens. </span><span class="sxs-lookup"><span data-stu-id="f3185-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="f3185-134">Mer information finns i Använda [e-postflödesregler för att ange SCL (Spam Confidence Level) i meddelanden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)</span><span class="sxs-lookup"><span data-stu-id="f3185-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl).</span></span>

<span data-ttu-id="f3185-135">På ungefär samma sätt som SCL identifierar BCL (Bulk Complaint Level) felaktig massutskick av e-post (kallas även _gråskala)._</span><span class="sxs-lookup"><span data-stu-id="f3185-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="f3185-136">En högre BCL anger att ett Mass utskick innebär att det är mer troligt att vi skapar klagomål (och är därför förmodligen mer sannolikt att få skräp post).</span><span class="sxs-lookup"><span data-stu-id="f3185-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="f3185-137">Du konfigurerar BCL-tröskelvärdet i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="f3185-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="f3185-138">Mer information finns i Konfigurera principer för skräppostskydd i [EOP,](configure-your-spam-filter-policies.md) [BCL (Bulk complaint level)](bulk-complaint-level-values.md)i EOP och Vad är skillnaden mellan skräppost och massutskick? [](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="f3185-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="f3185-139">![Den korta ikonen för LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **är nytt för Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="f3185-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="f3185-140">Upptäck kostnadsfria videokurser **för Microsoft 365 administratörer och IT-proffs**, från LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="f3185-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
