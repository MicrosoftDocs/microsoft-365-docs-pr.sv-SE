---
title: Aktivera tilläggsprogrammet rapportera Phish
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
description: Lär dig hur du aktiverar tillägget för rapport-nätfiske för Outlook och Outlook på webben, för enskilda användare eller hela organisationen.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029144"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="84bd9-103">Aktivera tillägget för att rapportera nätfiske</span><span class="sxs-lookup"><span data-stu-id="84bd9-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="84bd9-104">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="84bd9-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="84bd9-105">Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="84bd9-106">Med tilläggen rapportera meddelande och rapportera nät fiske funktioner för Outlook och Outlook på webben (tidigare Outlook Web App) kan andra personer enkelt rapportera falsk identifiering (god e-post som är markerad som dålig) eller falsk negativ (dålig e-post) till Microsoft och dess dotter bolag för analys.</span><span class="sxs-lookup"><span data-stu-id="84bd9-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="84bd9-107">Microsoft använder dessa inlämningar för att förbättra effektiviteten hos e-postskydd.</span><span class="sxs-lookup"><span data-stu-id="84bd9-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="84bd9-108">Antag till exempel att personer rapporterar många meddelanden med hjälp av tillägget för rapport nät.</span><span class="sxs-lookup"><span data-stu-id="84bd9-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="84bd9-109">De här informations ytorna i [säkerhets instrument panelen](security-dashboard.md) och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="84bd9-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="84bd9-110">Din organisations säkerhets team kan använda den här informationen som en indikation på att mot nätfiske-principer kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="84bd9-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="84bd9-111">Du kan installera ett tilläggsprogram för rapport-eller rapport nät.</span><span class="sxs-lookup"><span data-stu-id="84bd9-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="84bd9-112">Om du vill att användarna ska kunna rapportera både skräp post och nät fiske meddelanden kan du distribuera tillägget rapportera meddelanden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="84bd9-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="84bd9-113">Mer information finns i [aktivera tillägget rapportera meddelanden](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="84bd9-114">Tillägget rapport nätfiske tillhandahåller alternativet att endast rapportera nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="84bd9-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="84bd9-115">Administratörer kan aktivera tillägget Rapportera nätfiske för organisationer och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="84bd9-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="84bd9-116">Om du är en enskild användare kan du [aktivera tillägget rapportera nät fiske för dig själv](#get-the-report-phishing-add-in-for-yourself).</span><span class="sxs-lookup"><span data-stu-id="84bd9-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="84bd9-117">Om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat för att använda OAuth-autentisering kan du [aktivera tillägget Rapportera nätfiske för din organisation](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="84bd9-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="84bd9-118">Nät fiske Add-In är nu tillgängligt via [centraliserad distribution](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="84bd9-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84bd9-119">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="84bd9-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84bd9-120">Tillägget rapport nät fiske fungerar med de flesta Microsoft 365-abonnemang och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="84bd9-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="84bd9-121">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="84bd9-121">Outlook on the web</span></span>
  - <span data-ttu-id="84bd9-122">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="84bd9-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="84bd9-123">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="84bd9-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="84bd9-124">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="84bd9-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="84bd9-125">Tillägget rapport nätfiske är inte tillgängligt för post lådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="84bd9-125">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="84bd9-126">Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="84bd9-126">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="84bd9-127">Mer information finns i [principer för användar profiler](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-127">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="84bd9-128">Din befintliga webbläsare bör fungera med tillägget rapportera nät fiske.</span><span class="sxs-lookup"><span data-stu-id="84bd9-128">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="84bd9-129">Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="84bd9-129">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="84bd9-130">För organisatoriska installationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="84bd9-130">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="84bd9-131">Mer information finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](../../admin/manage/centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-131">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="84bd9-132">Administratörer måste vara medlemmar i roll gruppen globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="84bd9-132">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="84bd9-133">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="84bd9-134">Hämta tillägget rapport nät fiske för dig själv</span><span class="sxs-lookup"><span data-stu-id="84bd9-134">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="84bd9-135">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och Sök efter tillägget för rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="84bd9-135">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="84bd9-136">Klicka på **Skaffa det nu**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-136">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="84bd9-137">Kontrol lera användnings villkoren och sekretess policyn i dialog rutan som visas och klicka sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="84bd9-138">Logga in med ditt arbets-eller skol konto (för företag) eller ditt Microsoft-konto (för personligt bruk).</span><span class="sxs-lookup"><span data-stu-id="84bd9-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="84bd9-139">När tillägget har installerats och Aktiver ATS ser du följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="84bd9-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="84bd9-140">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="84bd9-140">In Outlook, the icon looks like this:</span></span>

  ![Ikonen rapportera tilläggsprogram för nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="84bd9-142">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="84bd9-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen nät fiske tillägg för Outlook på webb sidan](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="84bd9-144">Hämta och aktivera tillägget Rapportera nätfiske för din organisation</span><span class="sxs-lookup"><span data-stu-id="84bd9-144">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="84bd9-145">Det kan ta upp till 12 timmar innan tillägget visas i din organisation.</span><span class="sxs-lookup"><span data-stu-id="84bd9-145">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="84bd9-146">Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .</span><span class="sxs-lookup"><span data-stu-id="84bd9-146">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="84bd9-147">Välj **distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-147">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan tjänster och tillägg i administrations centret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="84bd9-149">I **distribuera en ny** utfällbar tillägg som visas läser du informationen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="84bd9-150">På nästa sida klickar du på **Välj från butiken**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-150">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggs sida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="84bd9-152">Klicka i **sökrutan på** sidan **Välj tillägg** som visas, ange **rapport nätfiske** och klicka sedan på ikonen **Sök** ![ sökning ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="84bd9-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="84bd9-153">Sök efter **rapport nätfiske** i resultat listan och klicka sedan på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-153">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="84bd9-154">I dialog rutan som visas granskar du licensierings-och integritets informationen och klickar sedan på **Fortsätt**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-154">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="84bd9-155">På sidan **Konfigurera tillägg** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="84bd9-155">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="84bd9-156">**Tilldelade användare**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="84bd9-156">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="84bd9-157">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="84bd9-157">**Everyone** (default)</span></span>
     - <span data-ttu-id="84bd9-158">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="84bd9-158">**Specific users / groups**</span></span>
     - <span data-ttu-id="84bd9-159">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="84bd9-159">**Just me**</span></span>

   - <span data-ttu-id="84bd9-160">**Distributions metod**: Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="84bd9-160">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="84bd9-161">**Åtgärdat (standard)**: tillägget distribueras automatiskt till de angivna användarna och de kan inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="84bd9-161">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="84bd9-162">**Tillgängligt**: användarna kan installera **tillägget via** \> **Skaffa** tillägg som \> **hanteras av administratören**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-162">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="84bd9-163">**Valfritt**: tillägget distribueras automatiskt till angivna användare, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="84bd9-163">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="84bd9-164">När du är klar klickar du på **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-164">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="84bd9-165">I sidan **distribuera rapport nät fiske** som visas visas en status rapport följt av en bekräftelse på att tillägget distribuerades.</span><span class="sxs-lookup"><span data-stu-id="84bd9-165">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="84bd9-166">När du har läst informationen klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-166">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="84bd9-167">På sidan om meddelande **tillägget** som visas granskar du informationen och klickar sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="84bd9-167">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="84bd9-168">Lär dig hur du använder tillägget rapportera nät fiske</span><span class="sxs-lookup"><span data-stu-id="84bd9-168">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="84bd9-169">Personer som har tillägget tilldelat kommer att se följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="84bd9-169">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="84bd9-170">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="84bd9-170">In Outlook, the icon looks like this:</span></span>

  ![Ikonen rapportera tilläggsprogram för nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="84bd9-172">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="84bd9-172">In Outlook on the web, the icon looks like this:</span></span>

  ![Ikonen nät fiske tillägg för Outlook på webb sidan](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="84bd9-174">Granska eller redigera inställningar för tillägget rapportera nät fiske</span><span class="sxs-lookup"><span data-stu-id="84bd9-174">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="84bd9-175">Gå till sidan **Inställningar** för tillägg i administrations centret för Microsoft 365, \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> om du inte kan se **tilläggs** sidan går du till länken **Inställningar** för \> **integrerade appar** \>  i den övre delen av sidan **integrerade program** .</span><span class="sxs-lookup"><span data-stu-id="84bd9-175">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="84bd9-176">Sök reda på och välj tillägget **rapportera nät fiske** .</span><span class="sxs-lookup"><span data-stu-id="84bd9-176">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="84bd9-177">I **Redigera rapport nät fiske** som visas, granskar och redigerar du inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="84bd9-177">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="84bd9-178">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="84bd9-178">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="84bd9-179">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="84bd9-179">View and review reported messages</span></span>

<span data-ttu-id="84bd9-180">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="84bd9-180">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="84bd9-181">Använd portalen administrations underställda.</span><span class="sxs-lookup"><span data-stu-id="84bd9-181">Use the Admin Submissions portal.</span></span> <span data-ttu-id="84bd9-182">Mer information finns i [Visa användar inlämningar till Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="84bd9-182">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="84bd9-183">Skapa en regel för e-postflöde (kallas även transport regel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="84bd9-183">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="84bd9-184">Anvisningar finns i [använda e-postflödes regler för att se vad användarna rapporterar till Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="84bd9-184">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>