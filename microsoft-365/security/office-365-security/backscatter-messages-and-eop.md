---
title: Återspridning i EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om bakEOP och Microsoft Exchange Online Protection ()
ms.openlocfilehash: f1705fd7fc30c9a8cde5f6acfaf145861de3af08
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827791"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="80673-103">Återspridning i EOP</span><span class="sxs-lookup"><span data-stu-id="80673-103">Backscatter in EOP</span></span>

<span data-ttu-id="80673-104">*Bakgrunds rapporter som inte* kan levereras (kallas även NDR eller studsande meddelanden) som du får för meddelanden som du inte har skickat.</span><span class="sxs-lookup"><span data-stu-id="80673-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="80673-105">Skräp post Forge (förfalskningar) från: adress till sina meddelanden och använder ofta riktiga e-postadresser för att ge trovärdigheten till sina meddelanden.</span><span class="sxs-lookup"><span data-stu-id="80673-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="80673-106">Så när skräp post avsändare inte kan skicka meddelanden till icke befintliga mottagare (spam är en hög volym), är mål-e-postservern i huvudsak att returnera det icke-skickade meddelandet i en NDR till den förfalskade avsändaren i mappen från: adress.</span><span class="sxs-lookup"><span data-stu-id="80673-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="80673-107">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor gör EOP till att identifiera och tyst släppa meddelanden från Dubious källor utan att generera en NDR.</span><span class="sxs-lookup"><span data-stu-id="80673-107">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="80673-108">Men baserat på skir volym e-post som flödar via tjänsten är det alltid möjligt att EOP oavsiktligt skickar en bakgrunds bild.</span><span class="sxs-lookup"><span data-stu-id="80673-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="80673-109">Backscatterer.org bevarar en block lista (kallas även DNS-blockeringslistan eller DNSBL) av e-postservrar som är ansvariga för att skicka bakgrunds-och EOP servrar kan visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="80673-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="80673-110">Men det går inte att ta bort oss själva från Backscatterer.org-blockeringslistan eftersom det inte är en lista över skräp post avsändare (efter eget godkännande).</span><span class="sxs-lookup"><span data-stu-id="80673-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="80673-111">Backscatter.org webbplats ( <http://www.backscatterer.org/?target=usage> ) rekommenderar att den används för att kontrol lera inkommande e-post i fel säkert läge (stora e-posttjänster som nästan alltid skickar lite bakmatning).</span><span class="sxs-lookup"><span data-stu-id="80673-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
