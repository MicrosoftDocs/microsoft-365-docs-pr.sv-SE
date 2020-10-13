---
title: Vyer i Threat Explorer och identifieringar i real tid
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lär dig hur du använder Threat Explorer och rapporten om identifiering av real tids rapporter för att undersöka och reagera på hot i säkerhets &amp; Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 75286b3fa8319afc9baadbc7ed349e8fe689d11c
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447137"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="329dd-103">Vyer i Threat Explorer och identifieringar i real tid</span><span class="sxs-lookup"><span data-stu-id="329dd-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="329dd-105">[Threat Explorer](threat-explorer.md) (och rapporten om identifiering av real tid) är ett kraftfullt, nära real tids verktyg som hjälper säkerhets åtgärder att undersöka och reagera på hot i säkerhets &amp; Center.</span><span class="sxs-lookup"><span data-stu-id="329dd-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="329dd-106">Utforskaren (och rapporten real tids identifiering) visar information om misstänkt skadlig program vara och Phish i e-post och filer i Office 365 samt andra säkerhetshot och risker för din organisation.</span><span class="sxs-lookup"><span data-stu-id="329dd-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="329dd-107">Om du har [Office 365](office-365-atp.md) -abonnemang för avancerat skydd (ATP) 2 har du Explorer.</span><span class="sxs-lookup"><span data-stu-id="329dd-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="329dd-108">Om du har Office 365 ATP-abonnemang 1 har du real tids identifiering.</span><span class="sxs-lookup"><span data-stu-id="329dd-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="329dd-109">När du först öppnar Utforskaren (eller rapporten real tids identifiering) visas e-postidentifiering av skadlig program vara under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="329dd-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="329dd-110">Den här rapporten kan även Visa identifieringar av ATP, till exempel skadlig URL-adresser som identifieras av [säkra länkar](atp-safe-links.md)och skadliga filer som identifieras av [säkra bifogade](atp-safe-attachments.md)filer.</span><span class="sxs-lookup"><span data-stu-id="329dd-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="329dd-111">Den här rapporten kan ändras för att visa data för de senaste 30 dagarna (med ett ATP-betalat abonnemang).</span><span class="sxs-lookup"><span data-stu-id="329dd-111">This report can be modified to show data for the past 30 days (with an ATP P2 paid subscription).</span></span> <span data-ttu-id="329dd-112">Prov abonnemang kommer endast att omfatta data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="329dd-112">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="329dd-113">Prenumerationsvy</span><span class="sxs-lookup"><span data-stu-id="329dd-113">Subscription</span></span>|<span data-ttu-id="329dd-114">Nytta</span><span class="sxs-lookup"><span data-stu-id="329dd-114">Utility</span></span>|<span data-ttu-id="329dd-115">Dagar med data</span><span class="sxs-lookup"><span data-stu-id="329dd-115">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="329dd-116">ATP-test</span><span class="sxs-lookup"><span data-stu-id="329dd-116">ATP P1 trial</span></span>|<span data-ttu-id="329dd-117">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="329dd-117">Real-time detections</span></span>|<span data-ttu-id="329dd-118">borttagning</span><span class="sxs-lookup"><span data-stu-id="329dd-118">7</span></span>|
|<span data-ttu-id="329dd-119">ATP P1 betalt</span><span class="sxs-lookup"><span data-stu-id="329dd-119">ATP P1 paid</span></span>|<span data-ttu-id="329dd-120">Identifiering i realtid</span><span class="sxs-lookup"><span data-stu-id="329dd-120">Real-time detections</span></span>|<span data-ttu-id="329dd-121">halvtimme</span><span class="sxs-lookup"><span data-stu-id="329dd-121">30</span></span>|
|<span data-ttu-id="329dd-122">ATP P1-betal test för ATP</span><span class="sxs-lookup"><span data-stu-id="329dd-122">ATP P1 paid testing ATP P2 trial</span></span>|<span data-ttu-id="329dd-123">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="329dd-123">Threat Explorer</span></span>|<span data-ttu-id="329dd-124">borttagning</span><span class="sxs-lookup"><span data-stu-id="329dd-124">7</span></span>|
|<span data-ttu-id="329dd-125">ATP-prov</span><span class="sxs-lookup"><span data-stu-id="329dd-125">ATP P2 trial</span></span>|<span data-ttu-id="329dd-126">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="329dd-126">Threat Explorer</span></span>|<span data-ttu-id="329dd-127">borttagning</span><span class="sxs-lookup"><span data-stu-id="329dd-127">7</span></span>|
|<span data-ttu-id="329dd-128">ATP-betalat</span><span class="sxs-lookup"><span data-stu-id="329dd-128">ATP P2 paid</span></span>|<span data-ttu-id="329dd-129">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="329dd-129">Threat Explorer</span></span>|<span data-ttu-id="329dd-130">halvtimme</span><span class="sxs-lookup"><span data-stu-id="329dd-130">30</span></span>|
|

