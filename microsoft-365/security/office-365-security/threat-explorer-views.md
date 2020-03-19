---
title: Vyer i Threat Explorer och identifieringar i realtid
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: Lär dig mer om de olika typer av vyer som finns i Threat Explorer och identifieringar i realtid.
ms.openlocfilehash: 9e2d6ce0c51c6a43596885d9ccb529dc1464a052
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808998"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="eecb4-103">Vyer i Threat Explorer och identifieringar i realtid</span><span class="sxs-lookup"><span data-stu-id="eecb4-103">Views in Threat Explorer and real-time detections</span></span>

![Hot Explorer](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="eecb4-105">[Threat Explorer](threat-explorer.md) (och rapporten identifiering i realtid) är ett kraftfullt, nära realtidsverktyg som hjälper säkerhetsgrupper &amp; att undersöka och svara på hot i Security Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="eecb4-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="eecb4-106">Explorer (och rapporten identifiering i realtid) visar information om misstänkt skadlig kod och phish i e-post och filer i Office 365, samt andra säkerhetshot och risker för din organisation.</span><span class="sxs-lookup"><span data-stu-id="eecb4-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="eecb4-107">Om du har Atp-abonnemang [(Office 365 Advanced Threat Protection)](office-365-atp.md) 2 har du Explorer.</span><span class="sxs-lookup"><span data-stu-id="eecb4-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="eecb4-108">Om du har Office 365 ATP-abonnemang 1 har du identifiering i realtid.</span><span class="sxs-lookup"><span data-stu-id="eecb4-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="eecb4-109">När du öppnar Explorer (eller rapporten identifiering i realtid) visas identifiering av skadlig programvara för e-post under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="eecb4-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="eecb4-110">Den här rapporten kan också visa ATP-identifieringar, till exempel skadliga webbadresser som identifierats av [säkra länkar](atp-safe-links.md)och skadliga filer som [upptäckts](atp-safe-attachments.md)av säkra bilagor .</span><span class="sxs-lookup"><span data-stu-id="eecb4-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="eecb4-111">Den här rapporten kan ändras för att visa data under de senaste 30 dagarna (om du inte använder en utvärderingsprenumeration).</span><span class="sxs-lookup"><span data-stu-id="eecb4-111">This report can be modified to show data for the past 30 days (unless you are using a trial subscription).</span></span> <span data-ttu-id="eecb4-112">Utvärderingsprenumerationer innehåller data endast under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="eecb4-112">Trial subscriptions will include data for the past seven days only.</span></span>

<span data-ttu-id="eecb4-113">Använd **Visa-menyn** för att ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="eecb4-113">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="eecb4-114">Verktygstips hjälper dig att avgöra vilken vy du ska använda.</span><span class="sxs-lookup"><span data-stu-id="eecb4-114">Tooltips help you determine which view to use.</span></span>
  
![Visa-menyn Hot Explorer](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="eecb4-116">När du har valt en vy kan du använda filter och ställa in frågor för att utföra ytterligare analys.</span><span class="sxs-lookup"><span data-stu-id="eecb4-116">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="eecb4-117">Följande avsnitt ger en kort översikt över de olika vyer som finns i Explorer (eller identifieringi realtid).</span><span class="sxs-lookup"><span data-stu-id="eecb4-117">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="eecb4-118">E-post > malware</span><span class="sxs-lookup"><span data-stu-id="eecb4-118">Email > Malware</span></span>

<span data-ttu-id="eecb4-119">Om du vill visa den här rapporten i Explorer (eller identifiering i realtid) väljer du **Visa** > **skadlig e-post** > **Malware**.</span><span class="sxs-lookup"><span data-stu-id="eecb4-119">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="eecb4-120">Den här vyn visar information om e-postmeddelanden som har identifierats som innehåller skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="eecb4-120">This view shows information about email messages that were identified as containing malware.</span></span>  

![Visa data om e-post som identifierats som skadlig kod](../../media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="eecb4-122">Klicka på **Avsändare** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="eecb4-122">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="eecb4-123">Använd den här listan om du vill visa data efter avsändare, mottagare, avsändare, ämne, identifieringsteknik, skyddsstatus med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-123">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="eecb4-124">Om du till exempel vill se vilka åtgärder som har vidtagits för identifierade e-postmeddelanden väljer du **Skyddsstatus** i listan.</span><span class="sxs-lookup"><span data-stu-id="eecb4-124">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="eecb4-125">Välj ett alternativ och klicka sedan på knappen Uppdatera för att använda filtret i rapporten.</span><span class="sxs-lookup"><span data-stu-id="eecb4-125">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Alternativ för hotskydd för Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="eecb4-127">Under diagrammet visar du mer information om specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="eecb4-127">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="eecb4-128">När du markerar ett objekt i listan öppnas ett utfällbart fönster där du kan läsa mer om det objekt du valde.</span><span class="sxs-lookup"><span data-stu-id="eecb4-128">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Threat Explorer med utfällbart program öppnat](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="eecb4-130">E-post > Phish</span><span class="sxs-lookup"><span data-stu-id="eecb4-130">Email > Phish</span></span>

<span data-ttu-id="eecb4-131">Om du vill visa den här rapporten i Explorer (eller identifiering i realtid) väljer du **Visa** > **postphish\*\*\*\*Email** > .</span><span class="sxs-lookup"><span data-stu-id="eecb4-131">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="eecb4-132">I den här vyn visas e-postmeddelanden som identifierats som nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="eecb4-132">This view shows email messages identified as phishing attempts.</span></span>  

![Visa data om e-post som identifieras som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="eecb4-134">Klicka på **Avsändare** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="eecb4-134">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="eecb4-135">Använd den här listan om du vill visa data efter avsändare, mottagare, avsändardomän, avsändares IP, URL-domän, klicka på dom med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-135">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="eecb4-136">Om du till exempel vill se vilka åtgärder som har vidtagits när personer klickade på webbadresser som identifierats som nätfiskeförsök väljer du **Klicka på dom** i listan, väljer ett eller flera alternativ och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-136">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka på domsalternativ för Phish-rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="eecb4-138">Under diagrammet visar du mer information om specifika meddelanden, URL-klick, webbadresser och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="eecb4-138">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![Webbadresser upptäcktes som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="eecb4-140">När du markerar ett objekt i listan, till exempel en URL som upptäcktes, öppnas ett utfällbart fönster där du kan läsa mer om det objekt du valde.</span><span class="sxs-lookup"><span data-stu-id="eecb4-140">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Information om en identifierad WEBBADRESS](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="eecb4-142">E-post > inlagor</span><span class="sxs-lookup"><span data-stu-id="eecb4-142">Email > Submissions</span></span>

<span data-ttu-id="eecb4-143">Om du vill visa den här rapporten i Explorer (eller identifiering i realtid) väljer du **Visa** > **e-postinlämningar** > **Submissions**.</span><span class="sxs-lookup"><span data-stu-id="eecb4-143">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="eecb4-144">I den här vyn visas e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="eecb4-144">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="eecb4-146">Klicka på **Avsändare** för att öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="eecb4-146">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="eecb4-147">Använd den här listan om du vill visa information av avsändare, mottagare, rapporttyp (användarens beslutsamhet att e-postmeddelandet var skräp, inte skräp eller phish) med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-147">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="eecb4-148">Om du till exempel vill visa information om e-postmeddelanden som har rapporterats som nätfiskeförsök klickar du på typen **Avsändares** > **rapport,** väljer **Phish**och sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-148">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish markerat för filter för rapporttyp](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="eecb4-150">Under diagrammet visar du mer information om specifika e-postmeddelanden, till exempel ämnesrad, avsändarens IP-adress, användaren som rapporterade meddelandet som skräppost, inte skräp eller phish med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-150">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![Meddelanden som har rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="eecb4-152">Markera ett objekt i listan om du vill visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="eecb4-152">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="eecb4-153">E-> Alla e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="eecb4-153">Email > All email</span></span>

<span data-ttu-id="eecb4-154">Om du vill visa den här rapporten väljer du **Visa** > **e-post med e-post** > **All mail**i Explorer.</span><span class="sxs-lookup"><span data-stu-id="eecb4-154">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="eecb4-155">De här vyerna visar en all-up-vy av e-postaktivitet, inklusive e-post som identifieras som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (normal e-post, skräppost och masspost).</span><span class="sxs-lookup"><span data-stu-id="eecb4-155">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="eecb4-156">Om du får ett felmeddelande som läser **För mycket data för att visa**lägger du till ett filter och begränsar vid behov det datumintervall du visar.</span><span class="sxs-lookup"><span data-stu-id="eecb4-156">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="eecb4-157">Om du vill använda ett filter väljer du **Avsändare,** markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-157">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="eecb4-158">I vårt exempel använde vi **Detection-teknik** som filter (det finns flera alternativ tillgängliga).</span><span class="sxs-lookup"><span data-stu-id="eecb4-158">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="eecb4-159">Visa information av avsändaren, avsändarens domän, mottagare, ämne, filnamn för bifogade filer, skadlig kod familj, skyddsstatus (åtgärder som vidtas av dina hotskyddsfunktioner och principer i Office 365), identifieringsteknik (hur skadlig kod upptäcktes) och Mer.</span><span class="sxs-lookup"><span data-stu-id="eecb4-159">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Visa data om upptäckt e-post efter identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="eecb4-161">Under diagrammet visar du mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="eecb4-161">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="eecb4-162">Innehåll > skadlig kod</span><span class="sxs-lookup"><span data-stu-id="eecb4-162">Content > Malware</span></span>

<span data-ttu-id="eecb4-163">Om du vill visa den här rapporten i Explorer (eller identifiering i realtid) väljer du **Visa** > skadlig**kod för\*\*\*\*innehåll** > .</span><span class="sxs-lookup"><span data-stu-id="eecb4-163">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="eecb4-164">Den här vyn visar filer som har identifierats som skadliga av [Office 365 Advanced Threat Protection i SharePoint Online, OneDrive för företag och Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="eecb4-164">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="eecb4-165">Visa information efter skadlig kod familj, detektionsteknik (hur skadlig kod upptäcktes) och arbetsbelastning (OneDrive, SharePoint eller Teams).</span><span class="sxs-lookup"><span data-stu-id="eecb4-165">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Visa data om upptäckt skadlig kod](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="eecb4-167">Under diagrammet visar du mer information om specifika filer, till exempel filnamn för bifogade filer, arbetsbelastning, filstorlek, som senast ändrade filen med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-167">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="eecb4-168">Klicka för att filtrera funktioner</span><span class="sxs-lookup"><span data-stu-id="eecb4-168">Click-to-filter capabilities</span></span>

<span data-ttu-id="eecb4-169">Med Explorer (och identifiering i realtid) kan du använda ett filter med ett klick.</span><span class="sxs-lookup"><span data-stu-id="eecb4-169">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="eecb4-170">Klicka på ett objekt i förklaringen och objektet blir ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="eecb4-170">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="eecb4-171">Anta till exempel att vi tittar på vyn Skadlig kod i Explorer:</span><span class="sxs-lookup"><span data-stu-id="eecb4-171">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Gå till \> Utforskaren för hothantering](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="eecb4-173">Om du klickar på **ATP Detonation** i det här diagrammet visas en vy som denna:</span><span class="sxs-lookup"><span data-stu-id="eecb4-173">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorer filtreras för att endast visa ATP Detonation resultat](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="eecb4-175">I den här vyn tittar vi nu på data för filer som detonerade av [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="eecb4-175">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="eecb4-176">Under diagrammet kan vi se information om specifika e-postmeddelanden som hade bilagor som har upptäckts av ATP Safe Attachments.</span><span class="sxs-lookup"><span data-stu-id="eecb4-176">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Specifik information om e-postmeddelanden med identifierade bilagor](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="eecb4-178">Om du väljer ett eller flera objekt aktiveras **menyn Åtgärder,** som erbjuder flera alternativ att välja mellan för de markerade objekten.</span><span class="sxs-lookup"><span data-stu-id="eecb4-178">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Om du väljer ett objekt aktiveras menyn Åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="eecb4-180">Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid på att undersöka hot.</span><span class="sxs-lookup"><span data-stu-id="eecb4-180">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="eecb4-181">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="eecb4-181">Queries and filters</span></span>

<span data-ttu-id="eecb4-182">Explorer (samt rapporten identifiering i realtid) har flera kraftfulla filter och frågefunktioner som gör att du kan borra i detaljer, till exempel toppinriktade användare, toppfamiljer med skadlig kod, identifieringsteknik med mera.</span><span class="sxs-lookup"><span data-stu-id="eecb4-182">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="eecb4-183">Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="eecb4-183">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eecb4-184">Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i frågefältet för Explorer (eller identifieringi realtid).</span><span class="sxs-lookup"><span data-stu-id="eecb4-184">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="eecb4-185">När du söker i **ämnesfältet** efter e-postmeddelanden utför Explorer (eller identifieringi realtid) partiellmatchning och ger resultat som liknar en jokerteckensökning.</span><span class="sxs-lookup"><span data-stu-id="eecb4-185">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
