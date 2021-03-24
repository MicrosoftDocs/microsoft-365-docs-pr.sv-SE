---
title: Rapport om ej godkänd domän på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig hur de använder rapporten Ej godkänd domän i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka meddelanden från den lokala organisationen där avsändarens domän inte har konfigurerats i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071257"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="6adff-103">Rapport om ej godkänd domän i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="6adff-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6adff-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="6adff-104">**Applies to**</span></span>
- [<span data-ttu-id="6adff-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6adff-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6adff-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="6adff-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6adff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6adff-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6adff-108">I rapporten Ej godkänd [](mail-flow-insights-v2.md) domän i instrumentpanelen för e-postflöde i Säkerhets- och efterlevnadscenter för [&](https://protection.office.com) visas information om meddelanden från din lokala e-postorganisation där avsändarens domän inte är konfigurerad som en godkänd domän i din Microsoft 365-organisation. </span><span class="sxs-lookup"><span data-stu-id="6adff-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="6adff-109">Microsoft 365 kan begränsa dessa meddelanden om vi har data som bevisar att avsikten med dessa meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="6adff-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="6adff-110">Därför är det viktigt att du förstår vad som händer och kan åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="6adff-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Domänwidget som inte godkänts på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="6adff-112">Rapportvy för rapporten Ej godkänd domän</span><span class="sxs-lookup"><span data-stu-id="6adff-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="6adff-113">Om du klickar på diagrammet **på widgeten Godkänd** inte domän kommer du till **rapporten Ej godkänd** domän.</span><span class="sxs-lookup"><span data-stu-id="6adff-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="6adff-114">Som standard visas aktiviteten för alla berörda kopplingar.</span><span class="sxs-lookup"><span data-stu-id="6adff-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="6adff-115">Om du klickar **på Visa data för** kan du välja en specifik koppling i listrutan.</span><span class="sxs-lookup"><span data-stu-id="6adff-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="6adff-116">Om du hovrar över en datapunkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="6adff-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportvyn i rapporten Ej godkänd domän](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="6adff-118">Tabellvyn Detaljerad information för rapporten Om godkänd domän</span><span class="sxs-lookup"><span data-stu-id="6adff-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="6adff-119">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="6adff-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6adff-120">**Datum**</span><span class="sxs-lookup"><span data-stu-id="6adff-120">**Date**</span></span>
- <span data-ttu-id="6adff-121">**Namn på inkommande koppling**</span><span class="sxs-lookup"><span data-stu-id="6adff-121">**Inbound connector name**</span></span>
- <span data-ttu-id="6adff-122">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="6adff-122">**Sender domain**</span></span>
- <span data-ttu-id="6adff-123">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="6adff-123">**Message count**</span></span>
- <span data-ttu-id="6adff-124">**Exempelmeddelanden:** Meddelande-ID:na för ett exempel på påverkade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6adff-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="6adff-125">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="6adff-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6adff-126">Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="6adff-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="6adff-127">När du markerar en rad i tabellen visas en utfälltabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="6adff-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="6adff-128">**Datum**</span><span class="sxs-lookup"><span data-stu-id="6adff-128">**Date**</span></span>
- <span data-ttu-id="6adff-129">**Namn på inkommande koppling**</span><span class="sxs-lookup"><span data-stu-id="6adff-129">**Inbound connector name**</span></span>
- <span data-ttu-id="6adff-130">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="6adff-130">**Sender domain**</span></span>
- <span data-ttu-id="6adff-131">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="6adff-131">**Message count**</span></span>
- <span data-ttu-id="6adff-132">**Exempelmeddelanden:** Du kan klicka på **Visa exempelmeddelanden** om du vill se [resultatet av meddelandespårningen](message-trace-scc.md) för ett exempel på de berörda meddelandena.</span><span class="sxs-lookup"><span data-stu-id="6adff-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Information som visas när du har valt en rad i tabellvyn Information i rapporten Ej godkänd domän](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="6adff-134">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="6adff-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6adff-135">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6adff-135">Related topics</span></span>

<span data-ttu-id="6adff-136">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="6adff-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