<span data-ttu-id="329dd-131">Använd **Visa** -menyn för att ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="329dd-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="329dd-132">Med knapp beskrivningar kan du bestämma vilken vy som ska användas.</span><span class="sxs-lookup"><span data-stu-id="329dd-132">Tooltips help you determine which view to use.</span></span>

![Menyn Threat Explorer](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="329dd-134">När du har valt en vy kan du använda filter och ställa in frågor för att utföra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="329dd-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="329dd-135">I följande avsnitt får du en kort översikt över de olika vyer som är tillgängliga i Utforskaren (eller i real tid).</span><span class="sxs-lookup"><span data-stu-id="329dd-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="329dd-136">> skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="329dd-136">Email > Malware</span></span>

<span data-ttu-id="329dd-137">Om du vill visa rapporten klickar du på **Visa**  >  **e-**  >  **postskadlig kod**i Utforskaren (eller i real tid).</span><span class="sxs-lookup"><span data-stu-id="329dd-137">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="329dd-138">I den här vyn visas information om e-postmeddelanden som identifierats som innehåll ande malware.</span><span class="sxs-lookup"><span data-stu-id="329dd-138">This view shows information about email messages that were identified as containing malware.</span></span>

![Visa information om e-post som identifieras som skadlig program vara](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="329dd-140">Klicka på **avsändare** för att öppna listan över visnings alternativ.</span><span class="sxs-lookup"><span data-stu-id="329dd-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="329dd-141">Använd den här listan för att visa data efter avsändare, mottagare, avsändare, ämne, identifierings teknik, skydds status och mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="329dd-142">Om du till exempel vill se vilka åtgärder som har utförts på identifierade e-postmeddelanden väljer du **skydds status** i listan.</span><span class="sxs-lookup"><span data-stu-id="329dd-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="329dd-143">Välj ett alternativ och klicka sedan på knappen Uppdatera för att tillämpa filtret på rapporten.</span><span class="sxs-lookup"><span data-stu-id="329dd-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Status alternativ för hotets skydd för Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="329dd-145">Visa mer information om specifika meddelanden under diagrammet.</span><span class="sxs-lookup"><span data-stu-id="329dd-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="329dd-146">När du markerar ett objekt i listan öppnas ett alternativ för att få mer information om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="329dd-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Threat Explorer med utfällbar öppning](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="329dd-148">E-> Phish</span><span class="sxs-lookup"><span data-stu-id="329dd-148">Email > Phish</span></span>

<span data-ttu-id="329dd-149">Om du vill visa rapporten går du till Explorer (eller real tids identifiering) och väljer **Visa**  >  **e-**  >  **Phish**.</span><span class="sxs-lookup"><span data-stu-id="329dd-149">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="329dd-150">I den här vyn visas e-postmeddelanden som identifieras som nätfiske-försök.</span><span class="sxs-lookup"><span data-stu-id="329dd-150">This view shows email messages identified as phishing attempts.</span></span>

![Visa information om e-post som identifieras som nätfiske-försök](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="329dd-152">Klicka på **avsändare** för att öppna listan över visnings alternativ.</span><span class="sxs-lookup"><span data-stu-id="329dd-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="329dd-153">Använd den här listan för att visa data efter avsändare, mottagare, avsändarens domän, avsändarens IP, URL-domän, klicka på Verdict och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="329dd-154">Om du till exempel vill se vilka åtgärder som vidtogs när personer klickade på URL-adresser som har identifierats som nätfiske-försök väljer du **Klicka på Verdict** i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="329dd-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka på Verdict alternativ för rapporten Phish](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="329dd-156">Under diagrammet kan du Visa mer information om specifika meddelanden, URL-musklick, URL: er och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="329dd-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL-adresser identifieras som Phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="329dd-158">När du markerar ett objekt i listan, till exempel en webb adress som upptäckts, öppnas en dialog ruta för att ta reda på mer om det markerade objektet.</span><span class="sxs-lookup"><span data-stu-id="329dd-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Information om en upptäckd URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="329dd-160">Skicka e-post ></span><span class="sxs-lookup"><span data-stu-id="329dd-160">Email > Submissions</span></span>

<span data-ttu-id="329dd-161">Om du vill visa den här rapporten går du till Explorer (eller real tids identifieringar) och väljer **Visa**  >  **e-**  >  **postinlägg**.</span><span class="sxs-lookup"><span data-stu-id="329dd-161">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="329dd-162">I den här vyn visas e-post som användare har rapporterat som skräp post, inte skräp post eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="329dd-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-postmeddelanden som rapporter ATS av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="329dd-164">Klicka på **avsändare** för att öppna listan över visnings alternativ.</span><span class="sxs-lookup"><span data-stu-id="329dd-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="329dd-165">Använd den här listan för att visa information efter avsändare, mottagare, rapport typ (användarens kontroll att e-postmeddelandet var skräp, inte skräp post eller Phish) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="329dd-166">Om du till exempel vill visa information om e-postmeddelanden som rapporter ATS som nätfiske-försök klickar du på **avsändarens**  >  **typ**, väljer **Phish**och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="329dd-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish markerad för rapport typ filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="329dd-168">Under diagrammet visas mer information om specifika e-postmeddelanden, till exempel ämnes raden, avsändarens IP-adress, användaren som rapporterade meddelandet som skräp post, inte skräp post eller Phish.</span><span class="sxs-lookup"><span data-stu-id="329dd-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Meddelanden som rapporter ATS som nätfiske-försök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="329dd-170">Välj ett objekt i listan för att visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="329dd-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="329dd-171">E-posta > all e-post</span><span class="sxs-lookup"><span data-stu-id="329dd-171">Email > All email</span></span>

<span data-ttu-id="329dd-172">Om du vill visa rapporten klickar du på **Visa**  >  **e-** post i Utforskaren  >  **All mail**.</span><span class="sxs-lookup"><span data-stu-id="329dd-172">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="329dd-173">I den här vyn visas en uppkopplings aktivitet med e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig program vara (vanlig e-post, spam och Mass utskick).</span><span class="sxs-lookup"><span data-stu-id="329dd-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="329dd-174">Om du får ett fel meddelande som läser upp **för mycket data**kan du lägga till ett filter och, om det behövs, begränsa det datum intervall du visar.</span><span class="sxs-lookup"><span data-stu-id="329dd-174">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="329dd-175">Om du vill använda ett filter väljer du **avsändare**, markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="329dd-175">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="329dd-176">I vårt exempel använde vi **identifierings teknologi** som ett filter (det finns flera tillgängliga alternativ).</span><span class="sxs-lookup"><span data-stu-id="329dd-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="329dd-177">Visa information efter avsändare, avsändarens domän, mottagare, ämne, bifogade filer och skadlig program vara, skydds status (åtgärder som vidtas av funktioner och principer för hotets skydd i Office 365), identifierings teknologi (hur skadlig program vara upptäcktes) och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Visa data om identifierad e-post efter identifierings teknologi](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="329dd-179">Under diagrammet kan du Visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="329dd-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="329dd-180">Innehålls > skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="329dd-180">Content > Malware</span></span>

<span data-ttu-id="329dd-181">Om du vill visa rapporten i Utforskaren (eller i real tid) väljer du **Visa**  >  **Content**  >  **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="329dd-181">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="329dd-182">I den här vyn visas filer som har identifierats som skadliga av [Office 365 Avancerat skydd i SharePoint Online, OneDrive för företag och Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="329dd-182">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="329dd-183">Visa information från skadlig program vara, identifierings teknologi (hur skadlig kod har identifierats) och arbets belastning (OneDrive, SharePoint eller teams).</span><span class="sxs-lookup"><span data-stu-id="329dd-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Visa information om identifierad skadlig kod](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="329dd-185">Under diagrammet kan du Visa mer information om specifika filer, till exempel fil namn, arbets belastning, fil storlek, som senast ändrade filen och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="329dd-186">Klicka-och-filtrera-funktioner</span><span class="sxs-lookup"><span data-stu-id="329dd-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="329dd-187">Med Explorer (och real tids identifieringar) kan du använda ett filter i ett klick.</span><span class="sxs-lookup"><span data-stu-id="329dd-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="329dd-188">Klicka på ett objekt i förklaringen så blir objektet ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="329dd-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="329dd-189">Anta till exempel att vi tittar på vyn mot skadlig program vara i Utforskaren:</span><span class="sxs-lookup"><span data-stu-id="329dd-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Gå till Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="329dd-191">Om du klickar på **ATP-sprängor** i det här diagrammet visas en vy som här:</span><span class="sxs-lookup"><span data-stu-id="329dd-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Utforskaren är filtrerad för att endast visa resultat för ATP-Sprängor](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="329dd-193">I den här vyn visar vi nu data för filer som har sprängts med [säkra bifogade](atp-safe-attachments.md)filer.</span><span class="sxs-lookup"><span data-stu-id="329dd-193">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="329dd-194">Under diagrammet kan vi se information om specifika e-postmeddelanden med bifogade filer som upptäcktes av säkra bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="329dd-194">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifik information om e-postmeddelanden med identifierade bilagor](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="329dd-196">Om du markerar ett eller flera objekt aktive ras **Åtgärds** menyn, som innehåller flera alternativ som du kan välja för.</span><span class="sxs-lookup"><span data-stu-id="329dd-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![När du markerar ett objekt aktive ras menyn åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="329dd-198">Möjligheten att filtrera i ett klick och navigera till specifika uppgifter gör att du kan spara pengar.</span><span class="sxs-lookup"><span data-stu-id="329dd-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="329dd-199">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="329dd-199">Queries and filters</span></span>

<span data-ttu-id="329dd-200">Utforskaren (samt rapporter i real tid) innehåller flera kraftfulla filter och fråge funktioner som gör att du kan visa detaljer, till exempel Top riktade användare, de viktigaste, identifierings teknologin och mer.</span><span class="sxs-lookup"><span data-stu-id="329dd-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="329dd-201">I alla typer av rapporter finns det flera olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="329dd-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="329dd-202">Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i fråge fältet för Explorer (eller real tids identifiering).</span><span class="sxs-lookup"><span data-stu-id="329dd-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="329dd-203">När du söker i **ämnes fältet** för e-postmeddelanden kommer Explorer (eller real tids identifiering) att utföra delvis matchande och ge resultat som liknar en sökning med jokertecken.</span><span class="sxs-lookup"><span data-stu-id="329dd-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
