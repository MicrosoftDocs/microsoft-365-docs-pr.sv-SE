---
title: Rapport om utebliven leverans på instrumentpanelen för e-postflöde
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
description: Administratörer kan lära sig att använda rapporten Information om utebliven leverans i instrumentpanelen för e-postflöde i säkerhets- och efterlevnadscentret för & för att övervaka de ofta påträffade felkoderna i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskaviseringar) från avsändare i organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d25f11051606139c2ee8b88cade18963de599d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071234"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="be252-103">Rapport om utebliven leverans i säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="be252-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="be252-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="be252-104">**Applies to**</span></span>
- [<span data-ttu-id="be252-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="be252-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="be252-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="be252-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="be252-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be252-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="be252-108">Rapporten **Icke &-leverans** på instrumentpanelen [](https://protection.office.com) för e-postflöde i Säkerhets- och efterlevnadscenter visar de mest påträffade felkoderna i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveransk så kallade icke-leveranskroller) för användare i organisationen. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="be252-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="be252-109">Den här rapporten innehåller information om NDR-rapporter så att du kan felsöka problem med e-postleveransen.</span><span class="sxs-lookup"><span data-stu-id="be252-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget för rapport om utebliven leverans på instrumentpanelen för e-postflöde & Säkerhets- och efterlevnadscenter](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="be252-111">Rapportvy för rapporten om utebliven leverans</span><span class="sxs-lookup"><span data-stu-id="be252-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="be252-112">Om du klickar **på widgeten Rapport om** utebliven leverans kommer du till rapporten Ej **leverans.**</span><span class="sxs-lookup"><span data-stu-id="be252-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="be252-113">Som standard visas aktiviteten för alla felkoder.</span><span class="sxs-lookup"><span data-stu-id="be252-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="be252-114">Om du klickar **på Visa data** för kan du välja en specifik felkod i listrutan.</span><span class="sxs-lookup"><span data-stu-id="be252-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="be252-115">Om du hovrar över en viss färg (felkod) en viss dag i diagrammet visas det totala antalet meddelanden för felet.</span><span class="sxs-lookup"><span data-stu-id="be252-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Rapportvyn i rapporten Ej godkänd domän](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="be252-117">Tabellvyn Information för rapporten om utebliven leverans</span><span class="sxs-lookup"><span data-stu-id="be252-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="be252-118">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="be252-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="be252-119">**Datum**</span><span class="sxs-lookup"><span data-stu-id="be252-119">**Date**</span></span>
- <span data-ttu-id="be252-120">**Rapportkod för utebliven leverans**</span><span class="sxs-lookup"><span data-stu-id="be252-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="be252-121">**Antal**</span><span class="sxs-lookup"><span data-stu-id="be252-121">**Count**</span></span>
- <span data-ttu-id="be252-122">**Exempelmeddelanden:** Meddelande-ID:na för ett exempel på påverkade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="be252-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="be252-123">Om du klickar **på** Filter i en detaljtabellvy kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="be252-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="be252-124">Om du vill skicka rapporten med ett visst datumintervall till en eller flera mottagare klickar du på **Begär nedladdning.**</span><span class="sxs-lookup"><span data-stu-id="be252-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="be252-125">När du markerar en rad i tabellen visas en utfälltabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="be252-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="be252-126">**Datum**</span><span class="sxs-lookup"><span data-stu-id="be252-126">**Date**</span></span>
- <span data-ttu-id="be252-127">**Rapportkod för utebliven** leverans: Du kan klicka på länken för att hitta mer information om orsaker och lösningar för den specifika felkoden.</span><span class="sxs-lookup"><span data-stu-id="be252-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="be252-128">**Antal**</span><span class="sxs-lookup"><span data-stu-id="be252-128">**Count**</span></span>
- <span data-ttu-id="be252-129">**Exempelmeddelanden:** Du kan klicka på **Visa exempelmeddelanden** om du vill se [resultatet av meddelandespårningen](message-trace-scc.md) för ett exempel på de berörda meddelandena.</span><span class="sxs-lookup"><span data-stu-id="be252-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Information som visas när du har valt en rad i tabellvyn Information i rapporten Om leverans](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="be252-131">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="be252-131">Related topics</span></span>

<span data-ttu-id="be252-132">Mer information om andra insikter i instrumentpanelen för e-postflöde finns i [E-postflödesinformation i Säkerhets- & efterlevnadscenter.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="be252-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
