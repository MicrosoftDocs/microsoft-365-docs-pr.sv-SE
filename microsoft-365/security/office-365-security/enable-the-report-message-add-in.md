---
title: Aktivera tillägget för att rapportera meddelande
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Lär dig hur du aktiverar tillägget Rapportmeddelande för Outlook och Outlook på webben för enskilda användare eller hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b21472736cff2fd0eed7da5495ab6aae597032f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094861"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="c16ef-103">Aktivera tillägget för att rapportera meddelande</span><span class="sxs-lookup"><span data-stu-id="c16ef-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="c16ef-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="c16ef-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c16ef-105">Mer information finns i Använda [administrationsinskick för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="c16ef-106">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden markerade som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="c16ef-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="c16ef-107">Microsoft använder dessa inskickade e-postmeddelanden för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="c16ef-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="c16ef-108">Om personer till exempel rapporterar många meddelanden som flaggats som Skräppost med hjälp av tillägget Rapportmeddelande kan organisationens säkerhetsgrupp behöva justera principerna för [skräppostskydd.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c16ef-109">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c16ef-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="c16ef-110">Om du vill att användarna endast ska rapportera nätfiskemeddelanden distribuerar du tillägget Rapport nätfiske i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c16ef-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="c16ef-111">Mer information finns i [Aktivera tillägget Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="c16ef-112">Med tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c16ef-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="c16ef-113">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="c16ef-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="c16ef-114">Om du är en enskild användare kan [du aktivera tillägget Rapportmeddelande](#get-the-report-message-add-in-for-yourself)för dig själv.</span><span class="sxs-lookup"><span data-stu-id="c16ef-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="c16ef-115">Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för organisationen.</span><span class="sxs-lookup"><span data-stu-id="c16ef-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="c16ef-116">Rapportmeddelandets Add-In nu tillgänglig via [centraliserad distribution.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="c16ef-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c16ef-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c16ef-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c16ef-118">Tillägget Rapportmeddelande fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="c16ef-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="c16ef-119">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c16ef-119">Outlook on the web</span></span>
  - <span data-ttu-id="c16ef-120">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="c16ef-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="c16ef-121">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="c16ef-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="c16ef-122">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="c16ef-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="c16ef-123">Outlook-appen för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="c16ef-123">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="c16ef-124">Tillägget Rapportmeddelande är inte tillgängligt för postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="c16ef-124">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="c16ef-125">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="c16ef-125">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c16ef-126">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-126">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c16ef-127">Din befintliga webbläsare bör fungera med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="c16ef-127">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="c16ef-128">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova med en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="c16ef-128">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="c16ef-129">För organisationsinstallationer måste organisationen vara konfigurerad för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c16ef-129">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="c16ef-130">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-130">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="c16ef-131">Administratörer måste vara medlemmar i rollgruppen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="c16ef-131">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="c16ef-132">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c16ef-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="c16ef-133">Skaffa tillägget Rapportmeddelande åt dig själv</span><span class="sxs-lookup"><span data-stu-id="c16ef-133">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="c16ef-134">Gå till Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="c16ef-134">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="c16ef-135">Gå direkt till tillägget Rapportmeddelande genom att gå <https://appsource.microsoft.com/product/office/wa104381180> till.</span><span class="sxs-lookup"><span data-stu-id="c16ef-135">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="c16ef-136">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-136">Click **GET IT NOW**.</span></span>

   ![Rapportmeddelande – Skaffa nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="c16ef-138">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="c16ef-139">Logga in med ditt arbets- eller skolkonto (för företag) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="c16ef-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="c16ef-140">När tillägget är installerat och aktiverat visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="c16ef-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="c16ef-141">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="c16ef-141">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c16ef-143">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="c16ef-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="c16ef-145">Mer information om hur du använder tillägget finns i Använda tillägget [Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="c16ef-145">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="c16ef-146">Skaffa och aktivera tillägget Rapportmeddelande för din organisation</span><span class="sxs-lookup"><span data-stu-id="c16ef-146">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="c16ef-147">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c16ef-147">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="c16ef-148">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="c16ef-148">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="c16ef-149">Välj **Distribuera tillägg överst** på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-149">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="c16ef-151">Granska informationen **i den utfällbaserade menyn** Distribuera ett nytt tillägg som visas och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="c16ef-152">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-152">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="c16ef-154">På sidan Välj **tillägg som visas** klickar  du i sökrutan, skriver rapportmeddelande och klickar sedan på  ![ sökikonen. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="c16ef-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="c16ef-155">Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="c16ef-157">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="c16ef-158">På **sidan Konfigurera tillägg som** visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="c16ef-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c16ef-159">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c16ef-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="c16ef-160">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="c16ef-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="c16ef-161">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="c16ef-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="c16ef-162">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="c16ef-162">**Just me**</span></span>

   - <span data-ttu-id="c16ef-163">**Distributionsmetod:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c16ef-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="c16ef-164">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="c16ef-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="c16ef-165">**Tillgängligt:** Användare kan installera tillägget **på Startsidan** Få administratör \>  \> **hanterade tillägg.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="c16ef-166">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="c16ef-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Sidan Konfigurera tillägg](../../media/configure-add-in.png)

   <span data-ttu-id="c16ef-168">Klicka på Distribuera när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-168">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="c16ef-169">På sidan **Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="c16ef-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="c16ef-170">Klicka på Nästa när du har läst **informationen.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-170">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="c16ef-172">Granska **informationen på sidan Presentera** tillägg som visas och klicka sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="c16ef-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="c16ef-174">Lär dig hur du använder tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="c16ef-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="c16ef-175">Personer som har tilldelats tillägget ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="c16ef-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="c16ef-176">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="c16ef-176">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="c16ef-178">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="c16ef-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för tillägget Meddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="c16ef-180">När du meddelar användarna om tillägget Rapportmeddelande tar du med en länk [för att använda tillägget Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="c16ef-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="c16ef-181">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="c16ef-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="c16ef-182">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="c16ef-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="c16ef-184">Leta upp och **välj tillägget** Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="c16ef-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="c16ef-185">I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du inställningar efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="c16ef-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="c16ef-186">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c16ef-186">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="c16ef-188">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="c16ef-188">View and review reported messages</span></span>

<span data-ttu-id="c16ef-189">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="c16ef-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="c16ef-190">Använd administrationsportalen för inskickade material.</span><span class="sxs-lookup"><span data-stu-id="c16ef-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="c16ef-191">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="c16ef-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="c16ef-192">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="c16ef-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="c16ef-193">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c16ef-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
