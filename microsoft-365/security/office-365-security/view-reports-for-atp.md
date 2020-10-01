---
title: Visa rapporter för avancerat skydd
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
description: Hitta och använda rapporter för Office 365 Avancerat skydd för säkerhets &amp; Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16fef101f722a23b3a64d91c85c2f946c67036f0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328041"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="cc056-103">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="cc056-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cc056-104">Office 365 organisationer för avancerat skydd (ATP) (till exempel Microsoft 365 E5-prenumerationer eller ATP-abonnemang 1 eller ATP-abonnemang 2 tillägg) innehåller en mängd säkerhets relaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="cc056-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="cc056-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-the-atp-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="cc056-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="cc056-106">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="cc056-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panelen för rapporter i säkerhets & efterlevnad](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="cc056-108">Filtypsrapporter för ATP</span><span class="sxs-lookup"><span data-stu-id="cc056-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="cc056-109">I rapporten **avancerade skydds filtyper** visas en typ av filer som identifieras som skadliga [bifogade filer](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="cc056-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="cc056-110">I den sammanställda vyn i rapporten kan du använda 90 dagar för att filtrera den, men i detaljvyn kan du bara tillåta 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="cc056-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="cc056-111">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **typer av Office ATP-filer**.</span><span class="sxs-lookup"><span data-stu-id="cc056-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="cc056-112">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="cc056-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widgeten fil typer för Office ATP i instrument panelen rapporter](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="cc056-114">Informationen i den här rapporten är också tillgänglig i [rapporten för avancerat skydds meddelande](#advanced-threat-protection-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="cc056-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="cc056-115">Rapportvy för rapporten avancerade filtyper för avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="cc056-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="cc056-116">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="cc056-116">The following views are available:</span></span>

- <span data-ttu-id="cc056-117">**Visa data genom: fil**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="cc056-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="cc056-118">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="cc056-119">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="cc056-120">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="cc056-121">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="cc056-122">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="cc056-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="cc056-123">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="cc056-124">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="cc056-125">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="cc056-125">**Others**</span></span>

  <span data-ttu-id="cc056-126">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cc056-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn fil i rapporten ATP-filtyper](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="cc056-128">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-129">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-130">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="cc056-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="cc056-131">**Visa data via: meddelande**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="cc056-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="cc056-132">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="cc056-132">**Block access**</span></span>
  - <span data-ttu-id="cc056-133">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="cc056-133">**Messages replaced**</span></span>
  - <span data-ttu-id="cc056-134">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="cc056-134">**Messages monitored**</span></span>
  - <span data-ttu-id="cc056-135">**Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="cc056-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten typer av ATP-filer](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="cc056-137">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-138">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-139">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="cc056-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="cc056-140">Detaljerad tabellvy för rapporten avancerade skydds filtyper</span><span class="sxs-lookup"><span data-stu-id="cc056-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="cc056-141">Om du klickar på **Visa informations tabell**visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="cc056-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="cc056-142">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="cc056-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cc056-143">**Visa data per: fil**:</span><span class="sxs-lookup"><span data-stu-id="cc056-143">**View data by: File**:</span></span>

  - <span data-ttu-id="cc056-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="cc056-144">**Date**</span></span>
  - <span data-ttu-id="cc056-145">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-145">**Recipient address**</span></span>
  - <span data-ttu-id="cc056-146">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-146">**Sender address**</span></span>
  - <span data-ttu-id="cc056-147">**Meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="cc056-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="cc056-148">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="cc056-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="cc056-149">**Fil**</span><span class="sxs-lookup"><span data-stu-id="cc056-149">**File**</span></span>

  <span data-ttu-id="cc056-150">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-151">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-152">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="cc056-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="cc056-153">**Visa data via: meddelande**:</span><span class="sxs-lookup"><span data-stu-id="cc056-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="cc056-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="cc056-154">**Date**</span></span>
  - <span data-ttu-id="cc056-155">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-155">**Recipient address**</span></span>
  - <span data-ttu-id="cc056-156">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-156">**Sender address**</span></span>
  - <span data-ttu-id="cc056-157">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="cc056-157">**Message ID**</span></span>
  - <span data-ttu-id="cc056-158">**Fil**</span><span class="sxs-lookup"><span data-stu-id="cc056-158">**File**</span></span>
  - <span data-ttu-id="cc056-159">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="cc056-159">**Subject**</span></span>

  <span data-ttu-id="cc056-160">Om du klickar på **filter**kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="cc056-161">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-162">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="cc056-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="cc056-163">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="cc056-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="cc056-164">Meddelandedispositionsrapport för ATP</span><span class="sxs-lookup"><span data-stu-id="cc056-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="cc056-165">I rapporten för att visa **ATP** visas de åtgärder som vidtogs för e-postmeddelanden som identifierats som skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="cc056-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="cc056-166">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **dispositionen för Office ATP-meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="cc056-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="cc056-167">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="cc056-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Office 365-widget för ATP-meddelande i instrument panelen rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="cc056-169">Informationen i den här rapporten är också tillgänglig i [rapporten om filtyper för avancerat skydd](#advanced-threat-protection-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="cc056-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="cc056-170">Rapportvy för rapport om Avancerat skydds meddelande</span><span class="sxs-lookup"><span data-stu-id="cc056-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="cc056-171">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="cc056-171">The following views are available:</span></span>

- <span data-ttu-id="cc056-172">**Visa data via: meddelande**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="cc056-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="cc056-173">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="cc056-173">**Block access**</span></span>
  - <span data-ttu-id="cc056-174">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="cc056-174">**Messages replaced**</span></span>
  - <span data-ttu-id="cc056-175">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="cc056-175">**Messages monitored**</span></span>
  - <span data-ttu-id="cc056-176">**Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="cc056-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten typer av ATP-filer](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="cc056-178">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-179">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-180">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="cc056-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="cc056-181">**Visa data genom: fil**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="cc056-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="cc056-182">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="cc056-183">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="cc056-184">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="cc056-185">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="cc056-186">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="cc056-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="cc056-187">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="cc056-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="cc056-188">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="cc056-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="cc056-189">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="cc056-189">**Others**</span></span>

  <span data-ttu-id="cc056-190">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cc056-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn fil i rapporten ATP-filtyper](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="cc056-192">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-193">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-194">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="cc056-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="cc056-195">Detaljerad tabellvy för rapport om Avancerat skydds meddelande disposition</span><span class="sxs-lookup"><span data-stu-id="cc056-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="cc056-196">Om du klickar på **Visa informations tabell**visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="cc056-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="cc056-197">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="cc056-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="cc056-198">**Visa data via: meddelande**:</span><span class="sxs-lookup"><span data-stu-id="cc056-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="cc056-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="cc056-199">**Date**</span></span>
  - <span data-ttu-id="cc056-200">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-200">**Recipient address**</span></span>
  - <span data-ttu-id="cc056-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-201">**Sender address**</span></span>
  - <span data-ttu-id="cc056-202">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="cc056-202">**Message ID**</span></span>
  - <span data-ttu-id="cc056-203">**Fil**</span><span class="sxs-lookup"><span data-stu-id="cc056-203">**File**</span></span>
  - <span data-ttu-id="cc056-204">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="cc056-204">**Subject**</span></span>

  <span data-ttu-id="cc056-205">Om du klickar på **filter**kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="cc056-206">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-207">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="cc056-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="cc056-208">**Visa data per: fil**:</span><span class="sxs-lookup"><span data-stu-id="cc056-208">**View data by: File**:</span></span>

  - <span data-ttu-id="cc056-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="cc056-209">**Date**</span></span>
  - <span data-ttu-id="cc056-210">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-210">**Recipient address**</span></span>
  - <span data-ttu-id="cc056-211">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="cc056-211">**Sender address**</span></span>
  - <span data-ttu-id="cc056-212">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="cc056-212">**Message ID**</span></span>
  - <span data-ttu-id="cc056-213">**Fil**</span><span class="sxs-lookup"><span data-stu-id="cc056-213">**File**</span></span>

  <span data-ttu-id="cc056-214">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-215">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-216">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="cc056-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="cc056-217">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="cc056-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cc056-218">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="cc056-218">Threat protection status report</span></span>

<span data-ttu-id="cc056-219">Status rapporten för **hotets skydd** är en enkel vy som innehåller information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="cc056-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="cc056-220">För mer information, se [status rapport för hot skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="cc056-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="cc056-221">Rapport om skydd mot URL-hotet</span><span class="sxs-lookup"><span data-stu-id="cc056-221">URL threat protection report</span></span>

<span data-ttu-id="cc056-222">**Rapporten skydd mot URL-hotet** innehåller översikts-och trend lägen för hot som upptäcks och åtgärder som vidtas på URL-adresser till vissa [säkra länkar](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="cc056-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="cc056-223">Den här rapporten kommer inte att behöva klicka på data från användare där **principen för Safe** Links har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="cc056-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="cc056-224">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **URL-skydd**.</span><span class="sxs-lookup"><span data-stu-id="cc056-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="cc056-225">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="cc056-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widgeten rapport om URL-skydd i instrument panelen rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="cc056-227">Det här är en *skydds trend rapport*som visar trender i en större data mängd.</span><span class="sxs-lookup"><span data-stu-id="cc056-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="cc056-228">Därför är data i den aggregerade vyn inte tillgängliga i real tid, men data i vyn detaljerad tabell är så att du kan se en liten avvikelse mellan de två vyerna.</span><span class="sxs-lookup"><span data-stu-id="cc056-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="cc056-229">Rapportvy för rapport om URL-Threat</span><span class="sxs-lookup"><span data-stu-id="cc056-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="cc056-230">Rapporten **skydd mot URL-hotet** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:</span><span class="sxs-lookup"><span data-stu-id="cc056-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="cc056-231">**Webb adress klicka på skydds åtgärd**: visar antalet URL-musklick efter användare i organisationen och resultatet av klickning:</span><span class="sxs-lookup"><span data-stu-id="cc056-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="cc056-232">**Blockerad** (användaren hindrades från att gå till URL-adressen)</span><span class="sxs-lookup"><span data-stu-id="cc056-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="cc056-233">**Blockerad och klickat genom**</span><span class="sxs-lookup"><span data-stu-id="cc056-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="cc056-234">**Klickning genom under genomsökning**</span><span class="sxs-lookup"><span data-stu-id="cc056-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="cc056-235">Ett klick visar att användaren har klickat via block sidan till webbplatsen för illasinnade webbplatser (administratörer kan inaktivera Klicka genom i principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="cc056-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="cc056-236">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-237">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-238">De tillgängliga Klicka på skydds åtgärder plus värdet som **tillåts** (användaren kunde navigera till URL: en).</span><span class="sxs-lookup"><span data-stu-id="cc056-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-adress klicka på skydds åtgärd i rapporten URL-skydd](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="cc056-240">**URL-adress klicka**här: visar antalet URL-musklick med program som stöder säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="cc056-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="cc056-241">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="cc056-241">**Email client**</span></span>
  - <span data-ttu-id="cc056-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="cc056-242">**PowerPoint**</span></span>
  - <span data-ttu-id="cc056-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="cc056-243">**Word**</span></span>
  - <span data-ttu-id="cc056-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="cc056-244">**Excel**</span></span>
  - <span data-ttu-id="cc056-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="cc056-245">**OneNote**</span></span>
  - <span data-ttu-id="cc056-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="cc056-246">**Visio**</span></span>
  - <span data-ttu-id="cc056-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="cc056-247">**Teams**</span></span>
  - <span data-ttu-id="cc056-248">**Annat**</span><span class="sxs-lookup"><span data-stu-id="cc056-248">**Other**</span></span>

  <span data-ttu-id="cc056-249">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="cc056-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="cc056-250">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="cc056-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="cc056-251">Tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="cc056-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="cc056-252">Vyn detaljerad tabell för rapportering av URL-hotet</span><span class="sxs-lookup"><span data-stu-id="cc056-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="cc056-253">Om du klickar på **Visa informations tabell**visas en vy i real tid av alla klickningar i organisationen under de senaste 7 dagarna med följande information:</span><span class="sxs-lookup"><span data-stu-id="cc056-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="cc056-254">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="cc056-254">**Click time**</span></span>
- <span data-ttu-id="cc056-255">**Användare**</span><span class="sxs-lookup"><span data-stu-id="cc056-255">**User**</span></span>
- <span data-ttu-id="cc056-256">**:**</span><span class="sxs-lookup"><span data-stu-id="cc056-256">**URL**</span></span>
- <span data-ttu-id="cc056-257">**Fattning**</span><span class="sxs-lookup"><span data-stu-id="cc056-257">**Action**</span></span>
- <span data-ttu-id="cc056-258">**Program**</span><span class="sxs-lookup"><span data-stu-id="cc056-258">**App**</span></span>

<span data-ttu-id="cc056-259">Om du klickar på **filter** i vyn detaljerad tabell kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="cc056-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="cc056-260">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="cc056-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="cc056-261">Ytterligare rapporter att Visa</span><span class="sxs-lookup"><span data-stu-id="cc056-261">Additional reports to view</span></span>

<span data-ttu-id="cc056-262">Utöver de ATP-rapporter som beskrivs i det här avsnittet är flera andra rapporter tillgängliga enligt följande tabell:</span><span class="sxs-lookup"><span data-stu-id="cc056-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="cc056-263">Rapport</span><span class="sxs-lookup"><span data-stu-id="cc056-263">Report</span></span>|<span data-ttu-id="cc056-264">Ämnes</span><span class="sxs-lookup"><span data-stu-id="cc056-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="cc056-265">**Explorer** (ATP-abonnemang 2) eller **real tids identifiering** (ATP-abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="cc056-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="cc056-266">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="cc056-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="cc056-267">**Säkerhets rapporter för e-post**, till exempel rapporten Top avsändare och mottagare, rapporten Spoof meddelanden och rapporten skräp identifiering.</span><span class="sxs-lookup"><span data-stu-id="cc056-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="cc056-268">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cc056-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="cc056-269">**E-postflödes rapporter**, till exempel vidarebefordran, rapporten flödes schema och rapport om avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="cc056-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="cc056-270">Visa rapporter om e-postflöden i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="cc056-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="cc056-271">**URL-spårning för säkra länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cc056-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="cc056-272">Utdata från denna cmdlet visar resultaten av åtgärder för säkra länkar under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="cc056-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="cc056-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="cc056-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="cc056-274">**Resultat för e-posttrafik för EOP och ATP** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cc056-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="cc056-275">Utdata från den här cmdleten innehåller information om domäner, datum, händelse typ, riktning, åtgärd och antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="cc056-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="cc056-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="cc056-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="cc056-277">**E-postdetaljerad rapporter för EOP och ATP-identifiering** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cc056-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="cc056-278">Utdata från den här cmdleten innehåller information om skadliga filer och URL-adresser, nät fiske försök, personifiering och andra potentiella hot i e-post och filer.</span><span class="sxs-lookup"><span data-stu-id="cc056-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="cc056-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="cc056-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="cc056-280">Vilka behörigheter behövs för att Visa ATP-rapporter?</span><span class="sxs-lookup"><span data-stu-id="cc056-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="cc056-281">För att kunna visa och använda de rapporter som beskrivs i det här avsnittet **måste du ha en lämplig roll kopplad till både säkerhets &amp; kontroll Center och administrations centret för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="cc056-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="cc056-282">För säkerhets & Compliance Center måste du ha någon av följande roller tilldelade:</span><span class="sxs-lookup"><span data-stu-id="cc056-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="cc056-283">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="cc056-283">Organization Management</span></span>
  - <span data-ttu-id="cc056-284">Säkerhets administratör (detta kan tilldelas i Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="cc056-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="cc056-285">Säkerhets ansvarig (detta kan tilldelas i Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="cc056-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="cc056-286">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="cc056-286">Security Reader</span></span>

- <span data-ttu-id="cc056-287">För Exchange Online måste du ha någon av följande roller tilldelade i antingen administrations centret för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) eller med PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="cc056-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="cc056-288">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="cc056-288">Organization Management</span></span>
  - <span data-ttu-id="cc056-289">Organisations hantering för endast visning</span><span class="sxs-lookup"><span data-stu-id="cc056-289">View-only Organization Management</span></span>
  - <span data-ttu-id="cc056-290">Rollen skrivskyddade mottagare</span><span class="sxs-lookup"><span data-stu-id="cc056-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="cc056-291">Hantering av efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cc056-291">Compliance Management</span></span>

<span data-ttu-id="cc056-292">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="cc056-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="cc056-293">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="cc056-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="cc056-294">Behörigheter för funktioner i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cc056-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cc056-295">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="cc056-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cc056-296">Om du inte ser data i dina ATP-rapporter kontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="cc056-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cc056-297">Din organisation måste ha principer för [säkra länkar](set-up-atp-safe-links-policies.md) och [principer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md) har DEFINIERAts för att ATP-skydd ska finnas.</span><span class="sxs-lookup"><span data-stu-id="cc056-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="cc056-298">Se även [antiskräppost-och skydd mot skadlig program vara](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cc056-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc056-299">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="cc056-299">Related topics</span></span>

[<span data-ttu-id="cc056-300">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="cc056-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="cc056-301">Roll behörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc056-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
