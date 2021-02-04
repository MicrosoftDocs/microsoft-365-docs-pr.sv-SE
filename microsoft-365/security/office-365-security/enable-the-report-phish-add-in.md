---
title: Aktivera tillägget Rapportt phish
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
description: Läs om hur du aktiverar tillägget Rapport nätfiske för Outlook och Outlook på webben för enskilda användare eller hela organisationen.
ms.openlocfilehash: abac24e447d0afe9bc725dd8f9a976dce900b278
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094683"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="c9d1a-103">Aktivera tillägget för att rapportera nätfiske</span><span class="sxs-lookup"><span data-stu-id="c9d1a-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c9d1a-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c9d1a-105">Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c9d1a-106">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c9d1a-107">Microsoft använder dessa inskickade e-postmeddelanden för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c9d1a-108">Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="c9d1a-109">Den här informationen visas i [säkerhetspanelen](security-dashboard.md) och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="c9d1a-110">Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att skydd mot nätfiskeprinciper kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="c9d1a-111">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c9d1a-112">Om du vill att användarna ska rapportera både skräppost och nätfiske ska du distribuera tillägget Rapportmeddelande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="c9d1a-113">Mer information finns i [Aktivera tillägget Rapportmeddelande.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="c9d1a-114">Med tillägget Rapport nätfiske kan du endast rapportera nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="c9d1a-115">Administratörer kan aktivera tillägget Rapport nätfiske för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c9d1a-116">Om du är enskild användare kan du aktivera tillägget Nätfiske för [dig själv.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="c9d1a-117">Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-phishing-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapport nätfiske för din organisation.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="c9d1a-118">Rapportens nätfiskeAdd-In är nu tillgänglig via [centraliserad distribution.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c9d1a-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c9d1a-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c9d1a-120">Tillägget Nätfiskerapport fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c9d1a-121">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c9d1a-121">Outlook on the web</span></span>
  - <span data-ttu-id="c9d1a-122">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="c9d1a-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c9d1a-123">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="c9d1a-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c9d1a-124">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="c9d1a-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c9d1a-125">Outlook-appen för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="c9d1a-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c9d1a-126">Tillägget Rapportfiske är inte tillgängligt för postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-126">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c9d1a-127">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c9d1a-128">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c9d1a-129">Din befintliga webbläsare bör fungera med tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="c9d1a-130">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova med en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c9d1a-131">För organisationsinstallationer måste organisationen vara konfigurerad för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c9d1a-132">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c9d1a-133">Administratörer måste vara medlemmar i rollgruppen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c9d1a-134">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c9d1a-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="c9d1a-135">Skaffa tillägget Nätfiske för dig själv</span><span class="sxs-lookup"><span data-stu-id="c9d1a-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="c9d1a-136">Gå till Microsoft AppSource och <https://appsource.microsoft.com/marketplace/apps> sök efter tillägget Rapportfiske.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="c9d1a-137">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="c9d1a-138">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c9d1a-139">Logga in med ditt arbets- eller skolkonto (för företag) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="c9d1a-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c9d1a-140">När tillägget är installerat och aktiverat visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c9d1a-141">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-141">In Outlook, the icon looks like this:</span></span>

  ![Ikon för tillägget Rapport om nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c9d1a-143">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook på webben- och nätfiskeikonen](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="c9d1a-145">Skaffa och aktivera tillägget Rapport nätfiske för din organisation</span><span class="sxs-lookup"><span data-stu-id="c9d1a-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c9d1a-146">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c9d1a-147">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="c9d1a-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c9d1a-148">Välj **Distribuera tillägg överst** på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c9d1a-150">Granska informationen **i den utfällbaserade menyn** Distribuera ett nytt tillägg som visas och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c9d1a-151">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-151">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c9d1a-153">På sidan Välj **tillägg som visas** klickar  du i sökrutan, anger nätfiskerapport och klickar sedan på  ![ sökikonen. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c9d1a-154">I listan med resultat går du till **Rapport nätfiske** och klickar sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="c9d1a-155">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c9d1a-156">På **sidan Konfigurera tillägg som** visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c9d1a-157">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c9d1a-158">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="c9d1a-159">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="c9d1a-160">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-160">**Just me**</span></span>

   - <span data-ttu-id="c9d1a-161">**Distributionsmetod:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c9d1a-162">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c9d1a-163">**Tillgängligt:** Användare kan installera tillägget **på Startsidan** Få administratör \>  \> **hanterade tillägg.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c9d1a-164">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="c9d1a-165">Klicka på Distribuera när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c9d1a-166">På sidan **Distribuera rapport nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c9d1a-167">Klicka på Nästa när du har läst **informationen.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="c9d1a-168">Granska **informationen på sidan Presentera** tillägg som visas och klicka sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="c9d1a-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="c9d1a-169">Lär dig hur du använder tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="c9d1a-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="c9d1a-170">Personer som har tilldelats tillägget ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c9d1a-171">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-171">In Outlook, the icon looks like this:</span></span>

  ![Ikon för tillägget Rapport om nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="c9d1a-173">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för tillägget Nätfiske i Outlook på webben](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="c9d1a-175">Granska eller redigera inställningar för tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="c9d1a-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="c9d1a-176">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="c9d1a-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c9d1a-177">Leta upp och **välj tillägget Rapport** nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="c9d1a-178">I den **utfällblad** för Redigera rapport nätfiske som visas, granskar och redigerar inställningar efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c9d1a-179">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c9d1a-180">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="c9d1a-180">View and review reported messages</span></span>

<span data-ttu-id="c9d1a-181">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="c9d1a-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c9d1a-182">Använd administrationsportalen för inskickade material.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c9d1a-183">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c9d1a-184">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c9d1a-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c9d1a-185">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c9d1a-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
