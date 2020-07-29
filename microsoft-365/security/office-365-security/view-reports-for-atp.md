---
title: Visa rapporter för avancerat hotskydd
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Hitta och använda rapporter för avancerat skydd mot office 365 i &amp; Säkerhetsefterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4210ea30457215f9adc2984f24f161dc94985873
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434131"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="86c91-103">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="86c91-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="86c91-104">Office 365 Atp-organisationer (Advanced Threat Protection) (till exempel Microsoft 365 E5-prenumerationer eller ATP-abonnemang 1 eller ATP-abonnemang 2) innehåller en mängd säkerhetsrelaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="86c91-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="86c91-105">Om du har [de behörigheter som krävs](#what-permissions-are-needed-to-view-the-atp-reports)kan du visa dessa rapporter i Security & Compliance Center genom att gå till **Reports** \> **Instrumentpanelen**för rapporter .</span><span class="sxs-lookup"><span data-stu-id="86c91-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="86c91-106">Om du vill gå direkt till instrumentpanelen för rapporter öppnar du <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="86c91-106">To go directly to the reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrumentpanelen Rapporter i security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="86c91-108">Rapport över avancerade filtyper för hotskydd</span><span class="sxs-lookup"><span data-stu-id="86c91-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="86c91-109">Rapporten **Avancerat skydd mot hotfiltyper** visar vilken typ av filer som har identifierats som skadliga av [ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="86c91-110">Den sammanlagda vyn av rapporten tillåter 90 dagars filtrering, medan detaljvyn endast tillåter 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="86c91-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="86c91-111">Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för Rapporter** och väljer Office \> **Dashboard** **ATP-filtyper**.</span><span class="sxs-lookup"><span data-stu-id="86c91-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="86c91-112">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="86c91-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widgeten Office ATP-filtyper i instrumentpanelen Rapporter](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="86c91-114">Informationen i den här rapporten finns också i [rapporten Disposition för avancerat skydd mot skydd.](#advanced-threat-protection-message-disposition-report)</span><span class="sxs-lookup"><span data-stu-id="86c91-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="86c91-115">Rapportvy för rapporten Avancerad skyddsskydd</span><span class="sxs-lookup"><span data-stu-id="86c91-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="86c91-116">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="86c91-116">The following views are available:</span></span>

- <span data-ttu-id="86c91-117">**Visa data efter: Fil:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="86c91-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="86c91-118">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="86c91-119">**Skadliga Flash-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="86c91-120">**Skadliga PDF-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="86c91-121">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="86c91-122">**Skadliga webbadresser**</span><span class="sxs-lookup"><span data-stu-id="86c91-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="86c91-123">**Bifogade filer med skadliga Word**</span><span class="sxs-lookup"><span data-stu-id="86c91-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="86c91-124">**Skadliga körbara bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="86c91-125">**Andra**</span><span class="sxs-lookup"><span data-stu-id="86c91-125">**Others**</span></span>

  <span data-ttu-id="86c91-126">När du hovrar över en viss dag (datapunkt) kan du se fördelningen av typer av skadliga filer som upptäcktes av [ATP Safe Attachments](atp-safe-attachments.md) och [skydd mot skadlig kod i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Filvy i ATP-filtyperrapporten](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="86c91-128">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-129">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-130">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="86c91-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="86c91-131">**Visa data efter: Meddelande**: Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="86c91-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="86c91-132">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="86c91-132">**Block access**</span></span>
  - <span data-ttu-id="86c91-133">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="86c91-133">**Messages replaced**</span></span>
  - <span data-ttu-id="86c91-134">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="86c91-134">**Messages monitored**</span></span>
  - <span data-ttu-id="86c91-135">**Ersatt av dynamisk e-postleverans:** Mer information finns i [Dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Meddelandevy i ATP-filtyperrapporten](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="86c91-137">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-138">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-139">Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.</span><span class="sxs-lookup"><span data-stu-id="86c91-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="86c91-140">Informationstabellvy för rapporten Avancerad skyddsskydd</span><span class="sxs-lookup"><span data-stu-id="86c91-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="86c91-141">Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid över alla klick som inträffar inom organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="86c91-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="86c91-142">Vilken information som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="86c91-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="86c91-143">**Visa data efter: Arkiv:**</span><span class="sxs-lookup"><span data-stu-id="86c91-143">**View data by: File**:</span></span>

  - <span data-ttu-id="86c91-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="86c91-144">**Date**</span></span>
  - <span data-ttu-id="86c91-145">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="86c91-145">**Recipient address**</span></span>
  - <span data-ttu-id="86c91-146">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="86c91-146">**Sender address**</span></span>
  - <span data-ttu-id="86c91-147">**Meddelande-ID:** Tillgängligt i fältet **Meddelande-ID-huvud** i meddelandehuvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="86c91-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="86c91-148">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (notera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="86c91-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="86c91-149">**ﬁlen**</span><span class="sxs-lookup"><span data-stu-id="86c91-149">**File**</span></span>

  <span data-ttu-id="86c91-150">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-151">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-152">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="86c91-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="86c91-153">**Visa data efter: Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="86c91-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="86c91-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="86c91-154">**Date**</span></span>
  - <span data-ttu-id="86c91-155">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="86c91-155">**Recipient address**</span></span>
  - <span data-ttu-id="86c91-156">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="86c91-156">**Sender address**</span></span>
  - <span data-ttu-id="86c91-157">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="86c91-157">**Message ID**</span></span>
  - <span data-ttu-id="86c91-158">**ﬁlen**</span><span class="sxs-lookup"><span data-stu-id="86c91-158">**File**</span></span>
  - <span data-ttu-id="86c91-159">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="86c91-159">**Subject**</span></span>

  <span data-ttu-id="86c91-160">Om du klickar på **Filter**kan du ändra resultaten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="86c91-161">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-162">Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.</span><span class="sxs-lookup"><span data-stu-id="86c91-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="86c91-163">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="86c91-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="86c91-164">Dispositionsrapport för avancerat skydd mot skydd</span><span class="sxs-lookup"><span data-stu-id="86c91-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="86c91-165">**Atp-meddelandedispositionsrapporten** visar de åtgärder som har vidtagits för e-postmeddelanden som har identifierats som skadliga innehåll.</span><span class="sxs-lookup"><span data-stu-id="86c91-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="86c91-166">Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer Office \> **Dashboard** **ATP-meddelandedisposition**.</span><span class="sxs-lookup"><span data-stu-id="86c91-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="86c91-167">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="86c91-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Office 365 ATP-meddelandedispositionswidget i instrumentpanelen Rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="86c91-169">Informationen i den här rapporten finns också i [rapporten Avancerade typer av hotskydd](#advanced-threat-protection-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="86c91-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="86c91-170">Rapportvy för meddelandedispositionsrapporten för avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="86c91-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="86c91-171">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="86c91-171">The following views are available:</span></span>

- <span data-ttu-id="86c91-172">**Visa data efter: Meddelande**: Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="86c91-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="86c91-173">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="86c91-173">**Block access**</span></span>
  - <span data-ttu-id="86c91-174">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="86c91-174">**Messages replaced**</span></span>
  - <span data-ttu-id="86c91-175">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="86c91-175">**Messages monitored**</span></span>
  - <span data-ttu-id="86c91-176">**Ersatt av dynamisk e-postleverans:** Mer information finns i [Dynamisk leverans och förhandsgranskning med ATP Säkra bilagor](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Meddelandevy i ATP-filtyperrapporten](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="86c91-178">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-179">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-180">Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.</span><span class="sxs-lookup"><span data-stu-id="86c91-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="86c91-181">**Visa data efter: Fil:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="86c91-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="86c91-182">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="86c91-183">**Skadliga Flash-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="86c91-184">**Skadliga PDF-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="86c91-185">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="86c91-186">**Skadliga webbadresser**</span><span class="sxs-lookup"><span data-stu-id="86c91-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="86c91-187">**Bifogade filer med skadliga Word**</span><span class="sxs-lookup"><span data-stu-id="86c91-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="86c91-188">**Skadliga körbara bilagor**</span><span class="sxs-lookup"><span data-stu-id="86c91-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="86c91-189">**Andra**</span><span class="sxs-lookup"><span data-stu-id="86c91-189">**Others**</span></span>

  <span data-ttu-id="86c91-190">När du hovrar över en viss dag (datapunkt) kan du se fördelningen av typer av skadliga filer som upptäcktes av [ATP Safe Attachments](atp-safe-attachments.md) och [skydd mot skadlig kod i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Filvy i ATP-filtyperrapporten](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="86c91-192">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-193">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-194">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="86c91-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="86c91-195">Informationstabellvy för meddelandedispositionsrapporten för avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="86c91-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="86c91-196">Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid över alla klick som inträffar inom organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="86c91-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="86c91-197">Vilken information som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="86c91-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="86c91-198">**Visa data efter: Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="86c91-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="86c91-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="86c91-199">**Date**</span></span>
  - <span data-ttu-id="86c91-200">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="86c91-200">**Recipient address**</span></span>
  - <span data-ttu-id="86c91-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="86c91-201">**Sender address**</span></span>
  - <span data-ttu-id="86c91-202">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="86c91-202">**Message ID**</span></span>
  - <span data-ttu-id="86c91-203">**ﬁlen**</span><span class="sxs-lookup"><span data-stu-id="86c91-203">**File**</span></span>
  - <span data-ttu-id="86c91-204">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="86c91-204">**Subject**</span></span>

  <span data-ttu-id="86c91-205">Om du klickar på **Filter**kan du ändra resultaten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="86c91-206">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-207">Samma meddelandedispositionsvärden som är tillgängliga i diagrammet och det ytterligare **meddelandebelåtet** värde.</span><span class="sxs-lookup"><span data-stu-id="86c91-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="86c91-208">**Visa data efter: Arkiv:**</span><span class="sxs-lookup"><span data-stu-id="86c91-208">**View data by: File**:</span></span>

  - <span data-ttu-id="86c91-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="86c91-209">**Date**</span></span>
  - <span data-ttu-id="86c91-210">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="86c91-210">**Recipient address**</span></span>
  - <span data-ttu-id="86c91-211">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="86c91-211">**Sender address**</span></span>
  - <span data-ttu-id="86c91-212">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="86c91-212">**Message ID**</span></span>
  - <span data-ttu-id="86c91-213">**ﬁlen**</span><span class="sxs-lookup"><span data-stu-id="86c91-213">**File**</span></span>

  <span data-ttu-id="86c91-214">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-215">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-216">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="86c91-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="86c91-217">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="86c91-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="86c91-218">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="86c91-218">Threat protection status report</span></span>

<span data-ttu-id="86c91-219">**Statusrapporten för hotskydd** är en enda vy som samlar information om skadligt innehåll och skadlig e-post som upptäckts och blockerats av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="86c91-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="86c91-220">Mer information finns i [statusrapport för hotskydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="86c91-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="86c91-221">Rapport om skydd av URL-hot</span><span class="sxs-lookup"><span data-stu-id="86c91-221">URL threat protection report</span></span>

<span data-ttu-id="86c91-222">**Rapporten för skydd av URL-hot** innehåller sammanfattnings- och trendvyer för upptäckta hot och åtgärder som vidtas på URL-klick som en del av [ATP Safe Links](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="86c91-223">Den här rapporten kommer inte att ha klickdata från användare där principen Säkra länkar tillämpas har alternativet **Spåra inte användarens klick** markerat.</span><span class="sxs-lookup"><span data-stu-id="86c91-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="86c91-224">Om du vill visa rapporten öppnar du [Security & Compliance Center,](https://protection.office.com)går till **Instrumentpanelen för rapporter** och väljer \> **Dashboard** **URL-skyddsrapport**.</span><span class="sxs-lookup"><span data-stu-id="86c91-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="86c91-225">Öppna om du vill gå direkt till rapporten <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="86c91-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widgeten URL-skyddsrapport på instrumentpanelen Rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="86c91-227">Det här är en *trendrapport*för skydd , vilket innebär att data representerar trender i en större datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="86c91-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="86c91-228">Därför är data i den aggregerade vyn inte tillgängliga i realtid här, men data i detaljtabellvyn är, så du kan se en liten diskrepans mellan de två vyerna.</span><span class="sxs-lookup"><span data-stu-id="86c91-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="86c91-229">Rapportvy för rapporten om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="86c91-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="86c91-230">**Url-hotskyddsrapporten** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:</span><span class="sxs-lookup"><span data-stu-id="86c91-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="86c91-231">**URL klicka skydd åtgärd**: Visar antalet URL klick av användare i organisationen och resultatet av klick:</span><span class="sxs-lookup"><span data-stu-id="86c91-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="86c91-232">**Blockerade**</span><span class="sxs-lookup"><span data-stu-id="86c91-232">**Blocked**</span></span>
  - <span data-ttu-id="86c91-233">**Blockerad och klickad igenom**</span><span class="sxs-lookup"><span data-stu-id="86c91-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="86c91-234">**Klickade igenom under genomsökningen**</span><span class="sxs-lookup"><span data-stu-id="86c91-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="86c91-235">Ett klick anger att användaren har klickat sig igenom blocksidan till den skadliga webbplatsen (administratörer kan inaktivera klickning i principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="86c91-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="86c91-236">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-237">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-238">De tillgängliga klickskyddsåtgärderna, plus värdet **Tillåten** att se information för alla URL-klick (inte bara blockerade klick).</span><span class="sxs-lookup"><span data-stu-id="86c91-238">The available click protection actions, plus the value **Allowed** to see information for all URL clicks (not just blocked clicks).</span></span>

  ![URL-klickskyddsåtgärdsvyn i rapporten för skydd mot URL-hot](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="86c91-240">**URL-klick för program**: Visar antalet URL-klick för program som stöder säkra länkar i Office 365 ATP:</span><span class="sxs-lookup"><span data-stu-id="86c91-240">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="86c91-241">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="86c91-241">**Email client**</span></span>
  - <span data-ttu-id="86c91-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="86c91-242">**PowerPoint**</span></span>
  - <span data-ttu-id="86c91-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="86c91-243">**Word**</span></span>
  - <span data-ttu-id="86c91-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="86c91-244">**Excel**</span></span>
  - <span data-ttu-id="86c91-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="86c91-245">**OneNote**</span></span>
  - <span data-ttu-id="86c91-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="86c91-246">**Visio**</span></span>
  - <span data-ttu-id="86c91-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="86c91-247">**Teams**</span></span>
  - <span data-ttu-id="86c91-248">**Annat**</span><span class="sxs-lookup"><span data-stu-id="86c91-248">**Other**</span></span>

  <span data-ttu-id="86c91-249">Om du klickar på **Filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="86c91-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="86c91-250">**Startdatum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="86c91-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="86c91-251">Tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="86c91-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="86c91-252">Informationstabellvy för rapporten om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="86c91-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="86c91-253">Om du klickar på **Visa informationstabell**ger rapporten en vy i nära realtid av alla klick som sker inom organisationen under de senaste sju dagarna med följande information:</span><span class="sxs-lookup"><span data-stu-id="86c91-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="86c91-254">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="86c91-254">**Click time**</span></span>
- <span data-ttu-id="86c91-255">**Användare**</span><span class="sxs-lookup"><span data-stu-id="86c91-255">**User**</span></span>
- <span data-ttu-id="86c91-256">**Url**</span><span class="sxs-lookup"><span data-stu-id="86c91-256">**URL**</span></span>
- <span data-ttu-id="86c91-257">**Åtgärder**</span><span class="sxs-lookup"><span data-stu-id="86c91-257">**Action**</span></span>
- <span data-ttu-id="86c91-258">**Program**</span><span class="sxs-lookup"><span data-stu-id="86c91-258">**App**</span></span>

<span data-ttu-id="86c91-259">Om du klickar på **Filter** i detaljtabellvyn kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="86c91-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="86c91-260">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="86c91-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="86c91-261">Ytterligare rapporter att visa</span><span class="sxs-lookup"><span data-stu-id="86c91-261">Additional reports to view</span></span>

<span data-ttu-id="86c91-262">Förutom de ATP-rapporter som beskrivs i det här avsnittet finns flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="86c91-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="86c91-263">Rapport</span><span class="sxs-lookup"><span data-stu-id="86c91-263">Report</span></span>|<span data-ttu-id="86c91-264">Ämne</span><span class="sxs-lookup"><span data-stu-id="86c91-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="86c91-265">**Explorer** (ATP Plan 2) eller **realtidsidentifieringar** (ATP-plan 1)</span><span class="sxs-lookup"><span data-stu-id="86c91-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="86c91-266">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="86c91-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="86c91-267">**Säkerhetsrapporter för e-post**, till exempel rapporten Toppavsändare och mottagare, rapporten Spoof-e-post och rapporten Skräppostidentifieringar.</span><span class="sxs-lookup"><span data-stu-id="86c91-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="86c91-268">Visa säkerhetsrapporter för e-post i Säkerhets- & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="86c91-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="86c91-269">**E-postflödesrapporter**, till exempel rapporten Vidarebefordran, statusrapporten för e-postflödet och rapporten Toppavsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="86c91-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="86c91-270">Visa e-postflödesrapporter i Säkerhets- & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="86c91-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="86c91-271">**URL-spårning för ATP-säkra länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="86c91-271">**URL trace for ATP Safe Links** (PowerShell only).</span></span> <span data-ttu-id="86c91-272">Utdata från den här cmdleten visar resultatet av ATP Safe Links-åtgärder under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="86c91-272">The output of this cmdlet shows you the results of ATP Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="86c91-273">Få-urltrace</span><span class="sxs-lookup"><span data-stu-id="86c91-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="86c91-274">**E-posttrafikresultat för EOP och ATP** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="86c91-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="86c91-275">Utdata för den här cmdleten innehåller information om domän, datum, händelsetyp, riktning, åtgärd och meddelanderäkning.</span><span class="sxs-lookup"><span data-stu-id="86c91-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="86c91-276">Hämta-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="86c91-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport) <br/><br/> |
|<span data-ttu-id="86c91-277">**E-postinformationsrapporter för EOP- och ATP-identifieringar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="86c91-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="86c91-278">Utdata från den här cmdleten innehåller information om skadliga filer eller webbadresser, nätfiskeförsök, personifiering och andra potentiella hot i e-post eller filer.</span><span class="sxs-lookup"><span data-stu-id="86c91-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="86c91-279">Hämta-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="86c91-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="86c91-280">Vilka behörigheter behövs för att visa ATP-rapporterna?</span><span class="sxs-lookup"><span data-stu-id="86c91-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="86c91-281">Om du vill visa och använda de rapporter som beskrivs i det här avsnittet **måste du ha en lämplig roll tilldelad för både Security Compliance Center och &amp; Administrationscenter för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="86c91-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="86c91-282">För Security & Compliance Center måste du ha tilldelats någon av följande roller:</span><span class="sxs-lookup"><span data-stu-id="86c91-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="86c91-283">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="86c91-283">Organization Management</span></span>
  - <span data-ttu-id="86c91-284">Säkerhetsadministratör (detta kan tilldelas i Administrationscentret för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="86c91-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="86c91-285">Säkerhetsoperatör (detta kan tilldelas i Administrationscentret för Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="86c91-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="86c91-286">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="86c91-286">Security Reader</span></span>

- <span data-ttu-id="86c91-287">För Exchange Online måste du ha någon av följande roller tilldelad i administrationscentret för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) eller med PowerShell-cmdletar (se [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="86c91-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="86c91-288">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="86c91-288">Organization Management</span></span>
  - <span data-ttu-id="86c91-289">Organisationshantering endast med enbart vy</span><span class="sxs-lookup"><span data-stu-id="86c91-289">View-only Organization Management</span></span>
  - <span data-ttu-id="86c91-290">Rollen Endast visa mottagare</span><span class="sxs-lookup"><span data-stu-id="86c91-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="86c91-291">Hantering av efterlevnad</span><span class="sxs-lookup"><span data-stu-id="86c91-291">Compliance Management</span></span>

<span data-ttu-id="86c91-292">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="86c91-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="86c91-293">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="86c91-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="86c91-294">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="86c91-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="86c91-295">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="86c91-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="86c91-296">Om du inte ser data i ATP-rapporterna dubbelkollar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="86c91-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="86c91-297">Din organisation måste ha [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) och [ATP-principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) definierade för att ATP-skydd ska vara på plats.</span><span class="sxs-lookup"><span data-stu-id="86c91-297">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="86c91-298">Se även [skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="86c91-298">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="86c91-299">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="86c91-299">Related topics</span></span>

[<span data-ttu-id="86c91-300">Smarta rapporter och insikter i Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="86c91-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="86c91-301">Rollbehörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="86c91-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
