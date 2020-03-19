---
title: Meddelanden på grund av bakåtspridning och EOP
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
description: Backscatter-meddelanden är automatiska avvisningsmeddelanden som skickas till förfalskade e-postadresser. Backscatterer DNSBL identifierar servrar som skickar återspridningsmeddelanden (som kan innehålla många legitima e-postkällor). Eftersom det inte är en spammare lista, försöker vi inte ta bort oss från Backscatterer DNSBL.
ms.openlocfilehash: 20ed828680dd20e82819730e6dcd509b896d8616
ms.sourcegitcommit: 1b1425142ae06deae3da10a7d30dce4db029d6d3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42808114"
---
# <a name="backscatter-messages-and-eop"></a><span data-ttu-id="18e73-105">Meddelanden på grund av bakåtspridning och EOP</span><span class="sxs-lookup"><span data-stu-id="18e73-105">Backscatter messages and EOP</span></span>

<span data-ttu-id="18e73-106">*Backscatter-meddelanden* är rapporter som inte levereras (kallas även NDR:er eller avvisningsmeddelanden) som du får för meddelanden som du inte har skickat.</span><span class="sxs-lookup"><span data-stu-id="18e73-106">*Backscatter messages* are non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="18e73-107">Spammare smider (parodi) från: adress till sina meddelanden, och de använder ofta riktiga e-postadresser för att ge trovärdighet åt sina meddelanden.</span><span class="sxs-lookup"><span data-stu-id="18e73-107">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="18e73-108">Så, när en spammare oundvikligen skicka meddelanden till icke-existerande mottagare (spam är en hög volym åtgärd), destinationen e-postserver kommer sannolikt att returnera undeliverable meddelandet i en NDR, som skickas till den förfalskade avsändaren i Från: adress.</span><span class="sxs-lookup"><span data-stu-id="18e73-108">So, when a spammer inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server will likely return the undeliverable message in an NDR, which is sent to the forged sender in the From: address.</span></span>

<span data-ttu-id="18e73-109">Exchange Online Protection (EOP) gör allt för att identifiera och tyst släppa meddelanden från tvivelaktiga källor utan att generera en NDR.</span><span class="sxs-lookup"><span data-stu-id="18e73-109">Exchange Online Protection (EOP) makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="18e73-110">Men baserat på den stora volymen e-post som flyter genom tjänsten, det finns alltid en möjlighet att EOP oavsiktligt kommer att skicka backscatter meddelanden.</span><span class="sxs-lookup"><span data-stu-id="18e73-110">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter messages.</span></span>

<span data-ttu-id="18e73-111">Backscatterer.org upprätthåller en blockeringslista (kallas även en DNS-blocklista eller DNSBL) för e-postservrar som ansvarar för att skicka meddelanden till återspridning, och EOP-servrar kan visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="18e73-111">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter messages, and EOP servers might appear on this list.</span></span> <span data-ttu-id="18e73-112">Men vi försöker inte ta bort oss från Backscatterer.org blocklistan eftersom det inte är en lista över spammare (enligt egen utsago).</span><span class="sxs-lookup"><span data-stu-id="18e73-112">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="18e73-113">Den Backscatter.org<http://www.backscatterer.org/?target=usage>webbplats ( ) rekommenderar att du använder sin tjänst för att kontrollera inkommande e-post i felsäkert läge istället för Avvisa läge (stora e-posttjänster nästan alltid skicka några backscatter-meddelanden).</span><span class="sxs-lookup"><span data-stu-id="18e73-113">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter messages).</span></span>
