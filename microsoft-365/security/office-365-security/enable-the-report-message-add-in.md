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
ms.openlocfilehash: 08ad2f61cc5dcd2e59af89ca788319c81e2f6bdb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287371"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="a3872-103">Aktivera tillägget för att rapportera meddelande</span><span class="sxs-lookup"><span data-stu-id="a3872-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3872-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a3872-104">**Applies to**</span></span>
- [<span data-ttu-id="a3872-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a3872-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a3872-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a3872-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a3872-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3872-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> <span data-ttu-id="a3872-108">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen För inskickade material i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="a3872-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a3872-109">Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a3872-110">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden markerade som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="a3872-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="a3872-111">Microsoft använder dessa inskickade e-postmeddelanden för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="a3872-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="a3872-112">Om personer till exempel rapporterar många meddelanden som flaggats som Skräppost med tillägget Rapportmeddelande kan din organisations säkerhetsgrupp behöva justera principerna för [skräppostskydd.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-112">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a3872-113">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="a3872-113">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="a3872-114">Om du vill att användarna endast ska rapportera nätfiskemeddelanden distribuerar du tillägget Rapport nätfiske i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3872-114">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="a3872-115">Mer information finns i [Aktivera tillägget Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-115">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="a3872-116">Med tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="a3872-116">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="a3872-117">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="a3872-117">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="a3872-118">Om du är en enskild användare kan du aktivera tillägget Rapportmeddelande [för dig själv.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="a3872-118">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="a3872-119">Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3872-119">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="a3872-120">Rapportmeddelandets Add-In nu tillgänglig via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-120">The Report Message Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3872-121">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a3872-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3872-122">Tillägget Rapportmeddelande fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="a3872-122">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="a3872-123">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="a3872-123">Outlook on the web</span></span>
  - <span data-ttu-id="a3872-124">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="a3872-124">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="a3872-125">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="a3872-125">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="a3872-126">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="a3872-126">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="a3872-127">Outlook-appen för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="a3872-127">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="a3872-128">Tillägget Rapportmeddelande är inte tillgängligt för postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="a3872-128">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="a3872-129">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="a3872-129">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="a3872-130">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-130">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="a3872-131">Din befintliga webbläsare bör fungera med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a3872-131">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="a3872-132">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova med en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="a3872-132">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="a3872-133">För organisationsinstallationer måste organisationen vara konfigurerad för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="a3872-133">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="a3872-134">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-134">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="a3872-135">Administratörer måste vara medlemmar i rollgruppen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="a3872-135">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="a3872-136">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a3872-136">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="a3872-137">Skaffa tillägget Rapportmeddelande åt dig själv</span><span class="sxs-lookup"><span data-stu-id="a3872-137">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="a3872-138">Gå till Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a3872-138">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="a3872-139">Gå direkt till tillägget Rapportmeddelande genom att gå <https://appsource.microsoft.com/product/office/wa104381180> till.</span><span class="sxs-lookup"><span data-stu-id="a3872-139">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="a3872-140">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="a3872-140">Click **GET IT NOW**.</span></span>

   ![Rapportmeddelande – skaffa nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="a3872-142">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="a3872-142">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="a3872-143">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="a3872-143">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="a3872-144">När tillägget är installerat och aktiverat visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="a3872-144">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="a3872-145">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="a3872-145">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a3872-147">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="a3872-147">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a3872-149">Mer information om hur du använder tillägget finns i Använda tillägget [Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="a3872-149">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="a3872-150">Skaffa och aktivera tillägget Rapportmeddelande för din organisation</span><span class="sxs-lookup"><span data-stu-id="a3872-150">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="a3872-151">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3872-151">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="a3872-152">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="a3872-152">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="a3872-153">Välj **Distribuera tillägg högst** upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a3872-153">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="a3872-155">Granska informationen **i den utfällbaserade menyn** Distribuera ett nytt tillägg som visas och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a3872-155">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="a3872-156">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="a3872-156">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="a3872-158">På sidan Välj **tillägg som visas** klickar  du i sökrutan, skriver rapportmeddelande och klickar sedan på  ![ sökikonen. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="a3872-158">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="a3872-159">Leta reda på rapportmeddelandet i **resultatlistan och** klicka sedan på **Lägg till.**</span><span class="sxs-lookup"><span data-stu-id="a3872-159">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="a3872-161">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="a3872-161">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="a3872-162">På **sidan Konfigurera tillägg som** visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a3872-162">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a3872-163">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="a3872-163">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="a3872-164">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="a3872-164">**Everyone** (default)</span></span>
     - <span data-ttu-id="a3872-165">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="a3872-165">**Specific users / groups**</span></span>
     - <span data-ttu-id="a3872-166">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="a3872-166">**Just me**</span></span>

   - <span data-ttu-id="a3872-167">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="a3872-167">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="a3872-168">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="a3872-168">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="a3872-169">**Tillgängligt:** Användare kan installera tillägget **på Startsidan** Få administratör \>  \> **hanterade tillägg.**</span><span class="sxs-lookup"><span data-stu-id="a3872-169">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="a3872-170">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="a3872-170">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Sidan Konfigurera tillägg](../../media/configure-add-in.png)

   <span data-ttu-id="a3872-172">Klicka på Distribuera när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="a3872-172">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="a3872-173">På sidan **Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="a3872-173">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="a3872-174">Klicka på Nästa när du har läst **informationen.**</span><span class="sxs-lookup"><span data-stu-id="a3872-174">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="a3872-176">Granska **informationen på sidan Presentera** tillägg som visas och klicka sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="a3872-176">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="a3872-178">Lär dig hur du använder tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="a3872-178">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="a3872-179">Personer som har tilldelats tillägget ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="a3872-179">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="a3872-180">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="a3872-180">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a3872-182">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="a3872-182">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för tillägget Meddelande i Outlook på webben](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a3872-184">När du meddelar användarna om tillägget Rapportmeddelande tar du med en länk [för att använda tillägget Rapportmeddelande.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="a3872-184">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="a3872-185">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="a3872-185">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="a3872-186">I administrationscentret för Microsoft 365 går  du till sidan Inställningar för tillägg. Om du inte ser tilläggssidan går du till länken Inställningar integrerade appar tillägg högst upp på sidan Integrerade \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  appar. </span><span class="sxs-lookup"><span data-stu-id="a3872-186">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="a3872-188">Leta upp och **välj tillägget** Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a3872-188">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="a3872-189">I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du lämpliga inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a3872-189">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="a3872-190">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a3872-190">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="a3872-192">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="a3872-192">View and review reported messages</span></span>

<span data-ttu-id="a3872-193">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="a3872-193">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="a3872-194">Använd administrationsportalen för inskickade material.</span><span class="sxs-lookup"><span data-stu-id="a3872-194">Use the Admin Submissions portal.</span></span> <span data-ttu-id="a3872-195">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="a3872-195">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="a3872-196">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a3872-196">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="a3872-197">Instruktioner finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="a3872-197">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
