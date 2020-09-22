---
title: Mass nivå värden för klagomål
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om värden för BCL (Mass Utjämnings nivå) som används i Exchange Online Protection (EOP).
ms.openlocfilehash: d59bb152de075bb807e3cae72839fe459d7da40f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203533"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="89589-103">Bulk klagomål (BCL) i EOP</span><span class="sxs-lookup"><span data-stu-id="89589-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="89589-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor tilldelar EOP ett Mass kompatibelt (BCL) för inkommande meddelanden från andra Mass utskick.</span><span class="sxs-lookup"><span data-stu-id="89589-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="89589-105">BCL läggs till i meddelandet i ett X-sidhuvud och liknar den [skräp nivå](spam-confidence-levels.md) som används för att identifiera meddelanden som skräp post.</span><span class="sxs-lookup"><span data-stu-id="89589-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="89589-106">Ett högre BCL tyder på att ett Mass meddelande är mer sannolikt att skapa klagomål (och därför är det mer sannolikt att få skräp post).</span><span class="sxs-lookup"><span data-stu-id="89589-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="89589-107">Microsoft använder både interna och tredje parts källor för att identifiera Mass utskick och fastställa lämpliga BCL.</span><span class="sxs-lookup"><span data-stu-id="89589-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="89589-108">Mass utskick är olika i deras skicka-och innehålls skapande och mottagnings rutiner.</span><span class="sxs-lookup"><span data-stu-id="89589-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="89589-109">Goda Mass utskick skickar önskade meddelanden till sina prenumeranter med relevant innehåll.</span><span class="sxs-lookup"><span data-stu-id="89589-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="89589-110">Dessa meddelanden genererar få klagomål från mottagarna.</span><span class="sxs-lookup"><span data-stu-id="89589-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="89589-111">Andra Mass utskick skickar oombedda meddelanden som liknar skräp posten och ger många klagomål från mottagarna.</span><span class="sxs-lookup"><span data-stu-id="89589-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="89589-112">Meddelanden från ett Mass utskick kallas Mass utskick och e-post.</span><span class="sxs-lookup"><span data-stu-id="89589-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="89589-113">Filtrering av skräp post markerar meddelanden som **Mass utskick** baserat på tröskelvärdet för BCL (standardvärdet eller ett värde som du anger) och utför den angivna åtgärden på meddelandet (standard åtgärden skickar meddelandet till mottagarens mapp för skräp post).</span><span class="sxs-lookup"><span data-stu-id="89589-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="89589-114">Mer information finns i [Konfigurera principer för skräp](configure-your-spam-filter-policies.md) post och [Vad är skillnaden mellan skräp post och Mass utskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="89589-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="89589-115">Tröskelvärdena för BCL beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="89589-115">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="89589-116">BCL</span><span class="sxs-lookup"><span data-stu-id="89589-116">BCL</span></span>|<span data-ttu-id="89589-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="89589-117">Description</span></span>|
|:---:|---|
|<span data-ttu-id="89589-118">siffrorna</span><span class="sxs-lookup"><span data-stu-id="89589-118">0</span></span>|<span data-ttu-id="89589-119">Meddelandet är inte från en Mass avsändare.</span><span class="sxs-lookup"><span data-stu-id="89589-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="89589-120">1; 2; 3</span><span class="sxs-lookup"><span data-stu-id="89589-120">1, 2, 3</span></span>|<span data-ttu-id="89589-121">Meddelandet kommer från en Mass avsändare som genererar några klagomål.</span><span class="sxs-lookup"><span data-stu-id="89589-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="89589-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="89589-122">4, 5, 6, 7</span></span>|<span data-ttu-id="89589-123">Meddelandet kommer från en Mass avsändare som genererar ett blandat antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="89589-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="89589-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="89589-124">8, 9</span></span>|<span data-ttu-id="89589-125">Meddelandet kommer från en Mass avsändare som genererar ett stort antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="89589-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
