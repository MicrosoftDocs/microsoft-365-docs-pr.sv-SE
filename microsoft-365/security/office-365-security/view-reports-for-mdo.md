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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan läsa mer om hur de hittar och använder Defender Office 365-rapporter som finns tillgängliga i Microsoft 365 Defender portalen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9279614571c123ad92f1684f86175b410c6c5c
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022862"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f3f9b-103">Visa Defender för Office 365 i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="f3f9b-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f3f9b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-104">**Applies to**</span></span>
- [<span data-ttu-id="f3f9b-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f3f9b-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f3f9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3f9b-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f3f9b-107">Microsoft Defender för Office 365-organisationer (till exempel Microsoft 365 E5-prenumerationer eller Microsoft Defender för Office 365 abonnemang 1 eller Microsoft Defender för tillägg för Office 365 Abonnemang 2) innehåller en mängd olika säkerhetsrelaterade rapporter.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="f3f9b-108">Om du har [nödvändiga](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)behörigheter kan du visa de här rapporterna  i Microsoft 365 Defender-portalen genom att gå till Rapporterar e-& för samarbete \>  \> **E& och samarbetsrapporter.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f3f9b-109">Om du vill gå direkt **till sidan & e-post och** samarbetsrapporter öppnar du <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="f3f9b-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Skicka & via e-post och samarbetsrapporter i Microsoft 365 Defender portalen](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="f3f9b-111">Säkerhetsrapporter för e-post som inte kräver Defender för Office 365 beskrivs i Visa [e-postsäkerhetsrapporter i Microsoft 365 Defender portalen.](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="f3f9b-112">Rapporter som är relaterade till e-postflödet finns nu Exchange administrationscenter (EAC).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f3f9b-113">Mer information om rapporterna finns i [E-postflödesrapporter i det nya Exchange administrationscentret.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="f3f9b-114">Valv Rapport över bifogade filer</span><span class="sxs-lookup"><span data-stu-id="f3f9b-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="f3f9b-115">Rapporten **Valv bifogade filer försvinner** så småningom.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="f3f9b-116">Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="f3f9b-117">Valv Dispositionsrapport för bifogade filer</span><span class="sxs-lookup"><span data-stu-id="f3f9b-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="f3f9b-118">Dispositionen **Valv bifogade filer försvinner** så småningom.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="f3f9b-119">Samma information är tillgänglig i rapporten [om skydd mot hot.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f3f9b-120">E-postsvarstid – rapport</span><span class="sxs-lookup"><span data-stu-id="f3f9b-120">Mail latency report</span></span>

<span data-ttu-id="f3f9b-121">I **rapporten E-postsvarstid** visas en samlad vy av den e-postleverans och detonationstid som har varit lång inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f3f9b-122">Leveranstiderna för e-post i tjänsten påverkas av ett antal faktorer och den absoluta leveranstiden i sekunder är ofta inte en bra indikator på ett lyckat resultat eller ett problem.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="f3f9b-123">En långsam leveranstid på en dag kan ses som en genomsnittlig leveranstid på en annan dag eller tvärtom.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="f3f9b-124">Meddelandet levereras som kvalificerar sig baserat på statistiska data om observerade leveranstider för andra meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="f3f9b-125">Klientsidan och nätverksfördröjning ingår inte.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="f3f9b-126">Om du vill visa rapporten öppnar du [Microsoft 365 Defender portalen](https://security.microsoft.com)och går till **Rapporterar** \> **e-& samarbete** \> **E& samarbetsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f3f9b-127">På sidan **E& över samarbetsrapporter hittar** du Svarstidsrapport för **e-post** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="f3f9b-128">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="f3f9b-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Rapportwidget för e-postfördröjning på sidan & för e-postsamarbete](../../media/mail-latency-report-widget.png)

<span data-ttu-id="f3f9b-130">På sidan **E-postfördröjningsrapport** är följande flikar tillgängliga på **sidan Med svarstid för e-post:**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="f3f9b-131">**50:e percentilen**: Det här är mitten för leveranstid för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="f3f9b-132">Du kan betrakta det här värdet som en genomsnittlig leveranstid.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="f3f9b-133">Den här fliken är markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-133">This tab is selected by default.</span></span>
- <span data-ttu-id="f3f9b-134">**90:e percentilen**: Det här anger en lång svarstid för meddelandeleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="f3f9b-135">Det tog bara 10 % längre tid än det här värdet att leverera.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="f3f9b-136">**99:e percentilen**: Det här anger den högsta svarstiden för meddelandeleveransen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="f3f9b-137">Oavsett vilken flik du väljer visas meddelanden ordnade i följande kategorier i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f3f9b-138">**Svarstid för e-postleverans**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="f3f9b-139">**Detonationer**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-139">**Detonations**</span></span>

<span data-ttu-id="f3f9b-140">När du hovrar över en kategori i diagrammet kan du se en uppdelning av svarstiden i varje kategori.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![50:e percentilvyn i rapporten E-postsvarstid](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="f3f9b-142">Om du klickar **på Filter** kan du filtrera både diagrammet och informationstabellen med hjälp av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="f3f9b-143">**Datum (UTC)**: **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f3f9b-144">**Meddelandevy:** Något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="f3f9b-145">**Alla meddelanden**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-145">**All messages**</span></span>
  - <span data-ttu-id="f3f9b-146">**Meddelanden som innehåller bifogade filer eller URL-adresser**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="f3f9b-147">**Detonerade meddelanden**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-147">**Detonated messages**</span></span>

<span data-ttu-id="f3f9b-148">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f3f9b-149">I informationstabellen under diagrammet finns följande information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f3f9b-150">**Datum (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-150">**Date (UTC)**</span></span>
- <span data-ttu-id="f3f9b-151">**Percentiler:** **50,** **90** eller **99**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="f3f9b-152">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-152">**Message count**</span></span>
- <span data-ttu-id="f3f9b-153">**Total svarstid**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f3f9b-154">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="f3f9b-154">Threat protection status report</span></span>

<span data-ttu-id="f3f9b-155">Statusrapporten **För skydd** mot hot är en vy som samlar information om skadligt innehåll och skadlig e-post som identifieras och blockeras av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f3f9b-156">Mer information finns i [Statusrapport för skydd mot hot.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="f3f9b-157">Rapport om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="f3f9b-157">URL threat protection report</span></span>

<span data-ttu-id="f3f9b-158">Rapporten **om skydd mot URL-hot** ger sammanfattnings- och trendvyer för identifierade hot och åtgärder som vidtas på URL-klick som en del av Valv [Länkar.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="f3f9b-159">Du kan inte klicka på data från användare i Valv länkprincipen som har markerats med alternativet Spåra inte **användarklick.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="f3f9b-160">Om du vill visa rapporten öppnar du [Microsoft 365 Defender portalen](https://security.microsoft.com)och går till **Rapporterar** \> **e-& samarbete** \> **E& samarbetsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f3f9b-161">På sidan **E& och samarbetsrapporter** hittar du **sidan URL-skydd** och klickar sedan **på Visa information.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="f3f9b-162">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="f3f9b-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Widget för URL-skyddsrapport på sidan & för e-postsamarbete](../../media/url-protection-report-widget.png)

<span data-ttu-id="f3f9b-164">De tillgängliga vyerna på **sidan för skydd mot URL-hot** beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="f3f9b-165">Det här är en *rapport om skyddtrender,* vilket innebär att data representerar trender i en större datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="f3f9b-166">Därför är data i diagrammen inte tillgängliga i realtid här, men data i detaljtabellen är det, så du kan se en liten avvikelse mellan dem.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="f3f9b-167">Diagrammen uppdateras en gång var fjärde timme och innehåller data för de senaste 90 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="f3f9b-168">Visa data via URL,klickskyddsåtgärd</span><span class="sxs-lookup"><span data-stu-id="f3f9b-168">View data by URL click protection action</span></span>

![Vy för URL-klickskyddsåtgärd i rapporten om skydd mot URL-hot](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="f3f9b-170">I **åtgärdsvyn Visa data via URL** klickar du på Skydd visas antalet URL-klick som användare i organisationen har klickat på och resultatet av klicket:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="f3f9b-171">**Tillåtet:** Användaren har tillåtits att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="f3f9b-172">**Blockerad:** Användaren blockerades från att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="f3f9b-173">**Blockeras och klickas igenom:** Användaren har valt att fortsätta navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="f3f9b-174">**Klickade igenom under genomsökningen:** Användaren har klickat på länken innan genomsökningen var klar.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="f3f9b-175">Ett klick anger att användaren har klickat igenom blockeringssidan till den skadliga webbplatsen (administratörer kan inaktivera klicka i Valv-länkar).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="f3f9b-176">Om du klickar **på** Filter kan du ändra rapporten och detaljtabellen genom att välja ett eller flera av följande värden i den utfällade menyn som visas:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f3f9b-177">**Datum (UTC)**: **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f3f9b-178">**Identifiering:**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-178">**Detection**:</span></span>
  - <span data-ttu-id="f3f9b-179">**Tillåts**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-179">**Allowed**</span></span>
  - <span data-ttu-id="f3f9b-180">**Blockeras**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-180">**Blocked**</span></span>
  - <span data-ttu-id="f3f9b-181">**Blockeras och klickas igenom**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="f3f9b-182">**Klickade igenom under genomsökning**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="f3f9b-183">**Domäner**: URL-domänerna som visas i rapportresultaten.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="f3f9b-184">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-184">**Recipients**</span></span>

<span data-ttu-id="f3f9b-185">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f3f9b-186">I detaljtabellen under diagrammet visas följande närtidsvy över alla klick som har hänt inom organisationen de senaste 7 dagarna:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="f3f9b-187">**Klicktid**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-187">**Click time**</span></span>
- <span data-ttu-id="f3f9b-188">**Användare**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-188">**User**</span></span>
- <span data-ttu-id="f3f9b-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-189">**URL**</span></span>
- <span data-ttu-id="f3f9b-190">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-190">**Action**</span></span>
- <span data-ttu-id="f3f9b-191">**Program**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="f3f9b-192">Visa data per URL, klicka på efter program</span><span class="sxs-lookup"><span data-stu-id="f3f9b-192">View data by URL click by application</span></span>

![URL-klick på efter programvy i rapporten om skydd mot URL-hot](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="f3f9b-194">I **vyn Visa data per URL som klickas** på efter programvy visas antalet URL-klickningar från appar som stöder Valv Länkar:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="f3f9b-195">**E-postklient**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-195">**Email client**</span></span>
- <span data-ttu-id="f3f9b-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-196">**PowerPoint**</span></span>
- <span data-ttu-id="f3f9b-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-197">**Word**</span></span>
- <span data-ttu-id="f3f9b-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-198">**Excel**</span></span>
- <span data-ttu-id="f3f9b-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-199">**OneNote**</span></span>
- <span data-ttu-id="f3f9b-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-200">**Visio**</span></span>
- <span data-ttu-id="f3f9b-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-201">**Teams**</span></span>
- <span data-ttu-id="f3f9b-202">**Andra**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-202">**Others**</span></span>

<span data-ttu-id="f3f9b-203">Om du klickar **på** Filter kan du ändra rapporten och detaljtabellen genom att välja ett eller flera av följande värden i den utfällade menyn som visas:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f3f9b-204">**Datum (UTC)**: **Startdatum** **och slutdatum**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f3f9b-205">**Identifiering:** Tillgängliga appar från diagrammet.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="f3f9b-206">**Domäner**: URL-domänerna som visas i rapportresultaten.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="f3f9b-207">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-207">**Recipients**</span></span>

<span data-ttu-id="f3f9b-208">När du är klar med att konfigurera filtren klickar du **på Använd**, **Avbryt** eller **Rensa filter.**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f3f9b-209">I detaljtabellen under diagrammet visas följande närtidsvy över alla klick som har hänt inom organisationen de senaste 7 dagarna:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="f3f9b-210">**Klicktid**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-210">**Click time**</span></span>
- <span data-ttu-id="f3f9b-211">**Användare**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-211">**User**</span></span>
- <span data-ttu-id="f3f9b-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-212">**URL**</span></span>
- <span data-ttu-id="f3f9b-213">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-213">**Action**</span></span>
- <span data-ttu-id="f3f9b-214">**Program**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="f3f9b-215">Ytterligare rapporter att visa</span><span class="sxs-lookup"><span data-stu-id="f3f9b-215">Additional reports to view</span></span>

<span data-ttu-id="f3f9b-216">Utöver rapporterna som beskrivs i den här artikeln finns det flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="f3f9b-217">Rapport</span><span class="sxs-lookup"><span data-stu-id="f3f9b-217">Report</span></span>|<span data-ttu-id="f3f9b-218">Ämne</span><span class="sxs-lookup"><span data-stu-id="f3f9b-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="f3f9b-219">**Utforskaren** (Microsoft Defender Office 365 abonnemang 2) eller identifieringar i realtid **(Microsoft** Defender för Office 365 abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="f3f9b-220">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="f3f9b-221">**Säkerhetsrapporter för** e-post, till exempel rapporten De största avsändarna och mottagarna, förfalskningsrapporten och rapporten Om identifiering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="f3f9b-222">Visa e-postsäkerhetsrapporter på Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="f3f9b-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="f3f9b-223">**E-postflödesrapporter,** till exempel vidarebefordransrapporten, statusrapporten E-postflöde och rapporten Betrodda avsändare och mottagare.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="f3f9b-224">E-postflödesrapporter i det Exchange administrationscentret</span><span class="sxs-lookup"><span data-stu-id="f3f9b-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="f3f9b-225">**URL-spårning för Valv länkar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="f3f9b-226">I utdata för den här cmdleten visas resultatet Valv åtgärder under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="f3f9b-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="f3f9b-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="f3f9b-228">**E-posttrafikresultat för EOP och Microsoft Defender för Office 365** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="f3f9b-229">Utdata för denna cmdlet innehåller information om Domän, Datum, Händelsetyp, Riktning, Åtgärd och Antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="f3f9b-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="f3f9b-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="f3f9b-231">**E-postdetaljrapporter för EOP och Defender Office 365 identifieringar** (endast PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="f3f9b-232">Utdata från denna cmdlet innehåller information om skadliga filer eller URL:er, nätfiskeförsök, personifiering och andra potentiella hot i e-postmeddelanden och filer.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="f3f9b-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="f3f9b-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="f3f9b-234">Vilka behörigheter krävs för att visa Defender för Office 365 rapporter?</span><span class="sxs-lookup"><span data-stu-id="f3f9b-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="f3f9b-235">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Microsoft 365 Defender portalen:</span><span class="sxs-lookup"><span data-stu-id="f3f9b-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f3f9b-236">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-236">**Organization Management**</span></span>
- <span data-ttu-id="f3f9b-237">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-237">**Security Administrator**</span></span>
- <span data-ttu-id="f3f9b-238">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-238">**Security Reader**</span></span>
- <span data-ttu-id="f3f9b-239">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="f3f9b-239">**Global Reader**</span></span>

<span data-ttu-id="f3f9b-240">Mer information finns i [Behörigheter i Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f3f9b-241">**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll i Administrationscenter för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f3f9b-242">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f3f9b-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f3f9b-243">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="f3f9b-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f3f9b-244">Om du inte ser data i Defender för Office 365 kontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f3f9b-245">Organisationen måste ha [principer Valv länkar](set-up-safe-links-policies.md) och principer [Valv](set-up-safe-attachments-policies.md) för att Defender Office 365 ska finnas på plats.</span><span class="sxs-lookup"><span data-stu-id="f3f9b-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="f3f9b-246">Se även [Skydd mot skräppost och skadlig programvara.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f3f9b-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3f9b-247">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="f3f9b-247">Related topics</span></span>

[<span data-ttu-id="f3f9b-248">Smarta rapporter och insikter i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="f3f9b-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f3f9b-249">Rollbehörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f3f9b-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
