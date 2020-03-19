---
title: Visa rapporter för Office 365 Advanced Threat Protection, malware reports, phish reports, komprometterade konton, URL-skyddsstatus, hotrapportering, rapporthot
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 02/07/2020
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
description: Sök efter och använda rapporter för Office 365 Advanced Threat Protection i Security &amp; Compliance Center.
ms.openlocfilehash: 1531a70439ae1c093ee472923696895eda0bc644
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42811139"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="424de-103">Visa rapporter för Avancerad hotskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="424de-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="424de-104">Om din organisation har [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) och du har de behörigheter som [krävs](#what-permissions-are-needed-to-view-the-atp-reports)kan du använda flera ATP-rapporter i Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="424de-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="424de-105">(Gå till **instrumentpanelen** **rapporter** \> .)</span><span class="sxs-lookup"><span data-stu-id="424de-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![Instrumentpanelen &amp; i Security Compliance Center kan hjälpa dig att se var avancerat hotskydd fungerar](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="424de-107">ATP-rapporter innehåller följande:</span><span class="sxs-lookup"><span data-stu-id="424de-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="424de-108">Rapport om skydd för hot</span><span class="sxs-lookup"><span data-stu-id="424de-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="424de-109">Rapporten ATP-filtyper</span><span class="sxs-lookup"><span data-stu-id="424de-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="424de-110">RAPPORT FÖR ATP-meddelandedisposition</span><span class="sxs-lookup"><span data-stu-id="424de-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="424de-111">antingen [identifieringi realtid eller Explorer](threat-explorer.md) (beroende på om du har Office 365 ATP-abonnemang 1 eller 2)</span><span class="sxs-lookup"><span data-stu-id="424de-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="424de-112">... [och mer](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="424de-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="424de-113">Läs den här artikeln om du vill få en översikt över ATP-rapporter och hur du använder dem.</span><span class="sxs-lookup"><span data-stu-id="424de-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="424de-114">Rapport om skydd för hot</span><span class="sxs-lookup"><span data-stu-id="424de-114">Threat Protection Status report</span></span>

<span data-ttu-id="424de-115">Rapporten **Status för skydd för hot** är en enda vy som samlar information om skadligt innehåll och skadlige e-postmeddelanden som har upptäckts och blockerats av Exchange Online [Protection](exchange-online-protection-overview.md) (EOP) och [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="424de-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="424de-116">Den här rapporten är användbar för att visa identifieringar över tid (upp till 90 dagar) och det gör det möjligt för säkerhetsadministratörer att identifiera trender eller avgöra om principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="424de-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="424de-117">Rapporten ger ett aggregerat antal unika e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (WEBBADRESSER) som blockerades av anti-malware motor, [noll timmars automatisk rensning (ZAP)](zero-hour-auto-purge.md)och ATP-funktioner som [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md)och [ATP anti-phishing funktioner](atp-anti-phishing.md).</span><span class="sxs-lookup"><span data-stu-id="424de-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

<span data-ttu-id="424de-118">Filter och uppdelningar av informationen möjliggör mer detaljerade kategoriseringar av informationen i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="424de-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="424de-119">Specifikt finns det en "bryta ner av" meny som ingår för *e-> Phish* och *E-> Malware visningar*.</span><span class="sxs-lookup"><span data-stu-id="424de-119">Specifically, there is a 'break down by' menu included for *Email > Phish* and *Email > Malware views*.</span></span> <span data-ttu-id="424de-120">Det kommer att dela upp data i:</span><span class="sxs-lookup"><span data-stu-id="424de-120">It will break down the data into:</span></span>

| |  |
|---------|---------|
|<span data-ttu-id="424de-121">Efter identifieringstyp</span><span class="sxs-lookup"><span data-stu-id="424de-121">By detection type</span></span>    | <span data-ttu-id="424de-122">Vilken politik bidrog till att fånga dessa hot?</span><span class="sxs-lookup"><span data-stu-id="424de-122">What policy helped catch these threats?</span></span>         |
|<span data-ttu-id="424de-123">Genom detektionsteknik</span><span class="sxs-lookup"><span data-stu-id="424de-123">By detection technology</span></span>     | <span data-ttu-id="424de-124">Vilken underliggande Microsoft-teknik fångade hotet?</span><span class="sxs-lookup"><span data-stu-id="424de-124">What underlying Microsoft technology caught the threat?</span></span>        |
|<span data-ttu-id="424de-125">Efter leveransstatus</span><span class="sxs-lookup"><span data-stu-id="424de-125">By delivery status</span></span>     | <span data-ttu-id="424de-126">Vad hände med e-postmeddelanden som upptäckts som hot?</span><span class="sxs-lookup"><span data-stu-id="424de-126">What happened to the email messages detected as threats?</span></span>         |
| | |

> [!TIP]
> <span data-ttu-id="424de-127">Både e-> Phish | Malware vyer har detaljerade uppdelningar för detektionsteknik som visas, med kategorier som *ATP-genererade fil rykte,* *Fil detonation,* *URL detonation,* *Anti-parodi: DMARC misslyckande,* till exempel, till hjälp för att precisera exakt vilken funktion som ledde din organisation att fånga hot.</span><span class="sxs-lookup"><span data-stu-id="424de-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Hot skyddsstatusrapport listrutan som visar "break down by".](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="424de-129">Dessa vyer ger dig möjlighet att exportera, via ett knappklick (i E-post > Phish, E-post > malware och innehåll > Malware visningar).</span><span class="sxs-lookup"><span data-stu-id="424de-129">These views give you the option to export, via a button click (in Email > Phish, Email > Malware, and Content > Malware views).</span></span> <span data-ttu-id="424de-130">De aggregerade data som exporteras till datorn kan öppnas i Excel.</span><span class="sxs-lookup"><span data-stu-id="424de-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Den här bilden visar Exportera som ett alternativ på menyn för vyn Skadlig kod, direkt mellan Skapa schema och begäranderapport.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="424de-132">Vyerna Översikt och E-postmeddelanden visar information inom några timmar efter bearbetning en timme (efterfrågan åter.</span><span class="sxs-lookup"><span data-stu-id="424de-132">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="424de-133">högre hastigheter här har varit en tydlig signal)!</span><span class="sxs-lookup"><span data-stu-id="424de-133">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="424de-134">En statusrapport för hotskydd är tillgänglig för kunder som antingen har [Office 365 ATP](office-365-atp.md) eller [Exchange Online Protection](exchange-online-protection-eop.md) (EOP). Informationen som visas i rapporten Status status för hotskydd för ATP-kunder kommer dock sannolikt att innehålla andra data än vad EOP-kunder kan se.</span><span class="sxs-lookup"><span data-stu-id="424de-134">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="424de-135">Rapporten Statusför hotskydd för ATP-kunder innehåller till exempel information om [skadliga filer som upptäckts i SharePoint Online, OneDrive eller Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="424de-135">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="424de-136">Sådan information är specifik för ATP, så kunder som har EOP men inte ATP kommer inte att se dessa uppgifter i sin hotskyddsstatusrapport.</span><span class="sxs-lookup"><span data-stu-id="424de-136">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="424de-137">Om du vill visa rapporten Status för hotskydd \> går du till **Rapportinstrumentpanelens** \> **Reports** **hotskyddsstatus**i [säkerhetsefterlevnadscenter &amp; ](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="424de-137">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![RAPPORT OM STATUSRAPPORT för ATP-hotskydd](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="424de-139">Om du vill få detaljerad status för en dag håller du muspekaren över diagrammet.</span><span class="sxs-lookup"><span data-stu-id="424de-139">To get detailed status for a day, hover over the graph.</span></span>
  
![STATUSdata för ATP-hotskydd för en dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="424de-141">Som standard visar rapporten Status för hotskydd data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="424de-141">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="424de-142">Du kan dock välja **Filter** och ändra datumintervallet för att visa data i upp till 90 dagar.</span><span class="sxs-lookup"><span data-stu-id="424de-142">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="424de-143">(Om du använder en utvärderingsprenumeration kan du vara begränsad till 30 dagars data.)</span><span class="sxs-lookup"><span data-stu-id="424de-143">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![Statusfilter för ATP-hotskydd](../../media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="424de-145">Du kan också använda **visa data efter** meny för att ändra vilken information som visas i rapporten.</span><span class="sxs-lookup"><span data-stu-id="424de-145">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![Visa alternativ för STATUSrapport för ATP-hotskydd](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="424de-147">Rapport om status för URL-skydd</span><span class="sxs-lookup"><span data-stu-id="424de-147">URL Protection Status report</span></span>

<span data-ttu-id="424de-148">Den här rapporten baseras på insamlade data och hot har upptäckts per klick (medan de flesta andra e-posthotrelaterade rapporter är per meddelandedata).</span><span class="sxs-lookup"><span data-stu-id="424de-148">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="424de-149">Den här rapporten är utformad för att visa hot som kommer från hyperlänkar i e-postmeddelanden och dokument, per klick.</span><span class="sxs-lookup"><span data-stu-id="424de-149">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="424de-150">Det finns två vyer:</span><span class="sxs-lookup"><span data-stu-id="424de-150">There are two views:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="424de-151">Skyddsåtgärd för URL-klick</span><span class="sxs-lookup"><span data-stu-id="424de-151">URL click protection action</span></span>   | <span data-ttu-id="424de-152">Se antalet url:er som blockerats, blockerats men åsidosätts med ett klick av en användare, åsidosätts med ett klick av en användare och tillåten.</span><span class="sxs-lookup"><span data-stu-id="424de-152">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>        |
|<span data-ttu-id="424de-153">URL-klick efter program</span><span class="sxs-lookup"><span data-stu-id="424de-153">URL click by application</span></span>     | <span data-ttu-id="424de-154">Se det program som url:en klickades på från.</span><span class="sxs-lookup"><span data-stu-id="424de-154">See the application from which the URL was clicked.</span></span>        |
|  |  |

<span data-ttu-id="424de-155">I informationstabellen kan du se mer information om klicktid och användarinformation.</span><span class="sxs-lookup"><span data-stu-id="424de-155">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="424de-156">Tänk slutligen på url-skyddsstatusrapporten visar skyddet från funktionen för ATP-säkra länkar, så endast kunder som har aktiverat ATP-säkra länkar kommer att se data som återspeglas i den här rapporten.</span><span class="sxs-lookup"><span data-stu-id="424de-156">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="424de-157">Detta är en *rapport om skyddstrend,* vilket innebär att data representerar trender i en större datauppsättning.</span><span class="sxs-lookup"><span data-stu-id="424de-157">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="424de-158">Rapportering är inte tillgänglig i realtid här.</span><span class="sxs-lookup"><span data-stu-id="424de-158">Reporting isn't available in real time here.</span></span> <span data-ttu-id="424de-159">För url-klickdata i realtid fortsätter du att använda URL Trace.</span><span class="sxs-lookup"><span data-stu-id="424de-159">For real time URL click data, please continue to use URL Trace.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="424de-160">Rapporten ATP-filtyper</span><span class="sxs-lookup"><span data-stu-id="424de-160">ATP File Types report</span></span>

<span data-ttu-id="424de-161">Rapporten **ATP-filtyper** visar vilken typ av filer som identifieras som skadliga av [ATP-säkra bilagor](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="424de-161">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="424de-162">Om du vill visa den här rapporten går du till **Rapporterar** \> **Dashboard** \> **ATP File Types**i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="424de-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![Rapporten ATP-filtyper](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="424de-164">När du hovrar över en viss dag kan du se fördelningen av typer av skadliga filer som har upptäckts av [ATP Safe Attachments](atp-safe-attachments.md) och [ &amp; anti-spam anti-malware skydd i Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="424de-164">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![ATP-filtyper rapporterar data för en dag](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="424de-166">RAPPORT FÖR ATP-meddelandedisposition</span><span class="sxs-lookup"><span data-stu-id="424de-166">ATP Message Disposition report</span></span>

<span data-ttu-id="424de-167">Rapporten **ATP-meddelandedisposition** visar de åtgärder som har vidtagits för e-postmeddelanden som har upptäckts ha skadligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="424de-167">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="424de-168">Om du vill visa den här rapporten går du till \> **RapportinstrumentpanelenATP-meddelandedisposition** \> **ATP Message Disposition**i [Säkerhetsefterlevnadscenter &amp; ](https://protection.office.com). **Reports**</span><span class="sxs-lookup"><span data-stu-id="424de-168">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![Rapport om disposition av ATP-meddelande](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="424de-170">När du hovrar över en stapel i diagrammet kan du se vilka åtgärder som har vidtagits för upptäckt e-post för den dagen.</span><span class="sxs-lookup"><span data-stu-id="424de-170">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![DATA för ATP-meddelandedispositionsrapport för en dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="424de-172">Ytterligare rapporter att visa</span><span class="sxs-lookup"><span data-stu-id="424de-172">Additional reports to view</span></span>

<span data-ttu-id="424de-173">Utöver de ATP-rapporter som beskrivs i den här artikeln finns flera andra rapporter tillgängliga, enligt beskrivningen i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="424de-173">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="424de-174">Rapport(er)</span><span class="sxs-lookup"><span data-stu-id="424de-174">Report(s)</span></span>  |<span data-ttu-id="424de-175">Information</span><span class="sxs-lookup"><span data-stu-id="424de-175">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="424de-176">**Explorer-** eller **realtidsidentifieringar** (Office 365 ATP Plan 2-kunder har Explorer. Office 365 ATP Plan 1-kunder har identifiering i realtid.)</span><span class="sxs-lookup"><span data-stu-id="424de-176">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="424de-177">Threat Explorer (och identifiering i realtid)</span><span class="sxs-lookup"><span data-stu-id="424de-177">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="424de-178">**E-postsäkerhetsrapporter**, till exempel en rapport över de bästa avsändarna och mottagarna, en Spoof Mail-rapport och en rapport om identifiering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="424de-178">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="424de-179">Visa e-postsäkerhetsrapporter &amp; i Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="424de-179">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="424de-180">**URL-spårning för ATP-säkra länkar** (Det här är en rapport som du genererar med PowerShell.) Den här rapporten visar resultaten av ÅTGÄRDER FÖR ATP Safe Links under de senaste sju (7) dagarna.</span><span class="sxs-lookup"><span data-stu-id="424de-180">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="424de-181">Hämta cmdlet-cmdlet-referens för get urlTrace</span><span class="sxs-lookup"><span data-stu-id="424de-181">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace) |
|<span data-ttu-id="424de-182">**EOP- och ATP-resultat** (Detta är en anpassad rapport som du genererar med PowerShell).</span><span class="sxs-lookup"><span data-stu-id="424de-182">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="424de-183">Den här rapporten innehåller information som Domän, Datum, Händelsetyp, Riktning, Åtgärd och Antal meddelanden.</span><span class="sxs-lookup"><span data-stu-id="424de-183">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="424de-184">Hämta cmdlet-referens för Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="424de-184">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport) |
|<span data-ttu-id="424de-185">**EOP- och ATP-identifieringar** (Det här är en anpassad rapport som du genererar med PowerShell).</span><span class="sxs-lookup"><span data-stu-id="424de-185">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="424de-186">Den här rapporten innehåller information om skadliga filer eller webbadresser, nätfiskeförsök, personifiering och andra potentiella hot i e-post eller filer.</span><span class="sxs-lookup"><span data-stu-id="424de-186">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="424de-187">Hämta cmdlet-referens för get-mailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="424de-187">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="424de-188">Vilka behörigheter krävs för att visa ATP-rapporterna?</span><span class="sxs-lookup"><span data-stu-id="424de-188">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="424de-189">För att kunna visa och använda de rapporter som beskrivs i den här artikeln **måste du ha en lämplig roll som tilldelats både administrationscenter för säkerhetsefterlevnad &amp; och administrationscentret för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="424de-189">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="424de-190">För Security &amp; Compliance Center måste du ha en av följande roller tilldelad:</span><span class="sxs-lookup"><span data-stu-id="424de-190">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="424de-191">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="424de-191">Organization Management</span></span>
    - <span data-ttu-id="424de-192">Säkerhetsadministratör (detta kan tilldelas i Administrationscentret[https://aad.portal.azure.com](https://aad.portal.azure.com)för Azure Active Directory ())</span><span class="sxs-lookup"><span data-stu-id="424de-192">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="424de-193">Säkerhetsoperator (detta kan tilldelas i Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory administrationscenter ())</span><span class="sxs-lookup"><span data-stu-id="424de-193">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="424de-194">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="424de-194">Security Reader</span></span>

- <span data-ttu-id="424de-195">För Exchange Online måste du ha en av följande roller som[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)tilldelats i antingen Administrationscentret för Exchange ( ) eller med PowerShell-cmdlets (se [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="424de-195">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>
    - <span data-ttu-id="424de-196">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="424de-196">Organization Management</span></span>
    - <span data-ttu-id="424de-197">Organisationshantering för endast vy</span><span class="sxs-lookup"><span data-stu-id="424de-197">View-only Organization Management</span></span>
    - <span data-ttu-id="424de-198">Roll för endast visningsmottagare</span><span class="sxs-lookup"><span data-stu-id="424de-198">View-Only Recipients role</span></span>
    - <span data-ttu-id="424de-199">Efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="424de-199">Compliance Management</span></span>

<span data-ttu-id="424de-200">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="424de-200">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="424de-201">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="424de-201">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="424de-202">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="424de-202">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="424de-203">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="424de-203">What if the reports aren't showing data?</span></span>

<span data-ttu-id="424de-204">Om du inte ser data i dina ATP-rapporter dubbelkontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="424de-204">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="424de-205">Din organisation måste ha [ATP Safe Links-principer](set-up-atp-safe-links-policies.md) och [ATP Safe Attachments-principer](set-up-atp-safe-attachments-policies.md) som definierats för att ATP-skyddet ska vara på plats.</span><span class="sxs-lookup"><span data-stu-id="424de-205">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="424de-206">Se även [skydd mot skräppost och skadlig kod i Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="424de-206">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="424de-207">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="424de-207">Related topics</span></span>

[<span data-ttu-id="424de-208">Rapporter och insikter i Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="424de-208">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="424de-209">Skapa ett schema för en &amp; rapport i Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="424de-209">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="424de-210">Konfigurera och hämta en anpassad &amp; rapport i Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="424de-210">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="424de-211">Behörighet för roller (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="424de-211">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
  

