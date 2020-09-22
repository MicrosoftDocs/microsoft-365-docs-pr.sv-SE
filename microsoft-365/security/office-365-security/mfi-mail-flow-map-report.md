---
title: E-postflödeskarta
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
description: Administratörer kan läsa mer om hur du använder översikten för e-postflöden i instrument panelen för e-postflöde i säkerhets & efterföljandekrav för att visualisera och spåra hur e-flöden kommer till och från sin organisation via kopplingar och utan att använda kopplingar.
ms.openlocfilehash: 74cabb7f7b34be6248d18d71565c8a9729d7e38b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199377"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="9d4cd-103">Översikt över e-postflöde i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="9d4cd-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9d4cd-104">**E-postflödes kartan** i [instrument panelen för e-postflöde](mail-flow-insights-v2.md) i [säkerhets & Compliance Center](https://protection.office.com) ger en överblick över hur e-flöden passerar genom din organisation.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="9d4cd-105">Du kan använda den här informationen för att lära dig mönster, identifiera avvikelser och åtgärda problem när de uppstår.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget för e-postflödes karta i instrument panelen för säkerhet &](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="9d4cd-107">Som standard visar widgeten e-postflödet från föregående dag i ett diagram som kallas *Sankey* -diagram.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="9d4cd-108">Du kan använda vänsterpilen vänsterpil ![ och HÖGERPIL ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) för att visa information från olika dagar.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="9d4cd-109">Varje färg representerar e-postflöden över en annan inkommande eller utgående koppling (eller utan att använda kopplingar).</span><span class="sxs-lookup"><span data-stu-id="9d4cd-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="9d4cd-110">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="9d4cd-111">Rapportvy för översikt över e-postflöde</span><span class="sxs-lookup"><span data-stu-id="9d4cd-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="9d4cd-112">Om du klickar på widgeten **Koppla dokument flöden** tas du till **översikten över e-postflöde** .</span><span class="sxs-lookup"><span data-stu-id="9d4cd-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="9d4cd-113">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="9d4cd-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9d4cd-114">**Visa data för: översikt**: det här är i stort sett en större vy av widgeten.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="9d4cd-115">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Vyn Översikt i rapporten e-postflödes karta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="9d4cd-117">**Visa data för: detail**: den här vyn visar information om kopplingarna och mål domänerna.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="9d4cd-118">De översta avsändarna och mottagar domänerna visas och resten placeras i **andra**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="9d4cd-119">Om du hovrar över en viss färg och ett avsnitt visas antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detaljvyn i rapporten dokument flödes karta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="9d4cd-121">Om du klickar på **filter** i en rapportvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9d4cd-122">Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9d4cd-123">Relaterade insikter visas under översikten över e-postflöden om de är tillgängliga (till exempel [korrigerings filen för möjlig e-postloop](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="9d4cd-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="9d4cd-124">Vyn detaljerad vy för översikt över e-postflöde</span><span class="sxs-lookup"><span data-stu-id="9d4cd-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="9d4cd-125">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="9d4cd-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9d4cd-126">**Datum**</span><span class="sxs-lookup"><span data-stu-id="9d4cd-126">**Date**</span></span>
- <span data-ttu-id="9d4cd-127">**Kategori**</span><span class="sxs-lookup"><span data-stu-id="9d4cd-127">**Category**</span></span>
- <span data-ttu-id="9d4cd-128">**Anslutning/tredjepartsleverantör från tredje part**</span><span class="sxs-lookup"><span data-stu-id="9d4cd-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="9d4cd-129">**Avsändare/mottagare**</span><span class="sxs-lookup"><span data-stu-id="9d4cd-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="9d4cd-130">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="9d4cd-130">**Message count**</span></span>

<span data-ttu-id="9d4cd-131">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9d4cd-132">Om du markerar en rad visas liknande information i en utfällbar lista:</span><span class="sxs-lookup"><span data-stu-id="9d4cd-132">If you select a row, similar details are shown in a flyout:</span></span>

![Information som utfälls från informations tabellen i översikten över e-postflöde](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="9d4cd-134">Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9d4cd-135">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="9d4cd-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d4cd-136">Se även</span><span class="sxs-lookup"><span data-stu-id="9d4cd-136">See also</span></span>

<span data-ttu-id="9d4cd-137">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9d4cd-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
