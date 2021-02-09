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
description: Administratörer kan lära sig att använda e-postflödeskartan i instrumentpanelen för e-postflöde i Säkerhets- & och efterlevnadscenter för att visualisera och spåra hur e-post flödar till och från organisationen via kopplingar och utan att använda kopplingar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150566"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="df206-103">E-postflödeskarta i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="df206-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="df206-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="df206-104">**Applies to**</span></span>
- [<span data-ttu-id="df206-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="df206-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="df206-106">Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="df206-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="df206-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df206-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="df206-108">**E-postflödeskartan** [i](mail-flow-insights-v2.md) instrumentpanelen för e-postflöde i Säkerhets- & [efterlevnadscenter](https://protection.office.com) ger insyn i hur e-post flödar genom organisationen.</span><span class="sxs-lookup"><span data-stu-id="df206-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="df206-109">Du kan använda den här informationen för att lära dig mönster, identifiera problem och åtgärda problem när de uppstår.</span><span class="sxs-lookup"><span data-stu-id="df206-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget för e-postflödeskarta i instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="df206-111">Som standard visar widgeten e-postflödesmönstret från föregående dag i ett diagram som kallas *Sankey-diagram.*</span><span class="sxs-lookup"><span data-stu-id="df206-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="df206-112">Du kan använda vänsterpilen ![ och ](../../media/scc-left-arrow.png) högerpilen till höger om ![ du vill visa information från olika ](../../media/scc-right-arrow.png) dagar.</span><span class="sxs-lookup"><span data-stu-id="df206-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="df206-113">Varje färg representerar e-postflöde över en annan inkommande eller utgående koppling (eller utan att använda kopplingar).</span><span class="sxs-lookup"><span data-stu-id="df206-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="df206-114">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="df206-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="df206-115">Rapportvy för e-postflödeskartan</span><span class="sxs-lookup"><span data-stu-id="df206-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="df206-116">Om du klickar på **widgeten för e-postflödeskartan** kommer du till rapporten **E-postflödeskarta.**</span><span class="sxs-lookup"><span data-stu-id="df206-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="df206-117">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="df206-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="df206-118">**Visa data för: Översikt:** Det här är i stort sett en större vy av widgeten.</span><span class="sxs-lookup"><span data-stu-id="df206-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="df206-119">Om du hovrar över en viss färg visas antalet meddelanden för den typen av koppling.</span><span class="sxs-lookup"><span data-stu-id="df206-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Översiktsvy i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="df206-121">**Visa data för: Information:** I den här vyn visas information om kopplingar och måldomäner.</span><span class="sxs-lookup"><span data-stu-id="df206-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="df206-122">De översta domänerna för avsändare och mottagare visas och resten läggs i **Andra.**</span><span class="sxs-lookup"><span data-stu-id="df206-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="df206-123">Om du hovrar över en viss färg och ett visst avsnitt visas antalet meddelanden.</span><span class="sxs-lookup"><span data-stu-id="df206-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Detaljvyn i rapporten E-postflödeskarta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="df206-125">Om du klickar **på** Filter i en rapportvy kan du ange ett datumintervall **med startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="df206-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="df206-126">Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="df206-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="df206-127">Relaterade insikter visas under e-postflödeskartan om de är tillgängliga (till exempel information om att åtgärda [möjlig e-postslinga).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="df206-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="df206-128">Detaljtabellvy för e-postflödeskartan</span><span class="sxs-lookup"><span data-stu-id="df206-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="df206-129">Om du **klickar på tabellen Visa** information i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="df206-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="df206-130">**Datum**</span><span class="sxs-lookup"><span data-stu-id="df206-130">**Date**</span></span>
- <span data-ttu-id="df206-131">**Kategori**</span><span class="sxs-lookup"><span data-stu-id="df206-131">**Category**</span></span>
- <span data-ttu-id="df206-132">**Anslutare/tjänstprovider**</span><span class="sxs-lookup"><span data-stu-id="df206-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="df206-133">**Domän för avsändare/mottagare**</span><span class="sxs-lookup"><span data-stu-id="df206-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="df206-134">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="df206-134">**Message count**</span></span>

<span data-ttu-id="df206-135">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="df206-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="df206-136">Om du markerar en rad visas liknande information i en utfällig plats:</span><span class="sxs-lookup"><span data-stu-id="df206-136">If you select a row, similar details are shown in a flyout:</span></span>

![Utfällbar information från detaljtabellen på e-postflödeskartan](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="df206-138">Om du vill skicka rapporten för ett visst datumintervall till en eller flera mottagare via e-post klickar du **på Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="df206-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="df206-139">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="df206-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="df206-140">Se även</span><span class="sxs-lookup"><span data-stu-id="df206-140">See also</span></span>

<span data-ttu-id="df206-141">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinsikter i Säkerhets- & Efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="df206-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
