---
title: Värden på nivå med massklagomål
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
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om BCL-värden (Massefterlevnadsnivå) som används i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d85dca6e18ebdad4d8f2a5c5f6c5b613c23b47d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207028"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a><span data-ttu-id="913af-103">Nivå för mass klagomål (BCL) i EOP</span><span class="sxs-lookup"><span data-stu-id="913af-103">Bulk complaint level (BCL) in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="913af-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="913af-104">**Applies to**</span></span>
- [<span data-ttu-id="913af-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="913af-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="913af-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="913af-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="913af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="913af-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="913af-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, tilldelar EOP en BCL-nivå (Bulk compliant Level) till inkommande meddelanden från massutskick.</span><span class="sxs-lookup"><span data-stu-id="913af-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP assigns a bulk compliant level (BCL) to inbound messages from bulk mailers.</span></span> <span data-ttu-id="913af-109">BCL läggs till i meddelandet i ett X-sidhuvud och liknar konfidensnivån för skräppost [(SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="913af-109">The BCL is added to the message in an X-header and is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="913af-110">Om ett större BCL-tecken anges är det mer sannolikt att ett massmeddelande skapar klagomål (och därför är det troligare att det är skräppost).</span><span class="sxs-lookup"><span data-stu-id="913af-110">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="913af-111">Microsoft använder både interna och tredjepartskällor för att identifiera massutskick och fastställa lämplig BCL.</span><span class="sxs-lookup"><span data-stu-id="913af-111">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

<span data-ttu-id="913af-112">Massutskick varierar vad gäller deras metoder för att skicka, skapa innehåll och mottagarköp.</span><span class="sxs-lookup"><span data-stu-id="913af-112">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="913af-113">Bra massutskick skickar önskade meddelanden med relevant innehåll till prenumeranterna.</span><span class="sxs-lookup"><span data-stu-id="913af-113">Good bulk mailers send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="913af-114">Dessa meddelanden genererar få klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="913af-114">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="913af-115">Andra massutskick skickar oönskade meddelanden som liknar skräppost och skapar många klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="913af-115">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="913af-116">Meddelanden från en massutskick kallas massutskick eller grå e-post.</span><span class="sxs-lookup"><span data-stu-id="913af-116">Messages from a bulk mailer are known as bulk mail or gray mail.</span></span>

 <span data-ttu-id="913af-117">Skräppostfiltrering  markerar meddelanden som Massutskick baserat på BCL-tröskelvärdet (standardvärdet eller ett värde som du anger) och vidtar den angivna åtgärden för meddelandet (standardåtgärden är att leverera meddelandet till mottagarens skräppostmapp).</span><span class="sxs-lookup"><span data-stu-id="913af-117">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="913af-118">Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md) [och Vad är skillnaden mellan skräppost och massutskick?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span><span class="sxs-lookup"><span data-stu-id="913af-118">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md)</span></span>

<span data-ttu-id="913af-119">BCL-tröskelvärdena beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="913af-119">The BCL thresholds are described in the following table.</span></span>

****

|<span data-ttu-id="913af-120">BCL</span><span class="sxs-lookup"><span data-stu-id="913af-120">BCL</span></span>|<span data-ttu-id="913af-121">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="913af-121">Description</span></span>|
|:---:|---|
|<span data-ttu-id="913af-122">0</span><span class="sxs-lookup"><span data-stu-id="913af-122">0</span></span>|<span data-ttu-id="913af-123">Meddelandet kommer inte från en massavsändare.</span><span class="sxs-lookup"><span data-stu-id="913af-123">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="913af-124">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="913af-124">1, 2, 3</span></span>|<span data-ttu-id="913af-125">Meddelandet kommer från en massavsändare som genererar få klagomål.</span><span class="sxs-lookup"><span data-stu-id="913af-125">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="913af-126">4, 5, 6, 7<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="913af-126">4, 5, 6, 7<sup>\*</sup></span></span>|<span data-ttu-id="913af-127">Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="913af-127">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="913af-128">8, 9</span><span class="sxs-lookup"><span data-stu-id="913af-128">8, 9</span></span>|<span data-ttu-id="913af-129">Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="913af-129">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|

<span data-ttu-id="913af-130"><sup>\*</sup> Det här är det standardtröskelvärde som används i principer mot skräppost.</span><span class="sxs-lookup"><span data-stu-id="913af-130"><sup>\*</sup> This is the default threshold value that's used in anti-spam policies.</span></span>
