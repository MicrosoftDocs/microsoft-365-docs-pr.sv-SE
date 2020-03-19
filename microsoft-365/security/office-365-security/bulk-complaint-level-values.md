---
title: Värden på massklagomålsnivå, massutskick, BCL-nivåer, hur BCL fungerar, BCL-klassificeringar, Antispam, Antispam-huvud, massfiltrering av e-post, stoppa massutskick
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
description: Läs mer om BCL-värden (Mass Complain Level) i Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807945"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="b2683-103">Värden på massklagomålsnivå</span><span class="sxs-lookup"><span data-stu-id="b2683-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="b2683-104">Massanvändare varierar i sina sändningsmönster, innehållsskapande och listförvärvsmetoder.</span><span class="sxs-lookup"><span data-stu-id="b2683-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="b2683-105">Vissa är bra bulk användare som skickar önskade meddelanden med relevant innehåll till sina abonnenter.</span><span class="sxs-lookup"><span data-stu-id="b2683-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="b2683-106">Dessa meddelanden genererar få klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="b2683-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="b2683-107">Andra massutskick skickar oönskade meddelanden som liknar skräppost och genererar många klagomål från mottagare.</span><span class="sxs-lookup"><span data-stu-id="b2683-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="b2683-108">Om du vill särskilja dessa typer av massutskick tilldelas meddelanden från massanvändare en BCL-klassificering (Bulk Complaint Level).</span><span class="sxs-lookup"><span data-stu-id="b2683-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="b2683-109">BCL betyg varierar från 1 till 9 beroende på hur sannolikt bulk mailer är att generera klagomål.</span><span class="sxs-lookup"><span data-stu-id="b2683-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="b2683-110">En avsändare som har ett betyg på BCL 9 kommer sannolikt att generera många klagomål från mottagare, medan en rating på BCL 3 är osannolikt att generera många klagomål.</span><span class="sxs-lookup"><span data-stu-id="b2683-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="b2683-111">Microsoft använder både interna och tredje parts källor för att identifiera massutskick och bestämma lämplig BCL.</span><span class="sxs-lookup"><span data-stu-id="b2683-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="b2683-112">Mer information om det här meddelandehuvudet finns i [Anti-spam-meddelanderubriker](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="b2683-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="b2683-113">Eftersom en massutskicksutskick med en rating på 9 sannolikt kommer att generera klagomål, är standard BCL 7.</span><span class="sxs-lookup"><span data-stu-id="b2683-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="b2683-114">Detta innebär att bulk post kommer att accepteras tills klagomålet nivå 7 och post kommer inte att accepteras därefter.</span><span class="sxs-lookup"><span data-stu-id="b2683-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="b2683-115">Ju lägre betyg, desto mindre bulk post accepteras.</span><span class="sxs-lookup"><span data-stu-id="b2683-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="b2683-116">Om användarna är, och deras arbete är, känslig för massutskick och din BCL är inställd på 4, kommer ingen masspost med en högre BCL än 4 att accepteras.</span><span class="sxs-lookup"><span data-stu-id="b2683-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="b2683-117">Du kan använda BCL-värden för att ange önskad nivå för massfiltrering som organisationen kräver genom att följa stegen i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2683-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="b2683-118">I följande tabell beskrivs de BCL-värden som används för närvarande.</span><span class="sxs-lookup"><span data-stu-id="b2683-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b2683-119">**BCL-värde**</span><span class="sxs-lookup"><span data-stu-id="b2683-119">**BCL Value**</span></span>|<span data-ttu-id="b2683-120">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="b2683-120">**Description**</span></span>|
|<span data-ttu-id="b2683-121">0</span><span class="sxs-lookup"><span data-stu-id="b2683-121">0</span></span>|<span data-ttu-id="b2683-122">Meddelandet kommer inte från en massavsändare.</span><span class="sxs-lookup"><span data-stu-id="b2683-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="b2683-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="b2683-123">1, 2, 3</span></span>|<span data-ttu-id="b2683-124">Meddelandet kommer från en massavsändare som genererar få klagomål.</span><span class="sxs-lookup"><span data-stu-id="b2683-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="b2683-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="b2683-125">4, 5, 6, 7</span></span>|<span data-ttu-id="b2683-126">Meddelandet kommer från en massavsändare som genererar ett blandat antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="b2683-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="b2683-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="b2683-127">8, 9</span></span>|<span data-ttu-id="b2683-128">Meddelandet kommer från en massavsändare som genererar ett stort antal klagomål.</span><span class="sxs-lookup"><span data-stu-id="b2683-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
