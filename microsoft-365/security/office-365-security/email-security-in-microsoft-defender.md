---
title: E-postsäkerhet med Threat Explorer i Microsoft Defender för Office 365
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
description: Visa och undersöka försök till nätfiske efter skadlig kod.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877902"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="df2e6-103">E-postsäkerhet med Threat Explorer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="df2e6-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="df2e6-104">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="df2e6-104">In this article:</span></span>

- [<span data-ttu-id="df2e6-105">Visa skadlig programvara som upptäckts i e-post</span><span class="sxs-lookup"><span data-stu-id="df2e6-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="df2e6-106">Visa nätfiske-URL och klicka på bedömningsdata</span><span class="sxs-lookup"><span data-stu-id="df2e6-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="df2e6-107">Starta automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="df2e6-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="df2e6-108">Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem).</span><span class="sxs-lookup"><span data-stu-id="df2e6-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="df2e6-109">De andra två artiklarna i den här serien [är Grunderna i Hotutforskaren](threat-hunting-in-threat-explorer.md) och Hotutforskaren och [Realtidsidentifiering.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="df2e6-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="df2e6-110">I den här artikeln förklarar vi hur du visar och undersöker skadlig kod och nätfiskeförsök som identifieras i e-Microsoft 365 säkerhetsfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="df2e6-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="df2e6-111">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="df2e6-111">**Applies to**</span></span>

- [<span data-ttu-id="df2e6-112">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="df2e6-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="df2e6-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df2e6-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="df2e6-114">Visa skadlig programvara som upptäckts i e-post</span><span class="sxs-lookup"><span data-stu-id="df2e6-114">View malware detected in email</span></span>

<span data-ttu-id="df2e6-115">Om du vill se skadlig programvara som upptäckts [](threat-explorer-views.md#email--malware) i e-Microsoft 365 efter teknik använder du vyn E> program för skadlig programvara i Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="df2e6-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="df2e6-116">Skadlig programvara är standardvyn, så den kan väljas så fort du öppnar Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="df2e6-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="df2e6-117">I Säkerhets- & (), <https://protection.office.com> väljer du **Utforskaren för hantering** av hot \>  **(eller identifieringar i realtid).**</span><span class="sxs-lookup"><span data-stu-id="df2e6-117">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="df2e6-118">(I det här exemplet används Utforskaren.)</span><span class="sxs-lookup"><span data-stu-id="df2e6-118">(This example uses Explorer.)</span></span>

   <span data-ttu-id="df2e6-119">Om du är i den konvergerade Microsoft 365 Defender-portalen <https://security.microsoft.com> () bläddrar du till **E-& för samarbete**  >  **i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="df2e6-119">If you're in the converged Microsoft 365 Defender portal (<https://security.microsoft.com>) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="df2e6-120">Härifrån börjar du med visa, väljer en viss tidsperiod att undersöka (om det behövs) och fokuserar dina filter, enligt [Utforskarens genomgång.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="df2e6-120">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="df2e6-121">Välj Skadlig **programvara för** e-post **i visa-menyn.** \> </span><span class="sxs-lookup"><span data-stu-id="df2e6-121">In the **View** menu, choose **Email** \> **Malware**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-122">![Visa-menyn för Utforskaren](../../media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-122">![View menu for Explorer](../../media/ExplorerViewEmailMalwareMenu.png)</span></span>

3. <span data-ttu-id="df2e6-123">Klicka **på Avsändare** och välj sedan **Enkel** \> **identifieringsteknik.**</span><span class="sxs-lookup"><span data-stu-id="df2e6-123">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   <span data-ttu-id="df2e6-124">Dina identifieringstekniker är nu tillgängliga som filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="df2e6-124">Your detection technologies are now available as filters for the report.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-125">![Teknik för identifiering av skadlig programvara](../../media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-125">![Malware detection technologies](../../media/ExplorerEmailMalwareDetectionTech.png)</span></span>

4. <span data-ttu-id="df2e6-126">Välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="df2e6-126">Choose an option.</span></span> <span data-ttu-id="df2e6-127">Välj sedan knappen **Uppdatera** för att använda filtret.</span><span class="sxs-lookup"><span data-stu-id="df2e6-127">Then select the **Refresh** button to apply that filter.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-128">![Vald identifieringsteknik](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-128">![Selected detection technology](../../media/ExplorerEmailMalwareDetectionTechATP.png)</span></span>

   <span data-ttu-id="df2e6-129">Rapporten uppdateras för att visa resultat som skadlig programvara upptäckt i e-post med hjälp av det teknikalternativ som du valt.</span><span class="sxs-lookup"><span data-stu-id="df2e6-129">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="df2e6-130">Härifrån kan du göra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="df2e6-130">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="df2e6-131">Visa nätfiske-URL och klicka på bedömningsdata</span><span class="sxs-lookup"><span data-stu-id="df2e6-131">View phishing URL and click verdict data</span></span>

<span data-ttu-id="df2e6-132">Du kan visa nätfiskeförsök via URL:er i e-postmeddelanden, inklusive en lista över URL:er som tillåts, blockerades och åsidosätts.</span><span class="sxs-lookup"><span data-stu-id="df2e6-132">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="df2e6-133">Om du vill identifiera url:er som [klickades Valv måste](safe-links.md) länkarna konfigureras.</span><span class="sxs-lookup"><span data-stu-id="df2e6-133">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="df2e6-134">Kontrollera att du har Valv [principer](set-up-safe-links-policies.md) för klickningsskydd och loggning av klickning genom att Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="df2e6-134">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="df2e6-135">Om du vill granska webbadresser i meddelanden och klicka på WEBBADRESSer i [   >  **phish-meddelanden**](threat-explorer-views.md#email--phish) använder du e-postvyn Phish i Utforskaren eller identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="df2e6-135">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="df2e6-136">I Säkerhets- & (), <https://protection.office.com> väljer du **Utforskaren för hantering** av hot \>  **(eller identifieringar i realtid).**</span><span class="sxs-lookup"><span data-stu-id="df2e6-136">In the Security & Compliance Center (<https://protection.office.com>), choose **Threat management** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="df2e6-137">(I det här exemplet används Utforskaren.)</span><span class="sxs-lookup"><span data-stu-id="df2e6-137">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="df2e6-138">Välj **E-post**  \> **phish på menyn Visa.**</span><span class="sxs-lookup"><span data-stu-id="df2e6-138">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-139">![Visa-menyn för Utforskaren i nätfiskekontext](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-139">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="df2e6-140">Klicka **på Avsändare** och välj sedan **URL:er Klicka** på \> **Bedömning**.</span><span class="sxs-lookup"><span data-stu-id="df2e6-140">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="df2e6-141">Välj ett eller flera  alternativ, som Blockerad och Blockera  **åsidosätts,** och välj sedan knappen Uppdatera på samma rad som alternativen för att använda filtret.</span><span class="sxs-lookup"><span data-stu-id="df2e6-141">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="df2e6-142">(Uppdatera inte webbläsarfönstret.)</span><span class="sxs-lookup"><span data-stu-id="df2e6-142">(Don't refresh your browser window.)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-143">![URL:er och klicka på bedömningar](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-143">![URLs and click verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span>

   <span data-ttu-id="df2e6-144">Rapporten uppdateras så att två olika URL-tabeller visas på fliken URL under rapporten:</span><span class="sxs-lookup"><span data-stu-id="df2e6-144">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="df2e6-145">**Url:er** är URL:er i de meddelanden som du filtrerat ned till och åtgärden för e-postleverans räknas för varje URL.</span><span class="sxs-lookup"><span data-stu-id="df2e6-145">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="df2e6-146">I e-postvyn för phish innehåller den här listan vanligtvis legitima URL:er.</span><span class="sxs-lookup"><span data-stu-id="df2e6-146">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="df2e6-147">Attacker kan innehålla en blandning av bra och dåliga URL-adresser i sina meddelanden för att försöka få dem levererade, men de gör skadliga länkar mer intressanta.</span><span class="sxs-lookup"><span data-stu-id="df2e6-147">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="df2e6-148">Tabellen med URL:er sorteras efter totalt antal e-postmeddelanden, men den här kolumnen är dold för att förenkla vyn.</span><span class="sxs-lookup"><span data-stu-id="df2e6-148">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="df2e6-149">**De översta klicken** är Valv Länkar-radbrutna WEBBADRESSer som klickades, sorterade efter totalt antal klick.</span><span class="sxs-lookup"><span data-stu-id="df2e6-149">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="df2e6-150">Den här kolumnen visas inte heller för att förenkla vyn.</span><span class="sxs-lookup"><span data-stu-id="df2e6-150">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="df2e6-151">Totalt antal efter kolumn anger antalet Valv klickar på antal bedömningsvärden för varje klickad URL.</span><span class="sxs-lookup"><span data-stu-id="df2e6-151">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="df2e6-152">I e-postvyn är det oftast misstänkta eller skadliga URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="df2e6-152">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="df2e6-153">Men vyn kan innehålla URL:er som inte är hot men som är i phish-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="df2e6-153">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="df2e6-154">URL-klick på olästa länkar visas inte här.</span><span class="sxs-lookup"><span data-stu-id="df2e6-154">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="df2e6-155">De två URL-tabellerna visar de viktigaste webbadresserna i nätfiskemeddelanden genom leveransåtgärd och -plats.</span><span class="sxs-lookup"><span data-stu-id="df2e6-155">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="df2e6-156">Tabellerna visar URL-klick som har blockerats eller besökts, trots en varning, så att du kan se vilka potentiella dåliga länkar som visades för användare och att användarna har klickat på dem.</span><span class="sxs-lookup"><span data-stu-id="df2e6-156">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="df2e6-157">Härifrån kan du göra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="df2e6-157">From here, you can conduct further analysis.</span></span> <span data-ttu-id="df2e6-158">Under diagrammet kan du till exempel se de översta webbadresserna i e-postmeddelanden som har blockerats i organisationens miljö.</span><span class="sxs-lookup"><span data-stu-id="df2e6-158">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="df2e6-159">![Url-adresser som har blockerats i Utforskaren](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="df2e6-159">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="df2e6-160">Välj en URL för att visa mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="df2e6-160">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="df2e6-161">I dialogrutan för utfällningsrutan för URL tas filtreringen av e-postmeddelanden bort för att visa den fullständiga visningen av exponering av URL:en i miljön.</span><span class="sxs-lookup"><span data-stu-id="df2e6-161">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="df2e6-162">På så sätt kan du filtrera efter e-postmeddelanden som du är orolig för i Utforskaren, hitta specifika WEBBADRESSer som är potentiella hot och sedan utöka förståelsen av exponering av URL-adresser i din miljö (via dialogrutan URL-information) utan att behöva lägga till URL-filter i utforskarvyn.</span><span class="sxs-lookup"><span data-stu-id="df2e6-162">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="df2e6-163">Tolkning av klickningar</span><span class="sxs-lookup"><span data-stu-id="df2e6-163">Interpretation of click verdicts</span></span>

<span data-ttu-id="df2e6-164">I de utfällliga e-post- eller URL-adresserna, de övre klicken och i våra filtreringsupplevelser visas olika värden för klickning:</span><span class="sxs-lookup"><span data-stu-id="df2e6-164">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="df2e6-165">**Ingen:** Det går inte att registrera url-adressens bedömning.</span><span class="sxs-lookup"><span data-stu-id="df2e6-165">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="df2e6-166">Användaren kan ha klickat via URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-166">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="df2e6-167">**Tillåtet:** Användaren tillåts navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-167">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="df2e6-168">**Blockerad:** Användaren blockerades från att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-168">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="df2e6-169">**Väntande bedömning:** Användaren visades en sida som väntar på att detonation.</span><span class="sxs-lookup"><span data-stu-id="df2e6-169">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="df2e6-170">**Blockerad åsidosätts:** Användaren blockerades från att navigera direkt till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-170">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="df2e6-171">Men användaren överränder blocket för att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-171">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="df2e6-172">**Väntande bedömning kringgås:** Användaren visades med detonationssidan.</span><span class="sxs-lookup"><span data-stu-id="df2e6-172">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="df2e6-173">Men användaren överränder meddelandet för att få åtkomst till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-173">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="df2e6-174">**Fel:** Användaren visades på felsidan eller så uppstod ett fel vid inspelning av bedömningsfelet.</span><span class="sxs-lookup"><span data-stu-id="df2e6-174">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="df2e6-175">**Fel:** Ett okänt undantag uppstod vid inspelningen av bedömningsfelet.</span><span class="sxs-lookup"><span data-stu-id="df2e6-175">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="df2e6-176">Användaren kan ha klickat via URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2e6-176">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="df2e6-177">Starta automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="df2e6-177">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="df2e6-178">Funktioner för automatisk undersökning och svar finns i *Microsoft Defender för Office 365 abonnemang 2* och *e5 Office 365.*</span><span class="sxs-lookup"><span data-stu-id="df2e6-178">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="df2e6-179">[Med automatiserad undersökning och](automated-investigation-response-office.md) svar kan du spara tid och arbete som utförs i säkerhetsåtgärder mot cyberattacker.</span><span class="sxs-lookup"><span data-stu-id="df2e6-179">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="df2e6-180">Förutom att konfigurera aviseringar som kan utlösa en säkerhetsspelbok kan du starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="df2e6-180">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="df2e6-181">Mer information finns i [Exempel: En säkerhetsadministratör utlöser en undersökning från Utforskaren](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="df2e6-181">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="df2e6-182">Andra artiklar</span><span class="sxs-lookup"><span data-stu-id="df2e6-182">Other articles</span></span>

[<span data-ttu-id="df2e6-183">Undersöka e-postmeddelanden med sidan E-post entitet</span><span class="sxs-lookup"><span data-stu-id="df2e6-183">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
