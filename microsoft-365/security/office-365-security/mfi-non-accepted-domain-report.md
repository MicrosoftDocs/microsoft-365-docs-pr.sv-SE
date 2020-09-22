---
title: Icke godkänd domän rapport i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda den icke godkända domän rapporten i instrument panelen för e-postflöde i säkerhets & efterlevnad för att övervaka meddelanden från din lokala organisation där avsändarens domän inte är konfigurerad i Microsoft 365.
ms.openlocfilehash: d05489ec4a6d670fc89b5d943b3e7061506b6fe8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199331"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="e3cfd-103">Icke godkänd domän rapport i Center för säkerhets &</span><span class="sxs-lookup"><span data-stu-id="e3cfd-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e3cfd-104">Den **icke godkända domän** rapporten i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) visar information om meddelanden från din lokala e-postorganisation där avsändarens domän inte är konfigurerad som en godkänd domän i Microsoft 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="e3cfd-105">Microsoft 365 kan begränsa dessa meddelanden om vi har data som visar att syftet med dessa meddelanden är skadligt.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="e3cfd-106">Därför är det viktigt att du förstår vad som händer och för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Icke godkänd domän-widget i instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e3cfd-108">Rapportvy för den icke godkände domän rapporten</span><span class="sxs-lookup"><span data-stu-id="e3cfd-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="e3cfd-109">Om du klickar på diagrammet i widgeten **icke godkänd domän** tas du till den **icke godkända domän** rapporten.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="e3cfd-110">Aktiviteten för alla berörda kopplingar visas som standard.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="e3cfd-111">Om du klickar på **Visa data för**kan du välja en specifik koppling i list rutan.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="e3cfd-112">Om du hovrar över en data punkt (dag) i diagrammet visas det totala antalet meddelanden för kopplingen.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Rapportvy i rapporten icke godkänd domän](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="e3cfd-114">Vyn detaljerad tabell för icke godkänd domän rapport</span><span class="sxs-lookup"><span data-stu-id="e3cfd-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="e3cfd-115">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="e3cfd-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e3cfd-116">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-116">**Date**</span></span>
- <span data-ttu-id="e3cfd-117">**Namn på inkommande anslutning**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-117">**Inbound connector name**</span></span>
- <span data-ttu-id="e3cfd-118">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-118">**Sender domain**</span></span>
- <span data-ttu-id="e3cfd-119">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-119">**Message count**</span></span>
- <span data-ttu-id="e3cfd-120">**Exempel meddelanden**: meddelande-ID för ett urval av påverkade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="e3cfd-121">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e3cfd-122">Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e3cfd-123">När du markerar en rad i tabellen visas en utfällbar tabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="e3cfd-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="e3cfd-124">**Datum**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-124">**Date**</span></span>
- <span data-ttu-id="e3cfd-125">**Namn på inkommande anslutning**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-125">**Inbound connector name**</span></span>
- <span data-ttu-id="e3cfd-126">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-126">**Sender domain**</span></span>
- <span data-ttu-id="e3cfd-127">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="e3cfd-127">**Message count**</span></span>
- <span data-ttu-id="e3cfd-128">**Exempel meddelanden**: du kan klicka på **Visa exempel meddelanden** om du vill visa [meddelande spårnings](message-trace-scc.md) resultaten för ett prov av de påverkade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Utfällda detaljer när du har markerat en rad i tabellvy för information i den icke godkända domän rapporten](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="e3cfd-130">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="e3cfd-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3cfd-131">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e3cfd-131">Related topics</span></span>

<span data-ttu-id="e3cfd-132">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="e3cfd-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
