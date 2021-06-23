---
title: Aktivera tillägget Rapportfras
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Läs om hur du aktiverar tillägget rapport nätfiske för Outlook Outlook på webben för enskilda användare eller hela organisationen.
ms.openlocfilehash: 44113237274d37aabeda954354182fe4da5aa970
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083422"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="6037a-103">Aktivera tillägget för att rapportera nätfiske</span><span class="sxs-lookup"><span data-stu-id="6037a-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="6037a-104">Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade material i Microsoft 365 Defender postportalen.</span><span class="sxs-lookup"><span data-stu-id="6037a-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="6037a-105">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6037a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="6037a-106">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-post markerad som dålig) eller falska negativa meddelanden (felaktig e-post tillåten) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="6037a-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="6037a-107">Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="6037a-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="6037a-108">Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6037a-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="6037a-109">Den här informationen visas i [säkerhetspanelen](security-dashboard.md) och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="6037a-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="6037a-110">Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="6037a-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="6037a-111">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6037a-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="6037a-112">Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6037a-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="6037a-113">Mer information finns [i Aktivera tillägget Rapportmeddelande.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="6037a-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="6037a-114">Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6037a-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="6037a-115">Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="6037a-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="6037a-116">Om du är enskild användare kan du [aktivera tillägget Rapport nätfiske för dig själv.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="6037a-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="6037a-117">Om du är global administratör eller [Exchange Online-administratör](#get-and-enable-the-report-phishing-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapport nätfiske för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6037a-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="6037a-118">Rapporten nätfiske-Add-In är nu tillgänglig via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="6037a-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6037a-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6037a-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6037a-120">Tillägget Rapport nätfiske fungerar med de flesta Microsoft 365 prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="6037a-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="6037a-121">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="6037a-121">Outlook on the web</span></span>
  - <span data-ttu-id="6037a-122">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="6037a-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="6037a-123">Outlook 2016 för Mac eller senare</span><span class="sxs-lookup"><span data-stu-id="6037a-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="6037a-124">Outlook ingår i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6037a-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="6037a-125">Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="6037a-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="6037a-126">Tillägget Rapport nätfiske är inte tillgängligt för delade postlådor eller postlådor i lokala Exchange organisationer.</span><span class="sxs-lookup"><span data-stu-id="6037a-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="6037a-127">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="6037a-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="6037a-128">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="6037a-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="6037a-129">Din befintliga webbläsare bör fungera med tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6037a-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="6037a-130">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="6037a-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="6037a-131">För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="6037a-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="6037a-132">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="6037a-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="6037a-133">Administratörer måste vara medlemmar i rollgruppen Globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="6037a-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="6037a-134">Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="6037a-134">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="6037a-135">Skaffa tillägget Rapport om nätfiske åt dig själv</span><span class="sxs-lookup"><span data-stu-id="6037a-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="6037a-136">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6037a-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="6037a-137">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="6037a-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="6037a-138">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="6037a-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="6037a-139">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="6037a-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="6037a-140">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="6037a-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="6037a-141">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="6037a-141">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="6037a-143">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="6037a-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook på webben Ikonen för tillägget Nätfiske](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="6037a-145">Hämta och aktivera tillägget Rapport om nätfiske för din organisation</span><span class="sxs-lookup"><span data-stu-id="6037a-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="6037a-146">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6037a-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="6037a-147">I Administrationscenter för Microsoft 365 går du till sidan **Inställningar-tillägg** på . Om du inte ser tilläggssidan går du till länken tillägg för \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Inställningar-integrerade**  appar högst upp på sidan Integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="6037a-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="6037a-148">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6037a-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i Administrationscenter för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="6037a-150">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6037a-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="6037a-151">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="6037a-151">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="6037a-153">På sidan **Välj tillägg som visas** klickar  du i rutan Sök, anger **Rapportfiske** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="6037a-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="6037a-154">Leta rätt på Rapport nätfiske i **listan med resultat och** klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="6037a-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="6037a-155">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="6037a-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="6037a-156">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="6037a-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="6037a-157">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="6037a-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="6037a-158">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="6037a-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="6037a-159">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="6037a-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="6037a-160">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="6037a-160">**Just me**</span></span>

   - <span data-ttu-id="6037a-161">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="6037a-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="6037a-162">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="6037a-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="6037a-163">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="6037a-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="6037a-164">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="6037a-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="6037a-165">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="6037a-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="6037a-166">På sidan **Distribuera nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="6037a-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="6037a-167">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="6037a-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="6037a-168">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="6037a-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="6037a-169">Lär dig hur du använder tillägget Rapport om nätfiske</span><span class="sxs-lookup"><span data-stu-id="6037a-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="6037a-170">Personer som har tilldelats tillägget ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="6037a-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="6037a-171">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="6037a-171">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="6037a-173">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="6037a-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook på ikonen för tillägget Nätfiske](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="6037a-175">Granska eller redigera inställningar för tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="6037a-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="6037a-176">I Administrationscenter för Microsoft 365 går du till sidan **Inställningar-tillägg** på . Om du inte ser tilläggssidan går du till länken tillägg för \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **Inställningar-integrerade**  appar högst upp på sidan Integrerade appar.</span><span class="sxs-lookup"><span data-stu-id="6037a-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="6037a-177">Leta upp och **välj tillägget** Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6037a-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="6037a-178">I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6037a-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="6037a-179">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="6037a-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="6037a-180">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="6037a-180">View and review reported messages</span></span>

<span data-ttu-id="6037a-181">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="6037a-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="6037a-182">Använd portalen för administrationsinskick.</span><span class="sxs-lookup"><span data-stu-id="6037a-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="6037a-183">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="6037a-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="6037a-184">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="6037a-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="6037a-185">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="6037a-185">For instructions, see [Use mail flow rules to see what users are reporting to Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft).</span></span>
