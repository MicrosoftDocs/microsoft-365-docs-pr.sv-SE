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
description: Administratörer kan lära sig mer om nivån för skräppostförtroende (SCL) som gäller för meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167161"
---
# <a name="spam-confidence-level-scl-in-eop"></a><span data-ttu-id="756db-103">SCL (Spam Confidence Level) i EOP</span><span class="sxs-lookup"><span data-stu-id="756db-103">Spam confidence level (SCL) in EOP</span></span>

<span data-ttu-id="756db-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="756db-104">**Applies to**</span></span>
- [<span data-ttu-id="756db-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="756db-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="756db-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="756db-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="756db-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="756db-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="756db-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tilldelas inkommande meddelanden skräppostfiltrering i EOP och tilldelas ett skräppostresultat.</span><span class="sxs-lookup"><span data-stu-id="756db-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound messages go through spam filtering in EOP and are assigned a spam score.</span></span> <span data-ttu-id="756db-109">Poängen mappas till en enskild nivå för skräppostförtroende (SCL) som läggs till i meddelandet i ett X-sidhuvud.</span><span class="sxs-lookup"><span data-stu-id="756db-109">That score is mapped to an individual spam confidence level (SCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="756db-110">Ett högre SCL-tecken anger att ett meddelande är mer troligt att det är skräppost.</span><span class="sxs-lookup"><span data-stu-id="756db-110">A higher SCL indicates a message is more likely to be spam.</span></span> <span data-ttu-id="756db-111">EOP vidtar åtgärder för meddelandet baserat på SCL.</span><span class="sxs-lookup"><span data-stu-id="756db-111">EOP takes action on the message based on the SCL.</span></span>

<span data-ttu-id="756db-112">Vad SCL innebär och standardåtgärderna som vidtas på meddelanden beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="756db-112">What the SCL means and the default actions that are taken on messages are described in the following table.</span></span> <span data-ttu-id="756db-113">Mer information om åtgärder du kan vidta på meddelanden baserat på skräppostfiltreringens bedömning finns i Konfigurera principer för skydd mot [skräppost i EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="756db-113">For more information about actions you can take on messages based on the spam filtering verdict, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

****

|<span data-ttu-id="756db-114">SCL</span><span class="sxs-lookup"><span data-stu-id="756db-114">SCL</span></span>|<span data-ttu-id="756db-115">Definition</span><span class="sxs-lookup"><span data-stu-id="756db-115">Definition</span></span>|<span data-ttu-id="756db-116">Standardåtgärd</span><span class="sxs-lookup"><span data-stu-id="756db-116">Default action</span></span>|
|:---:|---|---|
|<span data-ttu-id="756db-117">-1</span><span class="sxs-lookup"><span data-stu-id="756db-117">-1</span></span>|<span data-ttu-id="756db-118">Meddelandet hoppade över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="756db-118">The message skipped spam filtering.</span></span> <span data-ttu-id="756db-119">Meddelandet kommer till exempel från en betrodd avsändare, har skickats till en betrodd mottagare eller kommer från en e-postkälla på listan över tillåtna IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="756db-119">For example, the message is from a safe sender, was sent to a safe recipient, or is from an email source server on the IP Allow List.</span></span> <span data-ttu-id="756db-120">Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="756db-120">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>|<span data-ttu-id="756db-121">Skicka meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="756db-121">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="756db-122">0, 1</span><span class="sxs-lookup"><span data-stu-id="756db-122">0, 1</span></span>|<span data-ttu-id="756db-123">Skräppostfiltreringen gjorde att meddelandet inte var skräppost.</span><span class="sxs-lookup"><span data-stu-id="756db-123">Spam filtering determined the message was not spam.</span></span>|<span data-ttu-id="756db-124">Skicka meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="756db-124">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="756db-125">5, 6</span><span class="sxs-lookup"><span data-stu-id="756db-125">5, 6</span></span>|<span data-ttu-id="756db-126">Skräppostfiltrering har markerat meddelandet som **skräppost**</span><span class="sxs-lookup"><span data-stu-id="756db-126">Spam filtering marked the message as **Spam**</span></span>|<span data-ttu-id="756db-127">Leverera meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="756db-127">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="756db-128">9</span><span class="sxs-lookup"><span data-stu-id="756db-128">9</span></span>|<span data-ttu-id="756db-129">Skräppostfiltrering markerade meddelandet som **skräppost med hög konfidens**</span><span class="sxs-lookup"><span data-stu-id="756db-129">Spam filtering marked the message as **High confidence spam**</span></span>|<span data-ttu-id="756db-130">Leverera meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="756db-130">Deliver the message to the recipients' Junk Email folder.</span></span>|
|

<span data-ttu-id="756db-131">Du kommer att märka att SCL 2, 3, 4, 7 och 8 inte används av skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="756db-131">You'll notice that SCL 2, 3, 4, 7, and 8 aren't used by spam filtering.</span></span>

<span data-ttu-id="756db-132">Du kan använda e-postflödesregler (kallas även transportregler) för att stämpla SCL på meddelanden.</span><span class="sxs-lookup"><span data-stu-id="756db-132">You can use mail flow rules (also known as transport rules) to stamp the SCL on messages.</span></span> <span data-ttu-id="756db-133">Om du använder en e-postflödesregel för att ange SCL utlöser värdena 5 eller 6 skräppostfiltreringen för skräppost, och värdena 7, 8 eller 9 utlöser skräppostfiltreringsåtgärden för skräppost med hög konfidens. </span><span class="sxs-lookup"><span data-stu-id="756db-133">If you use a mail flow rule to set the SCL, the values 5 or 6 trigger the spam filtering action for **Spam**, and the values 7, 8, or 9 trigger the spam filtering action for **High confidence spam**.</span></span> <span data-ttu-id="756db-134">Mer information finns i Använda [e-postflödesregler för att ange](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)nivån för skräppostförtroende (SCL) i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="756db-134">For more information, see [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="756db-135">På liknande sätt som SCL identifierar gruppklagomålsnivån (BCL) felaktig massutskick (kallas även _grå_ post).</span><span class="sxs-lookup"><span data-stu-id="756db-135">Similar to the SCL, the bulk complaint level (BCL) identifies bad bulk email (also known as _gray mail_).</span></span> <span data-ttu-id="756db-136">En högre BCL anger att ett Mass utskick innebär att det är mer troligt att vi skapar klagomål (och är därför förmodligen mer sannolikt att få skräp post).</span><span class="sxs-lookup"><span data-stu-id="756db-136">A higher BCL indicates a bulk mail message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="756db-137">Du konfigurerar BCL-tröskelvärdet i principer för skydd mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="756db-137">You configure the BCL threshold in anti-spam policies.</span></span> <span data-ttu-id="756db-138">Mer information finns i Konfigurera principer för skräppostskydd i [EOP,](configure-your-spam-filter-policies.md)Nivå för gruppklagomål [(BCL)](bulk-complaint-level-values.md)i EOP och Vad är skillnaden mellan skräppost och [massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="756db-138">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md), [Bulk complaint level (BCL) in EOP)](bulk-complaint-level-values.md), and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

****

<span data-ttu-id="756db-139">![Den korta ikonen för LinkedIn ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Learning, ny för Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="756db-139">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?**</span></span> <span data-ttu-id="756db-140">Upptäck kostnadsfria videokurser **för Microsoft 365-administratörer och IT-proffs** från LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="756db-140">Discover free video courses for **Microsoft 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>
