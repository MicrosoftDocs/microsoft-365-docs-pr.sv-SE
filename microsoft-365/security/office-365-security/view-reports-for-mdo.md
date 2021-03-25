---
title: Visa Defender för Office 365-rapporter på instrumentpanelen Rapporter
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Hitta och använda rapporter för Microsoft Defender för Office 365 i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 28978dbca3f9e4039b4f8c21c49a2963802afa54
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207128"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="4a493-103">Visa Defender för Office 365-rapporter i instrumentpanelen Rapporter i & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4a493-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4a493-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4a493-104">**Applies to**</span></span>
- [<span data-ttu-id="4a493-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4a493-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4a493-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a493-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4a493-107">Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365-abonnemang 1 eller Microsoft Defender för tillägg för Office 365 abonnemang 2) innehåller ett antal olika säkerhetsrelaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="4a493-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="4a493-108">Om du har nödvändiga [behörigheter kan](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)du visa de här rapporterna i Säkerhets- & genom att gå till **Instrumentpanelen** \> **rapporter.**</span><span class="sxs-lookup"><span data-stu-id="4a493-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="4a493-109">Gå direkt till instrumentpanelen Rapporter genom att öppna <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="4a493-109">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrumentpanelen Rapporter i Säkerhets- & Säkerhets- och efterlevnadscenter](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="4a493-111">Typrapport för Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4a493-111">Defender for Office 365 file types report</span></span>

<span data-ttu-id="4a493-112">I **rapporten filtyper i Defender för Office 365** ser du vilken typ av filer som identifierats som skadliga av [säkra bifogade filer.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="4a493-112">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](safe-attachments.md).</span></span>

 <span data-ttu-id="4a493-113">Den samlade vyn för rapporten tillåter 90 dagars filtrering, medan detaljvyn bara tillåter 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="4a493-113">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="4a493-114">Om du vill visa rapporten öppnar du [Säkerhets- & Kompatibilitetscenter](https://protection.office.com), går till **instrumentpanelen** rapporter och väljer Defender för \>  **Office 365-filtyper.**</span><span class="sxs-lookup"><span data-stu-id="4a493-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="4a493-115">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="4a493-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Defender för Office 365-filtyperswidget på instrumentpanelen Rapporter](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="4a493-117">Informationen i den här rapporten är också tillgänglig i [meddelandedispositionsrapporten för Defender för Office 365.](#defender-for-office-365-message-disposition-report)</span><span class="sxs-lookup"><span data-stu-id="4a493-117">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="4a493-118">Rapportvyn för rapporten Om Defender för Office 365-filtyper</span><span class="sxs-lookup"><span data-stu-id="4a493-118">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="4a493-119">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4a493-119">The following views are available:</span></span>

- <span data-ttu-id="4a493-120">**Visa data efter: Arkiv:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="4a493-120">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="4a493-121">**Skadliga bifogade Excel-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-121">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="4a493-122">**Skadliga Flash-bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-122">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="4a493-123">**Skadliga bifogade PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-123">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="4a493-124">**Skadliga PowerPoint-bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-124">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="4a493-125">**Skadliga URL:er**</span><span class="sxs-lookup"><span data-stu-id="4a493-125">**Malicious URLs**</span></span>
  - <span data-ttu-id="4a493-126">**Skadliga bifogade Word-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-126">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="4a493-127">**Skadliga körbara bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-127">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="4a493-128">**Andra**</span><span class="sxs-lookup"><span data-stu-id="4a493-128">**Others**</span></span>

  <span data-ttu-id="4a493-129">När du hovrar över en viss dag (datapunkt) kan du se [](safe-attachments.md) detaljerad information om typer av skadliga filer som identifierats av Säkra bifogade filer och skydd mot [skadlig programvara i EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4a493-129">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Filvyn i rapporten om filtyper i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="4a493-131">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-131">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-132">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-132">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-133">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="4a493-133">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="4a493-134">**Visa data efter: Meddelande:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="4a493-134">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="4a493-135">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="4a493-135">**Block access**</span></span>
  - <span data-ttu-id="4a493-136">**Meddelanden har ersatts**</span><span class="sxs-lookup"><span data-stu-id="4a493-136">**Messages replaced**</span></span>
  - <span data-ttu-id="4a493-137">**Meddelanden övervakade**</span><span class="sxs-lookup"><span data-stu-id="4a493-137">**Messages monitored**</span></span>
  - <span data-ttu-id="4a493-138">**Ersatts av Dynamisk e-postleverans:** Mer information finns [i Principer för dynamisk leverans i säkra bifogade filer.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="4a493-138">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Meddelandevyn i rapporten om filtyper i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="4a493-140">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-140">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-141">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-141">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-142">Samma dispositionsvärden för meddelanden som är tillgängliga i diagrammet och ytterligare **Meddelanden som överförs..**</span><span class="sxs-lookup"><span data-stu-id="4a493-142">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="4a493-143">Detaljtabellvyn för filtyper i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4a493-143">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="4a493-144">Om du **klickar på Visa** informationstabell ger rapporten en nästan realtidsvy över alla klick som har hänt inom organisationen de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="4a493-144">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="4a493-145">Vilken information som visas beror på diagrammet du visade:</span><span class="sxs-lookup"><span data-stu-id="4a493-145">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4a493-146">**Visa data efter: Arkiv**:</span><span class="sxs-lookup"><span data-stu-id="4a493-146">**View data by: File**:</span></span>

  - <span data-ttu-id="4a493-147">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4a493-147">**Date**</span></span>
  - <span data-ttu-id="4a493-148">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="4a493-148">**Recipient address**</span></span>
  - <span data-ttu-id="4a493-149">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4a493-149">**Sender address**</span></span>
  - <span data-ttu-id="4a493-150">**Meddelande-ID:** Tillgängligt i **sidhuvudet för meddelande-ID** i meddelandehuvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="4a493-150">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="4a493-151">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="4a493-151">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="4a493-152">**Arkiv**</span><span class="sxs-lookup"><span data-stu-id="4a493-152">**File**</span></span>

  <span data-ttu-id="4a493-153">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-153">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-154">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-154">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-155">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="4a493-155">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="4a493-156">**Visa data efter: Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="4a493-156">**View data by: Message**:</span></span>

  - <span data-ttu-id="4a493-157">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4a493-157">**Date**</span></span>
  - <span data-ttu-id="4a493-158">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="4a493-158">**Recipient address**</span></span>
  - <span data-ttu-id="4a493-159">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4a493-159">**Sender address**</span></span>
  - <span data-ttu-id="4a493-160">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="4a493-160">**Message ID**</span></span>
  - <span data-ttu-id="4a493-161">**Arkiv**</span><span class="sxs-lookup"><span data-stu-id="4a493-161">**File**</span></span>
  - <span data-ttu-id="4a493-162">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4a493-162">**Subject**</span></span>

  <span data-ttu-id="4a493-163">Om du **klickar på** Filter kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-163">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="4a493-164">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-164">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-165">Samma dispositionsvärden för meddelanden som är tillgängliga i diagrammet och ytterligare **Meddelanden som överförs..**</span><span class="sxs-lookup"><span data-stu-id="4a493-165">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="4a493-166">Gå tillbaka till rapportvyn genom att klicka på **Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="4a493-166">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="4a493-167">Rapport om meddelandeborttagning i Office 365</span><span class="sxs-lookup"><span data-stu-id="4a493-167">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="4a493-168">Rapporten **ATP Message Disposition** visar de åtgärder som har vidtagits för e-postmeddelanden som identifierats med skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="4a493-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="4a493-169">Om du vill visa rapporten öppnar du [Säkerhets- &,](https://protection.office.com)går till instrumentpanelen rapporter och väljer Defender för  \>  meddelandedisposition i **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="4a493-169">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="4a493-170">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="4a493-170">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget för meddelandedisposition i Defender för Office 365 på instrumentpanelen rapporter](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="4a493-172">Informationen i den här rapporten är också tillgänglig i [filtyperna Defender för Office 365.](#defender-for-office-365-file-types-report)</span><span class="sxs-lookup"><span data-stu-id="4a493-172">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="4a493-173">Rapportvyn för meddelandedispositionsrapporten i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4a493-173">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="4a493-174">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4a493-174">The following views are available:</span></span>

- <span data-ttu-id="4a493-175">**Visa data efter: Meddelande:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="4a493-175">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="4a493-176">**Blockera åtkomst**</span><span class="sxs-lookup"><span data-stu-id="4a493-176">**Block access**</span></span>
  - <span data-ttu-id="4a493-177">**Meddelanden har ersatts**</span><span class="sxs-lookup"><span data-stu-id="4a493-177">**Messages replaced**</span></span>
  - <span data-ttu-id="4a493-178">**Meddelanden övervakade**</span><span class="sxs-lookup"><span data-stu-id="4a493-178">**Messages monitored**</span></span>
  - <span data-ttu-id="4a493-179">**Ersatts av Dynamisk e-postleverans:** Mer information finns [i Principer för dynamisk leverans i säkra bifogade filer.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)</span><span class="sxs-lookup"><span data-stu-id="4a493-179">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Meddelandevyn i rapporten om filtyper i Defender för Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="4a493-181">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-181">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-182">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-182">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-183">Samma dispositionsvärden för meddelanden som är tillgängliga i diagrammet och ytterligare **Meddelanden som överförs..**</span><span class="sxs-lookup"><span data-stu-id="4a493-183">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="4a493-184">**Visa data efter: Arkiv:** Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="4a493-184">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="4a493-185">**Skadliga bifogade Excel-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-185">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="4a493-186">**Skadliga Flash-bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-186">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="4a493-187">**Skadliga bifogade PDF-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-187">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="4a493-188">**Skadliga PowerPoint-bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-188">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="4a493-189">**Skadliga URL:er**</span><span class="sxs-lookup"><span data-stu-id="4a493-189">**Malicious URLs**</span></span>
  - <span data-ttu-id="4a493-190">**Skadliga bifogade Word-filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-190">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="4a493-191">**Skadliga körbara bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="4a493-191">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="4a493-192">**Andra**</span><span class="sxs-lookup"><span data-stu-id="4a493-192">**Others**</span></span>

  <span data-ttu-id="4a493-193">När du hovrar över en viss dag (datapunkt) kan du se [](safe-attachments.md) detaljerad information om typer av skadliga filer som identifierats av Säkra bifogade filer och skydd mot [skadlig programvara i EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4a493-193">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Filvyn i rapporten om filtyper i Defender för Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="4a493-195">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-195">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-196">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-196">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-197">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="4a493-197">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="4a493-198">Detaljtabellvyn för meddelandedispositionsrapporten i Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="4a493-198">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="4a493-199">Om du **klickar på Visa** informationstabell ger rapporten en nästan realtidsvy över alla klick som har hänt inom organisationen de senaste 10 dagarna.</span><span class="sxs-lookup"><span data-stu-id="4a493-199">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="4a493-200">Vilken information som visas beror på diagrammet du visade:</span><span class="sxs-lookup"><span data-stu-id="4a493-200">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="4a493-201">**Visa data efter: Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="4a493-201">**View data by: Message**:</span></span>

  - <span data-ttu-id="4a493-202">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4a493-202">**Date**</span></span>
  - <span data-ttu-id="4a493-203">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="4a493-203">**Recipient address**</span></span>
  - <span data-ttu-id="4a493-204">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4a493-204">**Sender address**</span></span>
  - <span data-ttu-id="4a493-205">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="4a493-205">**Message ID**</span></span>
  - <span data-ttu-id="4a493-206">**Arkiv**</span><span class="sxs-lookup"><span data-stu-id="4a493-206">**File**</span></span>
  - <span data-ttu-id="4a493-207">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4a493-207">**Subject**</span></span>

  <span data-ttu-id="4a493-208">Om du **klickar på** Filter kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-208">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="4a493-209">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-209">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-210">Samma dispositionsvärden för meddelanden som är tillgängliga i diagrammet och ytterligare **Meddelanden som överförs..**</span><span class="sxs-lookup"><span data-stu-id="4a493-210">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="4a493-211">**Visa data efter: Arkiv**:</span><span class="sxs-lookup"><span data-stu-id="4a493-211">**View data by: File**:</span></span>

  - <span data-ttu-id="4a493-212">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4a493-212">**Date**</span></span>
  - <span data-ttu-id="4a493-213">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="4a493-213">**Recipient address**</span></span>
  - <span data-ttu-id="4a493-214">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4a493-214">**Sender address**</span></span>
  - <span data-ttu-id="4a493-215">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="4a493-215">**Message ID**</span></span>
  - <span data-ttu-id="4a493-216">**Arkiv**</span><span class="sxs-lookup"><span data-stu-id="4a493-216">**File**</span></span>

  <span data-ttu-id="4a493-217">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-217">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-218">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-218">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-219">Samma filtypsvärden som visas i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="4a493-219">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="4a493-220">Gå tillbaka till rapportvyn genom att klicka på **Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="4a493-220">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="4a493-221">E-postsvarstid – rapport</span><span class="sxs-lookup"><span data-stu-id="4a493-221">Mail latency report</span></span>

<span data-ttu-id="4a493-222">I **rapporten E-postsvarstid** visas en samlad vy av den e-postleverans och detonationstid som har varit lång inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="4a493-222">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="4a493-223">Leveranstiderna för e-post i tjänsten påverkas av ett antal faktorer och den absoluta leveranstiden i sekunder är ofta inte en bra indikator på ett lyckat resultat eller ett problem.</span><span class="sxs-lookup"><span data-stu-id="4a493-223">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="4a493-224">En långsam leveranstid på en dag kan ses som en genomsnittlig leveranstid på en annan dag eller tvärtom.</span><span class="sxs-lookup"><span data-stu-id="4a493-224">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="4a493-225">Svarstiden **för E-post** försöker kvalificera meddelandeleveransen baserat på statistiska data om observerade leveranstider för andra meddelanden:</span><span class="sxs-lookup"><span data-stu-id="4a493-225">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="4a493-226">**50:e percentilen**: Det här är mitten för leveranstid för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4a493-226">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="4a493-227">Du kan betrakta det här värdet som en genomsnittlig leveranstid.</span><span class="sxs-lookup"><span data-stu-id="4a493-227">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="4a493-228">**90:e percentilen**: Det här anger en lång svarstid för meddelandeleveransen.</span><span class="sxs-lookup"><span data-stu-id="4a493-228">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="4a493-229">Det tog bara 10 % längre tid än det här värdet att leverera.</span><span class="sxs-lookup"><span data-stu-id="4a493-229">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="4a493-230">**99:e percentilen**: Det här anger den högsta svarstiden för meddelandeleveransen.</span><span class="sxs-lookup"><span data-stu-id="4a493-230">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="4a493-231">Klientsidan och nätverksfördröjning ingår inte.</span><span class="sxs-lookup"><span data-stu-id="4a493-231">Client side and network latency are not included.</span></span>

<span data-ttu-id="4a493-232">Om du vill visa rapporten öppnar du [Säkerhets- & Kompatibilitetscenter](https://protection.office.com), går till  \> **instrumentpanelen rapporter** och väljer **E-postfördröjningsrapport.**</span><span class="sxs-lookup"><span data-stu-id="4a493-232">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="4a493-233">Gå direkt till rapporten genom att öppna <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="4a493-233">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget för rapport om e-postsvarstid i instrumentpanelen Rapporter](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="4a493-235">Rapportvy för e-postsvarstidsrapporten</span><span class="sxs-lookup"><span data-stu-id="4a493-235">Report view for the Mail latency report</span></span>

<span data-ttu-id="4a493-236">När du öppnar rapporten är den **50:e percentilfliken** markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="4a493-236">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="4a493-237">Som standard innehåller den här vyn ett diagram som är konfigurerat med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-237">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="4a493-238">**Datum:** De senaste sju dagarna</span><span class="sxs-lookup"><span data-stu-id="4a493-238">**Date**: The last 7 days</span></span>
- <span data-ttu-id="4a493-239">**Meddelandevy:**</span><span class="sxs-lookup"><span data-stu-id="4a493-239">**Message View**:</span></span>
  - <span data-ttu-id="4a493-240">Detonerade meddelanden</span><span class="sxs-lookup"><span data-stu-id="4a493-240">Detonated messages</span></span>

<span data-ttu-id="4a493-241">Det här diagrammet visar meddelanden ordnade i följande kategorier:</span><span class="sxs-lookup"><span data-stu-id="4a493-241">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="4a493-242">**Svarstid för e-postleverans**</span><span class="sxs-lookup"><span data-stu-id="4a493-242">**Mail delivery latency**</span></span>
- <span data-ttu-id="4a493-243">**Detonationsfördröjning**</span><span class="sxs-lookup"><span data-stu-id="4a493-243">**Detonation latency**</span></span>

<span data-ttu-id="4a493-244">När du hovrar över en kategori i diagrammet kan du se en uppdelning av svarstiden i varje kategori.</span><span class="sxs-lookup"><span data-stu-id="4a493-244">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![E-postsvarstid – rapport](../../media/mail-latency-report.png)

<span data-ttu-id="4a493-246">Om du **klickar på** Filter i rapportvyn kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-246">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="4a493-247">Alla meddelanden</span><span class="sxs-lookup"><span data-stu-id="4a493-247">All messages</span></span>
- <span data-ttu-id="4a493-248">Meddelanden som innehåller bifogade filer eller URL-adresser</span><span class="sxs-lookup"><span data-stu-id="4a493-248">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="4a493-249">Om du klickar på den **90:e** percentilfliken eller på den **99:e** percentilfliken används samma standardfilter från vyn för de **50:e percentilerna.**</span><span class="sxs-lookup"><span data-stu-id="4a493-249">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="4a493-250">Detaljtabellvyn för e-postsvarstidsrapporten</span><span class="sxs-lookup"><span data-stu-id="4a493-250">Details table view for the Mail latency report</span></span>

<span data-ttu-id="4a493-251">Följande information visas i detaljtabellvyn:</span><span class="sxs-lookup"><span data-stu-id="4a493-251">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="4a493-252">**Datum**</span><span class="sxs-lookup"><span data-stu-id="4a493-252">**Date**</span></span>
- <span data-ttu-id="4a493-253">**Percentiler**</span><span class="sxs-lookup"><span data-stu-id="4a493-253">**Percentiles**</span></span>
- <span data-ttu-id="4a493-254">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="4a493-254">**Message count**</span></span>
- <span data-ttu-id="4a493-255">**Total svarstid**</span><span class="sxs-lookup"><span data-stu-id="4a493-255">**Overall latency**</span></span>

![Information om e-postsvarstid](../../media/mail-latency-report-details.png)

<span data-ttu-id="4a493-257">Ovanstående visar att den genomsnittliga svarstiden för alla meddelanden som levererats och detonerats den **108,033** sekunder den 14 november.</span><span class="sxs-lookup"><span data-stu-id="4a493-257">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="4a493-258">Informationstabellen innehåller samma information på varje flik.</span><span class="sxs-lookup"><span data-stu-id="4a493-258">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="4a493-259">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="4a493-259">Threat protection status report</span></span>

<span data-ttu-id="4a493-260">Statusrapporten **För skydd** mot hot är en vy som samlar information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a493-260">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4a493-261">Mer information finns i [Statusrapport för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="4a493-261">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="4a493-262">Rapport om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="4a493-262">URL threat protection report</span></span>

<span data-ttu-id="4a493-263">Rapporten **om skydd mot URL-hot** ger sammanfattnings- och trendvyer för identifierade hot och åtgärder som vidtas på URL-klick som en del av Säkra [länkar.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="4a493-263">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="4a493-264">I den här rapporten visas ingen klickning för data från användare där alternativet Spåra inte användarklick har **markerats** i principen För säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="4a493-264">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="4a493-265">Om du vill visa rapporten öppnar du [Säkerhets- & Kompatibilitetscenter](https://protection.office.com), går till **Rapporter** \> **instrumentpanel** och väljer **URL-skyddsrapport**.</span><span class="sxs-lookup"><span data-stu-id="4a493-265">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="4a493-266">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="4a493-266">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget för URL-skyddsrapport på instrumentpanelen Rapporter](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="4a493-268">Det här är en *rapport om skyddtrender,* vilket innebär att data representerar trender i en större datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="4a493-268">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="4a493-269">Därför är data i mängdvyn inte tillgängliga i realtid här, men data i detaljtabellvyn är det, så du kan se en liten avvikelse mellan de två vyerna.</span><span class="sxs-lookup"><span data-stu-id="4a493-269">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="4a493-270">Rapportvy för rapporten om URL-skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="4a493-270">Report view for the URL threat protection report</span></span>

<span data-ttu-id="4a493-271">Rapporten **om skydd mot URL-hot** har två aggregerade vyer som uppdateras en gång var fjärde timme och som visar data för de senaste 90 dagarna:</span><span class="sxs-lookup"><span data-stu-id="4a493-271">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="4a493-272">**Åtgärden URL-klickskydd:** Visar antalet URL-klick som användare i organisationen har klickat på och resultatet av klicket:</span><span class="sxs-lookup"><span data-stu-id="4a493-272">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="4a493-273">**Blockerad** (användaren blockerades från att navigera till URL:en)</span><span class="sxs-lookup"><span data-stu-id="4a493-273">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="4a493-274">**Blockeras och klickas igenom**</span><span class="sxs-lookup"><span data-stu-id="4a493-274">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="4a493-275">**Klickade igenom under genomsökning**</span><span class="sxs-lookup"><span data-stu-id="4a493-275">**Clicked through during scan**</span></span>

  <span data-ttu-id="4a493-276">Ett klick anger att användaren har klickat igenom blockeringssidan till den skadliga webbplatsen (administratörer kan inaktivera Klicka igenom i Principer för säkra länkar).</span><span class="sxs-lookup"><span data-stu-id="4a493-276">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="4a493-277">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-277">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-278">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-278">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-279">De tillgängliga åtgärderna för klickskydd plus värdet **Tillåts** (användaren tillåts navigera till URL-adressen).</span><span class="sxs-lookup"><span data-stu-id="4a493-279">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Vy för URL-klickskyddsåtgärd i rapporten om skydd mot URL-hot](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="4a493-281">**URL som klickas efter** program: Visar antalet URL-klickningar efter program som stöder säkra länkar:</span><span class="sxs-lookup"><span data-stu-id="4a493-281">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="4a493-282">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="4a493-282">**Email client**</span></span>
  - <span data-ttu-id="4a493-283">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="4a493-283">**PowerPoint**</span></span>
  - <span data-ttu-id="4a493-284">**Word**</span><span class="sxs-lookup"><span data-stu-id="4a493-284">**Word**</span></span>
  - <span data-ttu-id="4a493-285">**Excel**</span><span class="sxs-lookup"><span data-stu-id="4a493-285">**Excel**</span></span>
  - <span data-ttu-id="4a493-286">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="4a493-286">**OneNote**</span></span>
  - <span data-ttu-id="4a493-287">**Visio**</span><span class="sxs-lookup"><span data-stu-id="4a493-287">**Visio**</span></span>
  - <span data-ttu-id="4a493-288">**Teams**</span><span class="sxs-lookup"><span data-stu-id="4a493-288">**Teams**</span></span>
  - <span data-ttu-id="4a493-289">**Annat**</span><span class="sxs-lookup"><span data-stu-id="4a493-289">**Other**</span></span>

  <span data-ttu-id="4a493-290">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="4a493-290">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="4a493-291">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="4a493-291">**Start date** and **End date**</span></span>
  - <span data-ttu-id="4a493-292">Tillgängliga program.</span><span class="sxs-lookup"><span data-stu-id="4a493-292">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="4a493-293">Detaljtabellvy för rapporten om url-hotskydd</span><span class="sxs-lookup"><span data-stu-id="4a493-293">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="4a493-294">Om du **klickar på Visa** informationstabell ger rapporten en nästan realtidsvy över alla klick som har hänt inom organisationen de senaste 7 dagarna med följande information:</span><span class="sxs-lookup"><span data-stu-id="4a493-294">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="4a493-295">**Klicktid**</span><span class="sxs-lookup"><span data-stu-id="4a493-295">**Click time**</span></span>
- <span data-ttu-id="4a493-296">**Användare**</span><span class="sxs-lookup"><span data-stu-id="4a493-296">**User**</span></span>
- <span data-ttu-id="4a493-297">**URL**</span><span class="sxs-lookup"><span data-stu-id="4a493-297">**URL**</span></span>
- <span data-ttu-id="4a493-298">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="4a493-298">**Action**</span></span>
- <span data-ttu-id="4a493-299">**Program**</span><span class="sxs-lookup"><span data-stu-id="4a493-299">**App**</span></span>

<span data-ttu-id="4a493-300">Om du klickar **på** Filter i detaljtabellvyn kan du filtrera efter samma  villkor  som i rapportvyn och även efter Domäner eller Mottagare avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="4a493-300">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

> [!NOTE]
> <span data-ttu-id="4a493-301">Filtret **Domäner** refererar till den URL-domän som visas i rapportresultatet.</span><span class="sxs-lookup"><span data-stu-id="4a493-301">The **Domains** filter refers to the URL domain listed in the report results.</span></span> 

<span data-ttu-id="4a493-302">Gå tillbaka till rapportvyn genom att klicka på **Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="4a493-302">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="4a493-303">Ytterligare rapporter att visa</span><span class="sxs-lookup"><span data-stu-id="4a493-303">Additional reports to view</span></span>

<span data-ttu-id="4a493-304">Utöver rapporterna som beskrivs i den här artikeln finns det flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="4a493-304">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="4a493-305">Rapport</span><span class="sxs-lookup"><span data-stu-id="4a493-305">Report</span></span>|<span data-ttu-id="4a493-306">Ämne</span><span class="sxs-lookup"><span data-stu-id="4a493-306">Topic</span></span>|
|---|---|
|<span data-ttu-id="4a493-307">**Utforskaren** (Microsoft Defender för Office 365 abonnemang 2) eller identifieringar i realtid **(Microsoft** Defender för Office 365 abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="4a493-307">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="4a493-308">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="4a493-308">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="4a493-309">**Säkerhetsrapporter för** e-post, till exempel rapporten De största avsändarna och mottagarna, förfalskningsrapporten och rapporten Om identifiering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="4a493-309">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="4a493-310">Visa e-postsäkerhetsrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4a493-310">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="4a493-311">**E-postflödesrapporter,** till exempel vidarebefordransrapporten, statusrapporten E-postflöde och rapporten Betrodda avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="4a493-311">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="4a493-312">Visa e-postflödesrapporter i Säkerhets- & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4a493-312">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="4a493-313">**URL-spårning för säkra länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4a493-313">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="4a493-314">Resultatet av den här cmdleten visar resultatet för åtgärder med säkra länkar under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="4a493-314">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="4a493-315">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="4a493-315">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="4a493-316">**E-posttrafikresultat för EOP och Microsoft Defender för Office 365** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4a493-316">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="4a493-317">Utdata för denna cmdlet innehåller information om Domän, Datum, Händelsetyp, Riktning, Åtgärd och Antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4a493-317">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="4a493-318">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="4a493-318">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="4a493-319">**E-postdetaljrapporter för EOP och Defender för office 365-identifieringar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="4a493-319">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="4a493-320">Utdata från denna cmdlet innehåller information om skadliga filer eller URL:er, nätfiskeförsök, personifiering och andra potentiella hot i e-postmeddelanden och filer.</span><span class="sxs-lookup"><span data-stu-id="4a493-320">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="4a493-321">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="4a493-321">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="4a493-322">Vilka behörigheter krävs för att visa Defender för Office 365-rapporter?</span><span class="sxs-lookup"><span data-stu-id="4a493-322">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="4a493-323">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Säkerhets- och & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="4a493-323">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="4a493-324">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="4a493-324">**Organization Management**</span></span>
- <span data-ttu-id="4a493-325">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="4a493-325">**Security Administrator**</span></span>
- <span data-ttu-id="4a493-326">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="4a493-326">**Security Reader**</span></span>
- <span data-ttu-id="4a493-327">**Global läsare**</span><span class="sxs-lookup"><span data-stu-id="4a493-327">**Global Reader**</span></span>

<span data-ttu-id="4a493-328">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4a493-328">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="4a493-329">**Obs!** Om du lägger till användare till motsvarande Azure Active Directory-roll i administrationscentret för Microsoft  365 får användarna de behörigheter som krävs i säkerhets- och efterlevnadscentret för & och behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a493-329">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4a493-330">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4a493-330">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4a493-331">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="4a493-331">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4a493-332">Om du inte ser data i Defender för Office 365-rapporterna kan du dubbelkolla att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="4a493-332">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4a493-333">Organisationen måste ha principer [för säkra länkar](set-up-safe-links-policies.md) och principer för [säkra](set-up-safe-attachments-policies.md) bifogade filer definierade för att Defender för Office 365-skyddet ska finnas på plats.</span><span class="sxs-lookup"><span data-stu-id="4a493-333">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="4a493-334">Se även [Skydd mot skräppost och skadlig programvara.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4a493-334">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a493-335">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="4a493-335">Related topics</span></span>

[<span data-ttu-id="4a493-336">Smarta rapporter och insikter i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="4a493-336">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4a493-337">Rollbehörigheter (Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="4a493-337">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)