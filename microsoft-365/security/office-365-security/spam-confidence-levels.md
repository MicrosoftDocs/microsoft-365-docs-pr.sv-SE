---
title: Nivåer för förtroende för skräppost
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: När ett e-postmeddelande går igenom skräppostfiltrering tilldelas det en spam-poäng. Den poängen mappas till en individuell SCL-klassificering (Spam Confidence Level) och stämplas i en X-header. Tjänsten vidtar åtgärder på meddelandena beroende på spam förtroende tolkning av SCL rating. I följande tabell visas hur de olika SCL-klassificeringarna tolkas av filtren och standardåtgärden som vidtas för inkommande meddelanden för varje klassificering.
ms.openlocfilehash: 65b6f51199e6d8f6ce17a05b28c5bad15d9d1760
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806473"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="54d84-106">Nivåer för förtroende för skräppost</span><span class="sxs-lookup"><span data-stu-id="54d84-106">Spam confidence levels</span></span>

<span data-ttu-id="54d84-107">När ett e-postmeddelande går igenom skräppostfiltrering tilldelas det en spam-poäng.</span><span class="sxs-lookup"><span data-stu-id="54d84-107">When an email message goes through spam filtering it is assigned a spam score.</span></span> <span data-ttu-id="54d84-108">Den poängen mappas till en individuell SCL-klassificering (Spam Confidence Level) och stämplas i en X-header.</span><span class="sxs-lookup"><span data-stu-id="54d84-108">That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header.</span></span> <span data-ttu-id="54d84-109">Tjänsten vidtar åtgärder på meddelandena beroende på spam förtroende tolkning av SCL rating.</span><span class="sxs-lookup"><span data-stu-id="54d84-109">The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating.</span></span> <span data-ttu-id="54d84-110">I följande tabell visas hur de olika SCL-klassificeringarna tolkas av filtren och standardåtgärden som vidtas för inkommande meddelanden för varje klassificering.</span><span class="sxs-lookup"><span data-stu-id="54d84-110">The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="54d84-111">**SCL-klassificering**</span><span class="sxs-lookup"><span data-stu-id="54d84-111">**SCL Rating**</span></span>|<span data-ttu-id="54d84-112">**Tolkning av spamförtroende**</span><span class="sxs-lookup"><span data-stu-id="54d84-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="54d84-113">**Standardåtgärd**</span><span class="sxs-lookup"><span data-stu-id="54d84-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="54d84-114">-1</span><span class="sxs-lookup"><span data-stu-id="54d84-114">-1</span></span>|<span data-ttu-id="54d84-115">Icke-spam som kommer från en säker avsändare, säker mottagare eller säker IP-adress (betrodd partner).</span><span class="sxs-lookup"><span data-stu-id="54d84-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="54d84-116">Leverera meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="54d84-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="54d84-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="54d84-117">0, 1</span></span>|<span data-ttu-id="54d84-118">Icke-spam eftersom meddelandet skannades och bestämdes vara ren.</span><span class="sxs-lookup"><span data-stu-id="54d84-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="54d84-119">Leverera meddelandet till mottagarnas inkorg.</span><span class="sxs-lookup"><span data-stu-id="54d84-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="54d84-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="54d84-120">5, 6</span></span>|<span data-ttu-id="54d84-121">Spam</span><span class="sxs-lookup"><span data-stu-id="54d84-121">Spam</span></span>|<span data-ttu-id="54d84-122">Leverera meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="54d84-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="54d84-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="54d84-123">7, 8, 9</span></span>|<span data-ttu-id="54d84-124">Högt förtroende spam</span><span class="sxs-lookup"><span data-stu-id="54d84-124">High confidence spam</span></span>|<span data-ttu-id="54d84-125">Leverera meddelandet till mottagarnas skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="54d84-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="54d84-126">SCL-klassificeringar på 2, 3, 4, 7 och 8 ställs inte in av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="54d84-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="54d84-127">En SCL rating på 5 eller 6 anses misstänkt spam, vilket är mindre säkert att vara spam än en SCL rating 9, som anses vara vissa spam.</span><span class="sxs-lookup"><span data-stu-id="54d84-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="54d84-128">Olika åtgärder för skräppost och skräppost med hög säkerhet kan konfigureras via dina innehållsfilterprinciper i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="54d84-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="54d84-129">Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="54d84-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="54d84-130">Du kan också ange SCL-klassificering för meddelanden som matchar specifika villkor med hjälp av regler för e-postflöde (kallas även transportregler), enligt beskrivningen i [Använd regler för e-postflöde för att ställa in förtroendenivån för skräppost i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="54d84-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="54d84-131">Om du använder en e-postflödesregel för att ställa in SCL på 7, 8 eller 9 kommer meddelandet att behandlas som skräppost med högt förtroende.</span><span class="sxs-lookup"><span data-stu-id="54d84-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="54d84-132">![Den korta ikonen för](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New till Office 365?**</span><span class="sxs-lookup"><span data-stu-id="54d84-132">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**</span></span>         <span data-ttu-id="54d84-133">Upptäck kostnadsfria videokurser för **Office 365-administratörer och IT-proffs**som kommer till dig genom LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="54d84-133">Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

