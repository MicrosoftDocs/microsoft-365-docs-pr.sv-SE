---
title: Vyer i Hotutforskaren och identifieringar i realtid
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
description: Lär dig hur du använder Threat Explorer och rapporten om identifieringar i realtid för att undersöka och hantera hot i Säkerhets- & Efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406486"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="9c13e-103">Vyer i Hotutforskaren och identifieringar i realtid</span><span class="sxs-lookup"><span data-stu-id="9c13e-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9c13e-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9c13e-104">**Applies to**</span></span>
- [<span data-ttu-id="9c13e-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9c13e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9c13e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c13e-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="9c13e-108">[Threat Explorer](threat-explorer.md) (och rapporten om identifiering i realtid) är ett kraftfullt verktyg i närheten av realtid som hjälper grupper i säkerhetsoperationer att undersöka och reagera på hot i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="9c13e-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="9c13e-109">Utforskaren (och rapporten om identifiering i realtid) visar information om misstänkt skadlig programvara och phish i e-post och filer i Office 365, samt andra säkerhetshot och risker för din organisation.</span><span class="sxs-lookup"><span data-stu-id="9c13e-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="9c13e-110">Om du har [Microsoft Defender för Office 365](office-365-atp.md) abonnemang 2 har du Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="9c13e-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="9c13e-111">Om du har Microsoft Defender för Office 365 abonnemang 1 kan du göra identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="9c13e-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="9c13e-112">När du först öppnar Utforskaren (eller rapporten över identifieringar i realtid) visar standardvyn identifiering av skadlig kod för e-post under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="9c13e-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="9c13e-113">Den här rapporten kan också visa identifieringar av Microsoft Defender för Office [](atp-safe-links.md)365, till exempel skadliga URL-adresser som identifieras av säkra länkar och skadliga filer som identifieras av [säkra bifogade filer.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9c13e-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="9c13e-114">Den här rapporten kan ändras så att den visar data för de senaste 30 dagarna (med en betalprenumeration på Microsoft Defender för Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="9c13e-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="9c13e-115">Utvärderingsprenumerationer innehåller endast data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="9c13e-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="9c13e-116">Prenumeration</span><span class="sxs-lookup"><span data-stu-id="9c13e-116">Subscription</span></span>|<span data-ttu-id="9c13e-117">Verktyg</span><span class="sxs-lookup"><span data-stu-id="9c13e-117">Utility</span></span>|<span data-ttu-id="9c13e-118">Dagar med data</span><span class="sxs-lookup"><span data-stu-id="9c13e-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="9c13e-119">Utvärderingsversion av Microsoft Defender för Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="9c13e-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="9c13e-120">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="9c13e-120">Real-time detections</span></span>|<span data-ttu-id="9c13e-121">7</span><span class="sxs-lookup"><span data-stu-id="9c13e-121">7</span></span>|
|<span data-ttu-id="9c13e-122">Microsoft Defender för Office 365 P1 betalad</span><span class="sxs-lookup"><span data-stu-id="9c13e-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="9c13e-123">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="9c13e-123">Real-time detections</span></span>|<span data-ttu-id="9c13e-124">30</span><span class="sxs-lookup"><span data-stu-id="9c13e-124">30</span></span>|
|<span data-ttu-id="9c13e-125">Utvärderingsversion av Microsoft Defender för Office 365 P1-betaltestning av Defender för Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="9c13e-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="9c13e-126">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="9c13e-126">Threat Explorer</span></span>|<span data-ttu-id="9c13e-127">7</span><span class="sxs-lookup"><span data-stu-id="9c13e-127">7</span></span>|
|<span data-ttu-id="9c13e-128">Utvärderingsversion av Microsoft Defender för Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="9c13e-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="9c13e-129">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="9c13e-129">Threat Explorer</span></span>|<span data-ttu-id="9c13e-130">7</span><span class="sxs-lookup"><span data-stu-id="9c13e-130">7</span></span>|
|<span data-ttu-id="9c13e-131">Microsoft Defender för Office 365 P2 betalad</span><span class="sxs-lookup"><span data-stu-id="9c13e-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="9c13e-132">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="9c13e-132">Threat Explorer</span></span>|<span data-ttu-id="9c13e-133">30</span><span class="sxs-lookup"><span data-stu-id="9c13e-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="9c13e-134">Vi kommer snart att utöka datalagrings- och sökbegränsningen i Utforskaren (och realtidsidentifiering) för utvärderingsklienter från 7 till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="9c13e-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="9c13e-135">Den här ändringen spåras som en del av översiktsobjektet no. 70544 och håller på att distribueras.</span><span class="sxs-lookup"><span data-stu-id="9c13e-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="9c13e-136">Använd **Visa-menyn** om du vill ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="9c13e-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="9c13e-137">Verktygstips hjälper dig att avgöra vilken vy du ska använda.</span><span class="sxs-lookup"><span data-stu-id="9c13e-137">Tooltips help you determine which view to use.</span></span>

![Menyn Visa hotutforskaren](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="9c13e-139">När du har valt en vy kan du använda filter och konfigurera frågor för ytterligare analys.</span><span class="sxs-lookup"><span data-stu-id="9c13e-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="9c13e-140">Följande avsnitt innehåller en kort översikt över de olika vyerna som är tillgängliga i Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="9c13e-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="9c13e-141">E-> skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="9c13e-141">Email > Malware</span></span>

<span data-ttu-id="9c13e-142">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig programvara** för \> **e-post.** \> </span><span class="sxs-lookup"><span data-stu-id="9c13e-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="9c13e-143">I den här vyn visas information om e-postmeddelanden som identifierats som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="9c13e-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Visa data om e-post som identifieras som skadlig programvara](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="9c13e-145">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="9c13e-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9c13e-146">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, ämne, identifieringsteknik, skyddsstatus med mera.</span><span class="sxs-lookup"><span data-stu-id="9c13e-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="9c13e-147">Om du till exempel vill se vilka åtgärder som har vidtas på identifierade e-postmeddelanden väljer du **Skydd-status** i listan.</span><span class="sxs-lookup"><span data-stu-id="9c13e-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="9c13e-148">Välj ett alternativ och klicka sedan på knappen Uppdatera om du vill använda filtret i rapporten.</span><span class="sxs-lookup"><span data-stu-id="9c13e-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Alternativ för status för skydd mot hot i Utforskaren](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="9c13e-150">Under diagrammet kan du visa mer information om specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="9c13e-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="9c13e-151">När du markerar ett objekt i listan öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="9c13e-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Hotutforskaren med öppnad flygblad](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="9c13e-153">E-> Phish</span><span class="sxs-lookup"><span data-stu-id="9c13e-153">Email > Phish</span></span>

<span data-ttu-id="9c13e-154">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa** \>  \> **e-post phish.**</span><span class="sxs-lookup"><span data-stu-id="9c13e-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="9c13e-155">I den här vyn visas e-postmeddelanden som identifieras som nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="9c13e-155">This view shows email messages identified as phishing attempts.</span></span>

![Visa data om e-post som identifieras som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="9c13e-157">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="9c13e-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9c13e-158">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, avsändar-IP, URL-domän, klicka på bedömningsvyn och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="9c13e-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="9c13e-159">Om du till exempel vill se vilka åtgärder som har gjorts när  personer klickade på URL-adresser som identifierades som nätfiskeförsök väljer du Klicka på bedömning i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="9c13e-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka på alternativ för bedömning av phish-rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="9c13e-161">Under diagrammet kan du visa mer information om specifika meddelanden, URL-klick, URL-adresser och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="9c13e-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL:er som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="9c13e-163">När du markerar ett objekt i listan, till exempel en URL som identifierats, öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="9c13e-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Information om en upptäckt URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="9c13e-165">E-> inskickade meddelanden</span><span class="sxs-lookup"><span data-stu-id="9c13e-165">Email > Submissions</span></span>

<span data-ttu-id="9c13e-166">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa** \>  \> **e-postinskick.**</span><span class="sxs-lookup"><span data-stu-id="9c13e-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="9c13e-167">I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="9c13e-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="9c13e-169">Klicka **på Avsändaren** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="9c13e-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="9c13e-170">Använd den här listan för att visa information efter avsändare, mottagare, rapporttyp (användarens avgörande om e-postmeddelandet var skräppost, inte skräppost eller phish) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="9c13e-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="9c13e-171">Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Avsändarrapporttyp, väljer  Phish och klickar sedan \> på knappen Uppdatera. </span><span class="sxs-lookup"><span data-stu-id="9c13e-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish valt för Rapporttypfilter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="9c13e-173">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, avsändarens IP-adress, användaren som rapporterat meddelandet som skräppost, inte skräppost eller phish med mera.</span><span class="sxs-lookup"><span data-stu-id="9c13e-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Meddelanden som rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="9c13e-175">Markera ett objekt i listan om du vill visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="9c13e-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="9c13e-176">E-> all e-post</span><span class="sxs-lookup"><span data-stu-id="9c13e-176">Email > All email</span></span>

<span data-ttu-id="9c13e-177">Om du vill visa den här rapporten väljer du Visa **e-post** för all \> **e-post** \> **i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="9c13e-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="9c13e-178">I de här vyerna visas en vy över e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).</span><span class="sxs-lookup"><span data-stu-id="9c13e-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="9c13e-179">Om du får ett felmeddelande där det står För mycket **data** kan du lägga till ett filter och, om det behövs, begränsa det datumintervall som du visar.</span><span class="sxs-lookup"><span data-stu-id="9c13e-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="9c13e-180">Om du vill använda ett filter **väljer** du Avsändare, markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="9c13e-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="9c13e-181">I exemplet använde vi **identifieringsteknik som** ett filter (det finns flera tillgängliga alternativ).</span><span class="sxs-lookup"><span data-stu-id="9c13e-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="9c13e-182">Visa information efter avsändare, avsändarens domän, mottagare, ämne, filnamn på bifogad fil, skadlig programvara, skyddsstatus (åtgärder som vidtas av dina skyddsfunktioner och principer i Office 365), identifieringsteknik (hur skadlig programvara identifierades) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="9c13e-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="9c13e-184">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="9c13e-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="9c13e-185">Innehållskod > skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="9c13e-185">Content > Malware</span></span>

<span data-ttu-id="9c13e-186">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer **du Visa skadlig** programvara \> **för** \> **innehåll.**</span><span class="sxs-lookup"><span data-stu-id="9c13e-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="9c13e-187">I den här vyn visas filer som identifierats som skadliga av Microsoft Defender för [Office 365 i SharePoint Online, OneDrive för företag och Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="9c13e-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="9c13e-188">Visa information efter programfamilj, identifieringsteknik (hur skadlig programvara upptäcktes) och arbetsbelastningen (OneDrive, SharePoint eller Teams).</span><span class="sxs-lookup"><span data-stu-id="9c13e-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Visa data om upptäckt skadlig programvara](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="9c13e-190">Under diagrammet kan du visa mer information om specifika filer, till exempel filnamn på bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="9c13e-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="9c13e-191">Funktioner för Klicka-och-filtrera</span><span class="sxs-lookup"><span data-stu-id="9c13e-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="9c13e-192">Med Utforskaren (och identifieringar i realtid) kan du använda ett filter med ett klick.</span><span class="sxs-lookup"><span data-stu-id="9c13e-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="9c13e-193">Om du klickar på ett objekt i förklaringen blir objektet ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="9c13e-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="9c13e-194">Anta till exempel att vi tittar på vyn Skadlig programvara i Utforskaren:</span><span class="sxs-lookup"><span data-stu-id="9c13e-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Gå till \> Hothanteringsutforskaren](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="9c13e-196">Om **du klickar på ATP-detonation** i det här diagrammet visas en vy som ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="9c13e-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Utforskaren filtrerad för att endast visa Defender för Detonation-resultat för Office 365](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="9c13e-198">I den här vyn tittar vi nu på data för filer som detonerade av [säkra bifogade filer.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="9c13e-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="9c13e-199">Under diagrammet kan vi se information om specifika e-postmeddelanden som hade bifogade filer som identifierats av säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="9c13e-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifik information om e-postmeddelanden med identifierade bifogade filer](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="9c13e-201">Om du markerar ett eller flera objekt aktiveras **menyn** Åtgärder, där det finns flera alternativ att välja bland för de markerade objekten.</span><span class="sxs-lookup"><span data-stu-id="9c13e-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Om du markerar ett objekt aktiveras åtgärdsmenyn](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="9c13e-203">Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid vid undersökning av hot.</span><span class="sxs-lookup"><span data-stu-id="9c13e-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="9c13e-204">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="9c13e-204">Queries and filters</span></span>

<span data-ttu-id="9c13e-205">Utforskaren (liksom rapporten över identifieringar i realtid) har flera kraftfulla filter- och frågefunktioner som gör att du kan öka detaljgranskningen, till exempel de mest riktade användarna, de mest populära programfamiljerna, identifieringsteknik med mera.</span><span class="sxs-lookup"><span data-stu-id="9c13e-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="9c13e-206">Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="9c13e-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c13e-207">Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i frågefältet för Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="9c13e-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="9c13e-208">När du söker i **ämnesfältet** efter e-postmeddelanden utför Utforskaren (eller identifieringar i realtid) delvis matchning och ger resultat som liknar en sökning med jokertecken.</span><span class="sxs-lookup"><span data-stu-id="9c13e-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
