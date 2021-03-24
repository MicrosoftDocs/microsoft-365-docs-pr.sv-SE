---
title: E-postflödeskarta
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
description: Administratörer kan lära sig att använda e-postflödeskartan i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att visualisera och spåra hur e-post flödar till och från organisationen via kopplingar och utan att använda kopplingar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071305"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="c5d63-103">E-postflödeskarta i säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="c5d63-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c5d63-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="c5d63-104">**Applies to**</span></span>
- [<span data-ttu-id="c5d63-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c5d63-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c5d63-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="c5d63-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c5d63-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5d63-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c5d63-108">**E-postflödeskartan** [på instrumentpanelen](mail-flow-insights-v2.md) för e-postflöde i säkerhets- & [efterlevnadscenter](https://protection.office.com) ger insyn i hur e-post flödar genom organisationen.</span><span class="sxs-lookup"><span data-stu-id="c5d63-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="c5d63-109">Du kan använda den här informationen till att lära dig mönster, identifiera problem och åtgärda problem när de uppstår.</span><span class="sxs-lookup"><span data-stu-id="c5d63-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget för e-postflödeskarta i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="c5d63-111">Som standard visar widgeten e-postflödesmönstret från föregående dag i ett diagram som kallas *för Ett Sankey-diagram.*</span><span class="sxs-lookup"><span data-stu-id="c5d63-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="c5d63-112">Du kan använda vänsterpilen ![ Vänsterpil ](../../media/scc-left-arrow.png) och Högerpil för ![ att visa information från olika ](../../media/scc-right-arrow.png) dagar.</span><span class="sxs-lookup"><span data-stu-id="c5d63-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="c5d63-113">Varje färg representerar e-postflöde över en annan inkommande eller utgående koppling (eller utan att använda kopplingar).</span><span class="sxs-lookup"><span data-stu-id="c5d63-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="c5d63-114">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="c5d63-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="c5d63-115">Rapportvy för e-postflödeskartan</span><span class="sxs-lookup"><span data-stu-id="c5d63-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="c5d63-116">Om du klickar på **widgeten E-postflödeskarta** kommer du till **rapporten E-postflödeskarta.**</span><span class="sxs-lookup"><span data-stu-id="c5d63-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="c5d63-117">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="c5d63-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="c5d63-118">**Visa data för: Översikt:** Det här är i stort sett en större vy av widgeten.</span><span class="sxs-lookup"><span data-stu-id="c5d63-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="c5d63-119">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="c5d63-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Översiktsvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="c5d63-121">**Visa data för: Information:** I den här vyn visas information om kopplingarna och måldomänerna.</span><span class="sxs-lookup"><span data-stu-id="c5d63-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="c5d63-122">De översta domänerna för avsändare och mottagare visas och resten finns i **Andra**.</span><span class="sxs-lookup"><span data-stu-id="c5d63-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="c5d63-123">Om du hovrar över en viss färg och ett visst avsnitt visas antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c5d63-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detaljvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="c5d63-125">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="c5d63-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="c5d63-126">Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="c5d63-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="c5d63-127">Relaterade insikter visas under e-postflödeskartan om de är tillgängliga (till exempel åtgärda möjliga insikter om [e-postslinga](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="c5d63-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="c5d63-128">Detaljtabellvyn för e-postflödeskartan</span><span class="sxs-lookup"><span data-stu-id="c5d63-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="c5d63-129">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="c5d63-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="c5d63-130">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c5d63-130">**Date**</span></span>
- <span data-ttu-id="c5d63-131">**Kategori**</span><span class="sxs-lookup"><span data-stu-id="c5d63-131">**Category**</span></span>
- <span data-ttu-id="c5d63-132">**Anslutare/tredjepartsleverantör**</span><span class="sxs-lookup"><span data-stu-id="c5d63-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="c5d63-133">**Sender/Recipient domain**</span><span class="sxs-lookup"><span data-stu-id="c5d63-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="c5d63-134">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="c5d63-134">**Message count**</span></span>

<span data-ttu-id="c5d63-135">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="c5d63-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="c5d63-136">Om du markerar en rad visas liknande information i en utfällbladstext:</span><span class="sxs-lookup"><span data-stu-id="c5d63-136">If you select a row, similar details are shown in a flyout:</span></span>

![Utfällbar information från detaljtabellen i e-postflödeskartan](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="c5d63-138">Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="c5d63-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="c5d63-139">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="c5d63-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5d63-140">Se även</span><span class="sxs-lookup"><span data-stu-id="c5d63-140">See also</span></span>

<span data-ttu-id="c5d63-141">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c5d63-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
