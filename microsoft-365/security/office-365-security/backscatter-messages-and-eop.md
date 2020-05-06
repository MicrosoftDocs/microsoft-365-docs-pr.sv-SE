---
title: Backscatter och EOP
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
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om Backscatter och Microsoft Exchange Online Protection (EOP)
ms.openlocfilehash: 14460b75920b053461722b5a129d785fb6952a5a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035598"
---
# <a name="backscatter-and-eop"></a><span data-ttu-id="e38ee-103">Backscatter och EOP</span><span class="sxs-lookup"><span data-stu-id="e38ee-103">Backscatter and EOP</span></span>

<span data-ttu-id="e38ee-104">*Backscatter* är rapporter som inte är leveransrapporter (kallas även NDRs eller avstudsmeddelanden) som du får för meddelanden som du inte har skickat.</span><span class="sxs-lookup"><span data-stu-id="e38ee-104">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="e38ee-105">Spammare smida (parodi) Från: adressen till sina meddelanden, och de använder ofta riktiga e-postadresser för att ge trovärdighet åt sina meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e38ee-105">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="e38ee-106">Så, när spammare oundvikligen skicka meddelanden till icke-existerande mottagare (spam är en hög volym operation), destinationen e-postservern är i huvudsak luras att returnera det olevererbara meddelandet i en NDR till förfalskade avsändaren i Från: adress.</span><span class="sxs-lookup"><span data-stu-id="e38ee-106">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="e38ee-107">Exchange Online Protection (EOP) gör allt för att identifiera och tyst släppa meddelanden från tvivelaktiga källor utan att generera en NDR.</span><span class="sxs-lookup"><span data-stu-id="e38ee-107">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="e38ee-108">Men, baserat på den stora volymen e-post som flyter genom tjänsten, det finns alltid möjligheten att EOP oavsiktligt kommer att skicka tillbakascatter.</span><span class="sxs-lookup"><span data-stu-id="e38ee-108">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="e38ee-109">Backscatterer.org upprätthåller en blockeringslista (kallas även DNS-blocklista eller DNSBL) för e-postservrar som var ansvariga för att skicka tillbakascatter, och EOP-servrar kan visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="e38ee-109">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="e38ee-110">Men vi försöker inte ta bort oss själva från Backscatterer.org blocklistan eftersom det inte är en lista över spammare (enligt deras egen entré).</span><span class="sxs-lookup"><span data-stu-id="e38ee-110">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="e38ee-111">Den Backscatter.org webbplats (<http://www.backscatterer.org/?target=usage>) rekommenderar att du använder sin tjänst för att kontrollera inkommande e-post i felsäkert läge istället för Avvisa-läge (stora e-posttjänster nästan alltid skicka några backscatter).</span><span class="sxs-lookup"><span data-stu-id="e38ee-111">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
