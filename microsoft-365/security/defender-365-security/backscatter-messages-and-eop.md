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
ms.openlocfilehash: e5882f611c3feec9a22760e696973cd0713649b2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073490"
---
# <a name="backscatter-in-eop"></a><span data-ttu-id="e5b8d-103">Återspridning i EOP</span><span class="sxs-lookup"><span data-stu-id="e5b8d-103">Backscatter in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e5b8d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e5b8d-104">**Applies to**</span></span>
- [<span data-ttu-id="e5b8d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e5b8d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e5b8d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e5b8d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e5b8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5b8d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e5b8d-108">*Bakåtcatter är rapporter* om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskända meddelanden) som du får för meddelanden som du inte har skickat.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-108">*Backscatter* is non-delivery reports (also known as NDRs or bounce messages) you receive for messages that you didn't send.</span></span> <span data-ttu-id="e5b8d-109">Skräppostavs spammare förfalskar meddelandens adress från: och de använder ofta riktiga e-postadresser för att låna ut trovärdigheten för sina meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-109">Spammers forge (spoof) the From: address of their messages, and they often use real email addresses to lend credibility to their messages.</span></span> <span data-ttu-id="e5b8d-110">Så om skräppostavsändare oundvikligen skickar meddelanden till mottagare som inte finns (skräppost är en stor volym) förs nämligen mål-e-postservern i princip att returnera det olevererbara meddelandet i en NDR-meddelande till den förfalskade avsändaren i från:-adressen.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-110">So, when spammers inevitably send messages to non-existent recipients (spam is a high-volume operation), the destination email server is essentially tricked into returning the undeliverable message in an NDR to the forged sender in the From: address.</span></span>

<span data-ttu-id="e5b8d-111">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor gör EOP allt för att identifiera och tyst släppa meddelanden från olämpliga källor utan att generera en NDR-meddelande.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP makes every effort to identify and silently drop messages from dubious sources without generating an NDR.</span></span> <span data-ttu-id="e5b8d-112">Men utifrån den större volym-e-post som flödar genom tjänsten finns det alltid en möjlighet att EOP oavsiktligt skickar bakåtcatter.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-112">But, based on the sheer volume email flowing through the service, there's always the possibility that EOP will unintentionally send backscatter.</span></span>

<span data-ttu-id="e5b8d-113">Backscatterer.org har en blockeringslista (kallas även DNS-blockeringslista eller DNSBL) över e-postservrar som var ansvariga för att skicka bakåtcatter, och EOP-servrar kan visas i den här listan.</span><span class="sxs-lookup"><span data-stu-id="e5b8d-113">Backscatterer.org maintains a block list (also known as a DNS block list or DNSBL) of email servers that were responsible for sending backscatter, and EOP servers might appear on this list.</span></span> <span data-ttu-id="e5b8d-114">Men vi försöker inte ta bort skräpposten från Backscatterer.org-blockeringslistan eftersom det inte är en lista över skräppostavseningar (via eget medgivande).</span><span class="sxs-lookup"><span data-stu-id="e5b8d-114">But, we don't try to remove ourselves from the Backscatterer.org block list because it isn't a list of spammers (by their own admission).</span></span>

> [!TIP]
> <span data-ttu-id="e5b8d-115">Webbplatsen Backscatter.org () rekommenderar att man använder tjänsten för att kontrollera inkommande e-post i felsäkert läge i stället för i avvisande läge (stora e-posttjänster skickar nästan alltid en del <http://www.backscatterer.org/?target=usage> bakåtcatter).</span><span class="sxs-lookup"><span data-stu-id="e5b8d-115">The Backscatter.org website (<http://www.backscatterer.org/?target=usage>) recommends using their service to check incoming email in Safe mode instead of Reject mode (large email services almost always send some backscatter).</span></span>
