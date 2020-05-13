---
title: Värden för massnivå för klagomål
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om BCL-värden (Bulk Compliance Level) som används i Exchange Online Protection (EOP).
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209613"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="c42fd-103">Massklagomålsnivå (BCL) i EOP</span><span class="sxs-lookup"><span data-stu-id="c42fd-103">Bulk complaint level (BCL) in EOP</span></span>

<span data-ttu-id="c42fd-104">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tilldelar EOP en masskompatibel nivå (BCL) till inkommande meddelanden från massutskick.</span><span class="sxs-lookup"><span data-stu-id="c42fd-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="c42fd-105">BCL läggs till i meddelandet i en X-header och liknar [den spam-konfidensnivå (SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="c42fd-105">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="c42fd-106">En högre BCL indikerar att ett massmeddelande är mer sannolikt att generera klagomål (och är därför mer sannolikt att vara spam).</span><span class="sxs-lookup"><span data-stu-id="c42fd-106">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="c42fd-107">Microsoft använder både interna och tredje parts källor för att identifiera massutskick och fastställa lämplig BCL.</span><span class="sxs-lookup"><span data-stu-id="c42fd-107">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="c42fd-108">Massutskicksutskick varierar i sina sändningsmönster, skapande av innehåll och rutiner för anskaffning av mottagare.</span><span class="sxs-lookup"><span data-stu-id="c42fd-108">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="c42fd-109">Bra massutskick skickar önskade meddelanden med relevant innehåll till sina prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="c42fd-109">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c42fd-110">Dessa meddelanden genererar få klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="c42fd-110">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c42fd-111">Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="c42fd-111">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="c42fd-112">Meddelanden från en massutskick kallas massutskick eller grå e-post.</span><span class="sxs-lookup"><span data-stu-id="c42fd-112">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="c42fd-113">Skräppostfiltrering markerar meddelanden som **massmeddelande** baserat på BCL-tröskelvärdet (standardvärdet eller ett värde som du anger) och vidtar den angivna åtgärden i meddelandet (standardåtgärden levereras till mottagarens skräppostmapp).</span><span class="sxs-lookup"><span data-stu-id="c42fd-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="c42fd-114">Mer information finns i [Konfigurera policyer mot skräppost](configure-your-spam-filter-policies.md) och Vad är skillnaden mellan skräppost och [massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="c42fd-114">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="c42fd-115">BCL-tröskelvärdena beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="c42fd-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="c42fd-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="c42fd-116">**BCL**</span></span>|<span data-ttu-id="c42fd-117">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="c42fd-117">**Description**</span></span>|
|<span data-ttu-id="c42fd-118">0</span><span class="sxs-lookup"><span data-stu-id="c42fd-118">0</span></span>|<span data-ttu-id="c42fd-119">Meddelandet kommer inte från en massavsändare.</span><span class="sxs-lookup"><span data-stu-id="c42fd-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c42fd-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c42fd-120">1, 2, 3</span></span>|<span data-ttu-id="c42fd-121">Meddelandet kommer från en massavsändare som genererar få klagomål.</span><span class="sxs-lookup"><span data-stu-id="c42fd-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c42fd-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="c42fd-122">4, 5, 6, 7</span></span>|<span data-ttu-id="c42fd-123">Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="c42fd-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c42fd-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="c42fd-124">8, 9</span></span>|<span data-ttu-id="c42fd-125">Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="c42fd-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
