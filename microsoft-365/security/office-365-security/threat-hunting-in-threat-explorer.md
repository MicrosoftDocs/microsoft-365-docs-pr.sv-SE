---
title: Hot jaga i Threat Explorer för Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Använd Threat Explorer eller identifieringar i realtid i &amp; Säkerhetsefterlevnad center för att undersöka och reagera på hot effektivt.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fe67103d9a380c63a0362594c23290457ea3aa
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295328"
---
# <a name="threat-hunting-in-threat-explorer-for-microsoft-defender-for-office-365"></a><span data-ttu-id="e4dc3-103">Hot jaga i Threat Explorer för Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="e4dc3-103">Threat hunting in Threat Explorer for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="e4dc3-104">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-104">In this article:</span></span>

- [<span data-ttu-id="e4dc3-105">Genomgång av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="e4dc3-105">Threat Explorer walk-through</span></span>](#threat-explorer-walk-through)
- [<span data-ttu-id="e4dc3-106">Undersökning av e-post</span><span class="sxs-lookup"><span data-stu-id="e4dc3-106">Email investigation</span></span>](#email-investigation)
- [<span data-ttu-id="e4dc3-107">E-postreparation</span><span class="sxs-lookup"><span data-stu-id="e4dc3-107">Email remediation</span></span>](#email-remediation)
- [<span data-ttu-id="e4dc3-108">Förbättringar för att hitta hot</span><span class="sxs-lookup"><span data-stu-id="e4dc3-108">Improvements to threat hunting experience</span></span>](#improvements-to-threat-hunting-experience)

> [!NOTE]
> <span data-ttu-id="e4dc3-109">Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-109">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="e4dc3-110">De andra två artiklarna i den här serien [är E-postsäkerhet](email-security-in-microsoft-defender.md) med Threat Explorer och Threat Explorer samt grundläggande funktioner för [identifiering i realtid.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-110">The other two articles in this series are [Email security with Threat Explorer](email-security-in-microsoft-defender.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span>


<span data-ttu-id="e4dc3-111">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e4dc3-111">**Applies to**</span></span>
- [<span data-ttu-id="e4dc3-112">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e4dc3-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e4dc3-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4dc3-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e4dc3-114">Om din organisation har [Microsoft Defender för Office 365](defender-for-office-365.md) [](#required-licenses-and-permissions)och du har behörighet kan du använda **Utforskaren** eller **Realtidsidentifiering** för att identifiera och åtgärda hot.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-114">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** or **Real-time detections** to detect and remediate threats.</span></span> 

<span data-ttu-id="e4dc3-115">I **Säkerhets- & säkerhets- och** efterlevnadscenter går du till Hantering av hot och väljer **sedan Utforskaren**  **eller Identifieringar i realtid.**</span><span class="sxs-lookup"><span data-stu-id="e4dc3-115">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="e4dc3-116">Med Microsoft Defender för Office 365 abonnemang 2 visas:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-116">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="e4dc3-117">Med Microsoft Defender för Office 365 abonnemang 1 visas:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-117">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Hotutforskaren](../../media/threatmgmt-explorer.png)|![Identifiering i realtid](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="e4dc3-120">Med dessa verktyg kan du:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-120">With these tools, you can:</span></span>

- <span data-ttu-id="e4dc3-121">Se skadlig programvara som upptäckts Microsoft 365 säkerhetsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e4dc3-121">See malware detected by Microsoft 365 security features</span></span>
- <span data-ttu-id="e4dc3-122">Visa nätfiske-URL och klicka på bedömningsdata</span><span class="sxs-lookup"><span data-stu-id="e4dc3-122">View phishing URL and click verdict data</span></span>
- <span data-ttu-id="e4dc3-123">Starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren</span><span class="sxs-lookup"><span data-stu-id="e4dc3-123">Start an automated investigation and response process from a view in Explorer</span></span>
- <span data-ttu-id="e4dc3-124">Undersöka skadlig e-post med mera</span><span class="sxs-lookup"><span data-stu-id="e4dc3-124">Investigate malicious email, and more</span></span>

<span data-ttu-id="e4dc3-125">Mer information finns i [E-postsäkerhet med Hotutforskaren.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-125">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span> 

## <a name="threat-explorer-walk-through"></a><span data-ttu-id="e4dc3-126">Genomgång av Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="e4dc3-126">Threat Explorer walk-through</span></span>

<span data-ttu-id="e4dc3-127">I Microsoft Defender för Office 365 finns det två abonnemang – abonnemang 1 och abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-127">In Microsoft Defender for Office 365, there are two subscription plans—Plan 1 and Plan 2.</span></span> <span data-ttu-id="e4dc3-128">Manuellt använda sökverktyg för hot finns i båda abonnemangen, under olika namn och med olika funktioner.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-128">Manually operated Threat hunting tools exist in both plans, under different names and with different capabilities.</span></span>

<span data-ttu-id="e4dc3-129">Defender för Office 365 abonnemang 1 använder identifieringar i *realtid,* vilket är en del av sökverktyget i Threat *Explorer* (kallas även *Utforskaren)* i abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-129">Defender for Office 365 Plan 1 uses *Real-time detections*, which is a subset of the *Threat Explorer* (also called *Explorer*) hunting tool in Plan 2.</span></span> <span data-ttu-id="e4dc3-130">I den här serien med artiklar har de flesta av exemplen skapats med hjälp av hela Hotutforskaren.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-130">In this series of articles, most of the examples were created using the full Threat Explorer.</span></span> <span data-ttu-id="e4dc3-131">Administratörer bör testa stegen i realtidsidentifiering för att se var de är tillämpliga.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-131">Admins should test any steps in Real-time detections to see where they apply.</span></span>

<span data-ttu-id="e4dc3-132">Öppna Utforskaren genom att gå till **Säkerhets- & Säkerhetscenter**–  >    >  **Hothanteringsutforskaren** (eller **Identifieringar i realtid).**</span><span class="sxs-lookup"><span data-stu-id="e4dc3-132">To open the Explorer tool, go to **Security & Compliance Center** > **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="e4dc3-133">Som standard kommer du till  sidan Skadlig programvara, men använder listrutan **Visa** för att bekanta dig med alternativen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-133">By default, you’ll arrive on the **Malware** page, but use the **View** drop down to get familiar with your options.</span></span> <span data-ttu-id="e4dc3-134">Om du letar efter Phish eller är redo för en hotkampanj väljer du de här vyerna.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-134">If you’re hunting Phish, or digging into a threat campaign, choose those views.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-135">![Listrutan Visa i Utforskaren med hot](../../media/threat-explorer-view-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-135">![View drop down in Threat Explorer](../../media/threat-explorer-view-drop-down.png)</span></span>

<span data-ttu-id="e4dc3-136">När en säkerhetsoperationer (Sec Ops) väljer ut de data som de vill se, om omfattningen är smal vy som  användare Som skickar , eller en bredare vy, som All e-post, kan de använda knappen Avsändare för att filtrera ytterligare.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-136">Once a security operations (Sec Ops) person selects the data they want to see, whether the scope is narrow view like user **Submissions**, or a wider view, like **All email**, they can use the **Sender** button to further filter.</span></span> <span data-ttu-id="e4dc3-137">Kom ihåg att välja Uppdatera för att slutföra filtreringsåtgärderna.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-137">Remember to select Refresh to complete your filtering actions.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-138">![Knappen Avsändare i Utforskaren med hot](../../media/threat-explorer-sender-button.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-138">![Sender button in Threat Explorer](../../media/threat-explorer-sender-button.png)</span></span>

<span data-ttu-id="e4dc3-139">Du kan tänka på att förfina fokus i Utforskaren eller Identifiering i realtid i lager.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-139">Refining focus in Explorer or Real-time detection can be thought of in layers.</span></span> <span data-ttu-id="e4dc3-140">Det första är **Visa**.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-140">The first is **View**.</span></span> <span data-ttu-id="e4dc3-141">Det andra kan ses som ett *filtrerat fokus.*</span><span class="sxs-lookup"><span data-stu-id="e4dc3-141">The second can be thought of as a *filtered focus*.</span></span> <span data-ttu-id="e4dc3-142">Du kan till exempel gå tillbaka till de steg du gick genom att registrera ett hot genom att registrera dina beslut så här: För att hitta problemet i Utforskaren valde jag vyn Skadlig programvara med filtret Mottagare i **fokus**.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-142">For example, you can retrace the steps you took in finding a threat by recording your decisions like this: To find the issue in Explorer, **I chose the Malware View with a Recipient filter focus**.</span></span> <span data-ttu-id="e4dc3-143">Det gör det enklare att ta om stegen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-143">This makes retracing your steps easier.</span></span>

> [!TIP]
> <span data-ttu-id="e4dc3-144">Om Sek Ops använder **taggar** för att markera konton som de överväger högvärdiga mål, kan de göra val som Phish View med ett *taggfilterfokus (ta* med ett datumintervall om det används).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-144">If Sec Ops uses **Tags** to mark accounts they consider high valued targets, they can make selections like *Phish View with a Tags filter focus (include a date range if used)*.</span></span> <span data-ttu-id="e4dc3-145">Då visas deras nätfiskeförsök mot användarens högvärdesmålen under en tidsperiod (t.ex. datum när vissa nätfiskeattacker pågår mycket inom branschen).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-145">This will show them any phishing attempts directed at their high value user targets during a time-range (like dates when certain phishing attacks are happening a lot for their industry).</span></span> 

<span data-ttu-id="e4dc3-146">Du kan förbättra datumintervallen med hjälp av kontrollerna för datumintervall.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-146">Refinements can be made on date ranges by using the date range controls.</span></span> <span data-ttu-id="e4dc3-147">Här kan du se Utforskaren i **vyn Skadlig** programvara med filtret **Identifieringsteknik** i fokus.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-147">Here you can see Explorer in **Malware** view, with a **Detection Technology** filter focus.</span></span> <span data-ttu-id="e4dc3-148">Men det är filterknappen **Avancerat som** gör att Sek Ops grupper kan gräva djupare.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-148">But it’s the **Advanced filter** button that lets Sec Ops teams dig deep.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-149">![Avancerat filter i Hotutforskaren](../../media/threat-explorer-advanced-filter.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-149">![Advanced filter in Threat Explorer](../../media/threat-explorer-advanced-filter.png)</span></span>

<span data-ttu-id="e4dc3-150">Om du **klickar på filtret** Avancerat visas en panel som låter Sek Ops skapa frågor själva, så att de kan inkludera eller exkludera den information de behöver se.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-150">Clicking the **Advanced filter** pops a panel that will let Sec Ops hunters build queries themselves, letting them include or exclude the information they need to see.</span></span> <span data-ttu-id="e4dc3-151">Både diagrammet och tabellen på sidan Utforskaren speglar deras resultat.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-151">Both the chart and table on the Explorer page will reflect their results.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-152">![Resultat från en fråga](../../media/threat-explorer-chart-table.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-152">![Results from a query](../../media/threat-explorer-chart-table.png)</span></span>

<span data-ttu-id="e4dc3-153">Använd knappen **Kolumnalternativ** för att få den typ av information om tabellen som skulle vara mest användbar:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-153">Use the **Column options** button to get the kind of information on the table that would be most helpful:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-154">![Knappen Kolumnalternativ markerad](../../media/threat-explorer-column-options.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-154">![Column options button highlighted](../../media/threat-explorer-column-options.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-155">![Tillgängliga alternativ i Kolumner](../../media/threat-explorer-column-options-details.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-155">![Available options in Columns](../../media/threat-explorer-column-options-details.png)</span></span>

<span data-ttu-id="e4dc3-156">Testa bildskärmsalternativen med samma mien.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-156">In the same mien, make sure to test your display options.</span></span> <span data-ttu-id="e4dc3-157">Olika målgrupper kommer att reagera bra på olika presentationer med samma data.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-157">Different audiences will react well to different presentations of the same data.</span></span> <span data-ttu-id="e4dc3-158">För vissa användare kan kartan för e-postsprung visa att  ett hot är svårt eller **ödslar** snabbare än visningsalternativet Kampanj bredvid det.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-158">For some viewers, the **Email Origins** map can show that a threat is widespread or discreet more quickly than the **Campaign display** option right next to it.</span></span> <span data-ttu-id="e4dc3-159">Sek Ops kan använda dessa bildskärmar för att bäst understryka behovet av säkerhet och skydd, eller för senare jämförelse, för att visa hur effektivt deras åtgärder är.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-159">Sec Ops can make use of these displays to best make points that underscore the need for security and protection, or for later comparison, to demonstrate the effectiveness of their actions.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-160">![Karta över e-post origins](../../media/threat-explorer-email-origin-map.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-160">![Email Origins map](../../media/threat-explorer-email-origin-map.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-161">![Visningsalternativ för kampanj](../../media/threat-explorer-campaign-display.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-161">![Campaign display options](../../media/threat-explorer-campaign-display.png)</span></span>

### <a name="email-investigation"></a><span data-ttu-id="e4dc3-162">Undersökning av e-post</span><span class="sxs-lookup"><span data-stu-id="e4dc3-162">Email investigation</span></span>

<span data-ttu-id="e4dc3-163">När du ser ett misstänkt e-postmeddelande klickar du på namnet för att expandera den utfällade menyn till höger.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-163">When you see a suspicious email, click the name to expand the flyout on the right.</span></span> <span data-ttu-id="e4dc3-164">Här är banderollen som låter Sek Ops se sidan med [e-post entitet](mdo-email-entity-page.md) tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-164">Here, the banner that lets Sec Ops see the [email entity page](mdo-email-entity-page.md) is available.</span></span>

<span data-ttu-id="e4dc3-165">Sidan för e-post entitet samlas ihop med innehåll som finns under **Information**, **Bifogade filer** **,** Enheter , men innehåller mer ordnade data.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-165">The email entity page pulls together contents that can be found under **Details**, **Attachments**, **Devices**, but includes more organized data.</span></span> <span data-ttu-id="e4dc3-166">Det kan till exempel vara DMARC-resultat, oformaterad textvisning av e-postrubriken med ett kopieringsalternativ, bedömningsinformation om bifogade filer som har lösts och filer som detonationer har släppt (kan inkludera IP-adresser som kontaktades och skärmbilder på sidor eller filer).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-166">This includes things like DMARC results, plain text display of the email header with a copy option, verdict information on attachments that were securely detonated, and files those detonations dropped (can include IP addresses that were contacted and screenshots of pages or files).</span></span> <span data-ttu-id="e4dc3-167">Webbadresser och deras bedömnings inrapporter visas också med liknande information.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-167">URLs and their verdicts are also listed with similar details reported.</span></span> 

<span data-ttu-id="e4dc3-168">När du kommer till det här steget är sidan för e-post entitet kritisk till det sista steget *– åtgärd*.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-168">When you reach this stage, the email entity page will be critical to the final step—*remediation*.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-169">![Sidan e-post entitet](../../media/threat-explorer-email-entity-page.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-169">![The email entity page](../../media/threat-explorer-email-entity-page.png)</span></span>

> [!TIP]
> <span data-ttu-id="e4dc3-170">Om du vill veta mer om sidan  med en omfattande e-post entitet (som visas nedan på fliken Analys), inklusive resultatet av detonerade bifogade filer, resultat för inkluderade webbadresser och säker förhandsgranskning av e-post, klickar du [här](mdo-email-entity-page.md).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-170">To learn more about the rich email entity page (seen below on the **Analysis** tab), including the results of detonated Attachments, findings for included URLs, and safe Email preview, click [here](mdo-email-entity-page.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-171">![Fliken Analys på sidan e-post entitet](../../media/threat-explorer-analysis-tab.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-171">![Analysis tab of the email entity page](../../media/threat-explorer-analysis-tab.png)</span></span>

### <a name="email-remediation"></a><span data-ttu-id="e4dc3-172">E-postreparation</span><span class="sxs-lookup"><span data-stu-id="e4dc3-172">Email remediation</span></span>

<span data-ttu-id="e4dc3-173">När en sec Ops-person anser att ett e-postmeddelande är ett hot är nästa steg i Utforskaren eller identifiering i realtid att hantera hotet och åtgärda det.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-173">Once a Sec Ops person determines that an email is a threat, the next Explorer or Real-time detection step is dealing with the threat and remediating it.</span></span> <span data-ttu-id="e4dc3-174">Det kan du göra genom att gå tillbaka till Hotutforskaren, markera kryssrutan för problemmeddelandet och använda **knappen** Åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-174">This can be done by returning to Threat Explorer, selecting the checkbox for the problem email, and using the **Actions** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-175">![Knappen Åtgärder i Utforskaren med hot](../../media/threat-explorer-email-actions-button.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-175">![Actions button in Threat Explorer](../../media/threat-explorer-email-actions-button.png)</span></span>

<span data-ttu-id="e4dc3-176">Här kan analytikern vidta åtgärder som att rapportera e-post som skräppost, nätfiske eller skadlig kod, kontakta mottagare eller ytterligare undersökningar som kan omfatta utlösa spelböcker för automatisk undersökning och svar (eller AIR) (om du har abonnemang 2).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-176">Here, the analyst can take actions like reporting the mail as Spam, Phishing, or Malware, contacting recipients, or further investigations that can include triggering Automated Investigation and Response (or AIR) playbooks (if you have Plan 2).</span></span> <span data-ttu-id="e4dc3-177">Eller så kan e-posten rapporteras som ren.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-177">Or, the mail can also be reported as clean.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-178">![Listrutan Åtgärder](../../media/threat-explorer-email-actions-drop-down.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-178">![The Actions drop down](../../media/threat-explorer-email-actions-drop-down.png)</span></span>

## <a name="improvements-to-threat-hunting-experience"></a><span data-ttu-id="e4dc3-179">Förbättringar för att hitta hot</span><span class="sxs-lookup"><span data-stu-id="e4dc3-179">Improvements to threat hunting experience</span></span>

### <a name="alert-id"></a><span data-ttu-id="e4dc3-180">Aviserings-ID</span><span class="sxs-lookup"><span data-stu-id="e4dc3-180">Alert ID</span></span>

<span data-ttu-id="e4dc3-181">När du navigerar från en avisering till **Hotutforskaren filtreras** vyn med **aviserings-ID**.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-181">When navigating from an alert into Threat Explorer, the **View** will be filtered by **Alert ID**.</span></span> <span data-ttu-id="e4dc3-182">Det här gäller även vid identifiering i realtid.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-182">This also applies in Real-time detection.</span></span> <span data-ttu-id="e4dc3-183">Meddelanden som är relevanta för den specifika aviseringen och en summa för e-post (antal) visas.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-183">Messages relevant to the specific alert, and an email total (a count) are shown.</span></span> <span data-ttu-id="e4dc3-184">Du kan se om ett meddelande var en del av en avisering och även navigera från det meddelandet till den relaterade aviseringen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-184">You will be able to see if a message was part of an alert, as well as navigate from that message to the related alert.</span></span>

<span data-ttu-id="e4dc3-185">Slutligen inkluderas aviserings-ID i URL:en, till exempel: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span><span class="sxs-lookup"><span data-stu-id="e4dc3-185">Finally, alert ID is included in the URL, for example: `https://protection.office.com/viewalerts?id=372c9b5b-a6c3-5847-fa00-08d8abb04ef1`</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-186">![Filtrera efter aviserings-ID](../../media/AlertID-Filter.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-186">![Filtering for Alert ID](../../media/AlertID-Filter.png)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-187">![Aviserings-ID i den utfällade informationen](../../media/AlertID-DetailsFlyout.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-187">![Alert ID in details flyout](../../media/AlertID-DetailsFlyout.png)</span></span>

### <a name="extending-explorer-and-real-time-detections-data-retention-and-search-limit-for-trial-tenants"></a><span data-ttu-id="e4dc3-188">Utöka databevarandet i Utforskaren (och realtidsidentifiering) och sökbegränsningen för utvärderingsklienter</span><span class="sxs-lookup"><span data-stu-id="e4dc3-188">Extending Explorer (and Real-time detections) data retention and search limit for trial tenants</span></span> 

<span data-ttu-id="e4dc3-189">Som en del av den här ändringen kan analytiker söka efter och filtrera e-postdata i 30 dagar (ökad från sju dagar) i Threat Explorer och realtidsidentifiering för både Defender för Office P1- och P2-utvärderingsklienter.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-189">As part of this change, analysts will be able to search for, and filter email data across 30 days (increased from seven days) in Threat Explorer and Real-time detections for both Defender for Office P1 and P2 trial tenants.</span></span> <span data-ttu-id="e4dc3-190">Detta påverkar inte några produktionsklienter för både P1- och P2 E5-kunder, där standardinställningen för bevarande redan är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-190">This doesn’t impact any production tenants for both P1 and P2 E5 customers, where the retention default is already 30 days.</span></span>

### <a name="updated-export-limit"></a><span data-ttu-id="e4dc3-191">Uppdaterad exportgräns</span><span class="sxs-lookup"><span data-stu-id="e4dc3-191">Updated Export limit</span></span> 

<span data-ttu-id="e4dc3-192">Antalet e-postposter som kan exporteras från Threat Explorer är nu 200 000 (var 9990).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-192">The number of Emails records that can be exported from Threat Explorer is now 200,000 (was 9990).</span></span> <span data-ttu-id="e4dc3-193">Uppsättningen kolumner som kan exporteras ändras inte.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-193">The set of columns that can be exported is unchanged.</span></span> 

### <a name="tags-in-threat-explorer"></a><span data-ttu-id="e4dc3-194">Taggar i Hotutforskaren</span><span class="sxs-lookup"><span data-stu-id="e4dc3-194">Tags in Threat Explorer</span></span>

> [!NOTE]
> <span data-ttu-id="e4dc3-195">Funktionen med användartaggar är en förhandsversion och kanske inte tillgänglig för alla.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-195">The user tags feature is in Preview and may not be available to everyone.</span></span> <span data-ttu-id="e4dc3-196">Förhandsgranskningar kan också komma att ändras.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-196">Also, Previews are subject to change.</span></span> <span data-ttu-id="e4dc3-197">Mer information om versionsschemat finns i översikten över Microsoft 365 version.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-197">For information about the release schedule, check out the Microsoft 365 roadmap.</span></span>

<span data-ttu-id="e4dc3-198">Användartaggar identifierar specifika användargrupper i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-198">User tags identify specific groups of users in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e4dc3-199">Mer information om taggar, inklusive licensiering och konfiguration, finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-199">For more information about tags, including licensing and configuration, see [User tags](user-tags.md).</span></span>

<span data-ttu-id="e4dc3-200">I Hotutforskaren kan du se information om användartaggar i följande funktioner.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-200">In Threat Explorer, you can see information about user tags in the following experiences.</span></span>

#### <a name="email-grid-view"></a><span data-ttu-id="e4dc3-201">Rutnätsvyn för e-post</span><span class="sxs-lookup"><span data-stu-id="e4dc3-201">Email grid view</span></span>

<span data-ttu-id="e4dc3-202">När analytiker tittar på **kolumnen Taggar** i e-postrutnätet ser de alla taggar som har tillämpats på avsändares eller mottagares postlådor.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-202">When analysts look at the **Tags** column the email grid, they are seeing all tags that have been applied to sender or recipient mailboxes.</span></span> <span data-ttu-id="e4dc3-203">Som standard visas systemtaggar *som prioritetskonton* först.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-203">By default, system tags like *priority accounts* are shown first.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-204">![Filtertaggar i rutnätsvyn för e-post](../../media/tags-grid.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-204">![Filter tags in email grid view](../../media/tags-grid.png)</span></span>

#### <a name="filtering"></a><span data-ttu-id="e4dc3-205">Filtrera</span><span class="sxs-lookup"><span data-stu-id="e4dc3-205">Filtering</span></span>

<span data-ttu-id="e4dc3-206">Taggar kan användas som filter.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-206">Tags can be used as filters.</span></span> <span data-ttu-id="e4dc3-207">Jaga endast bland prioritetskonton eller använd specifika användartaggsscenarier på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-207">Hunt among priority accounts only, or use specific user tags scenarios this way.</span></span> <span data-ttu-id="e4dc3-208">Du kan också utesluta resultat som har vissa taggar.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-208">You can also exclude results that have certain tags.</span></span> <span data-ttu-id="e4dc3-209">Kombinera taggar med andra filter och datumintervall för att begränsa undersökningens omfattning.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-209">Combine Tags with other filters and date ranges to narrow your scope of investigation.</span></span> 

<span data-ttu-id="e4dc3-210">[![Filtertaggar](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-210">[![Filter tags](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-211">![Inte filtertaggar](../../media/tags-filter-not.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-211">![Not filter tags](../../media/tags-filter-not.png)</span></span>

#### <a name="email-detail-flyout"></a><span data-ttu-id="e4dc3-212">Utfällblad för e-postinformation</span><span class="sxs-lookup"><span data-stu-id="e4dc3-212">Email detail flyout</span></span>

<span data-ttu-id="e4dc3-213">Om du vill visa de enskilda taggarna för avsändare och mottagare väljer du ett e-postmeddelande för att öppna den utfällade meddelandeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-213">To view the individual tags for sender and recipient, select an email to open the message details flyout.</span></span> <span data-ttu-id="e4dc3-214">På fliken **Sammanfattning** visas taggarna för avsändare och mottagare separat.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-214">On the **Summary** tab, the sender and recipient tags are shown separately.</span></span> <span data-ttu-id="e4dc3-215">Informationen om enskilda taggar för avsändare och mottagare kan exporteras som CSV-data.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-215">The information about individual tags for sender and recipient can be exported as CSV data.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-216">![Taggar för e-postinformation](../../media/tags-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-216">![Email Details tags](../../media/tags-flyout.png)</span></span>

<span data-ttu-id="e4dc3-217">Information om taggar visas också i den utfällade URL-klickningen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-217">Tags information is also shown in the URL clicks flyout.</span></span> <span data-ttu-id="e4dc3-218">Du kan visa den i vyn Phish eller All e-> **url-adresser** **eller fliken URL-klickningar.** Välj en enskild utfällsida för URL om du vill se mer information om klickningar för URL-adressen, inklusive eventuella taggar som är kopplade till den klickningen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-218">To see it, go to Phish or All Email view > **URLs** or **URL Clicks** tab. Select an individual URL flyout to see additional details about clicks for that URL, including any Tags associated with that click.</span></span>

### <a name="updated-timeline-view"></a><span data-ttu-id="e4dc3-219">Uppdaterad tidslinjevy</span><span class="sxs-lookup"><span data-stu-id="e4dc3-219">Updated Timeline View</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-220">![URL-taggar](../../media/tags-urls.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-220">![URL tags](../../media/tags-urls.png)</span></span>
>
<span data-ttu-id="e4dc3-221">Lär dig mer genom att titta på [den här videon](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span><span class="sxs-lookup"><span data-stu-id="e4dc3-221">Learn more by watching [this video](https://www.youtube.com/watch?v=UoVzN0lYbfY&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=4).</span></span>

## <a name="extended-capabilities"></a><span data-ttu-id="e4dc3-222">Utökade funktioner</span><span class="sxs-lookup"><span data-stu-id="e4dc3-222">Extended capabilities</span></span>

### <a name="top-targeted-users"></a><span data-ttu-id="e4dc3-223">Mest riktade användare</span><span class="sxs-lookup"><span data-stu-id="e4dc3-223">Top targeted users</span></span>

<span data-ttu-id="e4dc3-224">Populära programfamiljer för skadlig **programvara visar de mest riktade användarna** i avsnittet Om skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-224">Top Malware Families shows the **top targeted users** in the Malware section.</span></span> <span data-ttu-id="e4dc3-225">De mest riktade användarna kommer även att utökas genom vyerna Phish och All e-post.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-225">Top targeted users will be extended through Phish and All Email views too.</span></span> <span data-ttu-id="e4dc3-226">Analytiker kommer att kunna se de fem viktigaste användarna, tillsammans med antalet försök för varje användare i varje vy.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-226">Analysts will be able to see the top-five targeted users, along with the number of attempts for each user in each view.</span></span> 

<span data-ttu-id="e4dc3-227">Säkerhetsåtgärder användarna kan exportera listan med riktade användare, upp till en gräns på 3 000, tillsammans med antalet försök som gjorts, för offlineanalys för varje e-postvy.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-227">Security operations people be able to export the list of targeted users, up to a limit of 3,000, along with the number of attempts made, for offline analysis for each email view.</span></span> <span data-ttu-id="e4dc3-228">Om du väljer antalet försök (till exempel 13 försök i bilden nedan) öppnas en filtrerad vy i Hotutforskaren, så att du kan se mer information om e-postmeddelanden och hot för den användaren.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-228">Also, selecting the number of attempts (for example, 13 attempts in the image below) will open a filtered view in Threat Explorer, so you can see more details across emails, and threats for that user.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-229">![Mest riktade användare](../../media/Top_Targeted_Users.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-229">![Top targeted users](../../media/Top_Targeted_Users.png)</span></span>

### <a name="exchange-transport-rules"></a><span data-ttu-id="e4dc3-230">Exchange för transport</span><span class="sxs-lookup"><span data-stu-id="e4dc3-230">Exchange transport rules</span></span>

<span data-ttu-id="e4dc3-231">Säkerhetsgruppen kommer att kunna se alla transportregler (Exchange eller E-postflödesregler) som tillämpas på ett meddelande i rutnätsvyn för e-post.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-231">The security operations team will be able to see all the Exchange transport rules (or Mail flow rules) applied to a message, in the Email grid view.</span></span> <span data-ttu-id="e4dc3-232">Välj **Kolumnalternativ** i rutnätet och välj **sedan Exchange för Transportregel** bland kolumnalternativen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-232">Select **Column options** in the grid and then **Add Exchange Transport Rule** from the column options.</span></span> <span data-ttu-id="e4dc3-233">Alternativet Exchange För transportregler visas också på den utfällbara **informationen** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-233">The Exchange transport rules option is also visible on the **Details** flyout in the email.</span></span> 

<span data-ttu-id="e4dc3-234">Namn och GUID för transportregler som tillämpas på meddelandet visas.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-234">Names and GUIDs of the transport rules applied to the message appear.</span></span> <span data-ttu-id="e4dc3-235">Analytiker kan söka efter meddelanden med hjälp av namnet på transportregeln.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-235">Analysts will be able to search for messages by using the name of the transport rule.</span></span> <span data-ttu-id="e4dc3-236">Det här är en CONTAINS-sökning, vilket innebär att det även går att göra partiella sökningar.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-236">This is a CONTAINS search, which means you can do partial searches as well.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e4dc3-237">Exchange med transportregelsökning och namntillgänglighet beror på vilken roll du har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-237">Exchange transport rule search and name availability depend on the specific role assigned to you.</span></span> <span data-ttu-id="e4dc3-238">Du måste ha någon av följande roller eller behörigheter för att visa transportregelnamn och sökning.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-238">You need to have one of the following roles or permissions to view the transport rule names and search.</span></span> <span data-ttu-id="e4dc3-239">Men även utan rollerna eller behörigheterna nedan kan en analytiker se transportregeletiketten och GUID-informationen i e-postinformationen.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-239">However, even without the roles or permissions below, an analyst may see the transport rule label and GUID information in the Email Details.</span></span> <span data-ttu-id="e4dc3-240">Andra funktioner för postvisning i e-postrutnät, utfällningar av e-post, filter och export påverkas inte.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-240">Other record-viewing experiences in Email Grids, Email flyouts, Filters, and Export are not affected.</span></span>
>
> - <span data-ttu-id="e4dc3-241">Exchange Online Endast – skydd mot dataförlust: alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-241">Exchange Online Only - Data Loss Prevention: All</span></span>
> - <span data-ttu-id="e4dc3-242">Exchange Online Endast – O365SupportViewConfig: Alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-242">Exchange Online Only - O365SupportViewConfig: All</span></span>
> - <span data-ttu-id="e4dc3-243">Microsoft Azure Active Directory eller Exchange Online – säkerhetsadministratör: Alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-243">Microsoft Azure Active Directory or Exchange Online - Security Admin: All</span></span>
> - <span data-ttu-id="e4dc3-244">Azure Active Directory eller Exchange Online – Säkerhetsläsare: Alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-244">Azure Active Directory or Exchange Online - Security Reader: All</span></span>
> - <span data-ttu-id="e4dc3-245">Exchange Online Endast – Transportregler: Alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-245">Exchange Online Only - Transport Rules: All</span></span>
> - <span data-ttu-id="e4dc3-246">Exchange Online Endast – View-Only konfiguration: Alla</span><span class="sxs-lookup"><span data-stu-id="e4dc3-246">Exchange Online Only - View-Only Configuration: All</span></span>
>
> <span data-ttu-id="e4dc3-247">I e-postrutnätet, den utfällliga listan Information och Exporterad CSV visas ETR-trafikerna med ett Namn/GUID enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-247">Within the email grid, Details flyout, and Exported CSV, the ETRs are presented with a Name/GUID as shown below.</span></span>
>
> > [!div class="mx-imgBorder"]
> > <span data-ttu-id="e4dc3-248">![Exchange Transportregler](../../media/ETR_Details.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-248">![Exchange Transport Rules](../../media/ETR_Details.png)</span></span>

### <a name="inbound-connectors"></a><span data-ttu-id="e4dc3-249">Inkommande kopplingar</span><span class="sxs-lookup"><span data-stu-id="e4dc3-249">Inbound connectors</span></span>

<span data-ttu-id="e4dc3-250">Kopplingar är en samling instruktioner som anpassar hur din e-post flödar till och från din Microsoft 365 eller Office 365 organisation.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-250">Connectors are a collection of instructions that customize how your email flows to and from your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="e4dc3-251">De gör att du kan tillämpa alla säkerhetsbegränsningar eller kontroller.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-251">They enable you to apply any security restrictions or controls.</span></span> <span data-ttu-id="e4dc3-252">I Hotutforskaren kan du visa kopplingar som är relaterade till ett e-postmeddelande och söka efter e-postmeddelanden med hjälp av kopplingsnamn.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-252">In Threat Explorer, you can view the connectors that are related to an email and search for emails using connector names.</span></span> 

<span data-ttu-id="e4dc3-253">Sökningen efter kopplingar är en CONTAINS-fråga, vilket innebär att partiella nyckelordssökningar kan fungera:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-253">The search for connectors is a CONTAINS query, which means partial keyword searches can work:</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4dc3-254">![Kopplingsinformation](../../media/Connector_Details.png)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-254">![Connector details](../../media/Connector_Details.png)</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e4dc3-255">Obligatoriska licenser och behörigheter</span><span class="sxs-lookup"><span data-stu-id="e4dc3-255">Required licenses and permissions</span></span>

<span data-ttu-id="e4dc3-256">Du måste ha [Microsoft Defender Office 365](defender-for-office-365.md) kunna använda Utforskaren eller identifiering i realtid.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-256">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use Explorer or Real-time detections.</span></span>

- <span data-ttu-id="e4dc3-257">Utforskaren ingår i Defender för Office 365 abonnemang 2.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-257">Explorer is included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="e4dc3-258">Rapporten Identifieringar i realtid ingår i Defender för Office 365 abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-258">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>
- <span data-ttu-id="e4dc3-259">Planera att tilldela licenser till alla användare som ska skyddas av Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-259">Plan to assign licenses for all users who should be protected by Defender for Office 365.</span></span> <span data-ttu-id="e4dc3-260">I Utforskaren och identifiering i realtid visas identifieringsdata för licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="e4dc3-260">Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="e4dc3-261">Om du vill visa och använda Utforskaren eller Identifieringar i realtid måste du ha följande:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-261">To view and use Explorer or Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="e4dc3-262">För Säkerhets- & Efterlevnadscenter:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-262">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="e4dc3-263">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="e4dc3-263">Organization Management</span></span>
  - <span data-ttu-id="e4dc3-264">Säkerhetsadministratör (det här kan tilldelas Azure Active Directory administrationscentret ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="e4dc3-264">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="e4dc3-265">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="e4dc3-265">Security Reader</span></span>

- <span data-ttu-id="e4dc3-266">För Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-266">For Exchange Online:</span></span>

  - <span data-ttu-id="e4dc3-267">Organisationshantering</span><span class="sxs-lookup"><span data-stu-id="e4dc3-267">Organization Management</span></span>
  - <span data-ttu-id="e4dc3-268">View-Only organisationshantering</span><span class="sxs-lookup"><span data-stu-id="e4dc3-268">View-Only Organization Management</span></span>
  - <span data-ttu-id="e4dc3-269">View-Only mottagare</span><span class="sxs-lookup"><span data-stu-id="e4dc3-269">View-Only Recipients</span></span>
  - <span data-ttu-id="e4dc3-270">Efterlevnadshantering</span><span class="sxs-lookup"><span data-stu-id="e4dc3-270">Compliance Management</span></span>

<span data-ttu-id="e4dc3-271">Mer information om roller och behörigheter finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="e4dc3-271">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="e4dc3-272">Behörigheter i Säkerhets- och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="e4dc3-272">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="e4dc3-273">Funktionsbehörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4dc3-273">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="e4dc3-274">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4dc3-274">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="e4dc3-275">Mer information</span><span class="sxs-lookup"><span data-stu-id="e4dc3-275">More information</span></span>

- [<span data-ttu-id="e4dc3-276">Hitta och undersöka skadlig e-post som har levererats</span><span class="sxs-lookup"><span data-stu-id="e4dc3-276">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md) 
- [<span data-ttu-id="e4dc3-277">Visa skadliga filer som upptäckts SharePoint Online, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e4dc3-277">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md) 
- [<span data-ttu-id="e4dc3-278">Få en översikt över vyerna i Hotutforskaren (och identifieringar i realtid)</span><span class="sxs-lookup"><span data-stu-id="e4dc3-278">Get an overview of the views in Threat Explorer (and Real-time detections)</span></span>](threat-explorer-views.md) 
- [<span data-ttu-id="e4dc3-279">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="e4dc3-279">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report) 
- [<span data-ttu-id="e4dc3-280">Automatisk undersökning och svar i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e4dc3-280">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md) 
- [<span data-ttu-id="e4dc3-281">Undersöka e-postmeddelanden med sidan E-post entitet</span><span class="sxs-lookup"><span data-stu-id="e4dc3-281">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)