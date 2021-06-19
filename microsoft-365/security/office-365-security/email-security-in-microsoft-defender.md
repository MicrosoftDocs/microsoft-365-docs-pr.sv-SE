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
ms.openlocfilehash: 917ad3caf96a982df8b88058ff1c394b3d21dd75
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028562"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a><span data-ttu-id="b29c2-103">E-postsäkerhet med Threat Explorer i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="b29c2-103">Email security with Threat Explorer in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="b29c2-104">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="b29c2-104">In this article:</span></span>

- [<span data-ttu-id="b29c2-105">Visa skadlig programvara som upptäckts i e-post</span><span class="sxs-lookup"><span data-stu-id="b29c2-105">View malware detected in email</span></span>](#view-malware-detected-in-email)
- [<span data-ttu-id="b29c2-106">Visa nätfiske-URL och klicka på bedömningsdata</span><span class="sxs-lookup"><span data-stu-id="b29c2-106">View phishing URL and click verdict data</span></span>](#view-phishing-url-and-click-verdict-data)
- [<span data-ttu-id="b29c2-107">Starta automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="b29c2-107">Start automated investigation and response</span></span>](#start-automated-investigation-and-response)

> [!NOTE]
> <span data-ttu-id="b29c2-108">Det här är en del av en **3-artikelserie** om grunderna för identifiering av  **hotutforskaren (Explorer),** e-postsäkerhet och Utforskaren och **realtidsidentifiering** (till exempel skillnader mellan verktygen och behörigheter som krävs för att hantera dem).</span><span class="sxs-lookup"><span data-stu-id="b29c2-108">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="b29c2-109">De andra två artiklarna i den här serien [är Grunderna i Hotutforskaren](threat-hunting-in-threat-explorer.md) och Hotutforskaren och [Realtidsidentifiering.](real-time-detections.md)</span><span class="sxs-lookup"><span data-stu-id="b29c2-109">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Threat Explorer and Real-time detections basics](real-time-detections.md).</span></span> 

<span data-ttu-id="b29c2-110">I den här artikeln förklarar vi hur du visar och undersöker skadlig kod och nätfiskeförsök som identifieras i e-Microsoft 365 säkerhetsfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="b29c2-110">This article explains how to view and investigate malware and phishing attempts that are detected in email by Microsoft 365 security features.</span></span> 

<span data-ttu-id="b29c2-111">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="b29c2-111">**Applies to**</span></span>

- [<span data-ttu-id="b29c2-112">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="b29c2-112">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b29c2-113">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b29c2-113">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a><span data-ttu-id="b29c2-114">Visa skadlig programvara som upptäckts i e-post</span><span class="sxs-lookup"><span data-stu-id="b29c2-114">View malware detected in email</span></span>

<span data-ttu-id="b29c2-115">Om du vill se skadlig programvara som upptäckts [](threat-explorer-views.md#email--malware) i e-Microsoft 365 efter teknik använder du vyn E> program för skadlig programvara i Utforskaren (eller identifieringar i realtid).</span><span class="sxs-lookup"><span data-stu-id="b29c2-115">To see malware detected in email sorted by Microsoft 365 technology, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or Real-time detections).</span></span> <span data-ttu-id="b29c2-116">Skadlig programvara är standardvyn, så den kan väljas så fort du öppnar Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="b29c2-116">Malware is the default view, so it may be selected as soon as you open Explorer.</span></span>

1. <span data-ttu-id="b29c2-117">I Microsoft 365 Defender () <https://security.microsoft.com> väljer du **E-& för samarbete** \> **i Utforskaren** (eller **Identifieringar i realtid).**</span><span class="sxs-lookup"><span data-stu-id="b29c2-117">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="b29c2-118">(I det här exemplet används Utforskaren.) Om du är i den konvergerade Microsoft 365 Defender (bläddra https://security.microsoft.com/) till Skicka e-& **med samarbetsutforskaren**  >  .</span><span class="sxs-lookup"><span data-stu-id="b29c2-118">(This example uses Explorer.) If you're in the converged Microsoft 365 Defender portal (https://security.microsoft.com/) scroll to **Email & collaboration** > **Explorer**.</span></span>

   <span data-ttu-id="b29c2-119">Härifrån börjar du med visa, väljer en viss tidsperiod att undersöka (om det behövs) och fokuserar dina filter, enligt [Utforskarens genomgång.](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)</span><span class="sxs-lookup"><span data-stu-id="b29c2-119">From here, start at the View, choose a particular frame of time to investigate (if needed), and focus your filters, as per the [Explorer walk- through](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through).</span></span>

2. <span data-ttu-id="b29c2-120">I **visa-menyn** väljer du Skadlig **programvara** under **E-post.**</span><span class="sxs-lookup"><span data-stu-id="b29c2-120">In the **View** menu, choose **Malware** under **Email**.</span></span>

3. <span data-ttu-id="b29c2-121">Klicka **på Avsändare** och välj sedan **Enkel** \> **identifieringsteknik.**</span><span class="sxs-lookup"><span data-stu-id="b29c2-121">Click **Sender**, and then choose **Basic** \> **Detection technology**.</span></span>

   
   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="teknik för identifiering av skadlig programvara":::

   <span data-ttu-id="b29c2-123">Dina identifieringstekniker är nu tillgängliga som filter för rapporten.</span><span class="sxs-lookup"><span data-stu-id="b29c2-123">Your detection technologies are now available as filters for the report.</span></span>

4. <span data-ttu-id="b29c2-124">Välj ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="b29c2-124">Choose an option.</span></span> <span data-ttu-id="b29c2-125">Välj sedan knappen **Uppdatera** för att använda filtret.</span><span class="sxs-lookup"><span data-stu-id="b29c2-125">Then select the **Refresh** button to apply that filter.</span></span>

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="vald identifieringsteknik"::: 

   <span data-ttu-id="b29c2-127">Rapporten uppdateras för att visa resultat som skadlig programvara upptäckt i e-post med hjälp av det teknikalternativ som du valt.</span><span class="sxs-lookup"><span data-stu-id="b29c2-127">The report refreshes to show the results that malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="b29c2-128">Härifrån kan du göra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="b29c2-128">From here, you can conduct further analysis.</span></span> 

## <a name="view-phishing-url-and-click-verdict-data"></a><span data-ttu-id="b29c2-129">Visa nätfiske-URL och klicka på bedömningsdata</span><span class="sxs-lookup"><span data-stu-id="b29c2-129">View phishing URL and click verdict data</span></span>

<span data-ttu-id="b29c2-130">Du kan visa nätfiskeförsök via URL:er i e-postmeddelanden, inklusive en lista över URL:er som tillåts, blockerades och åsidosätts.</span><span class="sxs-lookup"><span data-stu-id="b29c2-130">You can view phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="b29c2-131">Om du vill identifiera url:er som [klickades Valv måste](safe-links.md) länkarna konfigureras.</span><span class="sxs-lookup"><span data-stu-id="b29c2-131">To identify URLs that were clicked, [Safe Links](safe-links.md) must be configured.</span></span> <span data-ttu-id="b29c2-132">Kontrollera att du har Valv [principer](set-up-safe-links-policies.md) för klickningsskydd och loggning av klickning genom att Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="b29c2-132">Make sure that you set up [Safe Links policies](set-up-safe-links-policies.md) for time-of-click protection and logging of click verdicts by Safe Links.</span></span>

<span data-ttu-id="b29c2-133">Om du vill granska webbadresser i meddelanden och klicka på WEBBADRESSer i [   >  **phish-meddelanden**](threat-explorer-views.md#email--phish) använder du e-postvyn Phish i Utforskaren eller identifieringar i realtid.</span><span class="sxs-lookup"><span data-stu-id="b29c2-133">To review phish URLs in messages and clicks on URLs in phish messages, use the [**Email** > **Phish**](threat-explorer-views.md#email--phish) view of Explorer or Real-time detections.</span></span>

1. <span data-ttu-id="b29c2-134">I Microsoft 365 Defender () <https://security.microsoft.com> väljer du **E-& för samarbete** \> **i Utforskaren** (eller **Identifieringar i realtid).**</span><span class="sxs-lookup"><span data-stu-id="b29c2-134">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), choose **Email & collaboration** \> **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="b29c2-135">(I det här exemplet används Utforskaren.)</span><span class="sxs-lookup"><span data-stu-id="b29c2-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="b29c2-136">Välj **E-post**  \> **phish på menyn Visa.**</span><span class="sxs-lookup"><span data-stu-id="b29c2-136">In the **View** menu, choose **Email** \> **Phish**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b29c2-137">![Visa-menyn för Utforskaren i nätfiskekontext](../../media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="b29c2-137">![View menu for Explorer in phishing context](../../media/ExplorerViewEmailPhishMenu.png)</span></span>

3. <span data-ttu-id="b29c2-138">Klicka **på Avsändare** och välj sedan **URL:er Klicka** på \> **Bedömning**.</span><span class="sxs-lookup"><span data-stu-id="b29c2-138">Click **Sender**, and then choose **URLs** \> **Click verdict**.</span></span>

4. <span data-ttu-id="b29c2-139">Välj ett eller flera  alternativ, som Blockerad och Blockera  **åsidosätts,** och välj sedan knappen Uppdatera på samma rad som alternativen för att använda filtret.</span><span class="sxs-lookup"><span data-stu-id="b29c2-139">Select one or more options, such as **Blocked** and **Block overridden**, and then select the **Refresh** button on the same line as the options to apply that filter.</span></span> <span data-ttu-id="b29c2-140">(Uppdatera inte webbläsarfönstret.)</span><span class="sxs-lookup"><span data-stu-id="b29c2-140">(Don't refresh your browser window.)</span></span>

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URL:er och klicka på bedömningar":::

   <span data-ttu-id="b29c2-142">Rapporten uppdateras så att två olika URL-tabeller visas på fliken URL under rapporten:</span><span class="sxs-lookup"><span data-stu-id="b29c2-142">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   - <span data-ttu-id="b29c2-143">**Url:er** är URL:er i de meddelanden som du filtrerat ned till och åtgärden för e-postleverans räknas för varje URL.</span><span class="sxs-lookup"><span data-stu-id="b29c2-143">**Top URLs** are the URLs in the messages that you filtered down to and the email delivery action counts for each URL.</span></span> <span data-ttu-id="b29c2-144">I e-postvyn för phish innehåller den här listan vanligtvis legitima URL:er.</span><span class="sxs-lookup"><span data-stu-id="b29c2-144">In the Phish email view, this list typically contains legitimate URLs.</span></span> <span data-ttu-id="b29c2-145">Attacker kan innehålla en blandning av bra och dåliga URL-adresser i sina meddelanden för att försöka få dem levererade, men de gör skadliga länkar mer intressanta.</span><span class="sxs-lookup"><span data-stu-id="b29c2-145">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they make the malicious links look more interesting.</span></span> <span data-ttu-id="b29c2-146">Tabellen med URL:er sorteras efter totalt antal e-postmeddelanden, men den här kolumnen är dold för att förenkla vyn.</span><span class="sxs-lookup"><span data-stu-id="b29c2-146">The table of URLs is sorted by total email count, but this column is hidden to simplify the view.</span></span>

   - <span data-ttu-id="b29c2-147">**De översta klicken** är Valv Länkar-radbrutna WEBBADRESSer som klickades, sorterade efter totalt antal klick.</span><span class="sxs-lookup"><span data-stu-id="b29c2-147">**Top clicks** are the Safe Links-wrapped URLs that were clicked, sorted by total click count.</span></span> <span data-ttu-id="b29c2-148">Den här kolumnen visas inte heller för att förenkla vyn.</span><span class="sxs-lookup"><span data-stu-id="b29c2-148">This column also isn't displayed, to simplify the view.</span></span> <span data-ttu-id="b29c2-149">Totalt antal efter kolumn anger antalet Valv klickar på antal bedömningsvärden för varje klickad URL.</span><span class="sxs-lookup"><span data-stu-id="b29c2-149">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="b29c2-150">I e-postvyn är det oftast misstänkta eller skadliga URL-adresser.</span><span class="sxs-lookup"><span data-stu-id="b29c2-150">In the Phish email view, these are usually suspicious or malicious URLs.</span></span> <span data-ttu-id="b29c2-151">Men vyn kan innehålla URL:er som inte är hot men som är i phish-meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b29c2-151">But the view could include URLs that aren't threats but are in phish messages.</span></span> <span data-ttu-id="b29c2-152">URL-klick på olästa länkar visas inte här.</span><span class="sxs-lookup"><span data-stu-id="b29c2-152">URL clicks on unwrapped links don't show up here.</span></span>

   <span data-ttu-id="b29c2-153">De två URL-tabellerna visar de viktigaste webbadresserna i nätfiskemeddelanden genom leveransåtgärd och -plats.</span><span class="sxs-lookup"><span data-stu-id="b29c2-153">The two URL tables show top URLs in phishing email messages by delivery action and location.</span></span> <span data-ttu-id="b29c2-154">Tabellerna visar URL-klick som har blockerats eller besökts, trots en varning, så att du kan se vilka potentiella dåliga länkar som visades för användare och att användarna har klickat på dem.</span><span class="sxs-lookup"><span data-stu-id="b29c2-154">The tables show URL clicks that were blocked or visited despite a warning, so you can see what potential bad links were presented to users and that the users clicked.</span></span> <span data-ttu-id="b29c2-155">Härifrån kan du göra ytterligare analyser.</span><span class="sxs-lookup"><span data-stu-id="b29c2-155">From here, you can conduct further analysis.</span></span> <span data-ttu-id="b29c2-156">Under diagrammet kan du till exempel se de översta webbadresserna i e-postmeddelanden som har blockerats i organisationens miljö.</span><span class="sxs-lookup"><span data-stu-id="b29c2-156">For example, below the chart you can see the top URLs in email messages that were blocked in your organization's environment.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b29c2-157">![Url-adresser som har blockerats i Utforskaren](../../media/ExplorerPhishClickVerdictURLs.png)</span><span class="sxs-lookup"><span data-stu-id="b29c2-157">![Explorer URLs that were blocked](../../media/ExplorerPhishClickVerdictURLs.png)</span></span>

   <span data-ttu-id="b29c2-158">Välj en URL för att visa mer detaljerad information.</span><span class="sxs-lookup"><span data-stu-id="b29c2-158">Select a URL to view more detailed information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b29c2-159">I dialogrutan för utfällningsrutan för URL tas filtreringen av e-postmeddelanden bort för att visa den fullständiga visningen av exponering av URL:en i miljön.</span><span class="sxs-lookup"><span data-stu-id="b29c2-159">In the URL flyout dialog box, the filtering on email messages is removed to show the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="b29c2-160">På så sätt kan du filtrera efter e-postmeddelanden som du är orolig för i Utforskaren, hitta specifika WEBBADRESSer som är potentiella hot och sedan utöka förståelsen av exponering av URL-adresser i din miljö (via dialogrutan URL-information) utan att behöva lägga till URL-filter i utforskarvyn.</span><span class="sxs-lookup"><span data-stu-id="b29c2-160">This lets you filter for email messages you're concerned about in Explorer, find specific URLs that are potential threats, and then expand your understanding of the URL exposure in your environment (via the URL details dialog box) without having to add URL filters to the Explorer view itself.</span></span>

### <a name="interpretation-of-click-verdicts"></a><span data-ttu-id="b29c2-161">Tolkning av klickningar</span><span class="sxs-lookup"><span data-stu-id="b29c2-161">Interpretation of click verdicts</span></span>

<span data-ttu-id="b29c2-162">I de utfällliga e-post- eller URL-adresserna, de övre klicken och i våra filtreringsupplevelser visas olika värden för klickning:</span><span class="sxs-lookup"><span data-stu-id="b29c2-162">In the Email or URL flyouts, Top Clicks, and in our filtering experiences, you'll see different click verdict values:</span></span>

- <span data-ttu-id="b29c2-163">**Ingen:** Det går inte att registrera url-adressens bedömning.</span><span class="sxs-lookup"><span data-stu-id="b29c2-163">**None:** Unable to capture the verdict for the URL.</span></span> <span data-ttu-id="b29c2-164">Användaren kan ha klickat via URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-164">The user might have clicked through the URL.</span></span>
- <span data-ttu-id="b29c2-165">**Tillåtet:** Användaren tillåts navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-165">**Allowed:** The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="b29c2-166">**Blockerad:** Användaren blockerades från att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-166">**Blocked:** The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="b29c2-167">**Väntande bedömning:** Användaren visades en sida som väntar på att detonation.</span><span class="sxs-lookup"><span data-stu-id="b29c2-167">**Pending verdict:** The user was presented with the detonation-pending page.</span></span>
- <span data-ttu-id="b29c2-168">**Blockerad åsidosätts:** Användaren blockerades från att navigera direkt till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-168">**Blocked overridden:** The user was blocked from navigating directly to the URL.</span></span> <span data-ttu-id="b29c2-169">Men användaren överränder blocket för att navigera till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-169">But the user overrode the block to navigate to the URL.</span></span>
- <span data-ttu-id="b29c2-170">**Väntande bedömning kringgås:** Användaren visades med detonationssidan.</span><span class="sxs-lookup"><span data-stu-id="b29c2-170">**Pending verdict bypassed:** The user was presented with the detonation page.</span></span> <span data-ttu-id="b29c2-171">Men användaren överränder meddelandet för att få åtkomst till URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-171">But the user overrode the message to access the URL.</span></span>
- <span data-ttu-id="b29c2-172">**Fel:** Användaren visades på felsidan eller så uppstod ett fel vid inspelning av bedömningsfelet.</span><span class="sxs-lookup"><span data-stu-id="b29c2-172">**Error:** The user was presented with the error page, or an error occurred in capturing the verdict.</span></span>
- <span data-ttu-id="b29c2-173">**Fel:** Ett okänt undantag uppstod vid inspelningen av bedömningsfelet.</span><span class="sxs-lookup"><span data-stu-id="b29c2-173">**Failure:** An unknown exception occurred while capturing the verdict.</span></span> <span data-ttu-id="b29c2-174">Användaren kan ha klickat via URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="b29c2-174">The user might have clicked through the URL.</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="b29c2-175">Starta automatisk undersökning och svar</span><span class="sxs-lookup"><span data-stu-id="b29c2-175">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="b29c2-176">Funktioner för automatisk undersökning och svar finns i *Microsoft Defender för Office 365 abonnemang 2* och *Office 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="b29c2-176">Automated investigation and response capabilities are available in *Microsoft Defender for Office 365 Plan 2* and *Office 365 E5*.</span></span>

<span data-ttu-id="b29c2-177">[Med automatiserad undersökning och](automated-investigation-response-office.md) svar kan du spara tid och arbete som utförs i säkerhetsåtgärder mot cyberattacker.</span><span class="sxs-lookup"><span data-stu-id="b29c2-177">[Automated investigation and response](automated-investigation-response-office.md) can save your security operations team time and effort spent investigating and mitigating cyberattacks.</span></span> <span data-ttu-id="b29c2-178">Förutom att konfigurera aviseringar som kan utlösa en säkerhetsspelbok kan du starta en automatiserad undersökning och svarsprocess från en vy i Utforskaren.</span><span class="sxs-lookup"><span data-stu-id="b29c2-178">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> <span data-ttu-id="b29c2-179">Mer information finns i [Exempel: En säkerhetsadministratör utlöser en undersökning från Utforskaren](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span><span class="sxs-lookup"><span data-stu-id="b29c2-179">For details, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="other-articles"></a><span data-ttu-id="b29c2-180">Andra artiklar</span><span class="sxs-lookup"><span data-stu-id="b29c2-180">Other articles</span></span>

[<span data-ttu-id="b29c2-181">Undersöka e-postmeddelanden med sidan E-post entitet</span><span class="sxs-lookup"><span data-stu-id="b29c2-181">Investigate emails with the Email Entity Page</span></span>](mdo-email-entity-page.md)
