---
title: Microsoft Defender AV-händelse-ID och felkoder
description: Leta upp orsaker och lösningar för händelser och fel i Microsoft Defender Antivirus
keywords: händelse, felkod, siem, loggning, felsökning, wef, windows-händelse vidarebefordran
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d78728ae6b79914e5e9bac46e000d633793ae991
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691604"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="a66ec-104">Granska händelseloggar och felkoder för att felsöka problem med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a66ec-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a66ec-105">**Applies to:**</span></span>

- [<span data-ttu-id="a66ec-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a66ec-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a66ec-107">Om du stöter på ett problem med Microsoft Defender Antivirus kan du söka i tabellerna i den här artikeln för att hitta ett matchande problem och en möjlig lösning.</span><span class="sxs-lookup"><span data-stu-id="a66ec-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="a66ec-108">Tabelllistan:</span><span class="sxs-lookup"><span data-stu-id="a66ec-108">The tables list:</span></span>

- <span data-ttu-id="a66ec-109">[Microsoft Defender Antivirus händelse-Ds](#windows-defender-av-ids) (dessa gäller både Windows 10 och Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="a66ec-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="a66ec-110">Felkoder för Microsoft Defender Antivirus-klienten</span><span class="sxs-lookup"><span data-stu-id="a66ec-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="a66ec-111">Interna felkoder för Microsoft Defender Antivirus-klienten (används av Microsoft under utveckling och testning)</span><span class="sxs-lookup"><span data-stu-id="a66ec-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="a66ec-112">Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar:</span><span class="sxs-lookup"><span data-stu-id="a66ec-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="a66ec-113">Moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="a66ec-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="a66ec-114">Fast learning (inklusive Block at first sight)</span><span class="sxs-lookup"><span data-stu-id="a66ec-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="a66ec-115">Potentiellt oönskad programblockering</span><span class="sxs-lookup"><span data-stu-id="a66ec-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="a66ec-116">Händelse-ID:er för Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="a66ec-117">Microsoft Defender Antivirus registrerar händelse-IDn i händelseloggen i Windows.</span><span class="sxs-lookup"><span data-stu-id="a66ec-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="a66ec-118">Du kan visa händelseloggen direkt, eller om du har ett säkerhetsinformations- och händelsehanteringsverktyg från tredje part (SIEM), kan du också använda [Microsoft Defender Antivirus-klienthändelse-IDn](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) för att granska specifika händelser och fel från slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="a66ec-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="a66ec-119">Tabellen i det här avsnittet innehåller huvud-ID för Microsoft Defender Antivirus-händelser och, om möjligt, förslag på lösningar för att åtgärda eller lösa felet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="a66ec-120">Så här visar du en Microsoft Defender Antivirus-händelse</span><span class="sxs-lookup"><span data-stu-id="a66ec-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="a66ec-121">Öppna **Loggboken.**</span><span class="sxs-lookup"><span data-stu-id="a66ec-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="a66ec-122">I konsolträdet expanderar du **Program- och tjänstloggar** och **sedan Microsoft** och sedan **Windows** och sedan **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="a66ec-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="a66ec-123">Dubbelklicka på **Drift.**</span><span class="sxs-lookup"><span data-stu-id="a66ec-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="a66ec-124">I informationsfönstret kan du visa listan med enskilda händelser för att hitta händelsen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="a66ec-125">Klicka på händelsen om du vill se specifik information om en händelse i det nedre fönstret, under **flikarna** **Allmänt och** Information.</span><span class="sxs-lookup"><span data-stu-id="a66ec-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="a66ec-126">Händelse-ID: 1000</span><span class="sxs-lookup"><span data-stu-id="a66ec-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-127">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="a66ec-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-129">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-129">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-130">
<b>En sökning mot skadlig programvara startade. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="a66ec-131">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-132">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-133">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-134">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-134">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-135">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-136">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-137">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-137">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-138">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-138">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-139">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-139">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-140">
</dt>
<dt>Sökresurser: &lt; Resurser (till exempel filer/kataloger/BHO) som &gt; skannades.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-141">Händelse-ID: 1001</span><span class="sxs-lookup"><span data-stu-id="a66ec-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-142">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-144">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-144">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-145">
<b>En sökning efter program mot skadlig programvara slutförd.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-146">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-147">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-148">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-149">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-149">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-150">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-151">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-152">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-152">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-153">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-153">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-154">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-154">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-155">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarens</dt>
<dt>genomsökningstid: &lt; Varaktigheten &gt; för en genomsökning.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-156">Händelse-ID: 1002</span><span class="sxs-lookup"><span data-stu-id="a66ec-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-157">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-159">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-159">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-160">
<b>En sökning efter program mot skadlig programvara stoppades innan den slutfördes. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-161">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-162">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-163">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-164">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-164">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-165">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-166">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-167">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-167">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-168">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-168">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-169">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-169">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-170">
</dt>
<dt>Användare: &lt; Domain &gt; &amp; lt; &gt;Användarens</dt>
<dt>genomsökningstid: &lt; Varaktigheten &gt; för en genomsökning.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-171">Händelse-ID: 1003</span><span class="sxs-lookup"><span data-stu-id="a66ec-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-172">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-174">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-174">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-175">
<b>En sökning efter program mot skadlig programvara pausades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-176">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-177">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-178">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-179">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-179">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-180">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-181">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-182">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-182">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-183">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-183">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-184">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-184">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-185">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; Användare&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-186">Händelse-ID: 1004</span><span class="sxs-lookup"><span data-stu-id="a66ec-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-187">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-189">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-189">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-190">
<b>En sökning efter program mot skadlig programvara återupptades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-191">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-192">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-193">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-194">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-194">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-195">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-196">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-197">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-197">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-198">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-198">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-199">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-199">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-200">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; Användare&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-201">Händelse-ID: 1005</span><span class="sxs-lookup"><span data-stu-id="a66ec-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-202">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-204">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-204">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-205">
<b>En sökning efter program mot skadlig programvara misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-206">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="a66ec-207">
<dt>Genomsöknings-ID: &lt; ID-numret för den &gt; relevanta genomsökningen.</dt> 
<dt> Skanningstyp: &lt; &gt; Skanningstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-208">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-209">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-209">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-210">Antimalware</span></span></li>
</ul><span data-ttu-id="a66ec-211">
</dt>
<dt>&lt;Genomsökningsparametrar: &gt; Genomsökningsparametrar, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-212">Fullständig sökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-212">Full scan</span></span></li>
<li><span data-ttu-id="a66ec-213">Snabbsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-213">Quick scan</span></span></li>
<li><span data-ttu-id="a66ec-214">Kundsökning</span><span class="sxs-lookup"><span data-stu-id="a66ec-214">Customer scan</span></span></li>
</ul><span data-ttu-id="a66ec-215">
</dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-216">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-217">Ett fel uppstod på antivirusklienten och den aktuella genomsökningen har stoppats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="a66ec-218">Genomsökningen kan misslyckas på grund av problem på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="a66ec-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="a66ec-219">Den här händelseposten omfattar genomsöknings-ID, typ av genomsökning (Microsoft Defender Antivirus, antispionprogram, program mot skadlig kod), genomsökningsparametrar, användaren som startade genomsökningen, felkoden och en beskrivning av felet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="a66ec-220">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="a66ec-221">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="a66ec-222">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="a66ec-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="a66ec-223">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-224">Händelse-ID: 1006</span><span class="sxs-lookup"><span data-stu-id="a66ec-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-225">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-227">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-227">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-228">
<b>Kod mot skadlig programvara eller annan potentiellt oönskad programvara hittades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-229">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-230">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-231">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-232">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-232">Low</span></span></li>
<li><span data-ttu-id="a66ec-233">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-233">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-234">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-234">High</span></span></li>
<li><span data-ttu-id="a66ec-235">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-235">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-236">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-237">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-237">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-238">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-238">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-239">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-239">Network share</span></span></li>
<li><span data-ttu-id="a66ec-240">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-240">Internet</span></span></li>
<li><span data-ttu-id="a66ec-241">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-242">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-243">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-244">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-244">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-245">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-245">Generic</span></span></li>
<li><span data-ttu-id="a66ec-246">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-246">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-247">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-248">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-249">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-249">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-250">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-250">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-251">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-252">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-253">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-254">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-255">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-256">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-257">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-258">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-259">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-260"></dt>
<dt>UAC-status: &lt; Status &gt; </dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signaturversion:</dt>Definition
<dt> &lt; version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-261">Händelse-ID: 1007</span><span class="sxs-lookup"><span data-stu-id="a66ec-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-262">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-264">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-264">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-265">
<b>Program mot skadlig programvara utförde en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-266">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-267">Microsoft Defender Antivirus har vidtagit åtgärder för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="a66ec-268">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-269">
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt> &lt; Namn-ID för &gt; </dt>
<dt>hot: Allvarlighetsgrad för &lt; &gt; hot-ID:</dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-270">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-270">Low</span></span></li>
<li><span data-ttu-id="a66ec-271">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-271">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-272">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-272">High</span></span></li>
<li><span data-ttu-id="a66ec-273">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-273">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-274">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt> Åtgärd: &lt; &gt; Åtgärd, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-275">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="a66ec-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="a66ec-276">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="a66ec-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="a66ec-277">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="a66ec-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="a66ec-278">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="a66ec-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="a66ec-279">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="a66ec-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="a66ec-280">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-280">No action: No action</span></span></li>
<li><span data-ttu-id="a66ec-281">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="a66ec-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="a66ec-282">
</dt>
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version av &gt; definitionsversion:</dt>
<dt> &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-283">Händelse-ID: 1008</span><span class="sxs-lookup"><span data-stu-id="a66ec-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-284">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-286">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-286">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-287">
<b>Program mot skadlig programvara försökte utföra en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara, men åtgärden misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-288">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-289">Det har uppstått ett fel i Microsoft Defender Antivirus när skadlig programvara eller annan potentiellt oönskad programvara vidtas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="a66ec-290">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-291">
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt> &lt; Namn-ID för &gt; </dt>
<dt>hot: Allvarlighetsgrad för &lt; &gt; hot-ID:</dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-292">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-292">Low</span></span></li>
<li><span data-ttu-id="a66ec-293">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-293">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-294">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-294">High</span></span></li>
<li><span data-ttu-id="a66ec-295">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-295">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-296">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Filsökväg &gt; </dt> 
<dt> &lt; Åtgärd: &gt; Åtgärd, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-297">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="a66ec-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="a66ec-298">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="a66ec-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="a66ec-299">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="a66ec-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="a66ec-300">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="a66ec-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="a66ec-301">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="a66ec-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="a66ec-302">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-302">No action: No action</span></span></li>
<li><span data-ttu-id="a66ec-303">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="a66ec-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="a66ec-304">
</dt>
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Status: &lt; &gt;</dt>
<dt>Statussignaturversion: &lt; Version av &gt; definitionsversion:</dt>
<dt> &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-304">
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
<th colspan="2"><span data-ttu-id="a66ec-305">Händelse-ID: 1009</span><span class="sxs-lookup"><span data-stu-id="a66ec-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-306">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-308">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-308">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-309">
<b>Program mot skadlig programvara återställde ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-310">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-311">Microsoft Defender Antivirus har återställt ett objekt från karantän.</span><span class="sxs-lookup"><span data-stu-id="a66ec-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="a66ec-312">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-313">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-314">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-314">Low</span></span></li>
<li><span data-ttu-id="a66ec-315">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-315">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-316">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-316">High</span></span></li>
<li><span data-ttu-id="a66ec-317">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-317">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-318">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarsignaturversion: &lt; &gt; Definition version</dt>Engine
<dt>Version: &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-318">
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
<th colspan="2"><span data-ttu-id="a66ec-319">Händelse-ID: 1010</span><span class="sxs-lookup"><span data-stu-id="a66ec-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-320">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-322">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-322">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-323">
<b>Program mot skadlig programvara kunde inte återställa ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-324">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-325">Det har uppstått ett fel i Microsoft Defender Antivirus om att försöka återställa ett objekt från karantän.</span><span class="sxs-lookup"><span data-stu-id="a66ec-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="a66ec-326">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-327">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-328">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-328">Low</span></span></li>
<li><span data-ttu-id="a66ec-329">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-329">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-330">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-330">High</span></span></li>
<li><span data-ttu-id="a66ec-331">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-331">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-332">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-332">
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
<th colspan="2"><span data-ttu-id="a66ec-333">Händelse-ID: 1011</span><span class="sxs-lookup"><span data-stu-id="a66ec-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-334">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-336">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-336">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-337">
<b>Program mot skadlig programvara tog bort ett objekt från karantän. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-338">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-339">Ett objekt har tagits bort från karantän i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="a66ec-340">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-341">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-342">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-342">Low</span></span></li>
<li><span data-ttu-id="a66ec-343">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-343">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-344">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-344">High</span></span></li>
<li><span data-ttu-id="a66ec-345">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-345">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-346">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarsignaturversion: &lt; &gt; Definition version</dt>Engine
<dt>Version: &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-346">
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
<th colspan="2"><span data-ttu-id="a66ec-347">Händelse-ID: 1012</span><span class="sxs-lookup"><span data-stu-id="a66ec-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-348">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-350">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-350">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-351">
<b>Det gick inte att ta bort ett objekt från karantän på plattformen för program mot skadlig programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-352">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-353">Det har uppstått ett fel i Microsoft Defender Antivirus när ett objekt ska tas bort från karantän.</span><span class="sxs-lookup"><span data-stu-id="a66ec-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="a66ec-354">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-355">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-356">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-356">Low</span></span></li>
<li><span data-ttu-id="a66ec-357">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-357">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-358">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-358">High</span></span></li>
<li><span data-ttu-id="a66ec-359">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-359">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-360">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Användare:</dt>
<dt>Domän &lt; &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-360">
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
<th colspan="2"><span data-ttu-id="a66ec-361">Händelse-ID: 1013</span><span class="sxs-lookup"><span data-stu-id="a66ec-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-362">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-364">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-364">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-365">
<b>Program mot skadlig programvara raderades från historiken för skadlig programvara och annan potentiellt oönskad programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-366">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-367">Microsoft Defender Antivirus har tagit bort historik över skadlig programvara och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="a66ec-368">
<dt>Tid: Tiden då händelsen inträffade, till exempel när historiken rensas. Den här parametern används inte i hothändelser, så det finns ingen förvirring kring om det är åtgärdstid eller smitta tid. För dem kallar vi dem specifikt för Åtgärdstid eller Identifieringstid.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-369">Händelse-ID: 1014</span><span class="sxs-lookup"><span data-stu-id="a66ec-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-370">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-372">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-373">Det gick inte att radera historik över skadlig programvara och annan potentiellt oönskad programvara på programplattformen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-374">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-375">Ett fel har uppstått i Microsoft Defender Antivirus vid försök att ta bort historik över skadlig programvara och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="a66ec-376">
<dt>Tid: Tiden då händelsen inträffade, till exempel när historiken rensas. Den här parametern används inte i hothändelser, så det finns ingen förvirring kring om det är åtgärdstid eller smitta tid. För dem kallar vi dem specifikt för Åtgärdstid eller Identifieringstid.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden. </dt> 
<dt>Felbeskrivning: &lt; &gt; Felbeskrivning Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-377">Händelse-ID: 1015</span><span class="sxs-lookup"><span data-stu-id="a66ec-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-378">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-380">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-380">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-381">
<b>Motprogramplattformen upptäckte misstänkt beteende.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-382">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-383">Microsoft Defender Antivirus har upptäckt ett misstänkt beteende.</span><span class="sxs-lookup"><span data-stu-id="a66ec-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="a66ec-384">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-385">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-386">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-386">Low</span></span></li>
<li><span data-ttu-id="a66ec-387">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-387">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-388">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-388">High</span></span></li>
<li><span data-ttu-id="a66ec-389">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-389">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-390">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-391">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-391">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-392">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-392">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-393">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-393">Network share</span></span></li>
<li><span data-ttu-id="a66ec-394">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-394">Internet</span></span></li>
<li><span data-ttu-id="a66ec-395">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-396">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-397">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-398">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-398">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-399">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-399">Generic</span></span></li>
<li><span data-ttu-id="a66ec-400">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-400">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-401">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-402">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-403">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-403">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-404">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-404">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-405">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-406">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-407">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-408">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-409">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-410">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-411">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-412">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-413">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-414"></dt>
<dt>UAC-status: &lt; Status &gt; </dt>
<dt>Användare: &lt; Domain &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signatur-ID:</dt>
<dt>Uppräkningsmatchning för allvarlighetsgrad.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
<dt>Återgivningsetikett:</dt>
<dt>Target File Name: Filnamn för &lt; &gt; filen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="a66ec-415">Händelse-ID: 1116</span><span class="sxs-lookup"><span data-stu-id="a66ec-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-416">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-418">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-418">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-419">
<b>Program mot skadlig programvara eller annan potentiellt oönskad programvara har upptäckts. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-420">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-421">Microsoft Defender Antivirus har upptäckt skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="a66ec-422">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-423">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-424">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-424">Low</span></span></li>
<li><span data-ttu-id="a66ec-425">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-425">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-426">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-426">High</span></span></li>
<li><span data-ttu-id="a66ec-427">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-427">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-428">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-429">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-429">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-430">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-430">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-431">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-431">Network share</span></span></li>
<li><span data-ttu-id="a66ec-432">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-432">Internet</span></span></li>
<li><span data-ttu-id="a66ec-433">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-434">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-435">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-436">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-436">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-437">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-437">Generic</span></span></li>
<li><span data-ttu-id="a66ec-438">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-438">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-439">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-440">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-441">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-441">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-442">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-442">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-443">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-444">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-445">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-446">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-447">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-448">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-449">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-450">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-451">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-452"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-signaturversion:</dt>Definition
<dt> &lt; version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine-version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-453">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-454">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-454">No action is required.</span></span> <span data-ttu-id="a66ec-455">Microsoft Defender Antivirus kan avbryta och vidta rutinmässiga åtgärder mot det här hotet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="a66ec-456">Om du vill ta bort risken manuellt går du till gränssnittet för Microsoft Defender Antivirus och klickar på <b>Rensa dator.</b></span><span class="sxs-lookup"><span data-stu-id="a66ec-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-457">Händelse-ID: 1117</span><span class="sxs-lookup"><span data-stu-id="a66ec-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-458">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-460">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-460">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-461">
<b>Program mot skadlig programvara utförde en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-462">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-463">Microsoft Defender Antivirus har vidtagit åtgärder för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="a66ec-464">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-465">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-466">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-466">Low</span></span></li>
<li><span data-ttu-id="a66ec-467">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-467">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-468">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-468">High</span></span></li>
<li><span data-ttu-id="a66ec-469">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-469">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-470">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-471">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-471">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-472">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-472">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-473">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-473">Network share</span></span></li>
<li><span data-ttu-id="a66ec-474">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-474">Internet</span></span></li>
<li><span data-ttu-id="a66ec-475">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-476">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-477">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-478">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-478">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-479">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-479">Generic</span></span></li>
<li><span data-ttu-id="a66ec-480">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-480">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-481">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-482">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-483">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-483">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-484">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-484">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-485">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-486">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-487">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-488">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-489">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-490">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-491">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-492">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-493">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-494"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-495">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="a66ec-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="a66ec-496">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="a66ec-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="a66ec-497">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="a66ec-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="a66ec-498">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="a66ec-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="a66ec-499">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="a66ec-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="a66ec-500">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-500">No action: No action</span></span></li>
<li><span data-ttu-id="a66ec-501">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="a66ec-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="a66ec-502">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Version &gt; av definitionsversion:</dt>
<dt>Version av &lt; &gt; antimalwaremotorn:</dt> När Microsoft Defender Antivirus, Microsoft Security Essentials, borttagningsverktyget för skadlig programvara eller System Center Endpoint Protection upptäcker en skadlig programvara återställs följande systeminställningar och tjänster som den skadliga programvaran kan ha ändrat:</span><span class="sxs-lookup"><span data-stu-id="a66ec-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="a66ec-503">Standardinställning för Internet Explorer eller Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a66ec-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="a66ec-504">Inställningar för användaråtkomstkontroll</span><span class="sxs-lookup"><span data-stu-id="a66ec-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="a66ec-505">Chrome-inställningar</span><span class="sxs-lookup"><span data-stu-id="a66ec-505">Chrome settings</span></span></li>
<li><span data-ttu-id="a66ec-506">Startkontrolldata</span><span class="sxs-lookup"><span data-stu-id="a66ec-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="a66ec-507">Registerinställningar för Regedit och Aktivitetshanteraren</span><span class="sxs-lookup"><span data-stu-id="a66ec-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="a66ec-508">Windows Update, Intelligent Transfer-tjänst för bakgrund och tjänsten för fjärrprocedursamtal</span><span class="sxs-lookup"><span data-stu-id="a66ec-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="a66ec-509">Windows-operativsystemfiler</span><span class="sxs-lookup"><span data-stu-id="a66ec-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="a66ec-510">Ovanstående sammanhang gäller för följande klient- och serverversioner:</span><span class="sxs-lookup"><span data-stu-id="a66ec-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="a66ec-511">Operativsystem</span><span class="sxs-lookup"><span data-stu-id="a66ec-511">Operating system</span></span></th>
<th><span data-ttu-id="a66ec-512">Operativsystemsversion</span><span class="sxs-lookup"><span data-stu-id="a66ec-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-513">Klientoperativsystemet</span><span class="sxs-lookup"><span data-stu-id="a66ec-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="a66ec-514">Windows Vista (Service Pack 1 eller Service Pack 2), Windows 7 och senare</span><span class="sxs-lookup"><span data-stu-id="a66ec-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-515">Server-operativsystem</span><span class="sxs-lookup"><span data-stu-id="a66ec-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="a66ec-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 och Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a66ec-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-517">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-518">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-518">No action is necessary.</span></span> <span data-ttu-id="a66ec-519">Microsoft Defender Antivirus har tagits bort eller sätts i karantän för ett hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-520">Händelse-ID: 1118</span><span class="sxs-lookup"><span data-stu-id="a66ec-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-521">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-523">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-523">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-524">
<b>Program mot skadlig programvara försökte utföra en åtgärd för att skydda datorn mot skadlig programvara eller annan potentiellt oönskad programvara, men åtgärden misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-525">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-526">Ett icke-kritiskt fel har uppstått i Microsoft Defender Antivirus när skadlig programvara eller annan potentiellt oönskad programvara vidtas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="a66ec-527">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-528">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-529">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-529">Low</span></span></li>
<li><span data-ttu-id="a66ec-530">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-530">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-531">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-531">High</span></span></li>
<li><span data-ttu-id="a66ec-532">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-532">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-533">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-534">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-534">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-535">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-535">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-536">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-536">Network share</span></span></li>
<li><span data-ttu-id="a66ec-537">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-537">Internet</span></span></li>
<li><span data-ttu-id="a66ec-538">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-539">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-540">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-541">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-541">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-542">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-542">Generic</span></span></li>
<li><span data-ttu-id="a66ec-543">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-543">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-544">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-545">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-546">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-546">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-547">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-547">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-548">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-549">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-550">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-551">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-552">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-553">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-554">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-555">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-556">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-557"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-558">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="a66ec-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="a66ec-559">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="a66ec-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="a66ec-560">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="a66ec-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="a66ec-561">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="a66ec-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="a66ec-562">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="a66ec-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="a66ec-563">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-563">No action: No action</span></span></li>
<li><span data-ttu-id="a66ec-564">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="a66ec-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="a66ec-565">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-565">
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
<span data-ttu-id="a66ec-566">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-567">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-567">No action is necessary.</span></span> <span data-ttu-id="a66ec-568">Microsoft Defender Antivirus kunde inte slutföra en uppgift som rör åtgärden för skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="a66ec-569">Det här är inte ett kritiskt fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-570">Händelse-ID: 1119</span><span class="sxs-lookup"><span data-stu-id="a66ec-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-571">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-573">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-573">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-574">
<b>På program mot skadlig programvara påträffades ett kritiskt fel när man försökte vidta åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara. Det finns mer information i händelsemeddelandet.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-575">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-576">Ett kritiskt fel har uppstått i Microsoft Defender Antivirus när du vidtar åtgärder mot skadlig programvara eller annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="a66ec-577">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a66ec-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="a66ec-578">
<dt>Namn: &lt; Namn-ID &gt; </dt>
<dt>för hot: Allvarlighetsgrad för hot-ID: &lt; &gt; </dt> 
<dt> &lt; &gt; Allvarlighetsgrad , till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-579">Låg</span><span class="sxs-lookup"><span data-stu-id="a66ec-579">Low</span></span></li>
<li><span data-ttu-id="a66ec-580">Måttlig</span><span class="sxs-lookup"><span data-stu-id="a66ec-580">Moderate</span></span></li>
<li><span data-ttu-id="a66ec-581">Högsta</span><span class="sxs-lookup"><span data-stu-id="a66ec-581">High</span></span></li>
<li><span data-ttu-id="a66ec-582">Allvarligt</span><span class="sxs-lookup"><span data-stu-id="a66ec-582">Severe</span></span></li>
</ul><span data-ttu-id="a66ec-583">
</dt>
<dt>Kategori: &lt; &gt;Kategoribeskrivning, till exempel olika hot eller skadlig programvara.</dt> 
<dt>Sökväg: &lt; Sökväg &gt; Identifiering av</dt> 
<dt> ursprung: &lt; Identifierings &gt; ursprung, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-584">Okänd</span><span class="sxs-lookup"><span data-stu-id="a66ec-584">Unknown</span></span></li>
<li><span data-ttu-id="a66ec-585">Lokal dator</span><span class="sxs-lookup"><span data-stu-id="a66ec-585">Local computer</span></span></li>
<li><span data-ttu-id="a66ec-586">Nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-586">Network share</span></span></li>
<li><span data-ttu-id="a66ec-587">Internet</span><span class="sxs-lookup"><span data-stu-id="a66ec-587">Internet</span></span></li>
<li><span data-ttu-id="a66ec-588">Inkommande trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="a66ec-589">Utgående trafik</span><span class="sxs-lookup"><span data-stu-id="a66ec-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="a66ec-590">
</dt>
<dt>Identifieringstyp: &lt; &gt; Identifieringstyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-591">Heuristics</span><span class="sxs-lookup"><span data-stu-id="a66ec-591">Heuristics</span></span></li>
<li><span data-ttu-id="a66ec-592">Allmänt</span><span class="sxs-lookup"><span data-stu-id="a66ec-592">Generic</span></span></li>
<li><span data-ttu-id="a66ec-593">Betong</span><span class="sxs-lookup"><span data-stu-id="a66ec-593">Concrete</span></span></li>
<li><span data-ttu-id="a66ec-594">Dynamisk signatur</span><span class="sxs-lookup"><span data-stu-id="a66ec-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="a66ec-595">
</dt>
<dt>Identifieringskälla: &lt; &gt; Identifieringskälla till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="a66ec-596">Användare: användarinitierad</span><span class="sxs-lookup"><span data-stu-id="a66ec-596">User: user initiated</span></span></li>
<li><span data-ttu-id="a66ec-597">System: initierat system</span><span class="sxs-lookup"><span data-stu-id="a66ec-597">System: system initiated</span></span></li>
<li><span data-ttu-id="a66ec-598">Realtidskomponent initierad i realtid</span><span class="sxs-lookup"><span data-stu-id="a66ec-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="a66ec-599">IOAV: IE-nedladdningar och initierade Bifogade Outlook Express-filer</span><span class="sxs-lookup"><span data-stu-id="a66ec-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="a66ec-600">NIS: System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="a66ec-601">IEPROTECT: IE - IExtensionValidation; Detta skyddar mot skadliga webbsidekontroller</span><span class="sxs-lookup"><span data-stu-id="a66ec-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="a66ec-602">ELAM (Early Launch Antimalware).</span><span class="sxs-lookup"><span data-stu-id="a66ec-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="a66ec-603">Detta inkluderar skadlig programvara som upptäckts av startsekvensen</span><span class="sxs-lookup"><span data-stu-id="a66ec-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="a66ec-604">Fjärr attestation</span><span class="sxs-lookup"><span data-stu-id="a66ec-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="a66ec-605">Antimalware Scan Interface (AMSI).</span><span class="sxs-lookup"><span data-stu-id="a66ec-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="a66ec-606">Används främst för att skydda skript (PS, VBS), men kan även anropas av tredje part.</span><span class="sxs-lookup"><span data-stu-id="a66ec-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="a66ec-607"></dt>
<dt>UAC-användare: &lt; Domän &gt; \& lt; &gt;Användarnamn:</dt>
<dt>Process i &lt; &gt; PID-åtgärden:</dt>Åtgärd , till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="a66ec-608">Rensa: Resursen har rensats</span><span class="sxs-lookup"><span data-stu-id="a66ec-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="a66ec-609">Karantän: Resursen satt i karantän</span><span class="sxs-lookup"><span data-stu-id="a66ec-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="a66ec-610">Ta bort: Resursen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="a66ec-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="a66ec-611">Tillåt: Resursen har tillåtits att köra/finnas</span><span class="sxs-lookup"><span data-stu-id="a66ec-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="a66ec-612">Användardefinierad: Användardefinierad åtgärd som normalt är en från den här listan med åtgärder som användaren har angett</span><span class="sxs-lookup"><span data-stu-id="a66ec-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="a66ec-613">Ingen åtgärd: Ingen åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-613">No action: No action</span></span></li>
<li><span data-ttu-id="a66ec-614">Blockera: Resursen blockerades från att köras</span><span class="sxs-lookup"><span data-stu-id="a66ec-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="a66ec-615">
</dt>
<dt>Åtgärdsstatus: &lt; Beskrivning av &gt; ytterligare åtgärder</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-615">
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
<span data-ttu-id="a66ec-616">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-617">Det här felet påträffades på grund av kritiska problem i Microsoft Defender Antivirus-klienten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="a66ec-618">Slutpunkten kanske inte är skyddad.</span><span class="sxs-lookup"><span data-stu-id="a66ec-618">The endpoint might not be protected.</span></span> <span data-ttu-id="a66ec-619">Granska felbeskrivningen och följ sedan de relevanta <b>användaråtgärdsstegen</b> nedan.</span><span class="sxs-lookup"><span data-stu-id="a66ec-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="a66ec-620">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-620">Action</span></span></th>
<th><span data-ttu-id="a66ec-621">Användaråtgärd</span><span class="sxs-lookup"><span data-stu-id="a66ec-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="a66ec-622">
<b>Ta bort</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-623">Uppdatera definitionerna och kontrollera sedan att borttagningen lyckades.</span><span class="sxs-lookup"><span data-stu-id="a66ec-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="a66ec-624">
<b>Rensa</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-625">Uppdatera definitionerna och kontrollera sedan att korrigeringen lyckades.</span><span class="sxs-lookup"><span data-stu-id="a66ec-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="a66ec-626">
<b>Karantän</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-627">Uppdatera definitionerna och kontrollera att användaren har behörighet att komma åt nödvändiga resurser.</span><span class="sxs-lookup"><span data-stu-id="a66ec-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="a66ec-628">
<b>Tillåt</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-629">Kontrollera att användaren har behörighet att komma åt nödvändiga resurser.</span><span class="sxs-lookup"><span data-stu-id="a66ec-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="a66ec-630">Om händelsen kvarstår:</span><span class="sxs-lookup"><span data-stu-id="a66ec-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="a66ec-631">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="a66ec-632">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="a66ec-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="a66ec-633">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-634">Händelse-ID: 1120</span><span class="sxs-lookup"><span data-stu-id="a66ec-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-635">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-637">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-637">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-638">
<b>Microsoft Defender Antivirus har bortser från hashtaggarna för en hotresurs.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-639">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-640">Microsoft Defender Antivirus-klienten är igång i ett felfritt läge.</span><span class="sxs-lookup"><span data-stu-id="a66ec-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="a66ec-641">
<dt>Aktuell plattformsversion: &lt; Current platform &gt; version</dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="a66ec-642"><b>Obs! Den här händelsen loggas bara om följande policy har angetts: <b>ThreatFileHashLogging osignerad</b>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-643">Händelse-ID: 1150</span><span class="sxs-lookup"><span data-stu-id="a66ec-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-644">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-646">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-646">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-647">
<b>Om din antimalware-plattform rapporterar status till en övervakningsplattform anger den här händelsen att plattform mot skadlig programvara körs och är i ett felfritt tillstånd. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-648">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-649">Microsoft Defender Antivirus-klienten är igång i ett felfritt läge.</span><span class="sxs-lookup"><span data-stu-id="a66ec-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="a66ec-650">
<dt>Plattformsversion: &lt; Aktuell plattform &gt; version</dt>
<dt>Signatur version: Definition &lt; &gt; version</dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-651">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-652">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-652">No action is necessary.</span></span> <span data-ttu-id="a66ec-653">Microsoft Defender Antivirus-klienten är i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a66ec-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="a66ec-654">Händelsen rapporteras varje timme.</span><span class="sxs-lookup"><span data-stu-id="a66ec-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="a66ec-655">Händelse-ID: 1151</span><span class="sxs-lookup"><span data-stu-id="a66ec-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-656">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-658">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-658">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-659">
<b>Hälsorapport för endpoint Protection-klient (tid i UTC) </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-660">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-661">Hälsorapport för antivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="a66ec-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="a66ec-662">
<dt>Plattformsversion: &lt; Current platform &gt; version</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>Network
<dt>Realtime Inspection engine version: &lt; Network Realtime Inspection &gt; </dt>engine version Antivirus signature
<dt>version: Antivirus signature &lt; version &gt; </dt>
<dt>Antispyware signature version: &lt; Antispyware signature version &gt; </dt>Network
<dt>Realtime Inspection signature version: Network &lt; Realtime Inspection version &gt; RTP</dt>
<dt>state: &lt; Realtime protection state &gt; (Enabled or Disabled)</dt>
<dt>OA state: On Access state &lt; &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: IE-nedladdningar och Status för Outlook Express-bifogade filer (aktiverad eller &lt; inaktiverad) &gt; </dt>BM-läge: Status för funktionsövervakning (aktiverad eller
<dt> &lt; &gt; inaktiverad)</dt>ålder för antivirussignaturen: Ålder på antivirussignaturen (i dagar) Antispionprogramsignatur, ålder: Ålder för antivirussignatur
<dt> &lt; &gt; (i</dt>
<dt> &lt; &gt; dagar)</dt>
<dt> &lt; &gt; Antispionprogramsåldern:</dt>Senaste fullständiga genomsökningsåldern: Senaste fullständiga genomsökningsåldern
<dt> &lt; &gt; (i dagar)</dt>Tid då antivirussignaturen
<dt>skapades: ? &lt; Tid för &gt; att skapa antivirussignaturer</dt>
<dt>Tid då man skapade antispionwaresignaturer: ? &lt; Tid för att skapa &gt; antispionprogramssignaturer</dt>
<dt>Senaste snabbstarttiden: ? &lt; Sista snabba skanningens &gt; starttid</dt>Sista snabba
<dt>genomsökning sluttid: ? &lt; &gt;</dt>Sista snabba skanningens sluttid Senaste snabbsökningskälla: Senaste snabbsökningskälla (0 = genomsökning&#39;inte
<dt> &lt; &gt; körts, 1 = användare initierad, 2 = systeminitierad)</dt>Senaste
<dt>fullständiga genomsökningsstarttid: ? &lt; Senaste fullständiga genomsökningsstarttid &gt; </dt>Senaste fullständiga
<dt>genomsökning sluttid: ? &lt; &gt;</dt>Sista fullständiga genomsökningens sluttid Senaste fullständiga genomsökningskälla: Senaste fullständiga genomsökningskälla (0 = genomsökningen&#39;inte
<dt> &lt; &gt; körts, 1 = användarinitierad, 2 = systeminitierad)</dt>Produktstatus: För intern felsökning 
<dt></span><span class="sxs-lookup"><span data-stu-id="a66ec-662">
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

<tr><span data-ttu-id="a66ec-663">
<th colspan="2">Händelse-ID: 2000</span><span class="sxs-lookup"><span data-stu-id="a66ec-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-664">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-666">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-666">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-667">
<b>Definitionerna för program mot skadlig programvara har uppdaterats. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-668">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-669">Antivirussignaturversionen har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="a66ec-670">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt>
<dt>Tidigare signaturversion: Tidigare &lt; signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="a66ec-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-671">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-672">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-672">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-673">Antimalware</span></span></li>
<li><span data-ttu-id="a66ec-674">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-675">
</dt>
<dt>Uppdateringstyp: &lt; Uppdatera typen &gt; , antingen Fullständig eller Delta.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-675">
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
<span data-ttu-id="a66ec-676">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-677">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-677">No action is necessary.</span></span> <span data-ttu-id="a66ec-678">Microsoft Defender Antivirus-klienten är i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a66ec-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="a66ec-679">Händelsen rapporteras när signaturer har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-680">Händelse-ID: 2001</span><span class="sxs-lookup"><span data-stu-id="a66ec-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-681">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-683">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-683">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-684">
<b>Uppdateringen av säkerhetsintelligens misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-685">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-686">Det har uppstått ett fel i Microsoft Defender Antivirus när signaturer ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="a66ec-687">
<dt>Ny säkerhetsintelligensversion: &lt; Nytt versionsnummer &gt; </dt>
<dt>Tidigare säkerhetsinformationsversion: Tidigare &lt; &gt; versionsuppdateringskälla:</dt> 
<dt> &lt; &gt; Uppdateringskälla, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-688">Uppdateringsmapp för säkerhetsinformation</span><span class="sxs-lookup"><span data-stu-id="a66ec-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="a66ec-689">Uppdateringsserver för intern säkerhetsintelligens</span><span class="sxs-lookup"><span data-stu-id="a66ec-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="a66ec-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="a66ec-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="a66ec-691">Filresurs</span><span class="sxs-lookup"><span data-stu-id="a66ec-691">File share</span></span></li>
<li><span data-ttu-id="a66ec-692">Microsoft Malware Protection Center (MMPC)</span><span class="sxs-lookup"><span data-stu-id="a66ec-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="a66ec-693">
</dt>
<dt>Uppdateringsfas: &lt; &gt; Uppdateringsfas, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-694">Sök</span><span class="sxs-lookup"><span data-stu-id="a66ec-694">Search</span></span></li>
<li><span data-ttu-id="a66ec-695">Ladda ned</span><span class="sxs-lookup"><span data-stu-id="a66ec-695">Download</span></span></li>
<li><span data-ttu-id="a66ec-696">Installera</span><span class="sxs-lookup"><span data-stu-id="a66ec-696">Install</span></span></li>
</ul><span data-ttu-id="a66ec-697">
</dt>
<dt>Källsökväg: Filresursnamn för UNC (Universal Naming Convention), servernamn för Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="a66ec-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-698">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-699">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-699">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-700">Antimalware</span></span></li>
<li><span data-ttu-id="a66ec-701">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-702">
</dt>
<dt>Uppdateringstyp: &lt; Uppdatera typen &gt; , antingen Fullständig eller Delta.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användar &gt; </dt>
<dt>current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-702">
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
<span data-ttu-id="a66ec-703">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-704">Det här felet inträffar när det är problem med att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="a66ec-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="a66ec-705">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="a66ec-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Uppdatera definitioner</a> och tvinga fram en omsökning direkt i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="a66ec-707">Granska posterna i filen %Windir%\WindowsUpdate.log för mer information om det här felet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="a66ec-708">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-709">Händelse-ID: 2002</span><span class="sxs-lookup"><span data-stu-id="a66ec-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-710">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-712">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-712">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-713">
<b>Antimalware-motorn har uppdaterats. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-714">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-715">Microsoft Defender Antivirusmotorns version har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="a66ec-716">
<dt>Current Engine-version: &lt; Current engine &gt; version</dt>
<dt>Previous Engine Version: Previous engine &lt; version &gt; </dt>Engine
<dt>Type: Engine type , either &lt; &gt; antimalware engine or Network Inspection System engine.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; Användare &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-717">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-718">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-718">No action is necessary.</span></span> <span data-ttu-id="a66ec-719">Microsoft Defender Antivirus-klienten är i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a66ec-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="a66ec-720">Händelsen rapporteras när program mot skadlig programvara har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-721">Händelse-ID: 2003</span><span class="sxs-lookup"><span data-stu-id="a66ec-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-722">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-724">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-724">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-725">
<b>Uppdateringen av program mot skadlig programvara misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-726">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-727">Det har uppstått ett fel i Microsoft Defender Antivirus när motorn ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="a66ec-728">
<dt>Ny motorversion: Tidigare</dt>
<dt>motorversion: Tidigare &lt; &gt; </dt>motorversionstyp: Motortyp , antingen
<dt> &lt; &gt; programskyddsmotor eller system för nätverksinspektion.</dt> 
<dt>Användare: &lt; Domain &gt; \& lt; &gt;</dt>
<dt>Användarfelkod: &lt; Felkod &gt; resultatkod som är associerad med hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-728">
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
<span data-ttu-id="a66ec-729">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-730">Uppdateringen av Microsoft Defender Antivirus-klienten misslyckades.</span><span class="sxs-lookup"><span data-stu-id="a66ec-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="a66ec-731">Den här händelsen inträffar när klienten inte kan uppdatera sig själv.</span><span class="sxs-lookup"><span data-stu-id="a66ec-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="a66ec-732">Händelsen beror vanligtvis på ett avbrott i nätverksanslutningen under en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="a66ec-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="a66ec-733">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="a66ec-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Uppdatera definitioner</a> och tvinga fram en omsökning direkt i slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="a66ec-735">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-736">Händelse-ID: 2004</span><span class="sxs-lookup"><span data-stu-id="a66ec-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-737">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-739">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-739">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-740">
<b>Det gick inte att läsa in definitioner för program mot skadlig programvara. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-741">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-742">Det har uppstått ett fel i Microsoft Defender Antivirus när man försöker läsa in signaturer och försöker återgå till en känd uppsättning signaturer.</span><span class="sxs-lookup"><span data-stu-id="a66ec-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="a66ec-743">
<dt>Signaturer: Försöks:</dt>
<dt>Felkod: &lt; Felkod &gt; resultatkod som är kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Signaturversion: &lt; Definition &gt; version</dt>
<dt>Engine Version: &lt; Antimalware engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-743">
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
<span data-ttu-id="a66ec-744">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-745">Microsoft Defender Antivirus-klienten försökte hämta och installera den senaste definitionsfilen och misslyckades.</span><span class="sxs-lookup"><span data-stu-id="a66ec-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="a66ec-746">Det här felet kan uppstå när klienten stöter på ett fel när du försöker läsa in definitionerna eller om filen är skadad.</span><span class="sxs-lookup"><span data-stu-id="a66ec-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="a66ec-747">Microsoft Defender Antivirus försöker återgå till en känd uppsättning definitioner.</span><span class="sxs-lookup"><span data-stu-id="a66ec-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="a66ec-748">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="a66ec-749">Starta om datorn och försök igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="a66ec-750">Hämta de senaste definitionerna från <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-webbplatsen</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="a66ec-751">Obs! Storleken på definitionsfilen som laddas ned från webbplatsen kan överskrida 60 MB och bör inte användas som en långsiktig lösning för att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="a66ec-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="a66ec-752">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-753">Händelse-ID: 2005</span><span class="sxs-lookup"><span data-stu-id="a66ec-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-754">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-756">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-756">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-757">
<b>Antimalware-motorn kunde inte läsas in eftersom programplattformen mot skadlig programvara är in date. Antimalware-plattformen laddar den senast kända bra antimalware-motorn och försöker uppdatera.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-758">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-759">Det gick inte att läsa in skadlig programvara i Microsoft Defender Antivirus eftersom den aktuella plattformsversionen inte stöds.</span><span class="sxs-lookup"><span data-stu-id="a66ec-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="a66ec-760">Microsoft Defender Antivirus återgår till den senaste kända motorn och en plattformsuppdatering kommer att försökas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="a66ec-761">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-762">Händelse-ID: 2006</span><span class="sxs-lookup"><span data-stu-id="a66ec-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-763">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-765">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-765">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-766">
<b>Plattformsuppdateringen misslyckades. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-767">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-768">Det har uppstått ett fel i Microsoft Defender Antivirus när plattformen ska uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="a66ec-769">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion &gt; </dt>
<dt>Felkod: &lt; Resultatkod för &gt; felkod som är kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-770">Händelse-ID: 2007</span><span class="sxs-lookup"><span data-stu-id="a66ec-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-771">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-773">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-773">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-774">
<b>Plattformen är snart in föråldrad. Ladda ned den senaste plattformen för att ha ett uppdaterat skydd.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-775">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-776">Microsoft Defender Antivirus kommer snart att kräva en nyare plattformsversion för att stödja framtida versioner av program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="a66ec-777">Ladda ned den senaste Microsoft Defender Antivirus-plattformen för att upprätthålla den bästa skyddsnivån som finns tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a66ec-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="a66ec-778">
<dt>Aktuell plattformsversion: &lt; Aktuell plattformsversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-779">Händelse-ID: 2010</span><span class="sxs-lookup"><span data-stu-id="a66ec-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-780">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-782">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-782">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-783">
<b>Antimalware-motorn använde tjänsten Dynamic Signature Service för att få ytterligare definitioner. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-784">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-785">Microsoft Defender Antivirus använde <i>dynamisk signaturtjänst för</i> att hämta ytterligare signaturer som skyddar din dator.</span><span class="sxs-lookup"><span data-stu-id="a66ec-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="a66ec-786">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="a66ec-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-787">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-788">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-788">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-789">Antimalware</span></span></li>
<li><span data-ttu-id="a66ec-790">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-791">
</dt>
<dt>Current Engine-version: &lt; Aktuell motorversion &gt; </dt> 
<dt> av dynamisk signaturtyp: Dynamisk &lt; &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-792">Version</span><span class="sxs-lookup"><span data-stu-id="a66ec-792">Version</span></span></li>
<li><span data-ttu-id="a66ec-793">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-793">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-794">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-794">No limit</span></span></li>
<li><span data-ttu-id="a66ec-795">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="a66ec-795">Duration</span></span></li>
</ul><span data-ttu-id="a66ec-796">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Tidsstämpel</dt>Gränstyp för beständighet: Gränstyp för beständighet, till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-797">VDM-version</span><span class="sxs-lookup"><span data-stu-id="a66ec-797">VDM version</span></span></li>
<li><span data-ttu-id="a66ec-798">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-798">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-799">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-799">No limit</span></span></li>
</ul><span data-ttu-id="a66ec-800">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-801">Händelse-ID: 2011</span><span class="sxs-lookup"><span data-stu-id="a66ec-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-802">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-804">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-804">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-805">
<b>Tjänsten dynamisk signatur tog bort de in datera dynamiska definitionerna. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-806">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-807">Microsoft Defender Antivirus använde <i>dynamisk signaturtjänst för att</i> ignorera inaktuella signaturer.</span><span class="sxs-lookup"><span data-stu-id="a66ec-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="a66ec-808">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="a66ec-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-809">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-810">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-810">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-811">Antimalware</span></span></li>
<li><span data-ttu-id="a66ec-812">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-813">
</dt>
<dt>Current Engine-version: &lt; Aktuell motorversion &gt; </dt> 
<dt> av dynamisk signaturtyp: Dynamisk &lt; &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-814">Version</span><span class="sxs-lookup"><span data-stu-id="a66ec-814">Version</span></span></li>
<li><span data-ttu-id="a66ec-815">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-815">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-816">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-816">No limit</span></span></li>
<li><span data-ttu-id="a66ec-817">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="a66ec-817">Duration</span></span></li>
</ul><span data-ttu-id="a66ec-818">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Ta bort tidsstämpel</dt>
<dt>Orsak:</dt>Gränstyp för beständig beständighet: Gränstyp för beständighet, 
<dt> till &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-819">VDM-version</span><span class="sxs-lookup"><span data-stu-id="a66ec-819">VDM version</span></span></li>
<li><span data-ttu-id="a66ec-820">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-820">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-821">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-821">No limit</span></span></li>
</ul><span data-ttu-id="a66ec-822">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-823">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-824">Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-824">No action is necessary.</span></span> <span data-ttu-id="a66ec-825">Microsoft Defender Antivirus-klienten är i ett felfritt tillstånd.</span><span class="sxs-lookup"><span data-stu-id="a66ec-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="a66ec-826">Den här händelsen rapporteras när tjänsten Dynamisk signatur tar bort dynamiska definitioner som inte är aktuella.</span><span class="sxs-lookup"><span data-stu-id="a66ec-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-827">Händelse-ID: 2012</span><span class="sxs-lookup"><span data-stu-id="a66ec-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-828">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-830">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-830">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-831">
<b>Det uppstod ett fel på motorn mot skadlig programvara när man försökte använda tjänsten Dynamisk signatur. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-832">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-833">Det har uppstått ett fel i Microsoft Defender Antivirus när <i>tjänsten Dynamisk signatur ska användas.</i></span><span class="sxs-lookup"><span data-stu-id="a66ec-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="a66ec-834">
<dt>Aktuell signaturversion: &lt; Aktuell signaturversion &gt; </dt> 
<dt> Signaturtyp: &lt; &gt; Signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="a66ec-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="a66ec-835">Antivirus</span></span></li>
<li><span data-ttu-id="a66ec-836">Antispionprogram</span><span class="sxs-lookup"><span data-stu-id="a66ec-836">Antispyware</span></span></li>
<li><span data-ttu-id="a66ec-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="a66ec-837">Antimalware</span></span></li>
<li><span data-ttu-id="a66ec-838">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-839">
</dt>
<dt>Current Engine-version: &lt; Current engine &gt; version</dt>
<dt>Error Code: Error code Result &lt; code associated with threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt> Dynamisk signaturtyp: &lt; Dynamisk &gt; signaturtyp, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-840">Version</span><span class="sxs-lookup"><span data-stu-id="a66ec-840">Version</span></span></li>
<li><span data-ttu-id="a66ec-841">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-841">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-842">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-842">No limit</span></span></li>
<li><span data-ttu-id="a66ec-843">Varaktighet</span><span class="sxs-lookup"><span data-stu-id="a66ec-843">Duration</span></span></li>
</ul><span data-ttu-id="a66ec-844">
</dt>
<dt>Beständig sökväg: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; &gt; Versionsnummer</dt>Dynamic Signature Compilation
<dt> &lt; &gt; Timestamp: Tidsstämpel</dt>Gränstyp för beständighet: Gränstyp för beständighet, till 
<dt> &lt; &gt; exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-845">VDM-version</span><span class="sxs-lookup"><span data-stu-id="a66ec-845">VDM version</span></span></li>
<li><span data-ttu-id="a66ec-846">Tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="a66ec-846">Timestamp</span></span></li>
<li><span data-ttu-id="a66ec-847">Ingen gräns</span><span class="sxs-lookup"><span data-stu-id="a66ec-847">No limit</span></span></li>
</ul><span data-ttu-id="a66ec-848">
</dt>
<dt>Gräns för beständighet: Gränsen för beständighet för fastpath-signaturen.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-849">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-850">Kontrollera inställningarna för Internetanslutningen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-851">Händelse-ID: 2013</span><span class="sxs-lookup"><span data-stu-id="a66ec-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-852">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-854">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-854">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-855">
<b>Tjänsten Dynamisk signatur tog bort alla dynamiska definitioner. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-856">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-857">Alla signaturer för <i></i> dynamisk signaturtjänst ignorerades i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="a66ec-858">
<dt>Aktuell signaturversion: &lt; aktuell signaturversion&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-859">Händelse-ID: 2020</span><span class="sxs-lookup"><span data-stu-id="a66ec-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-860">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-862">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-862">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-863">
<b>Antimalware-motorn laddade ned en ren fil. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-864">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-865">Microsoft Defender Antivirus har laddat ned en ren fil.</span><span class="sxs-lookup"><span data-stu-id="a66ec-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="a66ec-866">
<dt>Filnamn: &lt; Filens &gt; filnamn.</dt> 
<dt>Aktuell signaturversion: &lt; Current signature &gt; version</dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-867">Händelse-ID: 2021</span><span class="sxs-lookup"><span data-stu-id="a66ec-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-868">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-870">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-870">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-871">
<b>Det gick inte att hämta en ren fil till programmotorn. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-872">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-873">Det har uppstått ett fel i Microsoft Defender Antivirus när en ren fil ska laddas ned.</span><span class="sxs-lookup"><span data-stu-id="a66ec-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="a66ec-874">
<dt>Filnamn: &lt; Filens &gt; filnamn.</dt> 
<dt>Aktuell signaturversion: &lt; Current signature &gt; version</dt>
<dt>Current Engine Version: Current engine &lt; version &gt; </dt>Error
<dt>Code: Error code Result code associated with &lt; threat &gt; status. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-874">
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
<span data-ttu-id="a66ec-875">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-876">Kontrollera inställningarna för Internetanslutningen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="a66ec-877">Det uppstod ett fel i Microsoft Defender Antivirus-klienten när tjänsten Dynamisk signatur skulle användas för att ladda ned de senaste definitionerna för ett visst hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="a66ec-878">Det här felet orsakas troligen av ett nätverksanslutningsproblem.</span><span class="sxs-lookup"><span data-stu-id="a66ec-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-879">Händelse-ID: 2030</span><span class="sxs-lookup"><span data-stu-id="a66ec-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-880">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-882">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-882">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-883">
<b>Antimalware-motorn har laddats ned och är konfigurerad att köras offline vid nästa systemomstart.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-884">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-885">Microsoft Defender Antivirus har laddats ned och konfigurerats att köras offline för att köras vid nästa omstart.</span><span class="sxs-lookup"><span data-stu-id="a66ec-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-886">Händelse-ID: 2031</span><span class="sxs-lookup"><span data-stu-id="a66ec-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-887">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-889">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-889">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-890">
<b>Det gick inte att hämta och konfigurera en offlinesökning via motorn för program mot skadlig programvara.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-891">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-892">Det har uppstått ett fel i Microsoft Defender Antivirus när antivirusprogrammet ska laddas ned och konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="a66ec-893">
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-894">Händelse-ID: 2040</span><span class="sxs-lookup"><span data-stu-id="a66ec-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-895">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-897">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-897">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-898">
<b>Stöd för program mot skadlig programvara för den här versionen av operativsystemet avslutas snart. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-899">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-900">Stödet för ditt operativsystem upphör snart.</span><span class="sxs-lookup"><span data-stu-id="a66ec-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="a66ec-901">Att köra Microsoft Defender Antivirus på ett operativsystem utan support är inte en lämplig lösning för att skydda mot hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-902">Händelse-ID: 2041</span><span class="sxs-lookup"><span data-stu-id="a66ec-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-903">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-905">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-905">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-906">
<b>Stödet för program mot skadlig programvara för det här operativsystemet har upphört. Du måste uppgradera operativsystemet för att kunna fortsätta stödja. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-907">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-908">Stödet för ditt operativsystem har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="a66ec-908">The support for your operating system has expired.</span></span> <span data-ttu-id="a66ec-909">Att köra Microsoft Defender Antivirus på ett operativsystem utan support är inte en lämplig lösning för att skydda mot hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-910">Händelse-ID: 2042</span><span class="sxs-lookup"><span data-stu-id="a66ec-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-911">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-913">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-913">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-914">
<b>Antimalware-motorn stöder inte längre det här operativsystemet och skyddar inte längre datorn mot skadlig programvara. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-915">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-916">Stödet för ditt operativsystem har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="a66ec-916">The support for your operating system has expired.</span></span> <span data-ttu-id="a66ec-917">Microsoft Defender Antivirus stöds inte längre i ditt operativsystem, har slutat fungera och skyddar inte mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-918">Händelse-ID: 3002</span><span class="sxs-lookup"><span data-stu-id="a66ec-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-919">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-921">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-921">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-922">
<b>Realtidsskyddet påträffade ett fel och misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-923">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-924">Ett fel har uppstått Real-Time har uppstått i funktionen Microsoft Defender Antivirus Real-Time Antivirus Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="a66ec-925">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-926">I Access</span><span class="sxs-lookup"><span data-stu-id="a66ec-926">On Access</span></span></li>
<li><span data-ttu-id="a66ec-927">Internet Explorer-nedladdningar och bifogade filer i Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="a66ec-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="a66ec-928">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="a66ec-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="a66ec-929">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-930">
</dt>
<dt>Felkod: &lt; Felkod &gt; Resultatkod kopplad till hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt> 
<dt>Orsak: Orsaken till att realtidsskyddet för Microsoft Defender Antivirus har startat om en funktion.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-931">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-932">Du bör starta om systemet och sedan köra en fullständig genomsökning eftersom&#39;det är möjligt att systemet inte var skyddat på ett tag.</span><span class="sxs-lookup"><span data-stu-id="a66ec-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="a66ec-933">Ett fel uppstod när&#39;antivirusklienten för Microsoft Defender i realtid påträffade ett fel eftersom en av tjänsterna inte kunde startas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="a66ec-934">Om det följs av ett 3007 händelse-ID var felet tillfälligt och klienten för program mot skadlig kod återställdes efter felet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-935">Händelse-ID: 3007</span><span class="sxs-lookup"><span data-stu-id="a66ec-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-936">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-938">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-938">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-939">
<b>Realtidsskydd som återställts efter ett fel. Vi rekommenderar att du kör en fullständig systemsökning när du ser det här felet. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-940">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-941">Microsoft Defender Antivirus Realtidsskydd har startat om en funktion.</span><span class="sxs-lookup"><span data-stu-id="a66ec-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="a66ec-942">Vi rekommenderar att du kör en fullständig systemsökning för att hitta eventuella objekt som kan ha missats under tiden den här agenten var nere.</span><span class="sxs-lookup"><span data-stu-id="a66ec-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="a66ec-943">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-944">I Access</span><span class="sxs-lookup"><span data-stu-id="a66ec-944">On Access</span></span></li>
<li><span data-ttu-id="a66ec-945">IE-nedladdningar och Outlook Express-bilagor</span><span class="sxs-lookup"><span data-stu-id="a66ec-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="a66ec-946">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="a66ec-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="a66ec-947">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-948">
</dt>
<dt>Orsak: Orsaken till att realtidsskyddet för Microsoft Defender Antivirus har startat om en funktion.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-949">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-950">Realtidsskyddet har startats om.</span><span class="sxs-lookup"><span data-stu-id="a66ec-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="a66ec-951">Om händelsen inträffar igen kontaktar du <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support.</a></span><span class="sxs-lookup"><span data-stu-id="a66ec-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-952">Händelse-ID: 5000</span><span class="sxs-lookup"><span data-stu-id="a66ec-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-953">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-955">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-955">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-956">
<b>Realtidsskydd är aktiverat. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-957">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-958">Sökning efter skadlig programvara och andra potentiellt oönskade program har aktiverats i realtid med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-959">Händelse-ID: 5001</span><span class="sxs-lookup"><span data-stu-id="a66ec-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-960">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-962">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-962">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-963">
<b>Realtidsskydd är inaktiverat. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-964">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-965">Genomsökning av realtidsskydd för skadlig programvara och andra potentiellt oönskade program har inaktiverats i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-966">Händelse-ID: 5004</span><span class="sxs-lookup"><span data-stu-id="a66ec-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-967">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-969">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-969">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-970">
<b>Konfigurationen av realtidsskyddet har ändrats. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-971">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-972">Funktionskonfigurationen för realtidsskyddet i Microsoft Defender Antivirus har ändrats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="a66ec-973">
<dt>Funktion: &lt; &gt; Funktion, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a66ec-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="a66ec-974">I Access</span><span class="sxs-lookup"><span data-stu-id="a66ec-974">On Access</span></span></li>
<li><span data-ttu-id="a66ec-975">IE-nedladdningar och Outlook Express-bilagor</span><span class="sxs-lookup"><span data-stu-id="a66ec-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="a66ec-976">Övervakning av beteende</span><span class="sxs-lookup"><span data-stu-id="a66ec-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="a66ec-977">System för nätverksinspektion</span><span class="sxs-lookup"><span data-stu-id="a66ec-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="a66ec-978">
</dt>
<dt>Konfiguration: </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-979">Händelse-ID: 5007</span><span class="sxs-lookup"><span data-stu-id="a66ec-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-980">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-982">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-982">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-983">
<b>Konfigurationen av motprogramsplattformen har ändrats.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-984">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-985">Microsoft Defender Antivirus-konfigurationen har ändrats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="a66ec-986">Om det här är en oväntad händelse bör du granska inställningarna eftersom det kan vara resultatet av skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="a66ec-987">
<dt>Gammalt värde: &lt; Gammalt värde nummer &gt; Gammalt antivirusprogram-konfigurationsvärde.</dt> 
<dt>Nytt värde: &lt; Nytt värdenummer &gt; Nytt antivirusprograms konfigurationsvärde.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-988">Händelse-ID: 5008</span><span class="sxs-lookup"><span data-stu-id="a66ec-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-989">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-991">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-991">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-992">
<b>Det uppstod ett fel på motorn mot skadlig programvara och misslyckades.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-993">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-994">Microsoft Defender Antivirus-motorn har avslutats på grund av ett oväntat fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="a66ec-995">
<dt>Feltyp: &lt; &gt;Feltyp, till exempel: Krasch- eller undantagskod:</dt>
<dt> &lt; Felkod &gt; Resurs:</dt>
<dt> &lt; Resurs &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-996">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-997">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="a66ec-998">Försök att starta om tjänsten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="a66ec-999">För program mot skadlig programvara, antivirus och spionprogram skriver du net <b>stop msmpsvc</b>i en upphöjd kommandotolk och skriver sedan net <b>start msmpsvc</b> för att starta om program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="a66ec-1000">För <i>System för</i>nätverksinspektion i en upphöjd kommandotolk skriver du <b>net start nissrv</b>och skriver sedan <b>net start nissrv</b> för att starta om <i>motorn i Network Inspection System</i> med hjälp av NiSSRV.exe filen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="a66ec-1001">Om den misslyckas på samma sätt letar du upp felkoden genom att gå <b></b> till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a> och ange felnumret i rutan Sök och kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support.</a></span><span class="sxs-lookup"><span data-stu-id="a66ec-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1002">Användaråtgärd:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1003">Microsoft Defender Antivirus-klientmotorn slutade fungera på grund av ett oväntat fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="a66ec-1004">Så här felsöker du händelsen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="a66ec-1005">Kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="a66ec-1006">Om det misslyckas på samma sätt går du till <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support-webbplatsen</a>och anger felnumret i rutan Sök för att leta efter felkoden. <b></b></span><span class="sxs-lookup"><span data-stu-id="a66ec-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="a66ec-1007">Kontakta <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsofts tekniska support</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1008">Händelse-ID: 5009</span><span class="sxs-lookup"><span data-stu-id="a66ec-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1009">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1011">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1012">
<b>Sökning efter skadlig programvara och annan potentiellt oönskad programvara aktiveras. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1013">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1014">Sökning efter skadlig programvara och andra potentiellt oönskade program har aktiverats i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1015">Händelse-ID: 5010</span><span class="sxs-lookup"><span data-stu-id="a66ec-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1016">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1018">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1019">
<b>Sökning efter skadlig programvara och annan potentiellt oönskad programvara inaktiveras.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1020">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1021">Genomsökning av skadlig programvara och andra potentiellt oönskade program inaktiveras i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1022">Händelse-ID: 5011</span><span class="sxs-lookup"><span data-stu-id="a66ec-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1023">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1025">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1026">
<b>Sökning efter virus har aktiverats.</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1027">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1028">Microsoft Defender Antivirus-genomsökning efter virus har aktiverats.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1029">Händelse-ID: 5012</span><span class="sxs-lookup"><span data-stu-id="a66ec-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1030">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1032">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1033">
<b>Sökning efter virus inaktiveras. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1034">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1035">Microsoft Defender Antivirus-genomsökning efter virus inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1036">Händelse-ID: 5100</span><span class="sxs-lookup"><span data-stu-id="a66ec-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1037">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1039">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1040">
<b>Antimalware-plattformen upphör snart att gälla. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1041">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1042">Microsoft Defender Antivirus har angett en respitperiod och upphör snart att gälla.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="a66ec-1043">Efter att programmet har gått ut inaktiveras skyddet mot virus, spionprogram och annan potentiellt oönskad programvara.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="a66ec-1044">
<dt>Orsak till förfallodatum: Orsaken till att Microsoft Defender Antivirus upphör att gälla.</dt> 
<dt>Förfallodatum: Datumet då Microsoft Defender Antivirus upphör att gälla.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1045">Händelse-ID: 5101</span><span class="sxs-lookup"><span data-stu-id="a66ec-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="a66ec-1046">Symboliskt namn:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1048">Meddelande:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="a66ec-1049">
<b>Antimalware-plattformen har upphört att gälla. </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1050">Beskrivning:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="a66ec-1051">Respitperioden för Microsoft Defender Antivirus har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="a66ec-1052">Skydd mot virus, spionprogram och annan potentiellt oönskad programvara inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="a66ec-1053">
<dt>Förfallodatum: Förfallodatum:</dt>
<dt>Felkod: </dt> 
<dt>Felkod &lt; resultatkod som är associerad med &gt; hotstatus. Vanliga HRESULT-värden.</dt> 
<dt>Felbeskrivning: &lt; Felbeskrivning &gt; Beskrivning av felet.</dt>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="a66ec-1054">
</table>

<a id="error-codes"></a>
## Felkoder för Microsoft Defender Antivirus-klienten Om microsoft Defender Antivirus upplever problem får du vanligtvis en felkod som hjälper dig att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="a66ec-1055">Oftast innebär ett fel att det gick att installera en uppdatering.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="a66ec-1056">Det här avsnittet innehåller följande information om Microsoft Defender Antivirus-klientfel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="a66ec-1057">-   Felkoden -   Den möjliga orsaken till felet Råd -   om vad du ska göra nu</span><span class="sxs-lookup"><span data-stu-id="a66ec-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="a66ec-1058">Använd informationen i de här tabellerna för felsökning av felkoder för Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1059">Felkod: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="a66ec-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="a66ec-1060">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1060">Message</span></span></td>
<td><span data-ttu-id="a66ec-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1062">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="a66ec-1063">Det här felet anger att minnet kan vara slut.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="a66ec-1064">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="a66ec-1065">Kontrollera enhetens tillgängliga minne.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="a66ec-1066">Stäng alla oanvända program som körs för att frigöra minne på enheten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="a66ec-1067">Starta om enheten och kör skanningen igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1068">Felkod: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="a66ec-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="a66ec-1069">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1069">Message</span></span></td>
<td><span data-ttu-id="a66ec-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1071">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1072">Det här felet anger att det kan vara problem med din säkerhetsprodukt.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="a66ec-1073">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="a66ec-1074">Uppdatera definitionerna.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1074">Update the definitions.</span></span> <span data-ttu-id="a66ec-1075">Antingen:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1075">Either:</span></span><ol>
<li><span data-ttu-id="a66ec-1076">Klicka på <b>knappen Uppdatera</b> definitioner på <b>fliken Uppdatera</b> i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="a66ec-1077">Eller:</span><span class="sxs-lookup"><span data-stu-id="a66ec-1077">Or,</span></span>
</li>
<li><span data-ttu-id="a66ec-1078">Hämta de senaste definitionerna från <a href="https://aka.ms/wdsi">Microsoft Security Intelligence-webbplatsen</a>.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="a66ec-1079">Obs! Storleken på definitionsfilen som laddas ned från webbplatsen kan överskrida 60 MB och bör inte användas som en långsiktig lösning för att uppdatera definitioner.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="a66ec-1080">Kör en fullständig genomsökning.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="a66ec-1081">Starta om enheten och försök igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1082">Felkod: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="a66ec-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="a66ec-1083">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1083">Message</span></span></td>
<td><span data-ttu-id="a66ec-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1085">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1086">Det här felet anger att det kan finnas ett motorkonfigurationsfel. vanligtvis är detta relaterat till indata som inte tillåter att motorn fungerar korrekt.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1087">Felkod: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="a66ec-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1088">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1088">Message</span></span></td>
<td><span data-ttu-id="a66ec-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1090">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1091">Det här felet anger att Microsoft Defender Antivirus inte kunde sätta ett hot i karantän.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1092">Felkod: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="a66ec-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1093">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1093">Message</span></span></td>
<td><span data-ttu-id="a66ec-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1095">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1096">Det här felet anger att en omstart krävs för att slutföra borttagningen av hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="a66ec-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="a66ec-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1098">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1098">Message</span></span></td>
<td><span data-ttu-id="a66ec-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1100">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1101">Det här felet anger att risken inte längre finns i media, eller att skadlig programvara hindrar dig från att skanna enheten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="a66ec-1102">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="a66ec-1103">Kör <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner och</a> uppdatera sedan säkerhetsprogramvaran och försök igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1104">Felkod: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="a66ec-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="a66ec-1105">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1105">Message</span></span></td>
<td><span data-ttu-id="a66ec-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1107">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1108">Det här felet anger att en fullständig systemsökning kan behövas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="a66ec-1109">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1109">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1110">Kör en fullständig systemsökning.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1111">Felkod: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="a66ec-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1112">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1112">Message</span></span></td>
<td><span data-ttu-id="a66ec-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1114">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1115">Det här felet anger att manuella steg krävs för att slutföra borttagningen av hot.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1116">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1116">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1117">Följ de anvisningar för manuella åtgärder som beskrivs i <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia.</a></span><span class="sxs-lookup"><span data-stu-id="a66ec-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="a66ec-1118">Du hittar en länk som är specifik för hot i händelsehistoriken.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1119">Felkod: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="a66ec-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1120">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1120">Message</span></span></td>
<td><span data-ttu-id="a66ec-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1122">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1123">Det här felet anger att borttagning inuti behållartypen kanske inte stöds.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1124">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1124">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1125">Microsoft Defender Antivirus kan inte åtgärda hot som upptäckts i arkivet.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="a66ec-1126">Överväg att manuellt ta bort identifierade resurser.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1127">Felkod: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="a66ec-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1128">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1128">Message</span></span></td>
<td><span data-ttu-id="a66ec-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1130">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1131">Det här felet anger att borttagning av små och medelstora hot kan inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1132">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1132">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1133">Kontrollera de identifierade hoten och lös dem efter behov.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1134">Felkod: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="a66ec-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1135">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1135">Message</span></span></td>
<td><span data-ttu-id="a66ec-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1137">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1138">Det här felet anger att en ny sökning av hot krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1139">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1139">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1140">Kör en fullständig systemsökning.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1141">Felkod: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="a66ec-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1142">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1142">Message</span></span></td>
<td><span data-ttu-id="a66ec-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="a66ec-1144">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1145">Det här felet anger att en offlinesökning krävs.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1146">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1146">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1147">Kör Microsoft Defender Antivirus offline.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="a66ec-1148">Du kan läsa om hur du gör detta i artikeln <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Microsoft Defender Antivirus offline.</a></span><span class="sxs-lookup"><span data-stu-id="a66ec-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="a66ec-1149">Felkod: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="a66ec-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="a66ec-1150">Meddelande</span><span class="sxs-lookup"><span data-stu-id="a66ec-1150">Message</span></span></td>
<td><span data-ttu-id="a66ec-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="a66ec-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="a66ec-1152">Möjlig orsak</span><span class="sxs-lookup"><span data-stu-id="a66ec-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="a66ec-1153">Det här felet anger att Microsoft Defender Antivirus inte stöder den aktuella versionen av plattformen och kräver en ny version av plattformen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="a66ec-1154">Lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1154">Resolution</span></span></td><td>
<span data-ttu-id="a66ec-1155">Du kan bara använda Microsoft Defender Antivirus i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="a66ec-1156">För Windows 8, Windows 7 och Windows Vista kan du använda <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection.</a></span><span class="sxs-lookup"><span data-stu-id="a66ec-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="a66ec-1157">

<a id="internal-error-codes"></a> Följande felkoder används vid intern testning av Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="a66ec-1158">Om du ser de här felen kan du försöka uppdatera [definitioner och](manage-updates-baselines-microsoft-defender-antivirus.md) tvinga fram en ny sökning direkt på slutpunkten.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="a66ec-1159">Interna felkoder</span><span class="sxs-lookup"><span data-stu-id="a66ec-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="a66ec-1160"><b>Felkod</b></span><span class="sxs-lookup"><span data-stu-id="a66ec-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="a66ec-1161">Meddelande som visas</span><span class="sxs-lookup"><span data-stu-id="a66ec-1161">Message displayed</span></span></th>
<th><span data-ttu-id="a66ec-1162">Möjlig orsak till fel och lösning</span><span class="sxs-lookup"><span data-stu-id="a66ec-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="a66ec-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="a66ec-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-1165">Kontrollera internetanslutningen och kör sedan sökningen igen.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="a66ec-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="a66ec-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="a66ec-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="a66ec-1168">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1168">This is an internal error.</span></span> <span data-ttu-id="a66ec-1169">Orsaken är inte tydligt definierad.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="a66ec-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="a66ec-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="a66ec-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="a66ec-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="a66ec-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="a66ec-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="a66ec-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="a66ec-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="a66ec-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="a66ec-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="a66ec-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="a66ec-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="a66ec-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="a66ec-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="a66ec-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="a66ec-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="a66ec-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="a66ec-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="a66ec-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="a66ec-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="a66ec-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="a66ec-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="a66ec-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="a66ec-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="a66ec-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="a66ec-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="a66ec-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="a66ec-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="a66ec-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="a66ec-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="a66ec-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="a66ec-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="a66ec-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="a66ec-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="a66ec-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="a66ec-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="a66ec-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="a66ec-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="a66ec-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="a66ec-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="a66ec-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="a66ec-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="a66ec-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="a66ec-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="a66ec-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="a66ec-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="a66ec-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="a66ec-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="a66ec-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="a66ec-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="a66ec-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="a66ec-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="a66ec-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="a66ec-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="a66ec-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="a66ec-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="a66ec-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="a66ec-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="a66ec-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="a66ec-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="a66ec-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="a66ec-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="a66ec-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="a66ec-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="a66ec-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="a66ec-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="a66ec-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="a66ec-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-1238">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1238">This is an internal error.</span></span> <span data-ttu-id="a66ec-1239">Det kan utlösas när borttagning av skadlig programvara inte lyckas.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="a66ec-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="a66ec-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="a66ec-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="a66ec-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="a66ec-1242">Det här är ett internt fel.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1242">This is an internal error.</span></span> <span data-ttu-id="a66ec-1243">Det kan ha utlösts när en genomsökning inte kunde slutföras.</span><span class="sxs-lookup"><span data-stu-id="a66ec-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="a66ec-1244">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a66ec-1244">Related topics</span></span>

- [<span data-ttu-id="a66ec-1245">Rapport om antivirusskyddet i Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a66ec-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="a66ec-1246">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="a66ec-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)