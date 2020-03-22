---
title: Massklagomålsnivåvärden, massutskick, BCL-nivåer, hur BCL fungerar, BCL-klassificeringar, Antispam, Antispam-huvud, massutskicksfiltrering, stoppa massutskick
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Lär dig mer om BCL-värden (Bulk bomplain level) i Office 365.
ms.openlocfilehash: 6b90064db7dd9b27fdc729b65fb798dfbe756da7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895399"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a><span data-ttu-id="eb809-103">Massklagomålsnivå (BCL) i Office 365</span><span class="sxs-lookup"><span data-stu-id="eb809-103">Bulk complaint level (BCL) in Office 365</span></span>

<span data-ttu-id="eb809-104">Massutskicksutskick varierar i sina sändningsmönster, skapande av innehåll och rutiner för anskaffning av mottagare.</span><span class="sxs-lookup"><span data-stu-id="eb809-104">Bulk mailers vary in their sending patterns, content creation, and recipient acquisition practices.</span></span> <span data-ttu-id="eb809-105">Vissa är bra massutskick som skickar önskade meddelanden med relevant innehåll till sina prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="eb809-105">Some are good bulk mailers that send desired messages with relevant content to their subscribers.</span></span> <span data-ttu-id="eb809-106">Dessa meddelanden genererar få klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="eb809-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="eb809-107">Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="eb809-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span> <span data-ttu-id="eb809-108">Meddelanden från en massutskick kallas massutskick eller grå e-post.</span><span class="sxs-lookup"><span data-stu-id="eb809-108">Messages from a bulk mailer is known as bulk mail or gray mail.</span></span>

<span data-ttu-id="eb809-109">Om du vill skilja meddelanden från olika typer av massutskick tilldelas inkommande e-post från massutskick till Office 365 (Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor) en massklagomålsnivå (BCL) som läggs till i meddelandet i ett X-header.</span><span class="sxs-lookup"><span data-stu-id="eb809-109">To distinguish messages from different types of bulk mailers, inbound email from bulk mailers to Office 365 (Exchange Online or standalone Exchange Online Protection (EOP) without Exchange Online mailboxes) is assigned a bulk complaint level (BCL) that's added to the message in an X-header.</span></span> <span data-ttu-id="eb809-110">BCL liknar den nivå för [misstroendevotum (SCL)](spam-confidence-levels.md) som används för att identifiera meddelanden som skräppost.</span><span class="sxs-lookup"><span data-stu-id="eb809-110">The BCL is similar to the [spam confidence level (SCL)](spam-confidence-levels.md) that's used to identify messages as spam.</span></span> <span data-ttu-id="eb809-111">En högre BCL indikerar att ett massmeddelande är mer sannolikt att generera klagomål (och är därför mer sannolikt att vara spam).</span><span class="sxs-lookup"><span data-stu-id="eb809-111">A higher BCL indicates a bulk message is more likely to generate complaints (and is therefore more likely to be spam).</span></span> <span data-ttu-id="eb809-112">Microsoft använder både interna och tredje parts källor för att identifiera massutskick och fastställa lämplig BCL.</span><span class="sxs-lookup"><span data-stu-id="eb809-112">Microsoft uses both internal and third party sources to identify bulk mail and determine the appropriate BCL.</span></span>

 <span data-ttu-id="eb809-113">Skräppostfiltrering markerar meddelanden som **massmeddelande** baserat på BCL-tröskelvärdet (standardvärdet eller ett värde som du anger) och vidtar den angivna åtgärden i meddelandet (standardåtgärden levereras till mottagarens skräppostmapp).</span><span class="sxs-lookup"><span data-stu-id="eb809-113">Spam filtering marks messages as **Bulk email** based on the BCL threshold (the default value or a value you specify) and takes the specified action on the message (the default action is deliver the message to the recipient's Junk Email folder).</span></span> <span data-ttu-id="eb809-114">Mer information finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md) och Vad är skillnaden mellan skräppost och [massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span><span class="sxs-lookup"><span data-stu-id="eb809-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md) and [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md).</span></span>

<span data-ttu-id="eb809-115">BCL-tröskelvärdena beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="eb809-115">The BCL thresholds are described in the following table.</span></span>

|||
|:---:|---|
|<span data-ttu-id="eb809-116">**BCL**</span><span class="sxs-lookup"><span data-stu-id="eb809-116">**BCL**</span></span>|<span data-ttu-id="eb809-117">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="eb809-117">**Description**</span></span>|
|<span data-ttu-id="eb809-118">0</span><span class="sxs-lookup"><span data-stu-id="eb809-118">0</span></span>|<span data-ttu-id="eb809-119">Meddelandet kommer inte från en massavsändare.</span><span class="sxs-lookup"><span data-stu-id="eb809-119">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="eb809-120">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="eb809-120">1, 2, 3</span></span>|<span data-ttu-id="eb809-121">Meddelandet kommer från en massavsändare som genererar få klagomål.</span><span class="sxs-lookup"><span data-stu-id="eb809-121">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="eb809-122">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="eb809-122">4, 5, 6, 7</span></span>|<span data-ttu-id="eb809-123">Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="eb809-123">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="eb809-124">8, 9</span><span class="sxs-lookup"><span data-stu-id="eb809-124">8, 9</span></span>|<span data-ttu-id="eb809-125">Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="eb809-125">The message is from a bulk sender that generates a high number of complaints.</span></span>|
|
