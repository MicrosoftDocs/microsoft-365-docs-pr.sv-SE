---
title: Rapport om utebliven leverans i instrument panelen för e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära dig hur du använder rapporten för information om ej leverans i instrument panelen för e-postflöde i säkerhets & Compliance Center för att övervaka de vanligaste fel koderna i rapporter som inte kunde levereras (kallas även NDR eller studs meddelanden) från avsändare i din organisation.
ms.openlocfilehash: d45382ab5c7e0d0a73487740544f20b9c25a3ad1
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577438"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="bb135-103">Rapport om utebliven leverans i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="bb135-103">Non-delivery report in the Security & Compliance Center</span></span>

<span data-ttu-id="bb135-104">I **rapporten om utebliven leverans** i [instrument panelen för e-postflöden](mail-flow-insights-v2.md) i säkerhets & Compliance Center visas de mest upptäckta fel koderna i rapporter för inte leverans (kallas även för NDR eller studs meddelanden) för användare i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bb135-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="bb135-105">Den här rapporten visar information om NDR så att du kan felsöka problem med e-postleverans.</span><span class="sxs-lookup"><span data-stu-id="bb135-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget för rapport om utebliven leverans i instrument panelen för e-postflöde i säkerhets & efterlevnad](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="bb135-107">Rapportvy för rapport om utebliven leverans</span><span class="sxs-lookup"><span data-stu-id="bb135-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="bb135-108">Om du klickar på widgeten för **ej leverans rapporter** tas du till **rapporten för ej leverans**.</span><span class="sxs-lookup"><span data-stu-id="bb135-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="bb135-109">Aktiviteten för alla felkoder visas som standard.</span><span class="sxs-lookup"><span data-stu-id="bb135-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="bb135-110">Om du klickar på **Visa data för**kan du välja en specifik felkod i list rutan.</span><span class="sxs-lookup"><span data-stu-id="bb135-110">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="bb135-111">Om du hovrar över en viss färg (felkod) på en viss dag i diagrammet visas det totala antalet meddelanden för felet.</span><span class="sxs-lookup"><span data-stu-id="bb135-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Rapportvy i rapporten icke godkänd domän](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="bb135-113">Vyn detaljerad lista för rapport om utebliven leverans</span><span class="sxs-lookup"><span data-stu-id="bb135-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="bb135-114">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="bb135-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="bb135-115">**Datum**</span><span class="sxs-lookup"><span data-stu-id="bb135-115">**Date**</span></span>
- <span data-ttu-id="bb135-116">**Rapport kod för ej leverans**</span><span class="sxs-lookup"><span data-stu-id="bb135-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="bb135-117">**Öka**</span><span class="sxs-lookup"><span data-stu-id="bb135-117">**Count**</span></span>
- <span data-ttu-id="bb135-118">**Exempel meddelanden**: meddelande-ID för ett urval av påverkade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="bb135-118">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="bb135-119">Om du klickar på **filter** i en detaljerad tabellvy kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="bb135-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bb135-120">Om du vill skicka rapporten för ett visst datum intervall till en eller flera mottagare klickar du på **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="bb135-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="bb135-121">När du markerar en rad i tabellen visas en utfällbar tabell med följande information:</span><span class="sxs-lookup"><span data-stu-id="bb135-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="bb135-122">**Datum**</span><span class="sxs-lookup"><span data-stu-id="bb135-122">**Date**</span></span>
- <span data-ttu-id="bb135-123">**Rapport kod för ej leverans**: du kan klicka på länken för att hitta mer information om orsakerna och lösningarna för den specifika felkoden.</span><span class="sxs-lookup"><span data-stu-id="bb135-123">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="bb135-124">**Öka**</span><span class="sxs-lookup"><span data-stu-id="bb135-124">**Count**</span></span>
- <span data-ttu-id="bb135-125">**Exempel meddelanden**: du kan klicka på **Visa exempel meddelanden** om du vill visa [meddelande spårnings](message-trace-scc.md) resultaten för ett prov av de påverkade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="bb135-125">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Utfällda detaljer när du har markerat en rad i Tabellvy i rapporten för ej leverans](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="bb135-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bb135-127">Related topics</span></span>

<span data-ttu-id="bb135-128">Information om andra insikter i instrument panelen för e-postflöden finns i avsnittet om [hur du använder e-postflöde i säkerhets & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bb135-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
