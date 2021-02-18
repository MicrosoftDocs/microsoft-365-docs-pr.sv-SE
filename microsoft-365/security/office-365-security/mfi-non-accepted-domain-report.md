---
title: Icke-godkänd domänrapport i instrumentpanelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de använder rapporten om icke-godkända domäner i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka meddelanden från den lokala organisationen där avsändarens domän inte har konfigurerats i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d7355af49c5810a593c5776b70cf7497b43af6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287871"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="dcf99-103">Icke-godkänd domänrapport i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="dcf99-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dcf99-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="dcf99-104">**Applies to**</span></span>
- [<span data-ttu-id="dcf99-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dcf99-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dcf99-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="dcf99-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="dcf99-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dcf99-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="dcf99-108">I instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för [&](https://protection.office.com) visas information om meddelanden från din lokala e-postorganisation där avsändarens domän inte har konfigurerats som en godkänd domän i Microsoft [](mail-flow-insights-v2.md) 365-organisationen. </span><span class="sxs-lookup"><span data-stu-id="dcf99-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="dcf99-109">Microsoft 365 kan begränsa dessa meddelanden om vi har data som bevisar att avsikten med dessa meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="dcf99-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="dcf99-110">Därför är det viktigt att du förstår vad som händer och åtgärdar problemet.</span><span class="sxs-lookup"><span data-stu-id="dcf99-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Domänwidget som inte godkänts i instrumentpanelen för e-postflöde i & Efterlevnadscenter](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dcf99-112">Rapportvy för domänrapporten Godkänd</span><span class="sxs-lookup"><span data-stu-id="dcf99-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="dcf99-113">Om du klickar på diagrammet **på widgeten Ej godkänd** domän kommer du till rapporten Om domänen inte **godkänns.**</span><span class="sxs-lookup"><span data-stu-id="dcf99-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="dcf99-114">Som standard visas aktiviteten för alla berörda kopplingar.</span><span class="sxs-lookup"><span data-stu-id="dcf99-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="dcf99-115">Om du klickar **på Visa data** för kan du välja en specifik koppling i listrutan.</span><span class="sxs-lookup"><span data-stu-id="dcf99-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="dcf99-116">Om du hovrar över en datapunkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="dcf99-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportvy i domänrapporten Godkänd](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dcf99-118">Detaljtabellvy för domänrapporten Godkänd</span><span class="sxs-lookup"><span data-stu-id="dcf99-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="dcf99-119">Om du **klickar på tabellen Visa** information i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="dcf99-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dcf99-120">**Datum**</span><span class="sxs-lookup"><span data-stu-id="dcf99-120">**Date**</span></span>
- <span data-ttu-id="dcf99-121">**Namn på inkommande koppling**</span><span class="sxs-lookup"><span data-stu-id="dcf99-121">**Inbound connector name**</span></span>
- <span data-ttu-id="dcf99-122">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="dcf99-122">**Sender domain**</span></span>
- <span data-ttu-id="dcf99-123">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="dcf99-123">**Message count**</span></span>
- <span data-ttu-id="dcf99-124">**Exempelmeddelanden:** Meddelande-ID:na för ett exempel på påverkade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="dcf99-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="dcf99-125">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="dcf99-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dcf99-126">Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="dcf99-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="dcf99-127">När du markerar en rad i tabellen visas en utfälltabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="dcf99-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="dcf99-128">**Datum**</span><span class="sxs-lookup"><span data-stu-id="dcf99-128">**Date**</span></span>
- <span data-ttu-id="dcf99-129">**Namn på inkommande koppling**</span><span class="sxs-lookup"><span data-stu-id="dcf99-129">**Inbound connector name**</span></span>
- <span data-ttu-id="dcf99-130">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="dcf99-130">**Sender domain**</span></span>
- <span data-ttu-id="dcf99-131">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="dcf99-131">**Message count**</span></span>
- <span data-ttu-id="dcf99-132">**Exempelmeddelanden:** Du kan klicka **på Visa exempelmeddelanden** om du vill visa [meddelandespårningsresultaten](message-trace-scc.md) för ett urval av de aktuella meddelandena.</span><span class="sxs-lookup"><span data-stu-id="dcf99-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Information som visas när du har valt en rad i tabellvyn Detaljer i rapporten Om godkänd domän](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="dcf99-134">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="dcf99-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dcf99-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="dcf99-135">Related topics</span></span>

<span data-ttu-id="dcf99-136">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dcf99-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
