---
title: Visa rapporter för Defender för Office 365
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
description: Hitta och använda rapporter för Microsoft Defender för Office 365 i säkerhetsrelaterade &amp; Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b24249bcbba60bc5340d973567369f534a0178fb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842922"
---
# <a name="view-reports-for-microsoft-defender-for-office-365"></a><span data-ttu-id="fdb11-103">Visa rapporter för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-103">View reports for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="fdb11-104">Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365 abonnemang 1 eller Microsoft Defender för Office 365 abonnemang 2 tillägg) innehåller flera olika säkerhets relaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="fdb11-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="fdb11-105">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till **Reports** \> **instrument panelen** för rapporter.</span><span class="sxs-lookup"><span data-stu-id="fdb11-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fdb11-106">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="fdb11-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panelen för rapporter i säkerhets & efterlevnad](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="fdb11-108">Rapport om fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="fdb11-109">I rapporten **Defender för Office 365-filtyper** visas en typ av filer som identifieras i skadlig kod för [bifogade](atp-safe-attachments.md)filer.</span><span class="sxs-lookup"><span data-stu-id="fdb11-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="fdb11-110">I den sammanställda vyn i rapporten kan du använda 90 dagar för att filtrera den, men i detaljvyn kan du bara tillåta 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="fdb11-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="fdb11-111">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Defender för Office 365-filtyper**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="fdb11-112">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="fdb11-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget för Office 365-filtyper i rapport instrument panelen](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fdb11-114">Informationen i den här rapporten är också tillgänglig i [meddelande dispositions rapporten för Defender för Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="fdb11-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="fdb11-115">Rapportvy för rapporten fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="fdb11-116">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="fdb11-116">The following views are available:</span></span>

- <span data-ttu-id="fdb11-117">**Visa data genom: fil** : diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="fdb11-117">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fdb11-118">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fdb11-119">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fdb11-120">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fdb11-121">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fdb11-122">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="fdb11-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="fdb11-123">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fdb11-124">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fdb11-125">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="fdb11-125">**Others**</span></span>

  <span data-ttu-id="fdb11-126">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fdb11-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fdb11-128">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-128">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-129">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-130">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="fdb11-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fdb11-131">**Visa data via: meddelande** : diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="fdb11-131">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fdb11-132">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="fdb11-132">**Block access**</span></span>
  - <span data-ttu-id="fdb11-133">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="fdb11-133">**Messages replaced**</span></span>
  - <span data-ttu-id="fdb11-134">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="fdb11-134">**Messages monitored**</span></span>
  - <span data-ttu-id="fdb11-135">**Ersatt med dynamisk e-postleverans** : Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="fdb11-135">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fdb11-137">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-137">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-138">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-139">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="fdb11-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="fdb11-140">Vyn detaljerad tabell för fil typer i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="fdb11-141">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="fdb11-141">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fdb11-142">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="fdb11-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fdb11-143">**Visa data per: fil** :</span><span class="sxs-lookup"><span data-stu-id="fdb11-143">**View data by: File** :</span></span>

  - <span data-ttu-id="fdb11-144">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-144">**Date**</span></span>
  - <span data-ttu-id="fdb11-145">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-145">**Recipient address**</span></span>
  - <span data-ttu-id="fdb11-146">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-146">**Sender address**</span></span>
  - <span data-ttu-id="fdb11-147">**Meddelande-ID** : tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="fdb11-147">**Message ID** : Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="fdb11-148">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="fdb11-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="fdb11-149">**Fil**</span><span class="sxs-lookup"><span data-stu-id="fdb11-149">**File**</span></span>

  <span data-ttu-id="fdb11-150">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-150">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-151">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-152">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="fdb11-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="fdb11-153">**Visa data via: meddelande** :</span><span class="sxs-lookup"><span data-stu-id="fdb11-153">**View data by: Message** :</span></span>

  - <span data-ttu-id="fdb11-154">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-154">**Date**</span></span>
  - <span data-ttu-id="fdb11-155">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-155">**Recipient address**</span></span>
  - <span data-ttu-id="fdb11-156">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-156">**Sender address**</span></span>
  - <span data-ttu-id="fdb11-157">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="fdb11-157">**Message ID**</span></span>
  - <span data-ttu-id="fdb11-158">**Fil**</span><span class="sxs-lookup"><span data-stu-id="fdb11-158">**File**</span></span>
  - <span data-ttu-id="fdb11-159">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="fdb11-159">**Subject**</span></span>

  <span data-ttu-id="fdb11-160">Om du klickar på **filter** kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-160">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fdb11-161">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-162">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="fdb11-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="fdb11-163">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fdb11-164">Meddelande disposition för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fdb11-165">I rapporten för att visa **ATP** visas de åtgärder som vidtogs för e-postmeddelanden som identifierats som skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="fdb11-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="fdb11-166">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **Defender för Office 365 meddelande disposition**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="fdb11-167">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="fdb11-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget för Defender för Office 365 meddelande dispositioner i instrument panelen rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fdb11-169">Informationen i den här rapporten är också tillgänglig i [rapporten fil typer i Defender för Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="fdb11-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fdb11-170">Rapportvy för meddelande dispositions rapport för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fdb11-171">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="fdb11-171">The following views are available:</span></span>

