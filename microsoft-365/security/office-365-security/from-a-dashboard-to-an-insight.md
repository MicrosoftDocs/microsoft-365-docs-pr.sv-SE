---
title: Genomgång – Från en instrumentpanel till en insikt
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
ms.collection:
- M365-security-compliance
description: Läs om hur du kan gå från en instrumentpanel till en insikt med rekommenderade åtgärder i Security &amp; Compliance Center.
ms.openlocfilehash: 22ca34696bc46e0142818be715d68f0b469c6255
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638100"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="fccb5-103">Genomgång – Från en instrumentpanel till en insikt</span><span class="sxs-lookup"><span data-stu-id="fccb5-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="fccb5-104">Om du inte har tidigare information [om &amp; rapporter och insikter i Security Compliance Center](reports-and-insights-in-security-and-compliance.md)kan det hjälpa dig att se hur du enkelt kan navigera från en instrumentpanel till en insikt och rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="fccb5-104">If you're new to [reports and insights in the Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="fccb5-105">Detta är en av flera genomgångar &amp; för Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="fccb5-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="fccb5-106">Mer information om hur du går igenom ytterligare genomgångar finns i avsnittet [Närliggande ämnen.](#related-topics)</span><span class="sxs-lookup"><span data-stu-id="fccb5-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="fccb5-107">Genomgång: Från en instrumentpanel till en insikt</span><span class="sxs-lookup"><span data-stu-id="fccb5-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="fccb5-108">Låt oss gå igenom flödet från en instrumentpanel till en rapport till en insikt och åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fccb5-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="fccb5-109">(Detta är en kort [parodi intelligens](learn-about-spoof-intelligence.md) exempel.)</span><span class="sxs-lookup"><span data-stu-id="fccb5-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="fccb5-110">Vi börjar med säkerhetsinstrumentpanelen i [Security &amp; Compliance Center](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="fccb5-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="fccb5-111">(Gå till **instrumentpanelen** **för hothantering** \> .)</span><span class="sxs-lookup"><span data-stu-id="fccb5-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="fccb5-112">![I Security &amp; Compliance Center väljer \> du Instrumentpanel för hothantering](../../media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="fccb5-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](../../media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="fccb5-113">På raden **Insikter** märker vi en insikt som visar att vi måste granska vissa domäner som kan vara misstänkta.</span><span class="sxs-lookup"><span data-stu-id="fccb5-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="fccb5-114">(På raden **Insikter** klickar du på **Domänpar**.)</span><span class="sxs-lookup"><span data-stu-id="fccb5-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="fccb5-115">![Insights raden nämner potentiella spoofing oro](../../media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="fccb5-115">![The Insights row mentions potential spoofing concerns](../../media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="fccb5-116">Vi får en lista över aktiviteter relaterade till falska underrättelser.</span><span class="sxs-lookup"><span data-stu-id="fccb5-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="fccb5-117">Det här är fall där e-postmeddelanden skickades som ser ut som de kom från vår organisation men i själva verket skickades från en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="fccb5-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="fccb5-118">Målet är att avgöra om falska meddelanden är auktoriserade eller inte.</span><span class="sxs-lookup"><span data-stu-id="fccb5-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="fccb5-119">![Falska underrättelseinsikter](../../media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="fccb5-119">![Spoof intelligence insights](../../media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="fccb5-120">I den här listan kan vi sortera informationen efter meddelanderäkning, datum då förfalskningen senast upptäcktes med mera.</span><span class="sxs-lookup"><span data-stu-id="fccb5-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="fccb5-121">(Klicka på kolumnrubriker, till exempel **Antal meddelanden** eller **Senast sett** för att se hur sortering fungerar.)</span><span class="sxs-lookup"><span data-stu-id="fccb5-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="fccb5-122">Om du väljer ett objekt i listan öppnas ett informationsfönster där vi kan se ytterligare information, inklusive liknande e-postmeddelanden som har identifierats.</span><span class="sxs-lookup"><span data-stu-id="fccb5-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="fccb5-123">(Klicka på ett objekt i listan och granska informationen och rekommendationerna.)</span><span class="sxs-lookup"><span data-stu-id="fccb5-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![Om du markerar ett objekt öppnas ett informationsfönster](../../media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="fccb5-125">Observera att högst upp i fönstret har vi möjlighet att lägga till avsändaren i organisationens lista över tillåtna avsändare.</span><span class="sxs-lookup"><span data-stu-id="fccb5-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="fccb5-126">(Välj inte **Lägg till i listan Tillåtspoof-avsändare** förrän du är säker på att du vill göra detta.</span><span class="sxs-lookup"><span data-stu-id="fccb5-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="fccb5-127">[Konfigurera falska underrättelser i Office 365](learn-about-spoof-intelligence.md).)</span><span class="sxs-lookup"><span data-stu-id="fccb5-127">[Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="fccb5-128">![Du kan auktorisera en avsändare](../../media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="fccb5-128">![You can authorize a sender](../../media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="fccb5-129">På så sätt kan vi gå från en instrumentpanel till insikter och rekommenderade åtgärder.</span><span class="sxs-lookup"><span data-stu-id="fccb5-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fccb5-130">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fccb5-130">Related topics</span></span>

[<span data-ttu-id="fccb5-131">Genomgång: Från en insikt till en detaljerad rapport</span><span class="sxs-lookup"><span data-stu-id="fccb5-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="fccb5-132">Genomgång: Från en detaljerad rapport till en insikt</span><span class="sxs-lookup"><span data-stu-id="fccb5-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

