---
title: Aktivera tillägget för att rapportera meddelande
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Lär dig hur du aktiverar tillägget Rapportmeddelande för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: 2b074d1bd260f5c95d138577e259aee14ec9e8d7
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430513"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="efae5-103">Aktivera tillägget för att rapportera meddelande</span><span class="sxs-lookup"><span data-stu-id="efae5-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="efae5-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="efae5-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="efae5-105">Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="efae5-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="efae5-106">Tillägget Report Message för Outlook och Outlook på webben (tidigare känt som Outlook Web App) gör det möjligt för människor att enkelt rapportera falska positiva (bra e-post markerad som dålig) eller falska negativ (dålig e-post tillåts) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="efae5-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="efae5-107">Microsoft använder dessa inlämningar för att förbättra effektiviteten i e-postskyddstekniker.</span><span class="sxs-lookup"><span data-stu-id="efae5-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="efae5-108">Anta till exempel att personer rapporterar många meddelanden som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="efae5-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="efae5-109">Den här informationen visas i [säkerhetsinstrumentpanelen](security-dashboard.md) och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="efae5-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="efae5-110">Organisationens säkerhetsteam kan använda den här informationen som en indikation på att anti-phishing-principer kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="efae5-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="efae5-111">Om personer rapporterar många meddelanden som har flaggats som skräppost som Inte skräppost med tillägget Rapportera meddelande kan organisationens säkerhetsteam behöva justera [policyerna mot skräppost.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="efae5-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="efae5-112">Om din organisation använder [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) eller [Plan 2](office-365-ti.md)ger tillägget Rapportmeddelande dessutom organisationens säkerhetsteam användbar information som de kan använda för att granska och uppdatera säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="efae5-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="efae5-113">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="efae5-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="efae5-114">Om du är en enskild användare kan du [aktivera tillägget Rapportmeddelande själv](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="efae5-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="efae5-115">Om du är global administratör eller Exchange [Online-administratör](#get-and-enable-the-report-message-add-in-for-your-organization)och Exchange är konfigurerad för att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande för din organisation .</span><span class="sxs-lookup"><span data-stu-id="efae5-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="efae5-116">Tillägget Rapportmeddelande är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="efae5-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="efae5-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="efae5-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="efae5-118">Tillägget Rapportmeddelande fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="efae5-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="efae5-119">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="efae5-119">Outlook on the web</span></span>
  - <span data-ttu-id="efae5-120">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="efae5-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="efae5-121">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="efae5-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="efae5-122">Outlook ingår i Microsoft 365-appar för Företag</span><span class="sxs-lookup"><span data-stu-id="efae5-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="efae5-123">Tillägget Rapportmeddelande är inte tillgängligt för postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="efae5-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="efae5-124">Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="efae5-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="efae5-125">Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="efae5-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="efae5-126">Din befintliga webbläsare bör fungera med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="efae5-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="efae5-127">Men om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="efae5-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="efae5-128">För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="efae5-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="efae5-129">Mer information finns [i Avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="efae5-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="efae5-130">Administratörer måste vara medlemmar i rollgruppen Globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="efae5-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="efae5-131">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="efae5-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="efae5-132">Hämta tillägget Rapportmeddelande själv</span><span class="sxs-lookup"><span data-stu-id="efae5-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="efae5-133">Gå till Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="efae5-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="efae5-134">Gå direkt till tillägget Rapportmeddelande och gå till <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="efae5-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="efae5-135">Klicka på **Hämta den nu.**</span><span class="sxs-lookup"><span data-stu-id="efae5-135">Click **GET IT NOW**.</span></span>

   ![Rapportera meddelande - Hämta det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="efae5-137">Granska användarvillkoren och sekretesspolicyn i dialogrutan som visas och klicka sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="efae5-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="efae5-138">Logga in med ditt arbets- eller skolkonto (för företagsbruk) eller ditt Microsoft-konto (för personligt bruk).</span><span class="sxs-lookup"><span data-stu-id="efae5-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="efae5-139">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="efae5-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="efae5-140">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="efae5-140">In Outlook, the icon looks like this:</span></span>

  ![Rapportmeddelandetillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="efae5-142">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="efae5-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook på ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="efae5-144">Mer information om hur du använder tillägget finns i [Använda tillägget Rapportmeddelande](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="efae5-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="efae5-145">Hämta och aktivera tillägget Rapportmeddelande för din organisation</span><span class="sxs-lookup"><span data-stu-id="efae5-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="efae5-146">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="efae5-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="efae5-147">Gå till sidan **Tjänster & tillägg i administrationscentret** för Microsoft 365 och klicka sedan på Distribuera <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **tillägg**.</span><span class="sxs-lookup"><span data-stu-id="efae5-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="efae5-149">Granska informationen i utfällningen **Distribuera ett nytt tillägg** som visas och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="efae5-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="efae5-150">Klicka på Välj **på**nästa sida .</span><span class="sxs-lookup"><span data-stu-id="efae5-150">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="efae5-152">På sidan **Välj tillägg** som visas klickar du i rutan **Sök,** anger **Rapportmeddelande**och klickar sedan på **Sök** ![ ](../../media/search-icon.png) eftersökikon .</span><span class="sxs-lookup"><span data-stu-id="efae5-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="efae5-153">Leta reda på **Rapportmeddelande i** resultatlistan och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="efae5-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="efae5-155">Granska licensierings- och sekretessinformationen i dialogrutan som visas och klicka sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="efae5-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="efae5-156">Konfigurera följande inställningar på sidan **Konfigurera tillägg** som visas:</span><span class="sxs-lookup"><span data-stu-id="efae5-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="efae5-157">**Tilldelade användare**: Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="efae5-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="efae5-158">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="efae5-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="efae5-159">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="efae5-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="efae5-160">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="efae5-160">**Just me**</span></span>

   - <span data-ttu-id="efae5-161">**Distributionsmetod**: Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="efae5-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="efae5-162">**Fast (standard)**: Tillägget distribueras automatiskt till de angivna användarna och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="efae5-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="efae5-163">**Tillgänglig:** Användare kan installera tillägget at **Home** \> **Get-tillägg** som \> **administreras.**</span><span class="sxs-lookup"><span data-stu-id="efae5-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="efae5-164">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="efae5-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   <span data-ttu-id="efae5-166">När du är klar klickar du på **Distribuera**.</span><span class="sxs-lookup"><span data-stu-id="efae5-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="efae5-167">På sidan **Distribuera rapportmeddelande** som visas visas visas en lägesrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="efae5-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="efae5-168">När du har läst informationen klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="efae5-168">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="efae5-170">På sidan **Meddela tillägg** som visas granskar du informationen och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="efae5-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Meddela tilläggssida](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="efae5-172">Läs om hur du använder tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="efae5-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="efae5-173">Personer som har tillägget tilldelats dem ser följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="efae5-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="efae5-174">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="efae5-174">In Outlook, the icon looks like this:</span></span>

  ![Ikonen För rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="efae5-176">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="efae5-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook i ikonen För webbrapportmeddelande](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="efae5-178">När du meddelar användarna om tillägget Rapportmeddelande ska du inkludera en länk till [Använda tillägget Rapportmeddelande](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="efae5-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="efae5-179">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="efae5-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="efae5-180">Gå till sidan **Tjänster & tillägg på** sidan Tjänster & på <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="efae5-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Sidan Tjänster och tillägg i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="efae5-182">Sök efter och välj tillägget **Rapportmeddelande.**</span><span class="sxs-lookup"><span data-stu-id="efae5-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="efae5-183">Granska och redigera inställningar som är lämpliga för din organisation i det utfällbara meddelandet **Redigera rapportmeddelande** som visas.</span><span class="sxs-lookup"><span data-stu-id="efae5-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="efae5-184">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="efae5-184">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="efae5-186">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="efae5-186">View and review reported messages</span></span>

<span data-ttu-id="efae5-187">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="efae5-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="efae5-188">Använd portalen För administratörsbidrag.</span><span class="sxs-lookup"><span data-stu-id="efae5-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="efae5-189">Mer information finns i [Visa användarinlämningar till Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="efae5-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="efae5-190">Skapa en regel för e-postflöde (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="efae5-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="efae5-191">Instruktioner finns i [Använda regler för e-postflöde för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="efae5-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
