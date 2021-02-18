---
title: Vyer i HotUtforskaren och identifieringar i realtid
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Läs mer om hur du använder Hotutforskaren och rapporten om identifiering i realtid för att undersöka och hantera hot i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: aef3f7fe69e5cbd1d70b7aee3284f0c5dc6416df
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290291"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="036e3-103">Vyer i HotUtforskaren och identifieringar i realtid</span><span class="sxs-lookup"><span data-stu-id="036e3-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="036e3-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="036e3-104">**Applies to**</span></span>
- [<span data-ttu-id="036e3-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="036e3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="036e3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="036e3-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="036e3-108">[Threat Explorer](threat-explorer.md) (och rapporten om identifiering i realtid) är ett kraftfullt verktyg i närheten av realtid som hjälper grupper i säkerhetsoperationer att undersöka och reagera på hot i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="036e3-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="036e3-109">Utforskaren (och rapporten om identifieringar i realtid) visar information om misstänkt skadlig programvara och phish i e-post och filer i Office 365, samt andra säkerhetshot och risker för din organisation.</span><span class="sxs-lookup"><span data-stu-id="036e3-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="036e3-110">Om du har [Microsoft Defender för Office 365](office-365-atp.md) abonnemang 2 har du Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="036e3-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="036e3-111">Om du har Microsoft Defender för Office 365 abonnemang 1 kan du göra identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="036e3-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="036e3-112">När du först öppnar Utforskaren (eller rapporten över identifieringar i realtid) visar standardvyn identifiering av skadlig kod för e-post under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="036e3-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="036e3-113">Den här rapporten kan också visa identifieringar av Microsoft Defender för Office [](atp-safe-links.md)365, till exempel skadliga URL-adresser som identifieras av säkra länkar och skadliga filer som identifieras av [säkra bifogade filer.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="036e3-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="036e3-114">Den här rapporten kan ändras så att den visar data för de senaste 30 dagarna (med en betalprenumeration på Microsoft Defender för Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="036e3-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="036e3-115">Utvärderingsprenumerationer innehåller endast data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="036e3-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="036e3-116">Prenumeration</span><span class="sxs-lookup"><span data-stu-id="036e3-116">Subscription</span></span>|<span data-ttu-id="036e3-117">Verktyg</span><span class="sxs-lookup"><span data-stu-id="036e3-117">Utility</span></span>|<span data-ttu-id="036e3-118">Dagar med data</span><span class="sxs-lookup"><span data-stu-id="036e3-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="036e3-119">Utvärderingsversion av Microsoft Defender för Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="036e3-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="036e3-120">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="036e3-120">Real-time detections</span></span>|<span data-ttu-id="036e3-121">7</span><span class="sxs-lookup"><span data-stu-id="036e3-121">7</span></span>|
|<span data-ttu-id="036e3-122">Microsoft Defender för Office 365 P1 betalad</span><span class="sxs-lookup"><span data-stu-id="036e3-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="036e3-123">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="036e3-123">Real-time detections</span></span>|<span data-ttu-id="036e3-124">30</span><span class="sxs-lookup"><span data-stu-id="036e3-124">30</span></span>|
|<span data-ttu-id="036e3-125">Betaltestning av Microsoft Defender för Office 365 P1 för Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="036e3-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="036e3-126">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="036e3-126">Threat Explorer</span></span>|<span data-ttu-id="036e3-127">7</span><span class="sxs-lookup"><span data-stu-id="036e3-127">7</span></span>|
|<span data-ttu-id="036e3-128">Utvärderingsversion av Microsoft Defender för Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="036e3-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="036e3-129">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="036e3-129">Threat Explorer</span></span>|<span data-ttu-id="036e3-130">7</span><span class="sxs-lookup"><span data-stu-id="036e3-130">7</span></span>|
|<span data-ttu-id="036e3-131">Microsoft Defender för Office 365 P2 betalad</span><span class="sxs-lookup"><span data-stu-id="036e3-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="036e3-132">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="036e3-132">Threat Explorer</span></span>|<span data-ttu-id="036e3-133">30</span><span class="sxs-lookup"><span data-stu-id="036e3-133">30</span></span>|
|

<span data-ttu-id="036e3-134">Använd **Visa-menyn** om du vill ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="036e3-134">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="036e3-135">Verktygstips hjälper dig att avgöra vilken vy du ska använda.</span><span class="sxs-lookup"><span data-stu-id="036e3-135">Tooltips help you determine which view to use.</span></span>

![Menyn Visa hotutforskaren](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="036e3-137">När du har valt en vy kan du använda filter och konfigurera frågor för ytterligare analys.</span><span class="sxs-lookup"><span data-stu-id="036e3-137">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="036e3-138">Följande avsnitt innehåller en kort översikt över de olika vyerna som är tillgängliga i Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="036e3-138">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="036e3-139">E-> skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="036e3-139">Email > Malware</span></span>

<span data-ttu-id="036e3-140">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig programvara** för \> **e-post.** \> </span><span class="sxs-lookup"><span data-stu-id="036e3-140">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="036e3-141">I den här vyn visas information om e-postmeddelanden som identifierats som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="036e3-141">This view shows information about email messages that were identified as containing malware.</span></span>

![Visa data om e-post som identifieras som skadlig programvara](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="036e3-143">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="036e3-143">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="036e3-144">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, ämne, identifieringsteknik, skyddsstatus med mera.</span><span class="sxs-lookup"><span data-stu-id="036e3-144">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="036e3-145">Om du till exempel vill se vilka åtgärder som har vidtas på identifierade e-postmeddelanden väljer du **Skydd-status** i listan.</span><span class="sxs-lookup"><span data-stu-id="036e3-145">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="036e3-146">Välj ett alternativ och klicka sedan på knappen Uppdatera om du vill använda filtret i rapporten.</span><span class="sxs-lookup"><span data-stu-id="036e3-146">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Alternativ för status för skydd mot hot i Utforskaren](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="036e3-148">Under diagrammet kan du visa mer information om specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="036e3-148">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="036e3-149">När du markerar ett objekt i listan öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="036e3-149">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Hotutforskaren med öppnad flygblad](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="036e3-151">E-> Phish</span><span class="sxs-lookup"><span data-stu-id="036e3-151">Email > Phish</span></span>

<span data-ttu-id="036e3-152">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa** \>  \> **e-post phish.**</span><span class="sxs-lookup"><span data-stu-id="036e3-152">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="036e3-153">I den här vyn visas e-postmeddelanden som identifieras som nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="036e3-153">This view shows email messages identified as phishing attempts.</span></span>

![Visa data om e-post som identifieras som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="036e3-155">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="036e3-155">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="036e3-156">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, avsändar-IP, URL-domän, klicka på bedömningsvyn och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="036e3-156">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="036e3-157">Om du till exempel vill se vilka åtgärder som har gjorts när  personer klickade på URL-adresser som identifierades som nätfiskeförsök väljer du Klicka på bedömning i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="036e3-157">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka på alternativ för bedömning av phish-rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="036e3-159">Under diagrammet kan du visa mer information om specifika meddelanden, URL-klick, URL-adresser och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="036e3-159">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL:er som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="036e3-161">När du markerar ett objekt i listan, till exempel en URL som identifierats, öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="036e3-161">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Information om en upptäckt URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="036e3-163">E-> inskickade meddelanden</span><span class="sxs-lookup"><span data-stu-id="036e3-163">Email > Submissions</span></span>

<span data-ttu-id="036e3-164">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa** \>  \> **e-postinskick.**</span><span class="sxs-lookup"><span data-stu-id="036e3-164">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="036e3-165">I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="036e3-165">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="036e3-167">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="036e3-167">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="036e3-168">Använd den här listan för att visa information efter avsändare, mottagare, rapporttyp (användarens avgörande om e-postmeddelandet var skräppost, inte skräppost eller phish) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="036e3-168">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="036e3-169">Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Avsändarrapporttyp, väljer  Phish och klickar sedan \> på knappen Uppdatera. </span><span class="sxs-lookup"><span data-stu-id="036e3-169">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish valt för Rapporttypfilter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="036e3-171">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, avsändarens IP-adress, användaren som rapporterat meddelandet som skräppost, inte skräppost eller phish med mera.</span><span class="sxs-lookup"><span data-stu-id="036e3-171">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Meddelanden som rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="036e3-173">Markera ett objekt i listan om du vill visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="036e3-173">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="036e3-174">E-> all e-post</span><span class="sxs-lookup"><span data-stu-id="036e3-174">Email > All email</span></span>

<span data-ttu-id="036e3-175">Om du vill visa den här rapporten väljer du Visa **e-post** för all \> **e-post i** \> **Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="036e3-175">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="036e3-176">I de här vyerna visas en vy över e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).</span><span class="sxs-lookup"><span data-stu-id="036e3-176">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="036e3-177">Om du får ett felmeddelande där det står För mycket **data** kan du lägga till ett filter och, om det behövs, begränsa det datumintervall som du visar.</span><span class="sxs-lookup"><span data-stu-id="036e3-177">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="036e3-178">Om du vill använda ett filter **väljer du Avsändare,** markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="036e3-178">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="036e3-179">I exemplet använde vi **identifieringsteknik som** ett filter (det finns flera tillgängliga alternativ).</span><span class="sxs-lookup"><span data-stu-id="036e3-179">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="036e3-180">Visa information efter avsändare, avsändarens domän, mottagare, ämne, filnamn på bifogad fil, skadlig kodfamilj, skyddsstatus (åtgärder som vidtas av dina skyddsfunktioner och principer i Office 365), identifieringsteknik (hur den skadlig programvara identifierades) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="036e3-180">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="036e3-182">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="036e3-182">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="036e3-183">Innehållskod > skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="036e3-183">Content > Malware</span></span>

<span data-ttu-id="036e3-184">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa skadlig** programvara \> **för** \> **innehåll.**</span><span class="sxs-lookup"><span data-stu-id="036e3-184">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="036e3-185">I den här vyn visas filer som identifierats som skadliga av Microsoft Defender för [Office 365 i SharePoint Online, OneDrive för företag och Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="036e3-185">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="036e3-186">Visa information efter programfamilj, identifieringsteknik (hur skadlig programvara upptäcktes) och arbetsbelastningen (OneDrive, SharePoint eller Teams).</span><span class="sxs-lookup"><span data-stu-id="036e3-186">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Visa data om upptäckt skadlig programvara](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="036e3-188">Under diagrammet kan du visa mer information om specifika filer, till exempel filnamn på bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="036e3-188">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="036e3-189">Funktioner för Klicka-och-filtrera</span><span class="sxs-lookup"><span data-stu-id="036e3-189">Click-to-filter capabilities</span></span>

<span data-ttu-id="036e3-190">Med Utforskaren (och identifieringar i realtid) kan du använda ett filter med ett klick.</span><span class="sxs-lookup"><span data-stu-id="036e3-190">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="036e3-191">Om du klickar på ett objekt i förklaringen blir objektet ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="036e3-191">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="036e3-192">Anta till exempel att vi tittar på vyn Skadlig programvara i Utforskaren:</span><span class="sxs-lookup"><span data-stu-id="036e3-192">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Gå till \> Hothanteringsutforskaren](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="036e3-194">Om **du klickar på ATP-detonation** i det här diagrammet visas en vy som ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="036e3-194">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Utforskaren filtrerad för att endast visa Defender för Detonation-resultat för Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="036e3-196">I den här vyn tittar vi nu på data för filer som detonerade av [säkra bifogade filer.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="036e3-196">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="036e3-197">Under diagrammet kan vi se information om specifika e-postmeddelanden som hade bifogade filer som identifierats av säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="036e3-197">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifik information om e-postmeddelanden med identifierade bifogade filer](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="036e3-199">Om du markerar ett eller flera objekt aktiveras **menyn** Åtgärder, där det finns flera alternativ att välja bland för de markerade objekten.</span><span class="sxs-lookup"><span data-stu-id="036e3-199">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Om du markerar ett objekt aktiveras åtgärdsmenyn](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="036e3-201">Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid vid undersökning av hot.</span><span class="sxs-lookup"><span data-stu-id="036e3-201">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="036e3-202">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="036e3-202">Queries and filters</span></span>

<span data-ttu-id="036e3-203">Utforskaren (liksom rapporten över identifieringar i realtid) har flera kraftfulla filter- och frågefunktioner som gör att du kan öka detalj detaljinformationen, till exempel de mest riktade användarna, de mest populära familjerna av skadlig programvara, identifieringsteknik med mera.</span><span class="sxs-lookup"><span data-stu-id="036e3-203">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="036e3-204">Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="036e3-204">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="036e3-205">Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i frågefältet för Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="036e3-205">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="036e3-206">När du söker i **ämnesfältet** efter e-postmeddelanden utför Utforskaren (eller identifieringar i realtid) delvis matchning och ger resultat som liknar en sökning med jokertecken.</span><span class="sxs-lookup"><span data-stu-id="036e3-206">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
