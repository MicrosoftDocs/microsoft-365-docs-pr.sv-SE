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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig mer om bakåtcatter och Microsoft Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3cdc556a8cc193466d150fc82298796779841cca
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165961"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="582b1-103">Återspridning i EOP</span><span class="sxs-lookup"><span data-stu-id="582b1-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="582b1-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="582b1-104">**Applies to**</span></span>
- [<span data-ttu-id="582b1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="582b1-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="582b1-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="582b1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="582b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="582b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="582b1-108">*Bakåtcatter är* rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) som du får för meddelanden som du inte har skickat.</span><span class="sxs-lookup"><span data-stu-id="582b1-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="582b1-109">Skräppostavsmedlare förfalskar från-adressen till sina meddelanden, och de använder ofta riktiga e-postadresser för att låna ut trovärdigheten för sina meddelanden.</span><span class="sxs-lookup"><span data-stu-id="582b1-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="582b1-110">Så om skräppostavsändare oundvikligen skickar meddelanden till mottagare som inte finns (skräppost är en stor volymåtgärd), luras mål-e-postservern i princip att returnera det olevererbara meddelandet i en NDR-meddelande till den förfalskade avsändaren i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="582b1-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="582b1-111">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor gör EOP allt för att identifiera och tyst släppa meddelanden från tveksamma källor utan att generera en NDR.</span><span class="sxs-lookup"><span data-stu-id="582b1-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="582b1-112">Men utifrån den större mängd e-post som flödar genom tjänsten finns det alltid en möjlighet att EOP oavsiktligt skickar bakåtcatter.</span><span class="sxs-lookup"><span data-stu-id="582b1-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="582b1-113">Backscatterer.org en blockeringslista (kallas även DNS-blockeringslista eller DNSBL) över e-postservrar som ansvarar för att skicka bakåtcatter, och EOP-servrar kan visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="582b1-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="582b1-114">Men vi försöker inte ta bort dig från blockeringslistan i Backscatterer.org för att det inte är en lista över skräppostavs skräppostavsägare (enligt eget medgivande).</span><span class="sxs-lookup"><span data-stu-id="582b1-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="582b1-115">Webbplatsen Backscatter.org () rekommenderar att du använder tjänsten för att kontrollera inkommande e-post i felsäkert läge i stället för i läget Avvisa (stora e-posttjänster skickar nästan alltid <http://www.backscatterer.org/?target=usage> bakåt).</span><span class="sxs-lookup"><span data-stu-id="582b1-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
