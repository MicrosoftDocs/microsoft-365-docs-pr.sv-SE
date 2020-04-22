---
title: Visa rapporter för Avancerat skydd mot office 365, rapporter om skadlig programvara, rapporter om intrång, komprometterade konton, URL-skyddsstatus, hotrapportering, rapportera hot
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
description: Hitta och använd rapporter för avancerat skydd mot &amp; office 365 i Säkerhetsefterlevnadscenter.
ms.openlocfilehash: 09e2f4be133d395b738219b3a280f08b915030e0
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43708505"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="1e741-103">Visa rapporter för avancerat hotskydd för Office 365</span><span class="sxs-lookup"><span data-stu-id="1e741-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="1e741-104">Om din organisation har [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) och du har de &amp; [behörigheter som krävs](#what-permissions-are-needed-to-view-the-atp-reports)kan du använda flera ATP-rapporter i Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1e741-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="1e741-105">(Gå till \> **instrumentpanelen** **Rapporter** .)</span><span class="sxs-lookup"><span data-stu-id="1e741-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![Instrumentpanelen för Säkerhetsefterlevnadscenter &amp; kan hjälpa dig att se var avancerat skydd mot hot fungerar](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="1e741-107">ATP-rapporter innehåller följande:</span><span class="sxs-lookup"><span data-stu-id="1e741-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="1e741-108">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="1e741-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="1e741-109">Rapporten för ATP-filtyper</span><span class="sxs-lookup"><span data-stu-id="1e741-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="1e741-110">Rapport om ATP-meddelandedisposition</span><span class="sxs-lookup"><span data-stu-id="1e741-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="1e741-111">antingen [identifiering i realtid eller Utforskaren](threat-explorer.md) (beroende på om du har Office 365 ATP-abonnemang 1 eller 2)</span><span class="sxs-lookup"><span data-stu-id="1e741-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="1e741-112">... [och mer](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="1e741-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="1e741-113">Läs den här artikeln om du vill få en översikt över ATP-rapporter och hur du använder dem.</span><span class="sxs-lookup"><span data-stu-id="1e741-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="1e741-114">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="1e741-114">Threat Protection Status report</span></span>

<span data-ttu-id="1e741-115">Rapporten **Status för hotskydd** är en enda vy som samlar information om skadligt innehåll och skadlig e-post som upptäckts och blockerats av [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) och [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="1e741-116">Den här rapporten är användbar för att visa identifieringar över tid (upp till 90 dagar) och gör det möjligt för säkerhetsadministratörer att identifiera trender eller avgöra om principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="1e741-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="1e741-117">Rapporten innehåller ett aggregerat antal unika e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (WEBBADRESSER) som blockerades av anti-malware-motorn, [nolltimmars automatisk rensning (ZAP)](zero-hour-auto-purge.md)och ATP-funktioner som [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md)och [ATP anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="1e741-118">Filter och uppdelningar av informationen möjliggör mer detaljerade kategoriseringar av informationen i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="1e741-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="1e741-119">Specifikt finns det en "break down by" meny **Email** \> som ingår för **E Phish** \> **Phish** och E Malware **visningar.**</span><span class="sxs-lookup"><span data-stu-id="1e741-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="1e741-120">Det kommer att dela upp data i:</span><span class="sxs-lookup"><span data-stu-id="1e741-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="1e741-121">Efter identifieringstyp</span><span class="sxs-lookup"><span data-stu-id="1e741-121">By detection type</span></span>|<span data-ttu-id="1e741-122">Vilken politik hjälpte till att fånga dessa hot?</span><span class="sxs-lookup"><span data-stu-id="1e741-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="1e741-123">Genom detektionsteknik</span><span class="sxs-lookup"><span data-stu-id="1e741-123">By detection technology</span></span>|<span data-ttu-id="1e741-124">Vilken underliggande Microsoft-teknik fångade hotet?</span><span class="sxs-lookup"><span data-stu-id="1e741-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="1e741-125">Efter leveransstatus</span><span class="sxs-lookup"><span data-stu-id="1e741-125">By delivery status</span></span>|<span data-ttu-id="1e741-126">Vad har hänt med de e-postmeddelanden som upptäckts som hot?</span><span class="sxs-lookup"><span data-stu-id="1e741-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="1e741-127">Både e-> Phish | Malware visningar har detaljerade uppdelningar för upptäckt teknik som visas, med kategorier som *ATP-genererade fil rykte*, *File detonation*, *URL detonation*, *Anti-parodi: DMARC misslyckande*, till exempel, till hjälp med att precisera exakt vilken funktion som ledde din organisation att fånga hot.</span><span class="sxs-lookup"><span data-stu-id="1e741-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Rullgardinsmenyn Status för hotskydd som visar "bryt ned efter".](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="1e741-129">Dessa vyer ger dig möjlighet att exportera, via ett knappklick (i **Mail** \> **Phish,** **E Malware** \> **och** **Content** \> **Malware** visningar).</span><span class="sxs-lookup"><span data-stu-id="1e741-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="1e741-130">De aggregerade data som exporteras till datorn kan öppnas i Excel.</span><span class="sxs-lookup"><span data-stu-id="1e741-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Den här bilden visar Export som ett alternativ i menyn för vyn Skadlig kod, precis mellan Skapa schema och Begäransrapport.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="1e741-132">**Obs:** Det maximala antalet poster som kan exporteras för **Phish** och **Malware** är strax under 10000.</span><span class="sxs-lookup"><span data-stu-id="1e741-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="1e741-133">Om du exporterar en vy exporteras endast de senaste 10000 posterna.</span><span class="sxs-lookup"><span data-stu-id="1e741-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="1e741-134">Översikts- och e-postvyerna visar information inom några timmar efter bearbetningen i stället för inom 24 timmar (efterfrågan på igen.</span><span class="sxs-lookup"><span data-stu-id="1e741-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="1e741-135">ökade hastigheter här har varit en tydlig signal)!</span><span class="sxs-lookup"><span data-stu-id="1e741-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="1e741-136">En rapport om status för hotskydd är tillgänglig för kunder som har antingen [Office 365 ATP](office-365-atp.md) eller [Exchange Online Protection](exchange-online-protection-eop.md) (EOP). Informationen som visas i rapporten Status för hotskydd för ATP-kunder innehåller dock sannolikt andra data än vad EOP-kunder kan se.</span><span class="sxs-lookup"><span data-stu-id="1e741-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="1e741-137">Rapporten Status för hotskydd för ATP-kunder innehåller till exempel information om [skadliga filer som identifierats i SharePoint Online, OneDrive eller Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="1e741-138">Sådan information är specifik för ATP, så kunder som har EOP men inte ATP kommer inte att se dessa uppgifter i sin rapport om hotskyddsstatus.</span><span class="sxs-lookup"><span data-stu-id="1e741-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="1e741-139">Om du vill visa rapporten [ &amp; ](https://protection.office.com)Status för hotskydd går du till **Rapporter om** \> skydd av **instrumentpanelens** \> **skydd .**</span><span class="sxs-lookup"><span data-stu-id="1e741-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![ATP-rapport om skydd mot hot](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="1e741-141">Om du vill ha detaljerad status för en dag håller du muspekaren över diagrammet.</span><span class="sxs-lookup"><span data-stu-id="1e741-141">To get detailed status for a day, hover over the graph.</span></span>

![ATP-hotskyddsstatusdata för en dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="1e741-143">Som standard visar rapporten Status för hotskydd data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="1e741-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="1e741-144">Du kan dock välja **Filter** och ändra datumintervallet för att visa data i upp till 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="1e741-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="1e741-145">(Om du använder en utvärderingsprenumeration kan du vara begränsad till 30 dagars data.)</span><span class="sxs-lookup"><span data-stu-id="1e741-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![STATUSFILTER FÖR ATP-hotskydd](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="1e741-147">Du kan också använda **Visa data efter** meny för att ändra vilken information som visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="1e741-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Visa alternativ för ATP-rapport om hotskyddsstatus](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="1e741-149">Statusrapport för URL-skydd</span><span class="sxs-lookup"><span data-stu-id="1e741-149">URL Protection Status report</span></span>

<span data-ttu-id="1e741-150">Den här rapporten är baserad på insamlade data och upptäckta hot per klick (medan de flesta andra e-posthotrelaterade rapporter är per meddelandedata).</span><span class="sxs-lookup"><span data-stu-id="1e741-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="1e741-151">Den här rapporten är utformad för att visa hot som kommer från hyperlänkar i e-postmeddelanden och dokument per klick.</span><span class="sxs-lookup"><span data-stu-id="1e741-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="1e741-152">Det finns två vyer:</span><span class="sxs-lookup"><span data-stu-id="1e741-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="1e741-153">Url-klickskyddsåtgärd</span><span class="sxs-lookup"><span data-stu-id="1e741-153">URL click protection action</span></span>|<span data-ttu-id="1e741-154">Se antalet webbadresser som blockerats, blockerats men åsidosättts med ett klick av en användare, åsidosatt med ett klick av en användare och tillåtet.</span><span class="sxs-lookup"><span data-stu-id="1e741-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="1e741-155">URL-klick efter program</span><span class="sxs-lookup"><span data-stu-id="1e741-155">URL click by application</span></span>|<span data-ttu-id="1e741-156">Se programmet som url:en klickades på.</span><span class="sxs-lookup"><span data-stu-id="1e741-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="1e741-157">I informationstabellen kan du se mer information om klicktid och användarinformation.</span><span class="sxs-lookup"><span data-stu-id="1e741-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="1e741-158">Slutligen, tänk på url skydd statusrapport visar skyddet från ATP Safe Links funktionen, så att endast kunder som har aktiverat ATP Safe Links kommer att se data återspeglas på den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="1e741-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="1e741-159">Det här är en *trendrapport*för skydd , vilket innebär att data representerar trender i en större datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="1e741-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="1e741-160">Rapportering är inte tillgängligt i realtid här.</span><span class="sxs-lookup"><span data-stu-id="1e741-160">Reporting isn't available in real time here.</span></span> <span data-ttu-id="1e741-161">För url-klickdata i realtid fortsätter du att använda URL-spårning.</span><span class="sxs-lookup"><span data-stu-id="1e741-161">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="1e741-162">Rapporten för ATP-filtyper</span><span class="sxs-lookup"><span data-stu-id="1e741-162">ATP File Types report</span></span>

<span data-ttu-id="1e741-163">I **atp-filtyper** visas vilken typ av filer som har identifierats som skadliga av [ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-163">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="1e741-164">Om du vill visa [ &amp; den](https://protection.office.com)här rapporten går du till **Rapporter** \> \> **instrumentpanels-ATP-filtyper**. **Dashboard**</span><span class="sxs-lookup"><span data-stu-id="1e741-164">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![Rapporten för ATP-filtyper](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="1e741-166">När du hovrar över en viss dag kan du se fördelningen av typer av skadliga filer som upptäcktes av [ATP Safe Bilagor](atp-safe-attachments.md) och [anti-spam &amp; anti-malware skydd](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-166">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP-filtyper rapportdata för en dag](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="1e741-168">Rapport om ATP-meddelandedisposition</span><span class="sxs-lookup"><span data-stu-id="1e741-168">ATP Message Disposition report</span></span>

<span data-ttu-id="1e741-169">**Atp Message Disposition-rapporten** visar de åtgärder som har vidtagits för e-postmeddelanden som har identifierats som skadliga innehåll.</span><span class="sxs-lookup"><span data-stu-id="1e741-169">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="1e741-170">Om du vill visa den här rapporten går du till \> **Rapportinstrumentpanelen** \> **ATP Message Disposition**i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com). **Reports**</span><span class="sxs-lookup"><span data-stu-id="1e741-170">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![ATP-meddelandedispositionsrapport](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="1e741-172">När du hovrar över en stapel i diagrammet kan du se vilka åtgärder som har vidtagits för upptäckt e-post för den dagen.</span><span class="sxs-lookup"><span data-stu-id="1e741-172">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![ATP Message Disposition Rapport data för en dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="1e741-174">Ytterligare rapporter att visa</span><span class="sxs-lookup"><span data-stu-id="1e741-174">Additional reports to view</span></span>

<span data-ttu-id="1e741-175">Utöver de ATP-rapporter som beskrivs i den här artikeln finns flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="1e741-175">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="1e741-176">**Rapport(er)**</span><span class="sxs-lookup"><span data-stu-id="1e741-176">**Report(s)**</span></span>|<span data-ttu-id="1e741-177">**Information**</span><span class="sxs-lookup"><span data-stu-id="1e741-177">**Details**</span></span>|
|<span data-ttu-id="1e741-178">**Explorer** eller **realtidsidentifieringar**: (Office 365 ATP Plan 2-kunder har Explorer; Office 365 ATP-abonnemang 1-kunder har identifieringar i realtid.)</span><span class="sxs-lookup"><span data-stu-id="1e741-178">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="1e741-179">Hotutforskaren (och realtidsidentifieringar)</span><span class="sxs-lookup"><span data-stu-id="1e741-179">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="1e741-180">**Säkerhetsrapporter för e-post**, till exempel en rapport om toppavsändare och mottagare, en rapport om falska e-postmeddelanden och en rapport om skräppostidentifieringar.</span><span class="sxs-lookup"><span data-stu-id="1e741-180">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="1e741-181">Visa säkerhetsrapporter för &amp; e-post i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1e741-181">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="1e741-182">**ATP-url-spårning för säkra länkar:**(Det här är en rapport som du genererar med PowerShell.) Den här rapporten visar resultaten av ATP Safe Links-åtgärder under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="1e741-182">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="1e741-183">Cmdlet-referens för Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="1e741-183">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|<span data-ttu-id="1e741-184">**EOP- och ATP-resultat**: (Det här är en anpassad rapport som du genererar med PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1e741-184">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1e741-185">Den här rapporten innehåller information, till exempel Domän, Datum, Händelsetyp, Riktning, Åtgärd och Meddelanderäkning.</span><span class="sxs-lookup"><span data-stu-id="1e741-185">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="1e741-186">Cmdlet-referens för Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="1e741-186">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|<span data-ttu-id="1e741-187">**EOP- och ATP-identifieringar**: (Det här är en anpassad rapport som du genererar med PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1e741-187">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="1e741-188">Den här rapporten innehåller information om skadliga filer eller webbadresser, nätfiskeförsök, personifiering och andra potentiella hot i e-post eller filer.</span><span class="sxs-lookup"><span data-stu-id="1e741-188">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="1e741-189">Cmdlet-referens för Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="1e741-189">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="1e741-190">Vilka behörigheter behövs för att visa ATP-rapporterna?</span><span class="sxs-lookup"><span data-stu-id="1e741-190">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="1e741-191">Om du vill visa och använda de rapporter som beskrivs i den här artikeln **måste du ha tilldelat en lämplig roll för både Security &amp; Compliance Center och Administrationscenter för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1e741-191">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="1e741-192">För Säkerhetsefterlevnadscenter &amp; måste du ha tilldelat en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="1e741-192">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="1e741-193">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="1e741-193">Organization Management</span></span>
  - <span data-ttu-id="1e741-194">Säkerhetsadministratör (detta kan tilldelas i Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory admin center ( ))</span><span class="sxs-lookup"><span data-stu-id="1e741-194">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1e741-195">Säkerhetsoperatör (detta kan tilldelas i Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory admin center ( ))</span><span class="sxs-lookup"><span data-stu-id="1e741-195">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="1e741-196">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="1e741-196">Security Reader</span></span>

- <span data-ttu-id="1e741-197">För Exchange Online måste du ha någon av följande roller tilldelad i administrationscentret för Exchange ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) eller med PowerShell-cmdletar (Se Exchange Online [PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="1e741-197">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="1e741-198">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="1e741-198">Organization Management</span></span>
  - <span data-ttu-id="1e741-199">Organisationshantering endast för vy</span><span class="sxs-lookup"><span data-stu-id="1e741-199">View-only Organization Management</span></span>
  - <span data-ttu-id="1e741-200">Rollen Endast visa mottagare</span><span class="sxs-lookup"><span data-stu-id="1e741-200">View-Only Recipients role</span></span>
  - <span data-ttu-id="1e741-201">Hantering av efterlevnad</span><span class="sxs-lookup"><span data-stu-id="1e741-201">Compliance Management</span></span>

<span data-ttu-id="1e741-202">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="1e741-202">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="1e741-203">Behörigheter i &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1e741-203">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="1e741-204">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1e741-204">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="1e741-205">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="1e741-205">What if the reports aren't showing data?</span></span>

<span data-ttu-id="1e741-206">Om du inte ser data i ATP-rapporterna dubbelkollar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="1e741-206">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="1e741-207">Din organisation måste ha [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) och [ATP-principer för säkra bilagor](set-up-atp-safe-attachments-policies.md) definierade för att ATP-skydd ska vara på plats.</span><span class="sxs-lookup"><span data-stu-id="1e741-207">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="1e741-208">Se även [skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="1e741-208">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e741-209">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1e741-209">Related topics</span></span>

[<span data-ttu-id="1e741-210">Rapporter och insikter i &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1e741-210">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="1e741-211">Skapa ett schema för en &amp; rapport i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1e741-211">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="1e741-212">Konfigurera och hämta en anpassad &amp; rapport i Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="1e741-212">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="1e741-213">Rollbehörigheter (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e741-213">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
