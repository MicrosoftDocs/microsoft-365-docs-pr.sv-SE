---
title: Microsoft Defender AV-händelse-ID och felkoder
description: Leta upp orsaker och lösningar för Microsoft Defender Antivirus och fel
keywords: händelse, felkod, siem, loggning, felsökning, wef, windows-händelse vidarebefordran
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cba7a9d6ed23ac1dc72ef6cbcecfdfc7a0f4c60b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926289"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="2ad37-104">Felsök problem med Microsoft Defender Antivirus genom att granska händelseloggar och felkoder</span><span class="sxs-lookup"><span data-stu-id="2ad37-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2ad37-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="2ad37-105">**Applies to:**</span></span>

- [<span data-ttu-id="2ad37-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="2ad37-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2ad37-107">Om du stöter på problem Microsoft Defender Antivirus tabellerna i det här avsnittet för att hitta ett matchande problem och en möjlig lösning.</span><span class="sxs-lookup"><span data-stu-id="2ad37-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="2ad37-108">Tabelllistan:</span><span class="sxs-lookup"><span data-stu-id="2ad37-108">The tables list:</span></span>

- <span data-ttu-id="2ad37-109">[Microsoft Defender Antivirus händelse-Ds](#windows-defender-av-ids) (detta gäller både för Windows 10 och Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="2ad37-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="2ad37-110">Microsoft Defender Antivirus felkoder för klienten</span><span class="sxs-lookup"><span data-stu-id="2ad37-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="2ad37-111">Intern Microsoft Defender Antivirus för klientfelkoder (används av Microsoft under utveckling och testning)</span><span class="sxs-lookup"><span data-stu-id="2ad37-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="2ad37-112">Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar:</span><span class="sxs-lookup"><span data-stu-id="2ad37-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="2ad37-113">Molnbaserat skydd</span><span class="sxs-lookup"><span data-stu-id="2ad37-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="2ad37-114">Fast learning (inklusive Block at first sight)</span><span class="sxs-lookup"><span data-stu-id="2ad37-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="2ad37-115">Potentiellt oönskad programblockering</span><span class="sxs-lookup"><span data-stu-id="2ad37-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="2ad37-116">Microsoft Defender Antivirus-händelse-ID</span><span class="sxs-lookup"><span data-stu-id="2ad37-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="2ad37-117">Microsoft Defender Antivirus registrerar händelse-IDt i Windows händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="2ad37-118">Du kan direkt visa händelseloggen, eller om du har ett säkerhetsinformations- och händelsehanteringsverktyg från tredje part (SIEM), kan du också använda [Microsoft Defender Antivirus-klienthändelse-ID](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) för att granska specifika händelser och fel från slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="2ad37-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="2ad37-119">Tabellen i det här avsnittet innehåller huvud-MICROSOFT DEFENDER ANTIVIRUS och, om möjligt, förslag på lösningar för att åtgärda eller lösa felet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="2ad37-120">Visa en Microsoft Defender Antivirus händelse</span><span class="sxs-lookup"><span data-stu-id="2ad37-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="2ad37-121">Öppna **Loggboken.**</span><span class="sxs-lookup"><span data-stu-id="2ad37-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="2ad37-122">I konsolträdet expanderar **du Program- och tjänstloggar** och **sedan Microsoft** och **Windows** och **sedan Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="2ad37-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="2ad37-123">Dubbelklicka på **Drift.**</span><span class="sxs-lookup"><span data-stu-id="2ad37-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="2ad37-124">I informationsfönstret kan du visa listan med enskilda händelser för att hitta händelsen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="2ad37-125">Klicka på händelsen om du vill se specifik information om en händelse i det nedre fönstret, under **flikarna** **Allmänt och** Information.</span><span class="sxs-lookup"><span data-stu-id="2ad37-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="2ad37-126">Händelse-ID: 1000</span><span class="sxs-lookup"><span data-stu-id="2ad37-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-127">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="2ad37-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-129">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-129">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-130">
<b>En sökning mot skadlig programvara startade. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="2ad37-131">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-132">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-133">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-134">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-134">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-135">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-136">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-137">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-137">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-138">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-138">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-139">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-139">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-140">
</dt>
<dt>Sökresurser: &lt; Resurser (till exempel filer/kataloger/BHO) som &gt; skannades.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-141">Händelse-ID: 1001</span><span class="sxs-lookup"><span data-stu-id="2ad37-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-142">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-144">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-144">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-145">
<b>En sökning efter program mot skadlig programvara slutförd.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-146">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-147">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-148">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-149">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-149">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-150">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-151">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-152">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-152">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-153">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-153">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-154">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-154">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-155">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarens</dt>
<dt>genomsökningstid: &lt; Varaktigheten &gt; för en genomsökning.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-156">Händelse-ID: 1002</span><span class="sxs-lookup"><span data-stu-id="2ad37-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-157">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-159">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-159">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-160">
<b>En sökning efter program mot skadlig programvara stoppades innan den slutfördes. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-161">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-162">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-163">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-164">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-164">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-165">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-166">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-167">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-167">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-168">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-168">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-169">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-169">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-170">
</dt>
<dt>Användare: &lt; Domain &gt; &amp; lt; &gt;Användarens</dt>
<dt>genomsökningstid: &lt; Varaktigheten &gt; för en genomsökning.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-171">Händelse-ID: 1003</span><span class="sxs-lookup"><span data-stu-id="2ad37-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-172">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-174">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-174">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-175">
<b>En sökning efter program mot skadlig programvara pausades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-176">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-177">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-178">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-179">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-179">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-180">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-181">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-182">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-182">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-183">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-183">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-184">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-184">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-185">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; Användare&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-186">Händelse-ID: 1004</span><span class="sxs-lookup"><span data-stu-id="2ad37-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-187">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-189">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-189">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-190">
<b>En sökning efter program mot skadlig programvara återupptades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-191">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-192">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-193">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-194">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-194">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-195">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-196">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-197">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-197">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-198">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-198">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-199">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-199">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-200">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; Användare&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-201">Händelse-ID: 1005</span><span class="sxs-lookup"><span data-stu-id="2ad37-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-202">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-204">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-204">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-205">
<b>En sökning efter program mot skadlig programvara misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-206">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="2ad37-207">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-208">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-209">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-209">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-210">Antimalware</span></span></li>
</ul><span data-ttu-id="2ad37-211">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-212">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-212">Full scan</span></span></li>
<li><span data-ttu-id="2ad37-213">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-213">Quick scan</span></span></li>
<li><span data-ttu-id="2ad37-214">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="2ad37-214">Customer scan</span></span></li>
</ul><span data-ttu-id="2ad37-215">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-216">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-217">Ett fel uppstod på antivirusklienten och den aktuella genomsökningen har stoppats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="2ad37-218">Genomsökningen kan misslyckas på grund av problem på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="2ad37-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="2ad37-219">Den här händelseposten omfattar genomsöknings-ID,typ av genomsökning (Microsoft Defender Antivirus, antispionprogram, program mot skadlig kod), genomsökningsparametrar, användaren som startade genomsökningen, felkoden och en beskrivning av felet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="2ad37-220">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="2ad37-221">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="2ad37-222">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="2ad37-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="2ad37-223">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-224">Händelse-ID: 1006</span><span class="sxs-lookup"><span data-stu-id="2ad37-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-225">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-227">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-227">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-228">
<b>Kod mot skadlig programvara eller annan potentiellt oönskad programvara hittades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-229">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-230">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-231">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-232">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-232">Low</span></span></li>
<li><span data-ttu-id="2ad37-233">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-233">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-234">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-234">High</span></span></li>
<li><span data-ttu-id="2ad37-235">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-235">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-236">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-237">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-237">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-238">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-238">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-239">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-239">Network share</span></span></li>
<li><span data-ttu-id="2ad37-240">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-240">Internet</span></span></li>
<li><span data-ttu-id="2ad37-241">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-242">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-243">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-244">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-245">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-245">Generic</span></span></li>
<li><span data-ttu-id="2ad37-246">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-246">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-247">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-248">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-249">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-249">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-250">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-250">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-251">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-252">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-253">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-254">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-255">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-256">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-257">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-258">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-259">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-260"></dt>
<dt>UAC-status: &lt; Status &gt; </dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signaturversion:</dt>Definition
<dt> &lt; version &gt; </dt>Engine
<dt>Version: skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-261">Händelse-ID: 1007</span><span class="sxs-lookup"><span data-stu-id="2ad37-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-262">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-264">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-264">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-265">
<b>Program mot skadlig programvara utförde en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-266">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-267">Microsoft Defender Antivirus har vidtagit åtgärder för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="2ad37-268">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-269">
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt> &lt; Namn-ID för &gt; </dt>
<dt>hot: Allvarlighetsgrad för &lt; &gt; hot-ID:</dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-270">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-270">Low</span></span></li>
<li><span data-ttu-id="2ad37-271">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-271">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-272">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-272">High</span></span></li>
<li><span data-ttu-id="2ad37-273">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-273">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-274">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt> Åtgärd: &lt; &gt; Åtgärd, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-275">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="2ad37-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="2ad37-276">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="2ad37-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="2ad37-277">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="2ad37-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="2ad37-278">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="2ad37-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="2ad37-279">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="2ad37-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="2ad37-280">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-280">No action: No action</span></span></li>
<li><span data-ttu-id="2ad37-281">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="2ad37-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="2ad37-282">
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-283">Händelse-ID: 1008</span><span class="sxs-lookup"><span data-stu-id="2ad37-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-284">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-286">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-286">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-287">
<b>Program mot skadlig programvara försökte utföra en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara, men åtgärden misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-288">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-289">Microsoft Defender Antivirus har stött på ett fel när du vidtar åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="2ad37-290">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-291">
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt> &lt; Namn-ID för &gt; </dt>
<dt>hot: Allvarlighetsgrad för &lt; &gt; hot-ID:</dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-292">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-292">Low</span></span></li>
<li><span data-ttu-id="2ad37-293">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-293">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-294">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-294">High</span></span></li>
<li><span data-ttu-id="2ad37-295">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-295">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-296">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Filsökväg &gt; </dt> 
<dt> &lt; Åtgärd: &gt; Åtgärd, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-297">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="2ad37-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="2ad37-298">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="2ad37-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="2ad37-299">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="2ad37-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="2ad37-300">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="2ad37-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="2ad37-301">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="2ad37-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="2ad37-302">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-302">No action: No action</span></span></li>
<li><span data-ttu-id="2ad37-303">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="2ad37-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="2ad37-304">
</dt>
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-305">Händelse-ID: 1009</span><span class="sxs-lookup"><span data-stu-id="2ad37-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-306">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-308">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-308">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-309">
<b>Program mot skadlig programvara återställde ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-310">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-311">Microsoft Defender Antivirus har återställt ett objekt från karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="2ad37-312">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-313">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-314">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-314">Low</span></span></li>
<li><span data-ttu-id="2ad37-315">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-315">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-316">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-316">High</span></span></li>
<li><span data-ttu-id="2ad37-317">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-317">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-318">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarsignaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-319">Händelse-ID: 1010</span><span class="sxs-lookup"><span data-stu-id="2ad37-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-320">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-322">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-322">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-323">
<b>Program mot skadlig programvara kunde inte återställa ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-324">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-325">Microsoft Defender Antivirus har stött på ett fel när du försöker återställa ett objekt från karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="2ad37-326">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-327">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-328">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-328">Low</span></span></li>
<li><span data-ttu-id="2ad37-329">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-329">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-330">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-330">High</span></span></li>
<li><span data-ttu-id="2ad37-331">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-331">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-332">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; skyddsmotor mot skadlig kod &gt; version</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-333">Händelse-ID: 1011</span><span class="sxs-lookup"><span data-stu-id="2ad37-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-334">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-336">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-336">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-337">
<b>Program mot skadlig programvara tog bort ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-338">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-339">Microsoft Defender Antivirus har tagit bort ett objekt från karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="2ad37-340">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-341">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-342">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-342">Low</span></span></li>
<li><span data-ttu-id="2ad37-343">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-343">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-344">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-344">High</span></span></li>
<li><span data-ttu-id="2ad37-345">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-345">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-346">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarsignaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-347">Händelse-ID: 1012</span><span class="sxs-lookup"><span data-stu-id="2ad37-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-348">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-350">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-350">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-351">
<b>Det gick inte att ta bort ett objekt från karantän på plattformen för program mot skadlig programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-352">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-353">Microsoft Defender Antivirus har stött på ett fel när ett objekt ska tas bort från karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="2ad37-354">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-355">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-356">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-356">Low</span></span></li>
<li><span data-ttu-id="2ad37-357">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-357">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-358">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-358">High</span></span></li>
<li><span data-ttu-id="2ad37-359">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-359">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-360">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; skyddsmotor mot skadlig kod &gt; version</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-361">Händelse-ID: 1013</span><span class="sxs-lookup"><span data-stu-id="2ad37-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-362">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-364">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-364">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-365">
<b>Program mot skadlig programvara raderades från historiken för skadlig programvara och annan potentiellt oönskad programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-366">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-367">Microsoft Defender Antivirus har tagit bort historik över skadlig programvara och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="2ad37-368">
<dt>Tid: Tiden då händelsen inträffade, till exempel när historiken rensas. Den här parametern används inte i hothändelser, så det finns ingen förvirring kring om det är åtgärdstid eller smitta tid. För dem kallar vi dem specifikt för Åtgärdstid eller Identifieringstid.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-369">Händelse-ID: 1014</span><span class="sxs-lookup"><span data-stu-id="2ad37-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-370">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-372">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-373">Det gick inte att radera historik över skadlig programvara och annan potentiellt oönskad programvara på programplattformen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-374">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-375">Microsoft Defender Antivirus har stött på ett fel i försök att ta bort historik över skadlig programvara och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="2ad37-376">
<dt>Tid: Tiden då händelsen inträffade, till exempel när historiken rensas. Den här parametern används inte i hothändelser, så det finns ingen förvirring kring om det är åtgärdstid eller smitta tid. För dem kallar vi dem specifikt för Åtgärdstid eller Identifieringstid.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-377">Händelse-ID: 1015</span><span class="sxs-lookup"><span data-stu-id="2ad37-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-378">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-380">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-380">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-381">
<b>Motprogramplattformen upptäckte misstänkt beteende.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-382">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-383">Microsoft Defender Antivirus har upptäckt ett misstänkt beteende.</span><span class="sxs-lookup"><span data-stu-id="2ad37-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="2ad37-384">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-385">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-386">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-386">Low</span></span></li>
<li><span data-ttu-id="2ad37-387">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-387">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-388">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-388">High</span></span></li>
<li><span data-ttu-id="2ad37-389">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-389">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-390">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-391">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-391">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-392">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-392">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-393">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-393">Network share</span></span></li>
<li><span data-ttu-id="2ad37-394">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-394">Internet</span></span></li>
<li><span data-ttu-id="2ad37-395">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-396">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-397">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-398">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-399">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-399">Generic</span></span></li>
<li><span data-ttu-id="2ad37-400">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-400">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-401">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-402">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-403">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-403">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-404">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-404">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-405">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-406">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-407">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-408">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-409">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-410">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-411">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-412">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-413">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-414"></dt>
<dt>UAC-status: &lt; Status &gt; </dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signatur-ID:</dt>
<dt>Uppräkningsmatchning för allvarlighetsgrad.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; skyddsmotor mot skadlig kod version &gt; </dt>
<dt>återgivning etikett:</dt>
<dt>Target File Name: Filnamn för &lt; &gt; filen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-415">Händelse-ID: 1116</span><span class="sxs-lookup"><span data-stu-id="2ad37-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-416">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-418">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-418">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-419">
<b>Program mot skadlig programvara eller annan potentiellt oönskad programvara har upptäckts. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-420">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-421">Microsoft Defender Antivirus har upptäckt skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="2ad37-422">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-423">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-424">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-424">Low</span></span></li>
<li><span data-ttu-id="2ad37-425">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-425">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-426">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-426">High</span></span></li>
<li><span data-ttu-id="2ad37-427">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-427">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-428">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-429">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-429">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-430">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-430">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-431">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-431">Network share</span></span></li>
<li><span data-ttu-id="2ad37-432">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-432">Internet</span></span></li>
<li><span data-ttu-id="2ad37-433">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-434">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-435">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-436">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-437">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-437">Generic</span></span></li>
<li><span data-ttu-id="2ad37-438">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-438">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-439">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-440">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-441">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-441">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-442">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-442">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-443">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-444">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-445">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-446">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-447">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-448">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-449">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-450">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-451">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-452"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signaturversion:</dt>Definition
<dt> &lt; version &gt; </dt>Engine
<dt>Version: skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-453">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-454">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-454">No action is required.</span></span> <span data-ttu-id="2ad37-455">Microsoft Defender Antivirus kan avbryta och vidta rutinmässiga åtgärder mot det här hotet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="2ad37-456">Om du vill ta bort risken manuellt går du till Microsoft Defender Antivirus klickar på <b>Rensa dator.</b></span><span class="sxs-lookup"><span data-stu-id="2ad37-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-457">Händelse-ID: 1117</span><span class="sxs-lookup"><span data-stu-id="2ad37-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-458">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-460">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-460">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-461">
<b>Program mot skadlig programvara utförde en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-462">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-463">Microsoft Defender Antivirus har vidtagit åtgärder för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="2ad37-464">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-465">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-466">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-466">Low</span></span></li>
<li><span data-ttu-id="2ad37-467">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-467">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-468">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-468">High</span></span></li>
<li><span data-ttu-id="2ad37-469">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-469">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-470">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-471">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-471">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-472">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-472">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-473">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-473">Network share</span></span></li>
<li><span data-ttu-id="2ad37-474">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-474">Internet</span></span></li>
<li><span data-ttu-id="2ad37-475">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-476">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-477">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-478">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-479">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-479">Generic</span></span></li>
<li><span data-ttu-id="2ad37-480">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-480">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-481">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-482">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-483">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-483">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-484">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-484">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-485">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-486">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-487">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-488">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-489">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-490">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-491">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-492">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-493">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-494"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-495">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="2ad37-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="2ad37-496">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="2ad37-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="2ad37-497">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="2ad37-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="2ad37-498">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="2ad37-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="2ad37-499">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="2ad37-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="2ad37-500">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-500">No action: No action</span></span></li>
<li><span data-ttu-id="2ad37-501">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="2ad37-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="2ad37-502">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>skyddsmotor mot skadlig kod &lt; version &gt; </dt> OBS! När Microsoft Defender Antivirus, Microsoft Security Essentials, Borttagning av skadlig programvara eller System Center Endpoint Protection upptäcker en skadlig programvara återställs följande systeminställningar och tjänster som den skadliga programvaran kan ha ändrat:</span><span class="sxs-lookup"><span data-stu-id="2ad37-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="2ad37-503">Standardinställning för Internet Explorer Microsoft Edge Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="2ad37-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="2ad37-504">Inställningar för användaråtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="2ad37-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="2ad37-505">Chrome-inställningar</span><span class="sxs-lookup"><span data-stu-id="2ad37-505">Chrome settings</span></span></li>
<li><span data-ttu-id="2ad37-506">Startkontrolldata</span><span class="sxs-lookup"><span data-stu-id="2ad37-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="2ad37-507">Registerinställningar för Regedit och Aktivitetshanteraren</span><span class="sxs-lookup"><span data-stu-id="2ad37-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="2ad37-508">Windows Uppdaterings-, Background Intelligent Transfer-tjänsten och tjänsten för fjärrprocedursamtal</span><span class="sxs-lookup"><span data-stu-id="2ad37-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="2ad37-509">Windows Operativsystemsfiler</span><span class="sxs-lookup"><span data-stu-id="2ad37-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="2ad37-510">Ovanstående sammanhang gäller för följande klient- och serverversioner:</span><span class="sxs-lookup"><span data-stu-id="2ad37-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="2ad37-511">Operativsystem</span><span class="sxs-lookup"><span data-stu-id="2ad37-511">Operating system</span></span></th>
<th><span data-ttu-id="2ad37-512">Operativsystemsversion</span><span class="sxs-lookup"><span data-stu-id="2ad37-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-513">Klientoperativsystemet</span><span class="sxs-lookup"><span data-stu-id="2ad37-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="2ad37-514">Windows Vista (Service Pack 1 eller Service Pack 2), Windows 7 och senare</span><span class="sxs-lookup"><span data-stu-id="2ad37-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-515">Server-operativsystem</span><span class="sxs-lookup"><span data-stu-id="2ad37-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="2ad37-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 och Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="2ad37-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-517">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-518">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-518">No action is necessary.</span></span> <span data-ttu-id="2ad37-519">Microsoft Defender Antivirus bort eller sätta ett hot i karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-520">Händelse-ID: 1118</span><span class="sxs-lookup"><span data-stu-id="2ad37-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-521">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-523">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-523">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-524">
<b>Program mot skadlig programvara försökte utföra en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara, men åtgärden misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-525">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-526">Microsoft Defender Antivirus på ett icke-kritiskt fel när du vidtar åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="2ad37-527">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-528">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-529">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-529">Low</span></span></li>
<li><span data-ttu-id="2ad37-530">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-530">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-531">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-531">High</span></span></li>
<li><span data-ttu-id="2ad37-532">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-532">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-533">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-534">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-534">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-535">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-535">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-536">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-536">Network share</span></span></li>
<li><span data-ttu-id="2ad37-537">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-537">Internet</span></span></li>
<li><span data-ttu-id="2ad37-538">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-539">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-540">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-541">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-542">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-542">Generic</span></span></li>
<li><span data-ttu-id="2ad37-543">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-543">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-544">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-545">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-546">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-546">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-547">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-547">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-548">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-549">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-550">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-551">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-552">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-553">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-554">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-555">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-556">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-557"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-558">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="2ad37-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="2ad37-559">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="2ad37-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="2ad37-560">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="2ad37-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="2ad37-561">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="2ad37-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="2ad37-562">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="2ad37-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="2ad37-563">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-563">No action: No action</span></span></li>
<li><span data-ttu-id="2ad37-564">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="2ad37-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="2ad37-565">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; skyddsmotor mot skadlig kod &gt; version</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-566">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-567">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-567">No action is necessary.</span></span> <span data-ttu-id="2ad37-568">Microsoft Defender Antivirus kunde inte slutföra en uppgift som rör åtgärden för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="2ad37-569">Det här är inte ett kritiskt fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-570">Händelse-ID: 1119</span><span class="sxs-lookup"><span data-stu-id="2ad37-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-571">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-573">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-573">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-574">
<b>På program mot skadlig programvara påträffades ett kritiskt fel när man försökte vidta åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara. Det finns mer information i händelsemeddelandet.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-575">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-576">Microsoft Defender Antivirus har stött på ett kritiskt fel när du vidtar åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="2ad37-577">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2ad37-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="2ad37-578">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-579">Låg</span><span class="sxs-lookup"><span data-stu-id="2ad37-579">Low</span></span></li>
<li><span data-ttu-id="2ad37-580">Måttlig</span><span class="sxs-lookup"><span data-stu-id="2ad37-580">Moderate</span></span></li>
<li><span data-ttu-id="2ad37-581">Högsta</span><span class="sxs-lookup"><span data-stu-id="2ad37-581">High</span></span></li>
<li><span data-ttu-id="2ad37-582">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="2ad37-582">Severe</span></span></li>
</ul><span data-ttu-id="2ad37-583">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-584">Okänd</span><span class="sxs-lookup"><span data-stu-id="2ad37-584">Unknown</span></span></li>
<li><span data-ttu-id="2ad37-585">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="2ad37-585">Local computer</span></span></li>
<li><span data-ttu-id="2ad37-586">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-586">Network share</span></span></li>
<li><span data-ttu-id="2ad37-587">Internet</span><span class="sxs-lookup"><span data-stu-id="2ad37-587">Internet</span></span></li>
<li><span data-ttu-id="2ad37-588">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="2ad37-589">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="2ad37-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="2ad37-590">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="2ad37-591">Heuristics</span></span></li>
<li><span data-ttu-id="2ad37-592">Allmänt</span><span class="sxs-lookup"><span data-stu-id="2ad37-592">Generic</span></span></li>
<li><span data-ttu-id="2ad37-593">Betong</span><span class="sxs-lookup"><span data-stu-id="2ad37-593">Concrete</span></span></li>
<li><span data-ttu-id="2ad37-594">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="2ad37-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="2ad37-595">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="2ad37-596">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="2ad37-596">User: user initiated</span></span></li>
<li><span data-ttu-id="2ad37-597">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="2ad37-597">System: system initiated</span></span></li>
<li><span data-ttu-id="2ad37-598">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="2ad37-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="2ad37-599">IOAV: IE-nedladdningar och e Outlook för expressbilagor initierade</span><span class="sxs-lookup"><span data-stu-id="2ad37-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="2ad37-600">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="2ad37-601">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="2ad37-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="2ad37-602">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="2ad37-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="2ad37-603">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="2ad37-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="2ad37-604">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="2ad37-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="2ad37-605">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="2ad37-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="2ad37-606">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="2ad37-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="2ad37-607"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="2ad37-608">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="2ad37-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="2ad37-609">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="2ad37-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="2ad37-610">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="2ad37-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="2ad37-611">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="2ad37-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="2ad37-612">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="2ad37-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="2ad37-613">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-613">No action: No action</span></span></li>
<li><span data-ttu-id="2ad37-614">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="2ad37-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="2ad37-615">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; skyddsmotor mot skadlig kod &gt; version</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-616">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-617">På Microsoft Defender Antivirus på grund av kritiska problem påträffades det här felet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="2ad37-618">Slutpunkten kanske inte är skyddad.</span><span class="sxs-lookup"><span data-stu-id="2ad37-618">The endpoint might not be protected.</span></span> <span data-ttu-id="2ad37-619">Granska felbeskrivningen och följ sedan de relevanta <b>användaråtgärdsstegen</b> nedan.</span><span class="sxs-lookup"><span data-stu-id="2ad37-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="2ad37-620">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-620">Action</span></span></th>
<th><span data-ttu-id="2ad37-621">Användaråtgärd</span><span class="sxs-lookup"><span data-stu-id="2ad37-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="2ad37-622">
<b>Ta bort</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-623">Uppdatera definitionerna och kontrollera sedan att borttagningen lyckades.</span><span class="sxs-lookup"><span data-stu-id="2ad37-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="2ad37-624">
<b>Rensa</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-625">Uppdatera definitionerna och kontrollera sedan att korrigeringen lyckades.</span><span class="sxs-lookup"><span data-stu-id="2ad37-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="2ad37-626">
<b>Karantän</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-627">Uppdatera definitionerna och kontrollera att användaren har behörighet att komma åt nödvändiga resurser.</span><span class="sxs-lookup"><span data-stu-id="2ad37-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="2ad37-628">
<b>Tillåt</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-629">Kontrollera att användaren har behörighet att komma åt nödvändiga resurser.</span><span class="sxs-lookup"><span data-stu-id="2ad37-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="2ad37-630">Om händelsen kvarstår:</span><span class="sxs-lookup"><span data-stu-id="2ad37-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="2ad37-631">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="2ad37-632">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="2ad37-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="2ad37-633">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-634">Händelse-ID: 1120</span><span class="sxs-lookup"><span data-stu-id="2ad37-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-635">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-637">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-637">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-638">
<b>Microsoft Defender Antivirus har tagit fram hashtaggarna för en hotresurs.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-639">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-640">Microsoft Defender Antivirus-klienten är igång i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="2ad37-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="2ad37-641">
<dt>Aktuell plattformsversion: &lt; Current platform &gt; version</dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="2ad37-642"><b>Obs! Den här händelsen loggas bara om följande policy har angetts: <b>ThreatFileHashLogging osignerad</b>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-643">Händelse-ID: 1150</span><span class="sxs-lookup"><span data-stu-id="2ad37-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-644">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-646">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-646">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-647">
<b>Om din antimalware-plattform rapporterar status till en övervakningsplattform anger den här händelsen att plattform mot skadlig programvara körs och är i ett felfritt tillstånd. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-648">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-649">Microsoft Defender Antivirus-klienten är igång i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="2ad37-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="2ad37-650">
<dt>Plattformsversion: &lt; Version av &gt; signatur för</dt>
<dt>aktuell plattform: Definition &lt; version &gt; </dt>
<dt>engine version: skyddsmotor mot skadlig kod &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-651">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-652">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-652">No action is necessary.</span></span> <span data-ttu-id="2ad37-653">Klient Microsoft Defender Antivirus statusen är felfri.</span><span class="sxs-lookup"><span data-stu-id="2ad37-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="2ad37-654">Händelsen rapporteras varje timme.</span><span class="sxs-lookup"><span data-stu-id="2ad37-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="2ad37-655">Händelse-ID: 1151</span><span class="sxs-lookup"><span data-stu-id="2ad37-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-656">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-658">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-658">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-659">
<b>Endpoint Protection för klienthälsa (tid i UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-660">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-661">Hälsorapport för antivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="2ad37-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="2ad37-662">
<dt>Plattformsversion: &lt; Current platform &gt; version</dt>
<dt>Engine Version: skyddsmotor mot skadlig kod &lt; &gt; version</dt>
<dt>Network Realtime Inspection engine version: &lt; Network Realtime &gt; Inspection</dt>engine version Antivirus signature
<dt>version: Antivirus signature &lt; version &gt; </dt>
<dt>Antispyware signature version: &lt; Antispyware signature version &gt; </dt>Network
<dt>Realtime Inspection signature version: Network &lt; Realtime Inspection signature version &gt; </dt>
<dt>RTP state: Skyddtillstånd i realtid (aktiverad eller inaktiverad) &lt; &gt; </dt>OA-läge: IOAV-läge vid åtkomst
<dt> &lt; &gt; (aktiverad</dt>eller inaktiverad): IE-nedladdningar och
<dt>Outlook &lt; Express-bilagor &gt; (aktiverad</dt>eller inaktiverad)
<dt>BM-läge: &lt; Funktionsövervakningstillstånd &gt; (aktiverad</dt>eller inaktiverad) antivirussignatur
<dt>ålder: &lt; Antivirussignatur ålder &gt; (i dagar)</dt>
<dt>Antispyware signature age: &lt; Antispyware signature age &gt; (in days)</dt>Last quick scan age: Last quick scan
<dt>age &lt; &gt; (in days)</dt>Last full scan
<dt>age: Last full scan age &lt; &gt; (in days)</dt>
<dt>Antivirus signature creation time: ? &lt; Tid för &gt; att skapa antivirussignaturer</dt>
<dt>Tid då man skapade antispionwaresignaturer: ? &lt; Tid för att skapa &gt; antispionprogramssignaturer</dt>
<dt>Senaste snabbstarttiden: ? &lt; Sista snabba skanningens &gt; starttid</dt>Sista snabba
<dt>genomsökning sluttid: ? &lt; &gt;</dt>Sista snabba skanningens sluttid Senaste snabbsökningskälla: Senaste snabbsökningskälla (0 = genomsökning&#39;inte
<dt> &lt; &gt; körts, 1 = användare initierad, 2 = systeminitierad)</dt>Senaste
<dt>fullständiga genomsökningsstarttid: ? &lt; Senaste fullständiga genomsökningsstarttid &gt; </dt>Senaste fullständiga
<dt>genomsökning sluttid: ? &lt; &gt;</dt>Sista fullständiga genomsökningens sluttid Senaste fullständiga genomsökningskälla: Senaste fullständiga genomsökningskälla (0 = genomsökningen&#39;inte
<dt> &lt; &gt; körts, 1 = användarinitierad, 2 = systeminitierad)</dt>Produktstatus: För intern felsökning 
<dt></span><span class="sxs-lookup"><span data-stu-id="2ad37-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="2ad37-663">
<th colspan="2">Händelse-ID: 2000</span><span class="sxs-lookup"><span data-stu-id="2ad37-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-664">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-666">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-666">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-667">
<b>Definitionerna för program mot skadlig programvara har uppdaterats. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-668">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-669">Antivirussignaturversionen har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="2ad37-670">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt>
<dt>Tidigare signaturversion: Tidigare &lt; signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="2ad37-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-671">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-672">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-672">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-673">Antimalware</span></span></li>
<li><span data-ttu-id="2ad37-674">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-675">
</dt>
<dt>Uppdateringstyp: &lt; Uppdatera typen &gt; , antingen Fullständig eller Delta.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-676">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-677">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-677">No action is necessary.</span></span> <span data-ttu-id="2ad37-678">Klient Microsoft Defender Antivirus statusen är felfri.</span><span class="sxs-lookup"><span data-stu-id="2ad37-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="2ad37-679">Händelsen rapporteras när signaturer har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-680">Händelse-ID: 2001</span><span class="sxs-lookup"><span data-stu-id="2ad37-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-681">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-683">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-683">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-684">
<b>Uppdateringen av säkerhetsintelligens misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-685">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-686">Microsoft Defender Antivirus har stött på ett fel vid försök att uppdatera signaturer.</span><span class="sxs-lookup"><span data-stu-id="2ad37-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="2ad37-687">
<dt>Ny säkerhetsintelligensversion: &lt; Nytt versionsnummer &gt; </dt>
<dt>Tidigare säkerhetsinformationsversion: Tidigare &lt; &gt; versionsuppdateringskälla:</dt> 
<dt> &lt; &gt; Uppdateringskälla, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-688">Uppdateringsmapp för säkerhetsinformation</span><span class="sxs-lookup"><span data-stu-id="2ad37-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="2ad37-689">Uppdateringsserver för intern säkerhetsintelligens</span><span class="sxs-lookup"><span data-stu-id="2ad37-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="2ad37-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="2ad37-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="2ad37-691">Filresurs</span><span class="sxs-lookup"><span data-stu-id="2ad37-691">File share</span></span></li>
<li><span data-ttu-id="2ad37-692">Microsoft Malware Protection Center (MMPC)</span><span class="sxs-lookup"><span data-stu-id="2ad37-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="2ad37-693">
</dt>
<dt>Uppdateringsfas: &lt; &gt; Uppdateringsfas, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-694">Söka</span><span class="sxs-lookup"><span data-stu-id="2ad37-694">Search</span></span></li>
<li><span data-ttu-id="2ad37-695">Ladda ned</span><span class="sxs-lookup"><span data-stu-id="2ad37-695">Download</span></span></li>
<li><span data-ttu-id="2ad37-696">Installera</span><span class="sxs-lookup"><span data-stu-id="2ad37-696">Install</span></span></li>
</ul><span data-ttu-id="2ad37-697">
</dt>
<dt>Källsökväg: Filresursnamn för UNC (Universal Naming Convention), servernamn för Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="2ad37-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-698">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-699">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-699">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-700">Antimalware</span></span></li>
<li><span data-ttu-id="2ad37-701">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-702">
</dt>
<dt>Uppdateringstyp: &lt; Uppdatera typen &gt; , antingen Fullständig eller Delta.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användar &gt; </dt>
<dt>current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-703">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-704">Det här felet inträffar när det är problem med att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="2ad37-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="2ad37-705">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="2ad37-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Uppdatera definitioner</a> och tvinga fram en omsökning direkt i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="2ad37-707">Granska posterna i filen %Windir%\WindowsUpdate.log för mer information om det här felet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="2ad37-708">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-709">Händelse-ID: 2002</span><span class="sxs-lookup"><span data-stu-id="2ad37-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-710">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-712">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-712">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-713">
<b>Antimalware-motorn har uppdaterats. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-714">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-715">Microsoft Defender Antivirus har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="2ad37-716">
<dt>Current Engine-version: &lt; Current engine &gt; version</dt>
<dt>Previous Engine Version: Previous engine &lt; version &gt; </dt>Engine
<dt>Type: Engine type , either &lt; &gt; antimalware engine or Network Inspection System engine.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-717">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-718">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-718">No action is necessary.</span></span> <span data-ttu-id="2ad37-719">Klient Microsoft Defender Antivirus statusen är felfri.</span><span class="sxs-lookup"><span data-stu-id="2ad37-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="2ad37-720">Händelsen rapporteras när program mot skadlig programvara har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-721">Händelse-ID: 2003</span><span class="sxs-lookup"><span data-stu-id="2ad37-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-722">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-724">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-724">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-725">
<b>Uppdateringen av program mot skadlig programvara misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-726">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-727">Microsoft Defender Antivirus har stött på ett fel när motorn ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="2ad37-728">
<dt>Ny motorversion: Tidigare</dt>
<dt>motorversion: Tidigare &lt; &gt; </dt>motorversionstyp: Motortyp , antingen
<dt> &lt; &gt; programskyddsmotor eller system för nätverksinspektion.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-729">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-730">Det Microsoft Defender Antivirus klientuppdateringen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="2ad37-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="2ad37-731">Den här händelsen inträffar när klienten inte kan uppdatera sig själv.</span><span class="sxs-lookup"><span data-stu-id="2ad37-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="2ad37-732">Händelsen beror vanligtvis på ett avbrott i nätverksanslutningen under en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="2ad37-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="2ad37-733">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="2ad37-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Uppdatera definitioner</a> och tvinga fram en omsökning direkt i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="2ad37-735">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-736">Händelse-ID: 2004</span><span class="sxs-lookup"><span data-stu-id="2ad37-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-737">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-739">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-739">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-740">
<b>Det gick inte att läsa in definitioner för program mot skadlig programvara. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-741">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-742">Microsoft Defender Antivirus har stött på ett fel i försök att läsa in signaturer och försöker återgå till en känd uppsättning signaturer.</span><span class="sxs-lookup"><span data-stu-id="2ad37-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="2ad37-743">
<dt>Signaturer: Försöks:</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-744">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-745">Användaren Microsoft Defender Antivirus försökte hämta och installera den senaste definitionsfilen och misslyckades.</span><span class="sxs-lookup"><span data-stu-id="2ad37-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="2ad37-746">Det här felet kan uppstå när klienten stöter på ett fel när du försöker läsa in definitionerna eller om filen är skadad.</span><span class="sxs-lookup"><span data-stu-id="2ad37-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="2ad37-747">Microsoft Defender Antivirus försöker återgå till en känd uppsättning definitioner.</span><span class="sxs-lookup"><span data-stu-id="2ad37-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="2ad37-748">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="2ad37-749">Starta om datorn och försök igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="2ad37-750">Hämta de senaste definitionerna från <a href="https://aka.ms/wdsi">Microsoft Säkerhetsinsikter webbplatsen</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="2ad37-751">Obs! Storleken på definitionsfilen som laddas ned från webbplatsen kan överskrida 60 MB och bör inte användas som en långsiktig lösning för att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="2ad37-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="2ad37-752">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-753">Händelse-ID: 2005</span><span class="sxs-lookup"><span data-stu-id="2ad37-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-754">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-756">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-756">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-757">
<b>Antimalware-motorn kunde inte läsas in eftersom programplattformen mot skadlig programvara är in date. Antimalware-plattformen laddar den senast kända bra antimalware-motorn och försöker uppdatera.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-758">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-759">Microsoft Defender Antivirus gick inte att läsa in program mot skadlig programvara eftersom den aktuella plattformsversionen inte stöds.</span><span class="sxs-lookup"><span data-stu-id="2ad37-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="2ad37-760">Microsoft Defender Antivirus går tillbaka till den senaste välkända motorn och en plattformsuppdatering kommer att försökas.</span><span class="sxs-lookup"><span data-stu-id="2ad37-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="2ad37-761">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-762">Händelse-ID: 2006</span><span class="sxs-lookup"><span data-stu-id="2ad37-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-763">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-765">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-765">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-766">
<b>Plattformsuppdateringen misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-767">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-768">Microsoft Defender Antivirus har stött på ett fel när plattformen ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="2ad37-769">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion &gt; </dt>
<dt>Felkod: &lt; Resultatkod för &gt; felkod som är kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-770">Händelse-ID: 2007</span><span class="sxs-lookup"><span data-stu-id="2ad37-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-771">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-773">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-773">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-774">
<b>Plattformen är snart in föråldrad. Ladda ned den senaste plattformen för att ha ett uppdaterat skydd.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-775">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-776">Microsoft Defender Antivirus snart att behöva en nyare plattformsversion för att stödja framtida versioner av program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="2ad37-777">Ladda ned den Microsoft Defender Antivirus-plattformen för att upprätthålla den bästa skyddsnivån som finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="2ad37-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="2ad37-778">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-779">Händelse-ID: 2010</span><span class="sxs-lookup"><span data-stu-id="2ad37-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-780">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-782">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-782">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-783">
<b>Antimalware-motorn använde tjänsten Dynamic Signature Service för att få ytterligare definitioner. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-784">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-785">Microsoft Defender Antivirus dynamisk <i>signaturtjänst för att</i> hämta ytterligare signaturer som hjälper till att skydda datorn.</span><span class="sxs-lookup"><span data-stu-id="2ad37-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="2ad37-786">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="2ad37-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-787">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-788">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-788">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-789">Antimalware</span></span></li>
<li><span data-ttu-id="2ad37-790">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-791">
</dt>
<dt>Current Engine-version: &lt; Aktuell motorversion &gt; </dt> 
<dt> av dynamisk signaturtyp: Dynamisk &lt; &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-792">Version</span><span class="sxs-lookup"><span data-stu-id="2ad37-792">Version</span></span></li>
<li><span data-ttu-id="2ad37-793">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-793">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-794">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-794">No limit</span></span></li>
<li><span data-ttu-id="2ad37-795">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="2ad37-795">Duration</span></span></li>
</ul><span data-ttu-id="2ad37-796">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Tidsstämpel</dt>Gränstyp för beständighet: Gränstyp för beständighet, till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-797">VDM-version</span><span class="sxs-lookup"><span data-stu-id="2ad37-797">VDM version</span></span></li>
<li><span data-ttu-id="2ad37-798">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-798">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-799">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-799">No limit</span></span></li>
</ul><span data-ttu-id="2ad37-800">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-801">Händelse-ID: 2011</span><span class="sxs-lookup"><span data-stu-id="2ad37-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-802">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-804">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-804">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-805">
<b>Tjänsten dynamisk signatur tog bort de in datera dynamiska definitionerna. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-806">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-807">Microsoft Defender Antivirus dynamisk <i>signaturtjänst för att</i> ignorera inaktuella signaturer.</span><span class="sxs-lookup"><span data-stu-id="2ad37-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="2ad37-808">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="2ad37-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-809">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-810">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-810">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-811">Antimalware</span></span></li>
<li><span data-ttu-id="2ad37-812">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-813">
</dt>
<dt>Current Engine-version: &lt; Aktuell motorversion &gt; </dt> 
<dt> av dynamisk signaturtyp: Dynamisk &lt; &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-814">Version</span><span class="sxs-lookup"><span data-stu-id="2ad37-814">Version</span></span></li>
<li><span data-ttu-id="2ad37-815">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-815">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-816">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-816">No limit</span></span></li>
<li><span data-ttu-id="2ad37-817">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="2ad37-817">Duration</span></span></li>
</ul><span data-ttu-id="2ad37-818">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Ta bort tidsstämpel</dt>
<dt>Orsak:</dt>Gränstyp för beständig beständighet: Gränstyp för beständighet, 
<dt> till &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-819">VDM-version</span><span class="sxs-lookup"><span data-stu-id="2ad37-819">VDM version</span></span></li>
<li><span data-ttu-id="2ad37-820">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-820">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-821">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-821">No limit</span></span></li>
</ul><span data-ttu-id="2ad37-822">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-823">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-824">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-824">No action is necessary.</span></span> <span data-ttu-id="2ad37-825">Klient Microsoft Defender Antivirus statusen är felfri.</span><span class="sxs-lookup"><span data-stu-id="2ad37-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="2ad37-826">Den här händelsen rapporteras när tjänsten Dynamisk signatur tar bort dynamiska definitioner som inte är aktuella.</span><span class="sxs-lookup"><span data-stu-id="2ad37-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-827">Händelse-ID: 2012</span><span class="sxs-lookup"><span data-stu-id="2ad37-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-828">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-830">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-830">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-831">
<b>Det uppstod ett fel på motorn mot skadlig programvara när man försökte använda tjänsten Dynamisk signatur. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-832">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-833">Microsoft Defender Antivirus har stött på ett fel när tjänsten <i>dynamisk signatur ska användas.</i></span><span class="sxs-lookup"><span data-stu-id="2ad37-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="2ad37-834">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="2ad37-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="2ad37-835">Antivirus</span></span></li>
<li><span data-ttu-id="2ad37-836">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="2ad37-836">Antispyware</span></span></li>
<li><span data-ttu-id="2ad37-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="2ad37-837">Antimalware</span></span></li>
<li><span data-ttu-id="2ad37-838">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-839">
</dt>
<dt>Current Engine-version: &lt; Current engine &gt; version</dt>
<dt>Error Code: Error code Result &lt; code associated with threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt> Dynamisk signaturtyp: &lt; Dynamisk &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-840">Version</span><span class="sxs-lookup"><span data-stu-id="2ad37-840">Version</span></span></li>
<li><span data-ttu-id="2ad37-841">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-841">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-842">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-842">No limit</span></span></li>
<li><span data-ttu-id="2ad37-843">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="2ad37-843">Duration</span></span></li>
</ul><span data-ttu-id="2ad37-844">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Tidsstämpel</dt>Gränstyp för beständighet: Gränstyp för beständighet, till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-845">VDM-version</span><span class="sxs-lookup"><span data-stu-id="2ad37-845">VDM version</span></span></li>
<li><span data-ttu-id="2ad37-846">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="2ad37-846">Timestamp</span></span></li>
<li><span data-ttu-id="2ad37-847">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="2ad37-847">No limit</span></span></li>
</ul><span data-ttu-id="2ad37-848">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-849">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-850">Kontrollera inställningarna för Internetanslutningen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-851">Händelse-ID: 2013</span><span class="sxs-lookup"><span data-stu-id="2ad37-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-852">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-854">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-854">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-855">
<b>Tjänsten Dynamisk signatur tog bort alla dynamiska definitioner. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-856">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-857">Microsoft Defender Antivirus ignorerade alla <i>signaturer för tjänsten</i> Dynamisk signatur.</span><span class="sxs-lookup"><span data-stu-id="2ad37-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="2ad37-858">
<dt>Aktuell signaturversion: &lt; aktuell signaturversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-859">Händelse-ID: 2020</span><span class="sxs-lookup"><span data-stu-id="2ad37-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-860">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-862">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-862">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-863">
<b>Antimalware-motorn laddade ned en ren fil. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-864">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-865">Microsoft Defender Antivirus en ren fil.</span><span class="sxs-lookup"><span data-stu-id="2ad37-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="2ad37-866">
<dt>Filnamn: &lt; Filens &gt; filnamn.</dt> 
<dt>Aktuell signaturversion: &lt; Current signature &gt; version</dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-867">Händelse-ID: 2021</span><span class="sxs-lookup"><span data-stu-id="2ad37-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-868">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-870">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-870">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-871">
<b>Det gick inte att hämta en ren fil till programmotorn. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-872">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-873">Microsoft Defender Antivirus har stött på ett fel när en ren fil ska hämtas.</span><span class="sxs-lookup"><span data-stu-id="2ad37-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="2ad37-874">
<dt>Filnamn: &lt; Filens &gt; filnamn.</dt> 
<dt>Aktuell signaturversion: &lt; Current signature &gt; version</dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>Error
<dt>Code: Error code Result code associated with &lt; threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-875">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-876">Kontrollera inställningarna för Internetanslutningen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="2ad37-877">Det Microsoft Defender Antivirus på grund av ett fel när tjänsten Dynamisk signatur används för att ladda ned de senaste definitionerna för ett visst hot.</span><span class="sxs-lookup"><span data-stu-id="2ad37-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="2ad37-878">Det här felet orsakas troligen av ett nätverksanslutningsproblem.</span><span class="sxs-lookup"><span data-stu-id="2ad37-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-879">Händelse-ID: 2030</span><span class="sxs-lookup"><span data-stu-id="2ad37-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-880">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-882">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-882">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-883">
<b>Antimalware-motorn har laddats ned och är konfigurerad att köras offline vid nästa systemomstart.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-884">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-885">Microsoft Defender Antivirus ned och konfigurerat offline antivirus att köras vid nästa omstart.</span><span class="sxs-lookup"><span data-stu-id="2ad37-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-886">Händelse-ID: 2031</span><span class="sxs-lookup"><span data-stu-id="2ad37-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-887">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-889">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-889">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-890">
<b>Det gick inte att hämta och konfigurera en offlinesökning via motorn för program mot skadlig programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-891">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-892">Microsoft Defender Antivirus har stött på ett fel vid försök att ladda ned och konfigurera offlineantivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="2ad37-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="2ad37-893">
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-894">Händelse-ID: 2040</span><span class="sxs-lookup"><span data-stu-id="2ad37-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-895">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-897">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-897">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-898">
<b>Stöd för program mot skadlig programvara för den här versionen av operativsystemet avslutas snart. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-899">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-900">Stödet för ditt operativsystem upphör snart.</span><span class="sxs-lookup"><span data-stu-id="2ad37-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="2ad37-901">Att Microsoft Defender Antivirus på ett operativsystem utan support är inte en lämplig lösning för att skydda mot hot.</span><span class="sxs-lookup"><span data-stu-id="2ad37-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-902">Händelse-ID: 2041</span><span class="sxs-lookup"><span data-stu-id="2ad37-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-903">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-905">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-905">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-906">
<b>Stödet för program mot skadlig programvara för det här operativsystemet har upphört. Du måste uppgradera operativsystemet för att kunna fortsätta stödja. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-907">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-908">Stödet för ditt operativsystem har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="2ad37-908">The support for your operating system has expired.</span></span> <span data-ttu-id="2ad37-909">Att Microsoft Defender Antivirus på ett operativsystem utan support är inte en lämplig lösning för att skydda mot hot.</span><span class="sxs-lookup"><span data-stu-id="2ad37-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-910">Händelse-ID: 2042</span><span class="sxs-lookup"><span data-stu-id="2ad37-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-911">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-913">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-913">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-914">
<b>Antimalware-motorn stöder inte längre det här operativsystemet och skyddar inte längre datorn mot skadlig programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-915">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-916">Stödet för ditt operativsystem har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="2ad37-916">The support for your operating system has expired.</span></span> <span data-ttu-id="2ad37-917">Microsoft Defender Antivirus inte längre stöds i operativsystemet, har slutat fungera och skyddar inte mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-918">Händelse-ID: 3002</span><span class="sxs-lookup"><span data-stu-id="2ad37-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-919">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-921">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-921">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-922">
<b>Realtidsskyddet påträffade ett fel och misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-923">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-924">Microsoft Defender Antivirus Real-Time Skydd har stött på ett fel och misslyckats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="2ad37-925">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-926">I Access</span><span class="sxs-lookup"><span data-stu-id="2ad37-926">On Access</span></span></li>
<li><span data-ttu-id="2ad37-927">Nedladdningar från Internet Explorer och Microsoft Outlook Express-bilagor</span><span class="sxs-lookup"><span data-stu-id="2ad37-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="2ad37-928">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="2ad37-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="2ad37-929">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-930">
</dt>
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Orsak: Orsaken Microsoft Defender Antivirus realtidsskyddet har startat om en funktion.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-931">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-932">Du bör starta om systemet och sedan köra en fullständig genomsökning eftersom&#39;det är möjligt att systemet inte var skyddat på ett tag.</span><span class="sxs-lookup"><span data-stu-id="2ad37-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="2ad37-933">Ett Microsoft Defender Antivirus av&#39;realtidsskydd påträffade ett fel på grund av att en av tjänsterna inte kunde starta.</span><span class="sxs-lookup"><span data-stu-id="2ad37-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="2ad37-934">Om det följs av ett 3007 händelse-ID var felet tillfälligt och klienten för program mot skadlig kod återställdes efter felet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-935">Händelse-ID: 3007</span><span class="sxs-lookup"><span data-stu-id="2ad37-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-936">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-938">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-938">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-939">
<b>Realtidsskydd som återställts efter ett fel. Vi rekommenderar att du kör en fullständig systemsökning när du ser det här felet. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-940">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-941">Microsoft Defender Antivirus Realtidsskyddet har startat om en funktion.</span><span class="sxs-lookup"><span data-stu-id="2ad37-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="2ad37-942">Vi rekommenderar att du kör en fullständig systemsökning för att hitta eventuella objekt som kan ha missats under tiden den här agenten var nere.</span><span class="sxs-lookup"><span data-stu-id="2ad37-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="2ad37-943">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-944">I Access</span><span class="sxs-lookup"><span data-stu-id="2ad37-944">On Access</span></span></li>
<li><span data-ttu-id="2ad37-945">IE laddar ned och Outlook Express-bilagor</span><span class="sxs-lookup"><span data-stu-id="2ad37-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="2ad37-946">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="2ad37-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="2ad37-947">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-948">
</dt>
<dt>Orsak: Orsaken Microsoft Defender Antivirus realtidsskyddet har startat om en funktion.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-949">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-950">Realtidsskyddet har startats om.</span><span class="sxs-lookup"><span data-stu-id="2ad37-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="2ad37-951">Om händelsen inträffar igen kontaktar du <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support.</a></span><span class="sxs-lookup"><span data-stu-id="2ad37-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-952">Händelse-ID: 5000</span><span class="sxs-lookup"><span data-stu-id="2ad37-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-953">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-955">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-955">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-956">
<b>Realtidsskydd är aktiverat. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-957">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-958">Microsoft Defender Antivirus skydd i realtid för skadlig programvara och annan potentiellt oönskad programvara har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-959">Händelse-ID: 5001</span><span class="sxs-lookup"><span data-stu-id="2ad37-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-960">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-962">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-962">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-963">
<b>Realtidsskydd är inaktiverat. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-964">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-965">Microsoft Defender Antivirus skydd i realtid för skadlig programvara och annan potentiellt oönskad programvara har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-966">Händelse-ID: 5004</span><span class="sxs-lookup"><span data-stu-id="2ad37-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-967">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-969">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-969">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-970">
<b>Konfigurationen av realtidsskyddet har ändrats. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-971">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-972">Microsoft Defender Antivirus är att realtidsskyddets funktionskonfiguration har ändrats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="2ad37-973">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="2ad37-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="2ad37-974">I Access</span><span class="sxs-lookup"><span data-stu-id="2ad37-974">On Access</span></span></li>
<li><span data-ttu-id="2ad37-975">IE laddar ned och Outlook Express-bilagor</span><span class="sxs-lookup"><span data-stu-id="2ad37-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="2ad37-976">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="2ad37-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="2ad37-977">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="2ad37-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="2ad37-978">
</dt>
<dt>Konfiguration: </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-979">Händelse-ID: 5007</span><span class="sxs-lookup"><span data-stu-id="2ad37-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-980">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-982">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-982">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-983">
<b>Konfigurationen av motprogramsplattformen har ändrats.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-984">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-985">Microsoft Defender Antivirus har ändrats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="2ad37-986">Om det här är en oväntad händelse bör du granska inställningarna eftersom det kan vara resultatet av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="2ad37-987">
<dt>Gammalt värde: &lt; Gammalt värde nummer &gt; Gammalt antivirusprogram-konfigurationsvärde.</dt> 
<dt>Nytt värde: &lt; Nytt värdenummer &gt; Nytt antivirusprograms konfigurationsvärde.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-988">Händelse-ID: 5008</span><span class="sxs-lookup"><span data-stu-id="2ad37-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-989">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-991">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-991">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-992">
<b>Det uppstod ett fel på motorn mot skadlig programvara och misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-993">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-994">Microsoft Defender Antivirus har avslutats på grund av ett oväntat fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="2ad37-995">
<dt>Feltyp: &lt; &gt;Feltyp, till exempel: Krasch- eller undantagskod:</dt>
<dt> &lt; Felkod &gt; Resurs:</dt>
<dt> &lt; Resurs &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-996">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-997">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="2ad37-998">Försök att starta om tjänsten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="2ad37-999">För program mot skadlig programvara, antivirus och spionprogram skriver du net <b>stop msmpsvc</b>i en upphöjd kommandotolk och skriver sedan net <b>start msmpsvc</b> för att starta om program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="2ad37-1000">För <i>System för</i>nätverksinspektion i en upphöjd kommandotolk skriver du <b>net start nissrv</b>och skriver sedan <b>net start nissrv</b> för att starta om <i>motorn i Network Inspection System</i> med hjälp av NiSSRV.exe filen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="2ad37-1001">Om den misslyckas på samma sätt letar du upp felkoden genom att gå <b></b> till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a> och ange felnumret i rutan Sök och kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support.</a></span><span class="sxs-lookup"><span data-stu-id="2ad37-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1002">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1003">Klientmotorn Microsoft Defender Antivirus på grund av ett oväntat fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="2ad37-1004">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="2ad37-1005">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="2ad37-1006">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="2ad37-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="2ad37-1007">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1008">Händelse-ID: 5009</span><span class="sxs-lookup"><span data-stu-id="2ad37-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1009">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1011">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1012">
<b>Sökning efter skadlig programvara och annan potentiellt oönskad programvara aktiveras. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1013">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1014">Microsoft Defender Antivirus för skadlig programvara och annan potentiellt oönskad programvara har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1015">Händelse-ID: 5010</span><span class="sxs-lookup"><span data-stu-id="2ad37-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1016">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1018">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1019">
<b>Sökning efter skadlig programvara och annan potentiellt oönskad programvara inaktiveras.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1020">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1021">Microsoft Defender Antivirus för skadlig programvara och annan potentiellt oönskad programvara inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1022">Händelse-ID: 5011</span><span class="sxs-lookup"><span data-stu-id="2ad37-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1023">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1025">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1026">
<b>Sökning efter virus har aktiverats.</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1027">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1028">Microsoft Defender Antivirus har aktiverats för att söka efter virus.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1029">Händelse-ID: 5012</span><span class="sxs-lookup"><span data-stu-id="2ad37-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1030">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1032">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1033">
<b>Sökning efter virus inaktiveras. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1034">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1035">Microsoft Defender Antivirus för virus inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1036">Händelse-ID: 5100</span><span class="sxs-lookup"><span data-stu-id="2ad37-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1037">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1039">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1040">
<b>Antimalware-plattformen upphör snart att gälla. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1041">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1042">Microsoft Defender Antivirus har angett en respitperiod och förfaller snart.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="2ad37-1043">Efter att programmet har gått ut inaktiveras skyddet mot virus, spionprogram och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="2ad37-1044">
<dt>Orsak till förfallodatum: Orsaken till att Microsoft Defender Antivirus går ut.</dt> 
<dt>Utgångsdatum: Datumet Microsoft Defender Antivirus förfaller.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1045">Händelse-ID: 5101</span><span class="sxs-lookup"><span data-stu-id="2ad37-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="2ad37-1046">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1048">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="2ad37-1049">
<b>Antimalware-plattformen har upphört att gälla. </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1050">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="2ad37-1051">Microsoft Defender Antivirus respitperioden har gått ut.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="2ad37-1052">Skydd mot virus, spionprogram och annan potentiellt oönskad programvara inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="2ad37-1053">
<dt>Förfallodatum: Förfallodatum:</dt>
<dt>Felkod: </dt> 
<dt>Felkod &lt; resultatkod som är associerad med &gt; hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="2ad37-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivirus felkoder på klienten Microsoft Defender Antivirus du upplever problem får du vanligtvis en felkod som hjälper dig att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="2ad37-1055">Oftast innebär ett fel att det gick att installera en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="2ad37-1056">Det här avsnittet innehåller följande information Microsoft Defender Antivirus om klientfel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="2ad37-1057">-   Felkoden -   Den möjliga orsaken till felet Råd -   om vad du ska göra nu</span><span class="sxs-lookup"><span data-stu-id="2ad37-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="2ad37-1058">Använd informationen i de här tabellerna för felsökning Microsoft Defender Antivirus felkoder.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1059">Felkod: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="2ad37-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="2ad37-1060">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1060">Message</span></span></td>
<td><span data-ttu-id="2ad37-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1062">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="2ad37-1063">Det här felet anger att minnet kan vara slut.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="2ad37-1064">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="2ad37-1065">Kontrollera enhetens tillgängliga minne.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="2ad37-1066">Stäng alla oanvända program som körs för att frigöra minne på enheten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="2ad37-1067">Starta om enheten och kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1068">Felkod: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="2ad37-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="2ad37-1069">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1069">Message</span></span></td>
<td><span data-ttu-id="2ad37-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1071">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1072">Det här felet anger att det kan vara problem med din säkerhetsprodukt.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="2ad37-1073">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="2ad37-1074">Uppdatera definitionerna.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1074">Update the definitions.</span></span> <span data-ttu-id="2ad37-1075">Antingen:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1075">Either:</span></span><ol>
<li><span data-ttu-id="2ad37-1076">Klicka på <b>knappen Uppdatera</b> definitioner på <b>fliken Uppdatera</b> i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="2ad37-1077">Eller:</span><span class="sxs-lookup"><span data-stu-id="2ad37-1077">Or,</span></span>
</li>
<li><span data-ttu-id="2ad37-1078">Hämta de senaste definitionerna från <a href="https://aka.ms/wdsi">Microsoft Säkerhetsinsikter webbplatsen</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="2ad37-1079">Obs! Storleken på definitionsfilen som laddas ned från webbplatsen kan överskrida 60 MB och bör inte användas som en långsiktig lösning för att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="2ad37-1080">Kör en fullständig genomsökning.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="2ad37-1081">Starta om enheten och försök igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1082">Felkod: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="2ad37-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="2ad37-1083">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1083">Message</span></span></td>
<td><span data-ttu-id="2ad37-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1085">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1086">Det här felet anger att det kan finnas ett motorkonfigurationsfel. vanligtvis är detta relaterat till indata som inte tillåter att motorn fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1087">Felkod: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="2ad37-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1088">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1088">Message</span></span></td>
<td><span data-ttu-id="2ad37-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1090">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1091">Det här felet anger Microsoft Defender Antivirus har misslyckats med att sätta ett hot i karantän.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1092">Felkod: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="2ad37-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1093">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1093">Message</span></span></td>
<td><span data-ttu-id="2ad37-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1095">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1096">Det här felet anger att en omstart krävs för att slutföra borttagningen av hot.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="2ad37-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="2ad37-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1098">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1098">Message</span></span></td>
<td><span data-ttu-id="2ad37-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1100">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1101">Det här felet anger att risken inte längre finns i media, eller att skadlig programvara hindrar dig från att skanna enheten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="2ad37-1102">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="2ad37-1103">Kör <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> uppdatera sedan säkerhetsprogramvaran och försök igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1104">Felkod: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="2ad37-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="2ad37-1105">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1105">Message</span></span></td>
<td><span data-ttu-id="2ad37-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1107">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1108">Det här felet anger att en fullständig systemsökning kan behövas.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="2ad37-1109">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1109">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1110">Kör en fullständig systemsökning.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1111">Felkod: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="2ad37-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1112">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1112">Message</span></span></td>
<td><span data-ttu-id="2ad37-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1114">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1115">Det här felet anger att manuella steg krävs för att slutföra borttagningen av hot.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1116">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1116">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1117">Följ de anvisningar för manuella åtgärder som beskrivs i <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia.</a></span><span class="sxs-lookup"><span data-stu-id="2ad37-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="2ad37-1118">Du hittar en länk som är specifik för hot i händelsehistoriken.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1119">Felkod: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="2ad37-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1120">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1120">Message</span></span></td>
<td><span data-ttu-id="2ad37-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1122">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1123">Det här felet anger att borttagning inuti behållartypen kanske inte stöds.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1124">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1124">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1125">Microsoft Defender Antivirus kan inte åtgärda hot som upptäckts i arkivet.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="2ad37-1126">Överväg att manuellt ta bort identifierade resurser.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1127">Felkod: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="2ad37-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1128">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1128">Message</span></span></td>
<td><span data-ttu-id="2ad37-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1130">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1131">Det här felet anger att borttagning av små och medelstora hot kan inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1132">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1132">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1133">Kontrollera de identifierade hoten och lös dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1134">Felkod: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="2ad37-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1135">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1135">Message</span></span></td>
<td><span data-ttu-id="2ad37-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1137">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1138">Det här felet anger att en ny sökning av hot krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1139">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1139">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1140">Kör en fullständig systemsökning.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1141">Felkod: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="2ad37-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1142">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1142">Message</span></span></td>
<td><span data-ttu-id="2ad37-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="2ad37-1144">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1145">Det här felet anger att en offlinesökning krävs.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1146">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1146">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1147">Kör offline-Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="2ad37-1148">Du kan läsa om hur du gör detta i <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">artikeln om offline-Microsoft Defender Antivirus</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="2ad37-1149">Felkod: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="2ad37-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="2ad37-1150">Meddelande</span><span class="sxs-lookup"><span data-stu-id="2ad37-1150">Message</span></span></td>
<td><span data-ttu-id="2ad37-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="2ad37-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="2ad37-1152">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="2ad37-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="2ad37-1153">Det här felet anger Microsoft Defender Antivirus versionen inte stöder den aktuella versionen av plattformen och kräver en ny version av plattformen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="2ad37-1154">Lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1154">Resolution</span></span></td><td>
<span data-ttu-id="2ad37-1155">Du kan bara använda Microsoft Defender Antivirus i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="2ad37-1156">Med Windows 8, Windows 7 och Windows Vista kan du använda <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="2ad37-1157">

<a id="internal-error-codes"></a>Följande felkoder används vid intern testning av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="2ad37-1158">Om du ser de här felen kan du försöka uppdatera [definitioner och](manage-updates-baselines-microsoft-defender-antivirus.md) tvinga fram en ny sökning direkt på slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="2ad37-1159">Interna felkoder</span><span class="sxs-lookup"><span data-stu-id="2ad37-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="2ad37-1160"><b>Felkod</b></span><span class="sxs-lookup"><span data-stu-id="2ad37-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="2ad37-1161">Meddelande som visas</span><span class="sxs-lookup"><span data-stu-id="2ad37-1161">Message displayed</span></span></th>
<th><span data-ttu-id="2ad37-1162">Möjlig orsak till fel och lösning</span><span class="sxs-lookup"><span data-stu-id="2ad37-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="2ad37-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="2ad37-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-1165">Kontrollera internetanslutningen och kör sedan sökningen igen.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="2ad37-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="2ad37-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="2ad37-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="2ad37-1168">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1168">This is an internal error.</span></span> <span data-ttu-id="2ad37-1169">Orsaken är inte tydligt definierad.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="2ad37-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="2ad37-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="2ad37-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="2ad37-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="2ad37-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="2ad37-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="2ad37-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="2ad37-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="2ad37-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="2ad37-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="2ad37-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="2ad37-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="2ad37-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="2ad37-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="2ad37-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="2ad37-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="2ad37-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="2ad37-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="2ad37-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="2ad37-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="2ad37-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="2ad37-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="2ad37-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="2ad37-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="2ad37-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="2ad37-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="2ad37-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="2ad37-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="2ad37-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="2ad37-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="2ad37-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="2ad37-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="2ad37-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="2ad37-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="2ad37-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="2ad37-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="2ad37-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="2ad37-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="2ad37-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="2ad37-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="2ad37-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="2ad37-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="2ad37-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="2ad37-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="2ad37-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="2ad37-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="2ad37-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="2ad37-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="2ad37-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="2ad37-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="2ad37-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="2ad37-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="2ad37-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="2ad37-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="2ad37-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="2ad37-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="2ad37-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="2ad37-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="2ad37-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="2ad37-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="2ad37-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="2ad37-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="2ad37-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="2ad37-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="2ad37-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="2ad37-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="2ad37-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="2ad37-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-1238">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1238">This is an internal error.</span></span> <span data-ttu-id="2ad37-1239">Det kan utlösas när borttagning av skadlig programvara inte lyckas.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="2ad37-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="2ad37-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="2ad37-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="2ad37-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="2ad37-1242">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1242">This is an internal error.</span></span> <span data-ttu-id="2ad37-1243">Det kan ha utlösts när en genomsökning inte kunde slutföras.</span><span class="sxs-lookup"><span data-stu-id="2ad37-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="2ad37-1244">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="2ad37-1244">Related topics</span></span>

- [<span data-ttu-id="2ad37-1245">Rapport om Microsoft Defender Antivirus skydd</span><span class="sxs-lookup"><span data-stu-id="2ad37-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2ad37-1246">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="2ad37-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)