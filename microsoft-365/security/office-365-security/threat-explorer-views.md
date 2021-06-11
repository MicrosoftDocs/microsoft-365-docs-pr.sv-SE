---
title: Vyer i Hotutforskaren och identifiering i realtid
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
description: Lär dig mer om hur du använder Threat Explorer och rapporten om identifiering i realtid för att undersöka och hantera hot i säkerhets- & efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78c03b45063f4bc34b47ab003bcf00d2befab886
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207332"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="0f459-103">Vyer i Hotutforskaren och identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="0f459-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0f459-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="0f459-104">**Applies to**</span></span>
- [<span data-ttu-id="0f459-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="0f459-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0f459-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f459-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="0f459-108">[Threat Explorer](threat-explorer.md) (och rapporten om identifieringar i realtid) är ett kraftfullt, när realtidsverktyg som hjälper grupper i säkerhetsåtgärder att undersöka och reagera på hot i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="0f459-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="0f459-109">Utforskaren (och rapporten om identifieringar i realtid) visar information om misstänkt skadlig kod och nätsegeni i e-post och filer i Office 365, liksom andra säkerhetshot och risker för organisationen.</span><span class="sxs-lookup"><span data-stu-id="0f459-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="0f459-110">Om du har [Microsoft Defender Office 365](defender-for-office-365.md) abonnemang 2 har du Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="0f459-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="0f459-111">Om du har Microsoft Defender Office 365 abonnemang 1 kan du göra identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="0f459-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="0f459-112">När du först öppnar Utforskaren (eller rapporten över identifieringar i realtid) visar standardvyn identifieringar av skadlig kod för e-post under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="0f459-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="0f459-113">Den här rapporten kan också visa Microsoft Defender för Office 365 identifieringar, till exempel skadliga URL-adresser som identifieras av [Valv-länkar](safe-links.md)och skadliga filer som identifieras [av Valv bifogade filer.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="0f459-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="0f459-114">Den här rapporten kan ändras så att den visar data för de senaste 30 dagarna (med en Microsoft Defender för Office 365 P2-betald prenumeration).</span><span class="sxs-lookup"><span data-stu-id="0f459-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="0f459-115">Utvärderingsprenumerationer kommer endast att innehålla data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="0f459-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="0f459-116">Prenumeration</span><span class="sxs-lookup"><span data-stu-id="0f459-116">Subscription</span></span>|<span data-ttu-id="0f459-117">Utility</span><span class="sxs-lookup"><span data-stu-id="0f459-117">Utility</span></span>|<span data-ttu-id="0f459-118">Datadagar</span><span class="sxs-lookup"><span data-stu-id="0f459-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="0f459-119">Utvärderingsversion av Microsoft Defender Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="0f459-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="0f459-120">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="0f459-120">Real-time detections</span></span>|<span data-ttu-id="0f459-121">7</span><span class="sxs-lookup"><span data-stu-id="0f459-121">7</span></span>|
|<span data-ttu-id="0f459-122">Microsoft Defender för Office 365 P1 betalad</span><span class="sxs-lookup"><span data-stu-id="0f459-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="0f459-123">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="0f459-123">Real-time detections</span></span>|<span data-ttu-id="0f459-124">30</span><span class="sxs-lookup"><span data-stu-id="0f459-124">30</span></span>|
|<span data-ttu-id="0f459-125">Betalda tester av Defender Office 365 P1 för utvärderingsversion av Microsoft Defender Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="0f459-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="0f459-126">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="0f459-126">Threat Explorer</span></span>|<span data-ttu-id="0f459-127">7</span><span class="sxs-lookup"><span data-stu-id="0f459-127">7</span></span>|
|<span data-ttu-id="0f459-128">Utvärderingsversion av Microsoft Defender Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="0f459-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="0f459-129">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="0f459-129">Threat Explorer</span></span>|<span data-ttu-id="0f459-130">7</span><span class="sxs-lookup"><span data-stu-id="0f459-130">7</span></span>|
|<span data-ttu-id="0f459-131">Microsoft Defender för Office 365 P2 betalad</span><span class="sxs-lookup"><span data-stu-id="0f459-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="0f459-132">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="0f459-132">Threat Explorer</span></span>|<span data-ttu-id="0f459-133">30</span><span class="sxs-lookup"><span data-stu-id="0f459-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="0f459-134">Vi kommer snart att utöka datalagrings- och sökgränsen för databevarande i Utforskaren (och realtidsidentifiering) för utvärderingsklienter från 7 till 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="0f459-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="0f459-135">Den här ändringen spåras som en del av översiktsobjektet no. 70544 och håller för närvarande på att distribueras.</span><span class="sxs-lookup"><span data-stu-id="0f459-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="0f459-136">Använd **Visa-menyn** för att ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="0f459-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="0f459-137">Verktygstips hjälper dig att avgöra vilken vy du ska använda.</span><span class="sxs-lookup"><span data-stu-id="0f459-137">Tooltips help you determine which view to use.</span></span>

![Menyn För att visa hot i Utforskaren](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="0f459-139">När du har valt en vy kan du använda filter och konfigurera frågor för vidare analys.</span><span class="sxs-lookup"><span data-stu-id="0f459-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="0f459-140">I följande avsnitt ges en kort översikt över de olika vyerna som är tillgängliga i Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="0f459-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="0f459-141">E-> skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="0f459-141">Email > Malware</span></span>

<span data-ttu-id="0f459-142">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig programvara** för \> **e-post.** \> </span><span class="sxs-lookup"><span data-stu-id="0f459-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="0f459-143">I den här vyn visas information om e-postmeddelanden som identifierats som innehåller skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="0f459-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Visa data om e-post som identifieras som skadlig programvara](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="0f459-145">Klicka **på Avsändare** så att listan med visningsalternativ öppnas.</span><span class="sxs-lookup"><span data-stu-id="0f459-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="0f459-146">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, ämne, identifieringsteknik, skyddsstatus med mera.</span><span class="sxs-lookup"><span data-stu-id="0f459-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="0f459-147">Om du till exempel vill se vilka åtgärder som har vidtagits för identifierade e-postmeddelanden väljer du **Skyddsstatus** i listan.</span><span class="sxs-lookup"><span data-stu-id="0f459-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="0f459-148">Välj ett alternativ och klicka sedan på knappen Uppdatera för att använda filtret i rapporten.</span><span class="sxs-lookup"><span data-stu-id="0f459-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Alternativ för status för skydd mot hot i Utforskaren](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="0f459-150">Under diagrammet kan du visa mer information om specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="0f459-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="0f459-151">När du markerar ett objekt i listan öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="0f459-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Hotutforskaren med öppnad utfällning](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="0f459-153">E-> Phish</span><span class="sxs-lookup"><span data-stu-id="0f459-153">Email > Phish</span></span>

<span data-ttu-id="0f459-154">Om du vill visa den här rapporten i Utforskaren (eller identifieringar i realtid) väljer du **Visa** \> **e-post** \> **phish**.</span><span class="sxs-lookup"><span data-stu-id="0f459-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="0f459-155">I den här vyn visas e-postmeddelanden som identifieras som nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="0f459-155">This view shows email messages identified as phishing attempts.</span></span>

![Visa data om e-post som identifierats som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="0f459-157">Klicka **på Avsändare** så att listan med visningsalternativ öppnas.</span><span class="sxs-lookup"><span data-stu-id="0f459-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="0f459-158">Använd den här listan för att visa data efter avsändare, mottagare, avsändardomän, avsändar-IP, URL-domän, klicka på bedömning med mera.</span><span class="sxs-lookup"><span data-stu-id="0f459-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="0f459-159">Om du till exempel vill se vilka åtgärder som har vidtagits när  personer klickade på URL-adresser som identifierats som nätfiskeförsök väljer du Klicka på bedömning i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="0f459-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka på alternativ för bedömning av phish-rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="0f459-161">Under diagrammet kan du visa mer information om specifika meddelanden, URL-klick, URL:er och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="0f459-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL:er som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="0f459-163">När du markerar ett objekt i listan, till exempel en URL som identifierats, öppnas ett utfällt fönster där du kan läsa mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="0f459-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Information om en upptäckt URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="0f459-165">Skicka e> postinskick</span><span class="sxs-lookup"><span data-stu-id="0f459-165">Email > Submissions</span></span>

<span data-ttu-id="0f459-166">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa e-postinskick.** \>  \> </span><span class="sxs-lookup"><span data-stu-id="0f459-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="0f459-167">I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0f459-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="0f459-169">Klicka **på Avsändare** så att listan med visningsalternativ öppnas.</span><span class="sxs-lookup"><span data-stu-id="0f459-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="0f459-170">Använd den här listan för att visa information efter avsändare, mottagare, rapporttyp (användarens avgörande om e-postmeddelandet var skräppost, inte skräppost eller nätt syfte) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="0f459-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="0f459-171">Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Avsändarrapporttyp , väljer  Phish och klickar \> sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="0f459-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Valt phish för Filtret Rapporttyp](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="0f459-173">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, avsändarens IP-adress, användaren som rapporterade meddelandet som skräppost, inte skräppost eller nätt syfte med mera.</span><span class="sxs-lookup"><span data-stu-id="0f459-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Meddelanden som har rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="0f459-175">Markera ett objekt i listan om du vill visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="0f459-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="0f459-176">E-> all e-post</span><span class="sxs-lookup"><span data-stu-id="0f459-176">Email > All email</span></span>

<span data-ttu-id="0f459-177">Om du vill visa den här rapporten väljer du Visa e-post **alla** \> **e-postmeddelanden** \> **i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="0f459-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="0f459-178">I de här vyerna visas en vy över all e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).</span><span class="sxs-lookup"><span data-stu-id="0f459-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="0f459-179">Om du får ett felmeddelande där det står **För mycket data** för att visas lägger du till ett filter och, om det behövs, begränsa det datumintervall du visar.</span><span class="sxs-lookup"><span data-stu-id="0f459-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="0f459-180">Om du vill använda ett filter **väljer du Avsändare**, markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="0f459-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="0f459-181">I exemplet använde vi **Identifieringsteknik som** ett filter (det finns flera tillgängliga alternativ).</span><span class="sxs-lookup"><span data-stu-id="0f459-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="0f459-182">Visa information efter avsändare, avsändares domän, mottagare, ämne, filnamn på bifogad fil, skadlig kodfamilj, skyddsstatus (åtgärder som vidtas av dina skyddsfunktioner och principer i Office 365), identifieringsteknik (hur den skadlig programvara upptäcktes) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="0f459-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="0f459-184">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesraden, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0f459-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="0f459-185">Innehålls > skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="0f459-185">Content > Malware</span></span>

<span data-ttu-id="0f459-186">Om du vill visa den här rapporten i Utforskaren (eller identifiering i realtid) väljer du **Visa skadlig** \> **programvara för** \> **innehåll.**</span><span class="sxs-lookup"><span data-stu-id="0f459-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="0f459-187">I den här vyn visas filer som identifierats som skadliga av Microsoft Defender för Office 365 i [SharePoint Online, OneDrive för företag och Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0f459-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0f459-188">Visa information efter programfamilj, identifieringsteknik (hur den skadlig programvara upptäcktes) och arbetsbelastningen (OneDrive, SharePoint eller Teams).</span><span class="sxs-lookup"><span data-stu-id="0f459-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Visa data om upptäckt skadlig programvara](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="0f459-190">Under diagrammet kan du visa mer information om specifika filer, till exempel filnamn på bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="0f459-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="0f459-191">Klicka-och-filtrera-funktioner</span><span class="sxs-lookup"><span data-stu-id="0f459-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="0f459-192">Med Utforskaren (och identifieringar i realtid) kan du använda ett filter med ett klick.</span><span class="sxs-lookup"><span data-stu-id="0f459-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="0f459-193">Klicka på ett objekt i förklaringen så blir objektet ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="0f459-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="0f459-194">Anta till exempel att vi tittar på vyn Skadlig programvara i Utforskaren:</span><span class="sxs-lookup"><span data-stu-id="0f459-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Gå till Utforskaren för hantering av \> hot](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="0f459-196">Om **du klickar på ATP-detonation** i det här diagrammet visas en vy som ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="0f459-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Utforskaren filtrerad för att endast visa Defender för Office 365 detonationsresultat](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="0f459-198">I den här vyn tittar vi nu på data för filer som detonerades av Valv [Bifogade filer](safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="0f459-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="0f459-199">Under diagrammet kan du se information om specifika e-postmeddelanden som har bifogade filer som upptäckts av Valv bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="0f459-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifik information om e-postmeddelanden med identifierade bifogade filer](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="0f459-201">Om du markerar ett eller flera objekt aktiveras **menyn** Åtgärder, där du kan välja mellan flera markerade objekt.</span><span class="sxs-lookup"><span data-stu-id="0f459-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![När du markerar ett objekt aktiveras menyn Åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="0f459-203">Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid när du undersöker hot.</span><span class="sxs-lookup"><span data-stu-id="0f459-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="0f459-204">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="0f459-204">Queries and filters</span></span>

<span data-ttu-id="0f459-205">Utforskaren (liksom rapporten över identifieringar i realtid) har flera kraftfulla filter- och frågefunktioner som gör att du kan öka detaljinformationen, till exempel de mest riktade användarna, de främsta familjerna med skadlig programvara, identifieringsteknik med mera.</span><span class="sxs-lookup"><span data-stu-id="0f459-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="0f459-206">Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="0f459-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f459-207">Använd inte jokertecken, till exempel asterisk eller frågetecken, i frågefältet för Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="0f459-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="0f459-208">När du söker i **ämnesfältet** efter e-postmeddelanden utför Utforskaren (eller identifieringar i realtid) delvis matchning och ger resultat som liknar en sökning med jokertecken.</span><span class="sxs-lookup"><span data-stu-id="0f459-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
