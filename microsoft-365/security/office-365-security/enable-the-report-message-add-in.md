---
title: Aktivera rapportmeddelandet eller tilläggen för nätfiske
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
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
description: Läs om hur du aktiverar rapportmeddelandet eller tilläggen för rapportfiske för Outlook och Outlook på webben, för enskilda användare eller för hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8949322b0b691d59e59e5f7b80d2b9650e4115d5
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029915"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="68a30-103">Aktivera rapportmeddelandet eller tilläggen för nätfiske</span><span class="sxs-lookup"><span data-stu-id="68a30-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="68a30-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="68a30-104">**Applies to**</span></span>
- [<span data-ttu-id="68a30-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="68a30-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="68a30-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="68a30-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="68a30-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68a30-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="68a30-108">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för inskickade material i Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="68a30-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="68a30-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="68a30-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="68a30-110">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva resultat (bra e-post markerad som dålig) eller falska negativa (felaktig e-post tillåten) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="68a30-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="68a30-111">Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="68a30-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="68a30-112">Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske.</span><span class="sxs-lookup"><span data-stu-id="68a30-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="68a30-113">Den här informationen visas i säkerhetspanelen och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="68a30-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="68a30-114">Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="68a30-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="68a30-115">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="68a30-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="68a30-116">Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="68a30-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="68a30-117">Mer information finns i Aktivera tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="68a30-117">For more information, see Enable the Report Message add-in.</span></span>

<span data-ttu-id="68a30-118">Via tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="68a30-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="68a30-119">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="68a30-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="68a30-120">Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="68a30-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="68a30-121">Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="68a30-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="68a30-122">Om du är enskild användare kan du aktivera båda tilläggen själv.</span><span class="sxs-lookup"><span data-stu-id="68a30-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="68a30-123">Om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat att använda OAuth-autentisering kan du aktivera tillägget Rapportmeddelande och tillägget Rapportfiske för organisationen.</span><span class="sxs-lookup"><span data-stu-id="68a30-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="68a30-124">Båda tilläggen är nu tillgängliga via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="68a30-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68a30-125">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="68a30-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="68a30-126">Både tillägget Rapportmeddelande och tillägget Rapportfiske fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="68a30-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="68a30-127">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="68a30-127">Outlook on the web</span></span>
  - <span data-ttu-id="68a30-128">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="68a30-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="68a30-129">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="68a30-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="68a30-130">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="68a30-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="68a30-131">Outlook-appen för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="68a30-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="68a30-132">Båda tilläggen är inte tillgängliga för delade postlådor eller postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="68a30-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="68a30-133">Din befintliga webbläsare bör fungera med tilläggen Rapportmeddelande och Rapportera nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="68a30-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="68a30-134">För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="68a30-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="68a30-135">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="68a30-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="68a30-136">Administratörer måste vara medlemmar i rollgruppen Globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="68a30-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="68a30-137">Mer information finns i [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="68a30-137">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="68a30-138">Mer information om hur du rapporterar ett meddelande med hjälp av funktionen Rapportmeddelande finns i Rapportera falska positiva och [falska negativa objekt i Outlook.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="68a30-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68a30-139">Vi rekommenderar inte den inbyggda rapporteringsupplevelsen i Outlook eftersom det inte kan använda principen för [användarinskickning.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="68a30-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="68a30-140">Vi rekommenderar att du använder tilläggen Rapportmeddelande eller Nätfiskerapport i stället.</span><span class="sxs-lookup"><span data-stu-id="68a30-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="68a30-141">Hämta tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="68a30-141">Get the Report Message add-in</span></span>

### <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="68a30-142">Skaffa tillägget Rapportmeddelande åt dig själv</span><span class="sxs-lookup"><span data-stu-id="68a30-142">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="68a30-143">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="68a30-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="68a30-144">Gå direkt till tillägget Rapportmeddelande genom att gå till <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="68a30-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="68a30-145">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="68a30-145">Click **GET IT NOW**.</span></span>

   ![Rapportmeddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="68a30-147">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="68a30-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="68a30-148">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="68a30-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="68a30-149">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="68a30-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="68a30-150">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="68a30-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="68a30-151">![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="68a30-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="68a30-152">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="68a30-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="68a30-153">![Tilläggsikon för meddelande i Outlook på webben](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="68a30-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="68a30-154">Hämta tillägget Rapportmeddelande för din organisation</span><span class="sxs-lookup"><span data-stu-id="68a30-154">Get the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="68a30-155">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="68a30-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="68a30-156">I administrationscentret för Microsoft 365  går du till \> **sidan Tillägg för inställningar** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="68a30-156">In the Microsoft 365 admin center, go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="68a30-157">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="68a30-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="68a30-158">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="68a30-160">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="68a30-161">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="68a30-161">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="68a30-163">På sidan **Välj tillägg som visas** klickar du i rutan **Sök,** skriver **Rapportmeddelande** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="68a30-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="68a30-164">Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="68a30-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="68a30-166">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="68a30-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="68a30-167">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="68a30-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="68a30-168">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="68a30-168">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="68a30-169">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="68a30-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="68a30-170">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="68a30-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="68a30-171">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="68a30-171">**Just me**</span></span>

   - <span data-ttu-id="68a30-172">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="68a30-172">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="68a30-173">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="68a30-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="68a30-174">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="68a30-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="68a30-175">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="68a30-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   <span data-ttu-id="68a30-177">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="68a30-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="68a30-178">På **sidan Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="68a30-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="68a30-179">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-179">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="68a30-181">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="68a30-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="68a30-183">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="68a30-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="68a30-184">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="68a30-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="68a30-185">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="68a30-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="68a30-187">Leta upp och **välj tillägget** Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="68a30-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="68a30-188">I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du lämpliga inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="68a30-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="68a30-189">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="68a30-189">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="68a30-191">Hämta tillägget Rapport om nätfiske</span><span class="sxs-lookup"><span data-stu-id="68a30-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="68a30-192">Skaffa tillägget Rapport om nätfiske åt dig själv</span><span class="sxs-lookup"><span data-stu-id="68a30-192">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="68a30-193">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="68a30-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="68a30-194">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="68a30-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="68a30-195">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="68a30-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="68a30-196">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="68a30-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="68a30-197">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="68a30-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="68a30-198">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="68a30-198">In Outlook, the icon looks like this:</span></span>

  ![Ikon för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="68a30-200">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="68a30-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="68a30-201">![Outlook på webben-tillägget Nätfiske](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="68a30-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="68a30-202">Hämta tillägget Rapport om nätfiske för din organisation</span><span class="sxs-lookup"><span data-stu-id="68a30-202">Get the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="68a30-203">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="68a30-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="68a30-204">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="68a30-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="68a30-205">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="68a30-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="68a30-206">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="68a30-208">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="68a30-209">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="68a30-209">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="68a30-211">På sidan **Välj tillägg som visas** klickar  du i rutan Sök, anger **Rapportfiske** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="68a30-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="68a30-212">Leta rätt på Rapport nätfiske i **listan med resultat och** klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="68a30-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="68a30-213">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="68a30-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="68a30-214">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="68a30-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="68a30-215">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="68a30-215">**Assigned users**: Select one of the following values:</span></span>
     - <span data-ttu-id="68a30-216">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="68a30-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="68a30-217">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="68a30-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="68a30-218">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="68a30-218">**Just me**</span></span>

   - <span data-ttu-id="68a30-219">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="68a30-219">**Deployment method**: Select one of the following values:</span></span>
     - <span data-ttu-id="68a30-220">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="68a30-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="68a30-221">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="68a30-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="68a30-222">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="68a30-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="68a30-223">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="68a30-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="68a30-224">På sidan **Distribuera nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="68a30-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="68a30-225">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="68a30-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="68a30-226">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="68a30-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="68a30-227">Granska eller redigera inställningar för tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="68a30-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="68a30-228">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="68a30-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="68a30-229">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="68a30-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="68a30-230">Leta upp och **välj tillägget** Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="68a30-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="68a30-231">I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="68a30-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="68a30-232">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="68a30-232">When you're finished, click **Save**.</span></span>