- <span data-ttu-id="fdb11-172">**Visa data via: meddelande** : diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="fdb11-172">**View data by: Message** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fdb11-173">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="fdb11-173">**Block access**</span></span>
  - <span data-ttu-id="fdb11-174">**Meddelanden ersatta**</span><span class="sxs-lookup"><span data-stu-id="fdb11-174">**Messages replaced**</span></span>
  - <span data-ttu-id="fdb11-175">**Meddelanden som övervakas**</span><span class="sxs-lookup"><span data-stu-id="fdb11-175">**Messages monitored**</span></span>
  - <span data-ttu-id="fdb11-176">**Ersatt med dynamisk e-postleverans** : Mer information finns i [dynamisk leverans i principer för säkra bifogade filer](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="fdb11-176">**Replaced by Dynamic Email Delivery** : For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Vyn meddelande i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="fdb11-178">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-178">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-179">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-180">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="fdb11-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fdb11-181">**Visa data genom: fil** : diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="fdb11-181">**View data by: File** : The chart contains the following information:</span></span>

  - <span data-ttu-id="fdb11-182">**Skadliga Excel-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="fdb11-183">**Skadliga Flash-filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="fdb11-184">**Skadliga PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="fdb11-185">**Skadliga PowerPoint-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="fdb11-186">**Illasinnade URL: er**</span><span class="sxs-lookup"><span data-stu-id="fdb11-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="fdb11-187">**Skadliga Word-bilagor**</span><span class="sxs-lookup"><span data-stu-id="fdb11-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="fdb11-188">**Skadliga körbara filer**</span><span class="sxs-lookup"><span data-stu-id="fdb11-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="fdb11-189">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="fdb11-189">**Others**</span></span>

  <span data-ttu-id="fdb11-190">När du håller mus pekaren över en viss dag (data punkt) kan du se en uppdelning av skadliga filer som identifieras av [säkra bifogade filer](atp-safe-attachments.md) och [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fdb11-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vyn Arkiv i rapporten fil typer i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="fdb11-192">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-192">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-193">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-194">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="fdb11-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="fdb11-195">Vyn detaljerad tabell för meddelande dispositionen för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="fdb11-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="fdb11-196">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="fdb11-196">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="fdb11-197">Informationen som visas beror på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="fdb11-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fdb11-198">**Visa data via: meddelande** :</span><span class="sxs-lookup"><span data-stu-id="fdb11-198">**View data by: Message** :</span></span>

  - <span data-ttu-id="fdb11-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-199">**Date**</span></span>
  - <span data-ttu-id="fdb11-200">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-200">**Recipient address**</span></span>
  - <span data-ttu-id="fdb11-201">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-201">**Sender address**</span></span>
  - <span data-ttu-id="fdb11-202">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="fdb11-202">**Message ID**</span></span>
  - <span data-ttu-id="fdb11-203">**Fil**</span><span class="sxs-lookup"><span data-stu-id="fdb11-203">**File**</span></span>
  - <span data-ttu-id="fdb11-204">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="fdb11-204">**Subject**</span></span>

  <span data-ttu-id="fdb11-205">Om du klickar på **filter** kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-205">If you click **Filters** , you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="fdb11-206">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-207">Samma meddelande dispositions värden som är tillgängliga i diagrammet och ytterligare **meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="fdb11-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="fdb11-208">**Visa data per: fil** :</span><span class="sxs-lookup"><span data-stu-id="fdb11-208">**View data by: File** :</span></span>

  - <span data-ttu-id="fdb11-209">**Datum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-209">**Date**</span></span>
  - <span data-ttu-id="fdb11-210">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-210">**Recipient address**</span></span>
  - <span data-ttu-id="fdb11-211">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="fdb11-211">**Sender address**</span></span>
  - <span data-ttu-id="fdb11-212">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="fdb11-212">**Message ID**</span></span>
  - <span data-ttu-id="fdb11-213">**Fil**</span><span class="sxs-lookup"><span data-stu-id="fdb11-213">**File**</span></span>

  <span data-ttu-id="fdb11-214">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-214">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-215">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-216">Samma fil typs värden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="fdb11-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="fdb11-217">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="fdb11-218">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="fdb11-218">Threat protection status report</span></span>

<span data-ttu-id="fdb11-219">Status rapporten för **hotets skydd** är en enkel vy som innehåller information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="fdb11-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="fdb11-220">För mer information, se [status rapport för hot skydd](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="fdb11-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="fdb11-221">Rapport om skydd mot URL-hotet</span><span class="sxs-lookup"><span data-stu-id="fdb11-221">URL threat protection report</span></span>

<span data-ttu-id="fdb11-222">**Rapporten skydd mot URL-hotet** innehåller översikts-och trend lägen för hot som upptäcks och åtgärder som vidtas på URL-adresser till vissa [säkra länkar](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="fdb11-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="fdb11-223">Den här rapporten kommer inte att behöva klicka på data från användare där **principen för Safe** Links har Aktiver ATS.</span><span class="sxs-lookup"><span data-stu-id="fdb11-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="fdb11-224">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **URL-skydd**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="fdb11-225">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="fdb11-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widgeten rapport om URL-skydd i instrument panelen rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="fdb11-227">Det här är en *skydds trend rapport* som visar trender i en större data mängd.</span><span class="sxs-lookup"><span data-stu-id="fdb11-227">This is a *protection trend report* , meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="fdb11-228">Därför är data i den aggregerade vyn inte tillgängliga i real tid, men data i vyn detaljerad tabell är så att du kan se en liten avvikelse mellan de två vyerna.</span><span class="sxs-lookup"><span data-stu-id="fdb11-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fdb11-229">Rapportvy för rapport om URL-Threat</span><span class="sxs-lookup"><span data-stu-id="fdb11-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="fdb11-230">Rapporten **skydd mot URL-hotet** har två aggregerade vyer som uppdateras en gång var fjärde timme som visar data för de senaste 90 dagarna:</span><span class="sxs-lookup"><span data-stu-id="fdb11-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="fdb11-231">**Webb adress klicka på skydds åtgärd** : visar antalet URL-musklick efter användare i organisationen och resultatet av klickning:</span><span class="sxs-lookup"><span data-stu-id="fdb11-231">**URL click protection action** : Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="fdb11-232">**Blockerad** (användaren hindrades från att gå till URL-adressen)</span><span class="sxs-lookup"><span data-stu-id="fdb11-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="fdb11-233">**Blockerad och klickat genom**</span><span class="sxs-lookup"><span data-stu-id="fdb11-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="fdb11-234">**Klickning genom under genomsökning**</span><span class="sxs-lookup"><span data-stu-id="fdb11-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="fdb11-235">Ett klick visar att användaren har klickat via block sidan till webbplatsen för illasinnade webbplatser (administratörer kan inaktivera Klicka genom i principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="fdb11-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="fdb11-236">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-236">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-237">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-238">De tillgängliga Klicka på skydds åtgärder plus värdet som **tillåts** (användaren kunde navigera till URL: en).</span><span class="sxs-lookup"><span data-stu-id="fdb11-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL-adress klicka på skydds åtgärd i rapporten URL-skydd](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="fdb11-240">**URL-adress klicka** här: visar antalet URL-musklick med program som stöder säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="fdb11-240">**URL click by application** : Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="fdb11-241">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="fdb11-241">**Email client**</span></span>
  - <span data-ttu-id="fdb11-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="fdb11-242">**PowerPoint**</span></span>
  - <span data-ttu-id="fdb11-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="fdb11-243">**Word**</span></span>
  - <span data-ttu-id="fdb11-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="fdb11-244">**Excel**</span></span>
  - <span data-ttu-id="fdb11-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="fdb11-245">**OneNote**</span></span>
  - <span data-ttu-id="fdb11-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="fdb11-246">**Visio**</span></span>
  - <span data-ttu-id="fdb11-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="fdb11-247">**Teams**</span></span>
  - <span data-ttu-id="fdb11-248">**Annat**</span><span class="sxs-lookup"><span data-stu-id="fdb11-248">**Other**</span></span>

  <span data-ttu-id="fdb11-249">Om du klickar på **filter** kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="fdb11-249">If you click **Filters** , you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="fdb11-250">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="fdb11-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="fdb11-251">Tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="fdb11-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="fdb11-252">Vyn detaljerad tabell för rapportering av URL-hotet</span><span class="sxs-lookup"><span data-stu-id="fdb11-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="fdb11-253">Om du klickar på **Visa informations tabell** visas en vy i real tid av alla klickningar i organisationen under de senaste 7 dagarna med följande information:</span><span class="sxs-lookup"><span data-stu-id="fdb11-253">If you click **View details table** , the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="fdb11-254">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="fdb11-254">**Click time**</span></span>
- <span data-ttu-id="fdb11-255">**Användare**</span><span class="sxs-lookup"><span data-stu-id="fdb11-255">**User**</span></span>
- <span data-ttu-id="fdb11-256">**:**</span><span class="sxs-lookup"><span data-stu-id="fdb11-256">**URL**</span></span>
- <span data-ttu-id="fdb11-257">**Fattning**</span><span class="sxs-lookup"><span data-stu-id="fdb11-257">**Action**</span></span>
- <span data-ttu-id="fdb11-258">**Program**</span><span class="sxs-lookup"><span data-stu-id="fdb11-258">**App**</span></span>

<span data-ttu-id="fdb11-259">Om du klickar på **filter** i vyn detaljerad tabell kan du filtrera efter samma villkor som i rapportvyn och även efter **domäner** eller **mottagare** avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="fdb11-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="fdb11-260">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="fdb11-261">Ytterligare rapporter att Visa</span><span class="sxs-lookup"><span data-stu-id="fdb11-261">Additional reports to view</span></span>

<span data-ttu-id="fdb11-262">Utöver de rapporter som beskrivs i det här avsnittet är flera andra rapporter tillgängliga, enligt följande tabell:</span><span class="sxs-lookup"><span data-stu-id="fdb11-262">In addition to the reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="fdb11-263">Rapport</span><span class="sxs-lookup"><span data-stu-id="fdb11-263">Report</span></span>|<span data-ttu-id="fdb11-264">Ämnes</span><span class="sxs-lookup"><span data-stu-id="fdb11-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="fdb11-265">**Explorer** (Microsoft Defender för Office 365 abonnemang 2) eller **real tids identifiering** (microsoft Defender för Office 365 abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="fdb11-265">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="fdb11-266">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="fdb11-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="fdb11-267">**Säkerhets rapporter för e-post** , till exempel rapporten Top avsändare och mottagare, rapporten Spoof meddelanden och rapporten skräp identifiering.</span><span class="sxs-lookup"><span data-stu-id="fdb11-267">**Email security reports** , such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="fdb11-268">Visa säkerhets rapporter för e-post i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="fdb11-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="fdb11-269">**E-postflödes rapporter** , till exempel vidarebefordran, rapporten flödes schema och rapport om avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="fdb11-269">**Mail flow reports** , such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="fdb11-270">Visa rapporter om e-postflöden i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="fdb11-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="fdb11-271">**URL-spårning för säkra länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fdb11-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="fdb11-272">Utdata från denna cmdlet visar resultaten av åtgärder för säkra länkar under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="fdb11-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="fdb11-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="fdb11-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="fdb11-274">**Resultat för e-posttrafik för EOP och Microsoft Defender för Office 365** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fdb11-274">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="fdb11-275">Utdata från den här cmdleten innehåller information om domäner, datum, händelse typ, riktning, åtgärd och antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="fdb11-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="fdb11-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="fdb11-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="fdb11-277">**E-postdetaljerade rapporter för EOP och Defender för Office 365-identifiering** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fdb11-277">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="fdb11-278">Utdata från den här cmdleten innehåller information om skadliga filer och URL-adresser, nät fiske försök, personifiering och andra potentiella hot i e-post och filer.</span><span class="sxs-lookup"><span data-stu-id="fdb11-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="fdb11-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="fdb11-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="fdb11-280">Vilka behörigheter behövs för att Visa Defender för Office 365-rapporterna?</span><span class="sxs-lookup"><span data-stu-id="fdb11-280">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="fdb11-281">För att kunna visa och använda de rapporter som beskrivs i det här avsnittet **måste du ha en lämplig roll kopplad till både säkerhets &amp; kontroll Center och administrations centret för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fdb11-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="fdb11-282">För säkerhets & Compliance Center måste du ha någon av följande roller tilldelade:</span><span class="sxs-lookup"><span data-stu-id="fdb11-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="fdb11-283">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="fdb11-283">Organization Management</span></span>
  - <span data-ttu-id="fdb11-284">Säkerhets administratör (detta kan tilldelas i Azure Active Directory Admin Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="fdb11-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fdb11-285">Säkerhets ansvarig (detta kan tilldelas i Azure Active Directory-administratörs Center ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="fdb11-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="fdb11-286">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="fdb11-286">Security Reader</span></span>

- <span data-ttu-id="fdb11-287">För Exchange Online måste du ha någon av följande roller tilldelade i antingen administrations centret för Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) eller med PowerShell-cmdletar (se [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="fdb11-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="fdb11-288">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="fdb11-288">Organization Management</span></span>
  - <span data-ttu-id="fdb11-289">Organisations hantering för endast visning</span><span class="sxs-lookup"><span data-stu-id="fdb11-289">View-only Organization Management</span></span>
  - <span data-ttu-id="fdb11-290">Roll för View-Only mottagare</span><span class="sxs-lookup"><span data-stu-id="fdb11-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="fdb11-291">Hantering av efterlevnad</span><span class="sxs-lookup"><span data-stu-id="fdb11-291">Compliance Management</span></span>

<span data-ttu-id="fdb11-292">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="fdb11-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="fdb11-293">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="fdb11-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="fdb11-294">Behörigheter för funktioner i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fdb11-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="fdb11-295">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="fdb11-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="fdb11-296">Om du inte ser data i din Defender för Office 365-rapporter kontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="fdb11-296">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="fdb11-297">Din organisation måste ha principer för [säkert](set-up-atp-safe-links-policies.md) och [bifogade filer](set-up-atp-safe-attachments-policies.md) definierade för att Defender för Office 365-skydd ska vara installerat.</span><span class="sxs-lookup"><span data-stu-id="fdb11-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="fdb11-298">Se även [antiskräppost-och skydd mot skadlig program vara](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="fdb11-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fdb11-299">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="fdb11-299">Related topics</span></span>

[<span data-ttu-id="fdb11-300">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="fdb11-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="fdb11-301">Roll behörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fdb11-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
