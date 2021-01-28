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
description: Lär dig hur du aktiverar rapport tillägget för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1f8cffaa6346ec7f426da3c862014ed85a9a367
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029238"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="2ceac-103">Aktivera tillägget för att rapportera meddelande</span><span class="sxs-lookup"><span data-stu-id="2ceac-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="2ceac-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="2ceac-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2ceac-105">Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="2ceac-106">Med tilläggen rapport meddelande och rapportera nät fiske funktioner för Outlook och Outlook på webben (tidigare Outlook Web App) kan andra personer enkelt rapportera falsk identifiering (god e-post som är markerad som dålig) eller falskt negativ (dålig e-post) till Microsoft och dess dotter bolag för analys.</span><span class="sxs-lookup"><span data-stu-id="2ceac-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="2ceac-107">Microsoft använder dessa inlämningar för att förbättra effektiviteten hos e-postskydd.</span><span class="sxs-lookup"><span data-stu-id="2ceac-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="2ceac-108">Om du till exempel rapporterar många meddelanden som har flaggats som skräp post som icke-skräppost-objekt med hjälp av tillägget rapport, kan organisationens säkerhets Team behöva justera [principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2ceac-109">Du kan installera ett tilläggsprogram för rapport-eller rapport nät.</span><span class="sxs-lookup"><span data-stu-id="2ceac-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="2ceac-110">Om du bara vill att användarna ska rapportera phishing-meddelanden kan du distribuera tillägget rapportera nät fiske i din organisation.</span><span class="sxs-lookup"><span data-stu-id="2ceac-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="2ceac-111">Mer information finns i [aktivera tillägget rapportera nät fiske](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="2ceac-112">Med tillägget rapport meddelanden kan du rapportera både skräp post och nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2ceac-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="2ceac-113">Administratörer kan aktivera tillägget rapportera till organisationen, och enskilda användare kan installera den själva.</span><span class="sxs-lookup"><span data-stu-id="2ceac-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="2ceac-114">Om du är en enskild användare kan du [Aktivera tilläggs tillägget för rapportering](#get-the-report-message-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="2ceac-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="2ceac-115">Om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat för att använda OAuth-autentisering kan du [aktivera tillägget rapportera till din organisation](#get-and-enable-the-report-message-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="2ceac-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="2ceac-116">Rapport meddelande Add-In är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="2ceac-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2ceac-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2ceac-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2ceac-118">Tillägget rapportera meddelanden fungerar med de flesta Microsoft 365-abonnemang och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="2ceac-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="2ceac-119">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="2ceac-119">Outlook on the web</span></span>
  - <span data-ttu-id="2ceac-120">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="2ceac-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="2ceac-121">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="2ceac-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="2ceac-122">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="2ceac-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="2ceac-123">Tillägget för rapport meddelanden är inte tillgängligt för post lådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="2ceac-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="2ceac-124">Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="2ceac-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2ceac-125">Mer information finns i [principer för användar profiler](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-125">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="2ceac-126">Din befintliga webbläsare bör fungera med tilläggsprogrammet rapportera meddelande.</span><span class="sxs-lookup"><span data-stu-id="2ceac-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="2ceac-127">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2ceac-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="2ceac-128">För organisatoriska installationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="2ceac-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="2ceac-129">Mer information finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="2ceac-130">Administratörer måste vara medlemmar i roll gruppen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="2ceac-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="2ceac-131">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="2ceac-132">Hämta tillägget för rapport meddelanden åt dig själv</span><span class="sxs-lookup"><span data-stu-id="2ceac-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="2ceac-133">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och Sök efter rapport meddelande tillägget.</span><span class="sxs-lookup"><span data-stu-id="2ceac-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="2ceac-134">Om du vill gå direkt till tillägget rapport, går du till <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="2ceac-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="2ceac-135">Klicka på **Skaffa det nu**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-135">Click **GET IT NOW**.</span></span>

   ![Rapport meddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="2ceac-137">Kontrol lera användnings villkoren och sekretess policyn i dialog rutan som visas och klicka sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="2ceac-138">Logga in med ditt arbets-eller skol konto (för företag) eller ditt Microsoft-konto (för personligt bruk).</span><span class="sxs-lookup"><span data-stu-id="2ceac-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="2ceac-139">När tillägget har installerats och Aktiver ATS ser du följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="2ceac-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="2ceac-140">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="2ceac-140">In Outlook, the icon looks like this:</span></span>

  ![Ikonen rapportera meddelande-tillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="2ceac-142">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="2ceac-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för att lägga till en Outlook-ikon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="2ceac-144">Information om hur du använder tillägget finns i [använda tillägget rapportera meddelanden](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="2ceac-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="2ceac-145">Hämta och aktivera tillägget rapportera meddelande till din organisation</span><span class="sxs-lookup"><span data-stu-id="2ceac-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="2ceac-146">Det kan ta upp till 12 timmar innan tillägget visas i din organisation.</span><span class="sxs-lookup"><span data-stu-id="2ceac-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="2ceac-147">Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .</span><span class="sxs-lookup"><span data-stu-id="2ceac-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="2ceac-148">Välj **distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan tjänster och tillägg i administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="2ceac-150">I **distribuera en ny** utfällbar tillägg som visas läser du informationen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="2ceac-151">På nästa sida klickar du på **Välj från butiken**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-151">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggs sida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="2ceac-153">Klicka i **sökrutan på** sidan **Välj tillägg** som visas, ange **rapport meddelande** och klicka sedan på ikonen **Sök** sökning ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="2ceac-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="2ceac-154">Sök efter **rapport meddelande** i listan med resultat och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-154">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välja Sök Resultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="2ceac-156">I dialog rutan som visas granskar du licensierings-och integritets informationen och klickar sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-156">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="2ceac-157">På sidan **Konfigurera tillägg** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2ceac-157">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="2ceac-158">**Tilldelade användare**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2ceac-158">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="2ceac-159">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="2ceac-159">**Everyone** (default)</span></span>
     - <span data-ttu-id="2ceac-160">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="2ceac-160">**Specific users / groups**</span></span>
     - <span data-ttu-id="2ceac-161">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="2ceac-161">**Just me**</span></span>

   - <span data-ttu-id="2ceac-162">**Distributions metod**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2ceac-162">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="2ceac-163">**Åtgärdat (standard)**: tillägget distribueras automatiskt till de angivna användarna och de kan inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="2ceac-163">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="2ceac-164">**Tillgängligt**: användarna kan installera **tillägget via** \> **Skaffa** tillägg som \> **hanteras av administratören**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-164">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="2ceac-165">**Valfritt**: tillägget distribueras automatiskt till angivna användare, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="2ceac-165">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurera tilläggs Sidan](../../media/configure-add-in.png)

   <span data-ttu-id="2ceac-167">När du är klar klickar du på **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-167">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="2ceac-168">På sidan **distribuera rapport meddelanden** som visas visas en status rapport följt av en bekräftelse på att tillägget distribuerades.</span><span class="sxs-lookup"><span data-stu-id="2ceac-168">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="2ceac-169">När du har läst informationen klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-169">After you read the information, click **Next**.</span></span>

   ![Distribuera rapport meddelande sidan](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="2ceac-171">På sidan om meddelande **tillägget** som visas granskar du informationen och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="2ceac-171">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan meddelande om tillägg](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="2ceac-173">Lär dig hur du använder tillägget rapport</span><span class="sxs-lookup"><span data-stu-id="2ceac-173">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="2ceac-174">Personer som har tillägget tilldelat kommer att se följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="2ceac-174">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="2ceac-175">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="2ceac-175">In Outlook, the icon looks like this:</span></span>

  ![Ikonen rapportera meddelande-tillägg för Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="2ceac-177">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="2ceac-177">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen för att lägga till en Outlook-ikon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="2ceac-179">När du meddelar användare om tillägget för rapport meddelanden infogar du en länk där du kan [använda tillägget rapport](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="2ceac-179">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="2ceac-180">Granska eller redigera inställningar för rapport tillägget</span><span class="sxs-lookup"><span data-stu-id="2ceac-180">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="2ceac-181">Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .</span><span class="sxs-lookup"><span data-stu-id="2ceac-181">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins sida i det nya administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="2ceac-183">Hitta och välj tillägget **rapportera meddelanden** .</span><span class="sxs-lookup"><span data-stu-id="2ceac-183">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="2ceac-184">I **Redigera rapport** utfällning som visas granskar och redigerar du inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="2ceac-184">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="2ceac-185">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="2ceac-185">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget rapport meddelande](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="2ceac-187">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="2ceac-187">View and review reported messages</span></span>

<span data-ttu-id="2ceac-188">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="2ceac-188">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="2ceac-189">Använd portalen administrations underställda.</span><span class="sxs-lookup"><span data-stu-id="2ceac-189">Use the Admin Submissions portal.</span></span> <span data-ttu-id="2ceac-190">Mer information finns i [Visa användar inlämningar till Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="2ceac-190">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="2ceac-191">Skapa en regel för e-postflöde (kallas även transport regel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2ceac-191">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="2ceac-192">Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2ceac-192">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
