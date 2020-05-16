---
title: Vyer i Threat Explorer och realtidsidentifieringar
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
description: Lär dig mer om hur du använder Threat Explorer och rapporten identifiering i realtid för att undersöka och svara på hot i Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 824fde8d6f6a03dd61a46d1f0ccc08c93b85adf8
ms.sourcegitcommit: 76edb413cbd7436252075ea7e314f5e1d07d8d55
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44267197"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="babff-103">Vyer i Threat Explorer och realtidsidentifieringar</span><span class="sxs-lookup"><span data-stu-id="babff-103">Views in Threat Explorer and real-time detections</span></span>

![Hotutforskaren](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="babff-105">[Threat Explorer](threat-explorer.md) (och realtidsidentifieringsrapporten) är ett kraftfullt, nära realtidsverktyg som hjälper säkerhetsteam att undersöka och svara på hot i Security &amp; Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="babff-105">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="babff-106">Explorer (och rapporten identifiering i realtid) visar information om misstänkt skadlig kod och phish i e-post och filer i Office 365, samt andra säkerhetshot och risker för din organisation.</span><span class="sxs-lookup"><span data-stu-id="babff-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="babff-107">Om du har [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2 har du Explorer.</span><span class="sxs-lookup"><span data-stu-id="babff-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="babff-108">Om du har Office 365 ATP-abonnemang 1 har du identifiering i realtid.</span><span class="sxs-lookup"><span data-stu-id="babff-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="babff-109">När du först öppnar Explorer (eller rapporten identifiering i realtid) visas identifiering av skadlig e-post för de senaste sju dagarna i standardvyn.</span><span class="sxs-lookup"><span data-stu-id="babff-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="babff-110">Den här rapporten kan också visa ATP-identifieringar, till exempel skadliga url:er som identifieras av [säkra länkar](atp-safe-links.md)och skadliga filer som identifieras av [säkra bilagor](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="babff-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="babff-111">Den här rapporten kan ändras för att visa data för de senaste 30 dagarna (med en betald ATP P2-prenumeration).</span><span class="sxs-lookup"><span data-stu-id="babff-111">This report can be modified to show data for the past 30 days (with an ATP P2 paid subscription).</span></span> <span data-ttu-id="babff-112">Provprenumerationer innehåller endast data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="babff-112">Trial subscriptions will include data for the past seven days only.</span></span>

|<span data-ttu-id="babff-113">Prenumeration</span><span class="sxs-lookup"><span data-stu-id="babff-113">Subscription</span></span>  |<span data-ttu-id="babff-114">Verktyg</span><span class="sxs-lookup"><span data-stu-id="babff-114">Utility</span></span>  |<span data-ttu-id="babff-115">Dagar med data</span><span class="sxs-lookup"><span data-stu-id="babff-115">Days of Data</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="babff-116">ATP P1-testversion</span><span class="sxs-lookup"><span data-stu-id="babff-116">ATP P1 trial</span></span>     | <span data-ttu-id="babff-117">Realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="babff-117">Real-time detections</span></span>        |   <span data-ttu-id="babff-118">7</span><span class="sxs-lookup"><span data-stu-id="babff-118">7</span></span>      |
|<span data-ttu-id="babff-119">ATP P1 betalas</span><span class="sxs-lookup"><span data-stu-id="babff-119">ATP P1 paid</span></span>     |   <span data-ttu-id="babff-120">Realtidsidentifiering</span><span class="sxs-lookup"><span data-stu-id="babff-120">Real-time detections</span></span>      |    <span data-ttu-id="babff-121">30</span><span class="sxs-lookup"><span data-stu-id="babff-121">30</span></span>     |
|<span data-ttu-id="babff-122">ATP P1 betald testning ATP P2 rättegång</span><span class="sxs-lookup"><span data-stu-id="babff-122">ATP P1 paid testing ATP P2 trial</span></span>     | <span data-ttu-id="babff-123">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="babff-123">Threat Explorer</span></span>   |   <span data-ttu-id="babff-124">7</span><span class="sxs-lookup"><span data-stu-id="babff-124">7</span></span>   |
|<span data-ttu-id="babff-125">ATP P2-test</span><span class="sxs-lookup"><span data-stu-id="babff-125">ATP P2 trial</span></span>     |  <span data-ttu-id="babff-126">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="babff-126">Threat Explorer</span></span>       |     <span data-ttu-id="babff-127">7</span><span class="sxs-lookup"><span data-stu-id="babff-127">7</span></span>    |
|<span data-ttu-id="babff-128">ATP P2 betald</span><span class="sxs-lookup"><span data-stu-id="babff-128">ATP P2 paid</span></span>     |     <span data-ttu-id="babff-129">Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="babff-129">Threat Explorer</span></span>    |  <span data-ttu-id="babff-130">30</span><span class="sxs-lookup"><span data-stu-id="babff-130">30</span></span>       |

<span data-ttu-id="babff-131">Använd **Visa-menyn** för att ändra vilken information som visas.</span><span class="sxs-lookup"><span data-stu-id="babff-131">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="babff-132">Verktygstips hjälper dig att avgöra vilken vy som ska användas.</span><span class="sxs-lookup"><span data-stu-id="babff-132">Tooltips help you determine which view to use.</span></span>
  
![Visa-menyn Hot Explorer](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="babff-134">När du har valt en vy kan du använda filter och ställa in frågor för att utföra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="babff-134">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="babff-135">Följande avsnitt ger en kort översikt över de olika vyer som är tillgängliga i Explorer (eller realtidsidentifieringar).</span><span class="sxs-lookup"><span data-stu-id="babff-135">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="babff-136">E-post > Malware</span><span class="sxs-lookup"><span data-stu-id="babff-136">Email > Malware</span></span>

<span data-ttu-id="babff-137">Om du vill visa den här rapporten väljer du **Visa**  >  **skadlig kod i**  >  **Malware**Explorer (eller realtidsidentifiering).</span><span class="sxs-lookup"><span data-stu-id="babff-137">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="babff-138">I den här vyn visas information om e-postmeddelanden som har identifierats som innehållande skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="babff-138">This view shows information about email messages that were identified as containing malware.</span></span>  

![Visa data om e-post som identifierats som skadlig kod](../../media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="babff-140">Klicka på **Avsändare** om du vill öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="babff-140">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="babff-141">Använd den här listan om du vill visa data efter avsändare, mottagare, avsändaredomän, ämne, identifieringsteknik, skyddsstatus med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-141">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="babff-142">Om du till exempel vill se vilka åtgärder som vidtogs på identifierade e-postmeddelanden väljer du **Skyddsstatus** i listan.</span><span class="sxs-lookup"><span data-stu-id="babff-142">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="babff-143">Välj ett alternativ och klicka sedan på knappen Uppdatera om du vill använda filtret i rapporten.</span><span class="sxs-lookup"><span data-stu-id="babff-143">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Alternativ för status för hotskydd för Hot Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="babff-145">Nedanför diagrammet kan du visa mer information om specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="babff-145">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="babff-146">När du markerar ett objekt i listan öppnas ett utfällbart fönster där du kan läsa mer om det objekt du valde.</span><span class="sxs-lookup"><span data-stu-id="babff-146">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Threat Explorer med utfällbart utfällbart öppet](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="babff-148">E-post > Phish</span><span class="sxs-lookup"><span data-stu-id="babff-148">Email > Phish</span></span>

<span data-ttu-id="babff-149">Om du vill visa den här rapporten väljer du **Visa**  >  **e-post phish**i Utforskaren (eller identifiering i  >  **Phish**realtid).</span><span class="sxs-lookup"><span data-stu-id="babff-149">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="babff-150">I den här vyn visas e-postmeddelanden som identifierats som nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="babff-150">This view shows email messages identified as phishing attempts.</span></span>  

![Visa data om e-post som identifierats som nätfiskeförsök](../../media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="babff-152">Klicka på **Avsändare** om du vill öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="babff-152">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="babff-153">Använd den här listan om du vill visa data efter avsändare, mottagare, avsändaredomän, avsändare-IP, URL-domän, klicka på dom med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-153">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="babff-154">Om du till exempel vill se vilka åtgärder som vidtogs när personer klickade på webbadresser som identifierades som nätfiskeförsök väljer du **Klicka på domslut** i listan, välj ett eller flera alternativ och klicka sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="babff-154">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klicka dom alternativ för Phish rapporten](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="babff-156">Nedanför diagrammet kan du visa mer information om specifika meddelanden, URL-klick, webbadresser och e-postursprung.</span><span class="sxs-lookup"><span data-stu-id="babff-156">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![Webbadresser som identifierats som phish i e-postmeddelanden](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="babff-158">När du väljer ett objekt i listan, till exempel en URL som upptäcktes, öppnas ett utfällbart fönster där du kan läsa mer om det objekt du valde.</span><span class="sxs-lookup"><span data-stu-id="babff-158">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![Information om en identifierad URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="babff-160">Skicka >-> e-post</span><span class="sxs-lookup"><span data-stu-id="babff-160">Email > Submissions</span></span>

<span data-ttu-id="babff-161">Om du vill visa den här rapporten väljer du **Visa**  >  **e-postinlämningar**i Utforskaren (eller identifiering i  >  **Submissions**realtid).</span><span class="sxs-lookup"><span data-stu-id="babff-161">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Submissions**.</span></span> <span data-ttu-id="babff-162">Den här vyn visar e-post som användare har rapporterat som skräppost, inte skräppost eller nätfiske.</span><span class="sxs-lookup"><span data-stu-id="babff-162">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![E-postmeddelanden som rapporterats av användare](../../media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="babff-164">Klicka på **Avsändare** om du vill öppna listan med visningsalternativ.</span><span class="sxs-lookup"><span data-stu-id="babff-164">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="babff-165">Använd den här listan om du vill visa information efter avsändare, mottagare, rapporttyp (användarens bedömning av att e-postmeddelandet var skräppost, inte skräppost eller phish) med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-165">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="babff-166">Om du till exempel vill visa information om e-postmeddelanden som rapporterats som nätfiskeförsök klickar du på Typ **av**  >  **avsändare,** väljer **Phish**och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="babff-166">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish vald för filtret Rapporttyp](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="babff-168">Under diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, avsändarens IP-adress, användaren som rapporterade meddelandet som skräppost, inte skräppost eller phish med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-168">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![Meddelanden som rapporterats som nätfiskeförsök](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="babff-170">Markera ett objekt i listan om du vill visa ytterligare information.</span><span class="sxs-lookup"><span data-stu-id="babff-170">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="babff-171">E-post > Alla e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="babff-171">Email > All email</span></span>

<span data-ttu-id="babff-172">Om du vill visa den här rapporten väljer du **Visa**  >  **e-post all e-post**i Utforskaren  >  **All mail**.</span><span class="sxs-lookup"><span data-stu-id="babff-172">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="babff-173">I de här vyerna visas en all-up-vy av e-postaktivitet, inklusive e-post som identifierats som skadlig på grund av nätfiske eller skadlig kod, samt all icke-skadlig e-post (vanlig e-post, skräppost och massutskick).</span><span class="sxs-lookup"><span data-stu-id="babff-173">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="babff-174">Om du får ett felmeddelande som läser **för mycket data för att visa**lägger du till ett filter och begränsar datumintervallet du visar om det behövs.</span><span class="sxs-lookup"><span data-stu-id="babff-174">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="babff-175">Om du vill använda ett filter väljer du **Avsändare,** markerar ett objekt i listan och klickar sedan på knappen Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="babff-175">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="babff-176">I vårt exempel använde vi **Detektionsteknik** som filter (det finns flera alternativ tillgängliga).</span><span class="sxs-lookup"><span data-stu-id="babff-176">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="babff-177">Visa information efter avsändare, avsändares domän, mottagare, ämne, filnamn för bifogade filer, en familj för skadlig programvara, skyddsstatus (åtgärder som vidtas av dina hotskyddsfunktioner och policyer i Office 365), identifieringsteknik (hur den skadliga koden upptäcktes) med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-177">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![Visa data om identifierad e-post med identifieringsteknik](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="babff-179">Nedanför diagrammet kan du visa mer information om specifika e-postmeddelanden, till exempel ämnesrad, mottagare, avsändare, status och så vidare.</span><span class="sxs-lookup"><span data-stu-id="babff-179">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="babff-180">Innehåll > skadlig kod</span><span class="sxs-lookup"><span data-stu-id="babff-180">Content > Malware</span></span>

<span data-ttu-id="babff-181">Om du vill visa den här rapporten väljer du **Visa**skadlig programvara i Utforskaren (eller identifiering i  >  **Content**  >  **Malware**realtid).</span><span class="sxs-lookup"><span data-stu-id="babff-181">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="babff-182">I den här vyn visas filer som har identifierats som skadliga av [Office 365 Advanced Threat Protection i SharePoint Online, OneDrive för företag och Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="babff-182">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="babff-183">Visa information efter en kod som är en familj för skadlig kod, identifieringsteknik (hur den skadliga koden upptäcktes) och arbetsbelastning (OneDrive, SharePoint eller Teams).</span><span class="sxs-lookup"><span data-stu-id="babff-183">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![Visa data om upptäckt skadlig kod](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="babff-185">Nedanför diagrammet kan du visa mer information om specifika filer, till exempel filnamn för bifogade filer, arbetsbelastning, filstorlek, vem som senast ändrade filen med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-185">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="babff-186">Klicka-för-filter-funktioner</span><span class="sxs-lookup"><span data-stu-id="babff-186">Click-to-filter capabilities</span></span>

<span data-ttu-id="babff-187">Med Explorer (och realtidsidentifieringar) kan du använda ett filter genom att klicka.</span><span class="sxs-lookup"><span data-stu-id="babff-187">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="babff-188">Klicka på ett objekt i förklaringen och det objektet blir ett filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="babff-188">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="babff-189">Anta till exempel att vi tittar på vyn Skadlig kod i Explorer:</span><span class="sxs-lookup"><span data-stu-id="babff-189">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![Gå till Explorer för hothantering \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="babff-191">Om du klickar på **ATP Detonation** i det här diagrammet visas en vy som denna:</span><span class="sxs-lookup"><span data-stu-id="babff-191">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![Explorer filtreras för att visa endast ATP Detonation resultat](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="babff-193">I den här vyn tittar vi nu på data för filer som detonerade av [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="babff-193">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="babff-194">Under diagrammet kan vi se information om specifika e-postmeddelanden som hade bilagor som upptäcktes av ATP Safe Bilagor.</span><span class="sxs-lookup"><span data-stu-id="babff-194">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![Specifik information om e-postmeddelanden med identifierade bilagor](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="babff-196">Om du väljer ett eller flera objekt aktiveras **menyn Åtgärder,** som innehåller flera alternativ att välja mellan för det valda objektet.Selecting one or more items activates the Actions menu, which offers several choices from which to choose for the selected item(s.</span><span class="sxs-lookup"><span data-stu-id="babff-196">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![Om du väljer ett objekt aktiveras menyn Åtgärder](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="babff-198">Möjligheten att filtrera med ett klick och navigera till specifika detaljer kan spara mycket tid på att undersöka hot.</span><span class="sxs-lookup"><span data-stu-id="babff-198">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="babff-199">Frågor och filter</span><span class="sxs-lookup"><span data-stu-id="babff-199">Queries and filters</span></span>

<span data-ttu-id="babff-200">Explorer (samt rapporten identifiering i realtid) har flera kraftfulla filter och frågefunktioner som gör att du kan gå in på detaljer, till exempel toppinriktade användare, de bästa familjerna för skadlig kod, identifieringsteknik med mera.</span><span class="sxs-lookup"><span data-stu-id="babff-200">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="babff-201">Varje typ av rapport erbjuder en mängd olika sätt att visa och utforska data.</span><span class="sxs-lookup"><span data-stu-id="babff-201">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="babff-202">Använd inte jokertecken, till exempel en asterisk eller ett frågetecken, i frågefältet för Explorer (eller identifiering i realtid).</span><span class="sxs-lookup"><span data-stu-id="babff-202">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="babff-203">När du söker i **fältet Ämne** efter e-postmeddelanden utför Explorer (eller realtidsidentifieringar) partiell matchning och ger resultat som liknar en jokerteckensökning.</span><span class="sxs-lookup"><span data-stu-id="babff-203">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
