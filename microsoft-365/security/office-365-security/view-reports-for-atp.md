---
title: Visa Defender för Office 365-rapporter i instrument panelen rapporter
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Hitta och använda rapporter för Microsoft Defender för Office 365 i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82c003478538274be1dd1d2e04816de80d1eae6d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659459"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="94776-103">Visa Defender för Office 365-rapporter i rapport instrument panelen i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="94776-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="94776-104">Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365 abonnemang 1 eller Microsoft Defender för Office 365 abonnemang 2 tillägg) innehåller flera olika säkerhets relaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="94776-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="94776-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till  \> **instrument panelen** för rapporter.</span><span class="sxs-lookup"><span data-stu-id="94776-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="94776-106">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="94776-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panelen för rapporter i säkerhets & efterlevnad](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="94776-108">Rapport om fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="94776-109">I rapporten **Defender för Office 365-filtyper** visas en typ av filer som identifieras i skadlig kod för [bifogade](atp-safe-attachments.md)filer.</span><span class="sxs-lookup"><span data-stu-id="94776-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="94776-110">I den sammanställda vyn i rapporten kan du använda 90 dagar för att filtrera den, men i detaljvyn kan du bara tillåta 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="94776-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="94776-111">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **Defender för Office 365-filtyper**.</span><span class="sxs-lookup"><span data-stu-id="94776-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="94776-112">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="94776-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget för Office 365-filtyper i rapport instrument panelen](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="94776-114">Informationen i den här rapporten är också tillgänglig i [meddelande dispositions rapporten för Defender för Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="94776-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="94776-115">Rapportvy för rapporten fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="94776-116">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="94776-116">The following views are available:</span></span>

- <span data-ttu-id="94776-117">**Visa data genom: fil**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="94776-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="94776-118">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="94776-119">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="94776-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="94776-120">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="94776-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="94776-121">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="94776-122">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="94776-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="94776-123">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="94776-124">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="94776-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="94776-125">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="94776-125">**Others**</span></span>

  <span data-ttu-id="94776-126">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="94776-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="94776-128">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-129">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-130">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="94776-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="94776-131">**Visa data via: meddelande**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="94776-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="94776-132">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="94776-132">**Block access**</span></span>
  - <span data-ttu-id="94776-133">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="94776-133">**Messages replaced**</span></span>
  - <span data-ttu-id="94776-134">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="94776-134">**Messages monitored**</span></span>
  - <span data-ttu-id="94776-135">**Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="94776-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="94776-137">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-138">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-139">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="94776-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="94776-140">Vyn detaljerad tabell för fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="94776-141">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="94776-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="94776-142">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="94776-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="94776-143">**Visa data per: fil**:</span><span class="sxs-lookup"><span data-stu-id="94776-143">**View data by: File**:</span></span>

  - <span data-ttu-id="94776-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="94776-144">**Date**</span></span>
  - <span data-ttu-id="94776-145">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-145">**Recipient address**</span></span>
  - <span data-ttu-id="94776-146">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-146">**Sender address**</span></span>
  - <span data-ttu-id="94776-147">**Meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="94776-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="94776-148">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="94776-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="94776-149">**Fil**</span><span class="sxs-lookup"><span data-stu-id="94776-149">**File**</span></span>

  <span data-ttu-id="94776-150">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-151">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-152">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="94776-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="94776-153">**Visa data via: meddelande**:</span><span class="sxs-lookup"><span data-stu-id="94776-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="94776-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="94776-154">**Date**</span></span>
  - <span data-ttu-id="94776-155">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-155">**Recipient address**</span></span>
  - <span data-ttu-id="94776-156">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-156">**Sender address**</span></span>
  - <span data-ttu-id="94776-157">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="94776-157">**Message ID**</span></span>
  - <span data-ttu-id="94776-158">**Fil**</span><span class="sxs-lookup"><span data-stu-id="94776-158">**File**</span></span>
  - <span data-ttu-id="94776-159">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="94776-159">**Subject**</span></span>

  <span data-ttu-id="94776-160">Om du klickar på **filter** kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="94776-161">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-162">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="94776-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="94776-163">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="94776-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="94776-164">Meddelande disposition för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="94776-165">I rapporten för att visa **ATP** visas de åtgärder som vidtogs för e-postmeddelanden som identifierats som skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="94776-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="94776-166">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **Defender för Office 365 meddelande disposition**.</span><span class="sxs-lookup"><span data-stu-id="94776-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="94776-167">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="94776-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget för Defender för Office 365 meddelande dispositioner i instrument panelen rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="94776-169">Informationen i den här rapporten är också tillgänglig i [rapporten fil typer i Defender för Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="94776-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="94776-170">Rapportvy för meddelande dispositions rapport för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="94776-171">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="94776-171">The following views are available:</span></span>

- <span data-ttu-id="94776-172">**Visa data via: meddelande**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="94776-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="94776-173">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="94776-173">**Block access**</span></span>
  - <span data-ttu-id="94776-174">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="94776-174">**Messages replaced**</span></span>
  - <span data-ttu-id="94776-175">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="94776-175">**Messages monitored**</span></span>
  - <span data-ttu-id="94776-176">**Ersatt med dynamisk e-postleverans**: Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="94776-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="94776-178">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-179">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-180">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="94776-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="94776-181">**Visa data genom: fil**: diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="94776-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="94776-182">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="94776-183">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="94776-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="94776-184">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="94776-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="94776-185">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="94776-186">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="94776-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="94776-187">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="94776-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="94776-188">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="94776-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="94776-189">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="94776-189">**Others**</span></span>

  <span data-ttu-id="94776-190">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="94776-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="94776-192">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-193">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-194">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="94776-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="94776-195">Vyn detaljerad tabell för meddelande dispositionen för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="94776-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="94776-196">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="94776-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="94776-197">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="94776-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="94776-198">**Visa data via: meddelande**:</span><span class="sxs-lookup"><span data-stu-id="94776-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="94776-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="94776-199">**Date**</span></span>
  - <span data-ttu-id="94776-200">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-200">**Recipient address**</span></span>
  - <span data-ttu-id="94776-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-201">**Sender address**</span></span>
  - <span data-ttu-id="94776-202">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="94776-202">**Message ID**</span></span>
  - <span data-ttu-id="94776-203">**Fil**</span><span class="sxs-lookup"><span data-stu-id="94776-203">**File**</span></span>
  - <span data-ttu-id="94776-204">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="94776-204">**Subject**</span></span>

  <span data-ttu-id="94776-205">Om du klickar på **filter** kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="94776-206">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-207">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="94776-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="94776-208">**Visa data per: fil**:</span><span class="sxs-lookup"><span data-stu-id="94776-208">**View data by: File**:</span></span>

  - <span data-ttu-id="94776-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="94776-209">**Date**</span></span>
  - <span data-ttu-id="94776-210">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-210">**Recipient address**</span></span>
  - <span data-ttu-id="94776-211">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="94776-211">**Sender address**</span></span>
  - <span data-ttu-id="94776-212">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="94776-212">**Message ID**</span></span>
  - <span data-ttu-id="94776-213">**Fil**</span><span class="sxs-lookup"><span data-stu-id="94776-213">**File**</span></span>

  <span data-ttu-id="94776-214">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-215">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-216">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="94776-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="94776-217">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="94776-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="94776-218">E-postrapport</span><span class="sxs-lookup"><span data-stu-id="94776-218">Mail latency report</span></span>

<span data-ttu-id="94776-219">I **rapporten e-postsvars tid** visas en sammanslagen för leverans-och spräng tiden i din organisation.</span><span class="sxs-lookup"><span data-stu-id="94776-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="94776-220">Leverans tiden för e-post påverkas av många faktorer och den absoluta leverans tiden i sekunder är ofta inte en bra indikation på framgång eller ett problem.</span><span class="sxs-lookup"><span data-stu-id="94776-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="94776-221">En långsam leverans tid på en dag kan betraktas som en genomsnittlig leverans tid på en annan dag, eller tvärtom.</span><span class="sxs-lookup"><span data-stu-id="94776-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="94776-222">I **rapporten e-postsvars tid** görs ett försök att kvalificera meddelande leverans baserat på statistik om den observerade leverans tiden för andra meddelanden:</span><span class="sxs-lookup"><span data-stu-id="94776-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="94776-223">**femtio percentil**: det här är mitten för leverans tider för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="94776-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="94776-224">Du kan betrakta detta värde som en genomsnittlig leverans tid.</span><span class="sxs-lookup"><span data-stu-id="94776-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="94776-225">**nittionde percentil**: Detta indikerar en hög latens för meddelande leverans.</span><span class="sxs-lookup"><span data-stu-id="94776-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="94776-226">Det tog längre tid än 10 procent av meddelandena att leverera.</span><span class="sxs-lookup"><span data-stu-id="94776-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="94776-227">**99th percentil**: här visas den högsta svars tiden för meddelande leverans.</span><span class="sxs-lookup"><span data-stu-id="94776-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="94776-228">Klient sidan och nätverks fördröjningen ingår inte.</span><span class="sxs-lookup"><span data-stu-id="94776-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="94776-229">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till  \> **instrument paneler** för rapporter och väljer **rapport om e-postsvar**.</span><span class="sxs-lookup"><span data-stu-id="94776-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="94776-230">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="94776-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget för tids rapport för e-post i instrument panelen rapporter](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="94776-232">Rapportvy för rapport om e-postsvar</span><span class="sxs-lookup"><span data-stu-id="94776-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="94776-233">När du öppnar rapporten är fliken **femtio percentil** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="94776-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="94776-234">Som standard innehåller den här vyn ett diagram som är konfigurerat med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="94776-235">**Datum**: de senaste 7 dagarna</span><span class="sxs-lookup"><span data-stu-id="94776-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="94776-236">**Meddelande vy**:</span><span class="sxs-lookup"><span data-stu-id="94776-236">**Message View**:</span></span>
  - <span data-ttu-id="94776-237">Översprängta meddelanden</span><span class="sxs-lookup"><span data-stu-id="94776-237">Detonated messages</span></span>

<span data-ttu-id="94776-238">I det här diagrammet visas meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="94776-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="94776-239">**Leverans svars tid för e-post**</span><span class="sxs-lookup"><span data-stu-id="94776-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="94776-240">**Fördröjning för sprängning**</span><span class="sxs-lookup"><span data-stu-id="94776-240">**Detonation latency**</span></span>

<span data-ttu-id="94776-241">När du hovrar över en kategori i diagrammet kan du se en uppdelning av svars tiden i varje kategori.</span><span class="sxs-lookup"><span data-stu-id="94776-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![E-postrapport](../../media/mail-latency-report.png)

<span data-ttu-id="94776-243">Om du klickar på **filter** i rapportvyn kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="94776-244">Alla meddelanden</span><span class="sxs-lookup"><span data-stu-id="94776-244">All messages</span></span>
- <span data-ttu-id="94776-245">Meddelanden som innehåller bilagor eller URL: er</span><span class="sxs-lookup"><span data-stu-id="94776-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="94776-246">Om du klickar på fliken **nittionde percentiler** eller på fliken **99th percentiler** används samma standard filter från vyn **50 percentiler** .</span><span class="sxs-lookup"><span data-stu-id="94776-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="94776-247">Vyn detaljerad tabell för rapporten e-postsvar</span><span class="sxs-lookup"><span data-stu-id="94776-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="94776-248">Följande information visas i vyn detaljerad tabell:</span><span class="sxs-lookup"><span data-stu-id="94776-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="94776-249">**Datum**</span><span class="sxs-lookup"><span data-stu-id="94776-249">**Date**</span></span>
- <span data-ttu-id="94776-250">**Värden**</span><span class="sxs-lookup"><span data-stu-id="94776-250">**Percentiles**</span></span>
- <span data-ttu-id="94776-251">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="94776-251">**Message count**</span></span>
- <span data-ttu-id="94776-252">**Total svars tid**</span><span class="sxs-lookup"><span data-stu-id="94776-252">**Overall latency**</span></span>

![Rapport information om e-postsvar](../../media/mail-latency-report-details.png)

<span data-ttu-id="94776-254">Ovanstående visar att genomsnittlig tids åtgång den 14 november för alla meddelanden som levererats och sprängat sig **108,033** sekunder.</span><span class="sxs-lookup"><span data-stu-id="94776-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="94776-255">Tabellen information innehåller samma information på varje flik.</span><span class="sxs-lookup"><span data-stu-id="94776-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="94776-256">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="94776-256">Threat protection status report</span></span>

<span data-ttu-id="94776-257">Status rapporten för **hotets skydd** är en enkel vy som innehåller information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="94776-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="94776-258">För mer information, se [status rapport för hot skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="94776-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="94776-259">Rapport om skydd mot URL-hotet</span><span class="sxs-lookup"><span data-stu-id="94776-259">URL threat protection report</span></span>

<span data-ttu-id="94776-260">**Rapporten skydd mot URL-hotet** innehåller översikts-och trend lägen för hot som upptäcks och åtgärder som vidtas på URL-adresser till vissa [säkra länkar](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="94776-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="94776-261">Den här rapporten kommer inte att behöva klicka på data från användare där **principen för Safe** Links har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="94776-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="94776-262">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **URL-skydd**.</span><span class="sxs-lookup"><span data-stu-id="94776-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="94776-263">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="94776-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widgeten rapport om URL-skydd i instrument panelen rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="94776-265">Det här är en *skydds trend rapport* som visar trender i en större data mängd.</span><span class="sxs-lookup"><span data-stu-id="94776-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="94776-266">Därför är data i den aggregerade vyn inte tillgängliga i real tid, men data i vyn detaljerad tabell är så att du kan se en liten avvikelse mellan de två vyerna.</span><span class="sxs-lookup"><span data-stu-id="94776-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="94776-267">Rapportvy för rapport om URL-Threat</span><span class="sxs-lookup"><span data-stu-id="94776-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="94776-268">Rapporten **skydd mot URL-hotet** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:</span><span class="sxs-lookup"><span data-stu-id="94776-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="94776-269">**Webb adress klicka på skydds åtgärd**: visar antalet URL-musklick efter användare i organisationen och resultatet av klickning:</span><span class="sxs-lookup"><span data-stu-id="94776-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="94776-270">**Blockerad** (användaren hindrades från att gå till URL-adressen)</span><span class="sxs-lookup"><span data-stu-id="94776-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="94776-271">**Blockerad och klickat genom**</span><span class="sxs-lookup"><span data-stu-id="94776-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="94776-272">**Klickning genom under genomsökning**</span><span class="sxs-lookup"><span data-stu-id="94776-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="94776-273">Ett klick visar att användaren har klickat via block sidan till webbplatsen för illasinnade webbplatser (administratörer kan inaktivera Klicka genom i principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="94776-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="94776-274">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-275">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-276">De tillgängliga Klicka på skydds åtgärder plus värdet som **tillåts** (användaren kunde navigera till URL: en).</span><span class="sxs-lookup"><span data-stu-id="94776-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-adress klicka på skydds åtgärd i rapporten URL-skydd](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="94776-278">**URL-adress klicka** här: visar antalet URL-musklick med program som stöder säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="94776-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="94776-279">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="94776-279">**Email client**</span></span>
  - <span data-ttu-id="94776-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="94776-280">**PowerPoint**</span></span>
  - <span data-ttu-id="94776-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="94776-281">**Word**</span></span>
  - <span data-ttu-id="94776-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="94776-282">**Excel**</span></span>
  - <span data-ttu-id="94776-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="94776-283">**OneNote**</span></span>
  - <span data-ttu-id="94776-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="94776-284">**Visio**</span></span>
  - <span data-ttu-id="94776-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="94776-285">**Teams**</span></span>
  - <span data-ttu-id="94776-286">**Annat**</span><span class="sxs-lookup"><span data-stu-id="94776-286">**Other**</span></span>

  <span data-ttu-id="94776-287">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="94776-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="94776-288">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="94776-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="94776-289">Tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="94776-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="94776-290">Vyn detaljerad tabell för rapportering av URL-hotet</span><span class="sxs-lookup"><span data-stu-id="94776-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="94776-291">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 7 dagarna med följande information:</span><span class="sxs-lookup"><span data-stu-id="94776-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="94776-292">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="94776-292">**Click time**</span></span>
- <span data-ttu-id="94776-293">**Användare**</span><span class="sxs-lookup"><span data-stu-id="94776-293">**User**</span></span>
- <span data-ttu-id="94776-294">**:**</span><span class="sxs-lookup"><span data-stu-id="94776-294">**URL**</span></span>
- <span data-ttu-id="94776-295">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="94776-295">**Action**</span></span>
- <span data-ttu-id="94776-296">**Program**</span><span class="sxs-lookup"><span data-stu-id="94776-296">**App**</span></span>

<span data-ttu-id="94776-297">Om du klickar på **filter** i vyn detaljerad tabell kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="94776-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="94776-298">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="94776-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="94776-299">Ytterligare rapporter att Visa</span><span class="sxs-lookup"><span data-stu-id="94776-299">Additional reports to view</span></span>

<span data-ttu-id="94776-300">Utöver de rapporter som beskrivs i den här artikeln är flera andra rapporter tillgängliga enligt följande tabell:</span><span class="sxs-lookup"><span data-stu-id="94776-300">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="94776-301">Rapport</span><span class="sxs-lookup"><span data-stu-id="94776-301">Report</span></span>|<span data-ttu-id="94776-302">Ämnes</span><span class="sxs-lookup"><span data-stu-id="94776-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="94776-303">**Explorer** (Microsoft Defender för Office 365 abonnemang 2) eller **real tids identifiering** (microsoft Defender för Office 365 abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="94776-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="94776-304">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="94776-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="94776-305">**Säkerhets rapporter för e-post**, till exempel rapporten Top avsändare och mottagare, rapporten Spoof meddelanden och rapporten skräp identifiering.</span><span class="sxs-lookup"><span data-stu-id="94776-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="94776-306">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="94776-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="94776-307">**E-postflödes rapporter**, till exempel vidarebefordran, rapporten flödes schema och rapport om avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="94776-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="94776-308">Visa rapporter om e-postflöden i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="94776-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="94776-309">**URL-spårning för säkra länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="94776-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="94776-310">Utdata från denna cmdlet visar resultaten av åtgärder för säkra länkar under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="94776-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="94776-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="94776-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="94776-312">**Resultat för e-posttrafik för EOP och Microsoft Defender för Office 365** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="94776-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="94776-313">Utdata från den här cmdleten innehåller information om domäner, datum, händelse typ, riktning, åtgärd och antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="94776-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="94776-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="94776-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="94776-315">**E-postdetaljerade rapporter för EOP och Defender för Office 365-identifiering** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="94776-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="94776-316">Utdata från den här cmdleten innehåller information om skadliga filer och URL-adresser, nät fiske försök, personifiering och andra potentiella hot i e-post och filer.</span><span class="sxs-lookup"><span data-stu-id="94776-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="94776-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="94776-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="94776-318">Vilka behörigheter behövs för att Visa Defender för Office 365-rapporterna?</span><span class="sxs-lookup"><span data-stu-id="94776-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="94776-319">För att kunna visa och använda de rapporter som beskrivs i den här artikeln måste du vara medlem i någon av följande roll grupper i säkerhets & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="94776-319">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="94776-320">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="94776-320">**Organization Management**</span></span>
- <span data-ttu-id="94776-321">**Säkerhets administratör**</span><span class="sxs-lookup"><span data-stu-id="94776-321">**Security Administrator**</span></span>
- <span data-ttu-id="94776-322">**Säkerhets läsare**</span><span class="sxs-lookup"><span data-stu-id="94776-322">**Security Reader**</span></span>
- <span data-ttu-id="94776-323">**Global läsare**</span><span class="sxs-lookup"><span data-stu-id="94776-323">**Global Reader**</span></span>

<span data-ttu-id="94776-324">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="94776-324">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="94776-325">**Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="94776-325">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="94776-326">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="94776-326">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="94776-327">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="94776-327">What if the reports aren't showing data?</span></span>

<span data-ttu-id="94776-328">Om du inte ser data i din Defender för Office 365-rapporter kontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="94776-328">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="94776-329">Din organisation måste ha principer för [säkert](set-up-atp-safe-links-policies.md) och [bifogade filer](set-up-atp-safe-attachments-policies.md) definierade för att Defender för Office 365-skydd ska vara installerat.</span><span class="sxs-lookup"><span data-stu-id="94776-329">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="94776-330">Se även [antiskräppost-och skydd mot skadlig program vara](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="94776-330">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="94776-331">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="94776-331">Related topics</span></span>

[<span data-ttu-id="94776-332">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="94776-332">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="94776-333">Roll behörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="94776-333">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
