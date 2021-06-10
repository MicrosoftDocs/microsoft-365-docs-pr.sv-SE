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
description: Läs om hur du aktiverar tilläggen Rapportmeddelande eller Rapport nätfiske för Outlook och Outlook på webben, för enskilda användare eller för hela organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ff91cf4c99c9552ab5f5fecd7c6d2efee8d2d9a8
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789262"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a><span data-ttu-id="e1398-103">Aktivera rapportmeddelandet eller tilläggen för nätfiske</span><span class="sxs-lookup"><span data-stu-id="e1398-103">Enable the Report Message or the Report Phishing add-ins</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e1398-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e1398-104">**Applies to**</span></span>
- [<span data-ttu-id="e1398-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e1398-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e1398-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e1398-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e1398-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1398-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="e1398-108">Om du är administratör i en Microsoft 365 organisation med Exchange Online postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="e1398-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e1398-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e1398-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="e1398-110">Med tilläggen Rapportmeddelande och Rapport om nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) eller falska negativa (felaktig e-post tillåts) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="e1398-110">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="e1398-111">Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="e1398-111">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="e1398-112">Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e1398-112">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="e1398-113">Den här informationen visas i säkerhetspanelen och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="e1398-113">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="e1398-114">Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="e1398-114">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="e1398-115">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e1398-115">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="e1398-116">Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1398-116">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="e1398-117">Mer information finns i Aktivera tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e1398-117">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="e1398-118">Via tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e1398-118">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="e1398-119">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="e1398-119">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e1398-120">Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="e1398-120">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="e1398-121">Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="e1398-121">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="e1398-122">Om du är enskild användare kan du aktivera båda tilläggen själv.</span><span class="sxs-lookup"><span data-stu-id="e1398-122">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="e1398-123">Om du är global administratör eller Exchange Online-administratör och Exchange har konfigurerats att använda OAuth-autentisering kan du aktivera tilläggen Rapportmeddelande och Rapportera nätfiske för organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1398-123">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="e1398-124">Båda tilläggen är nu tillgängliga via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="e1398-124">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1398-125">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="e1398-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1398-126">Både tillägget Rapportmeddelande och tillägget Rapportfiske fungerar med de flesta Microsoft 365 prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="e1398-126">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>
  - <span data-ttu-id="e1398-127">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="e1398-127">Outlook on the web</span></span>
  - <span data-ttu-id="e1398-128">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="e1398-128">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="e1398-129">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="e1398-129">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="e1398-130">Outlook ingår i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="e1398-130">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="e1398-131">Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="e1398-131">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="e1398-132">Båda tilläggen är inte tillgängliga för delade postlådor eller postlådor i lokala Exchange organisationer.</span><span class="sxs-lookup"><span data-stu-id="e1398-132">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="e1398-133">Din befintliga webbläsare bör fungera med tilläggen Rapportmeddelande och Rapportera nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="e1398-133">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="e1398-134">För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="e1398-134">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="e1398-135">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="e1398-135">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="e1398-136">Administratörer måste vara medlemmar i rollgruppen Globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="e1398-136">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="e1398-137">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1398-137">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e1398-138">Mer information om hur du rapporterar ett meddelande med hjälp av funktionen Rapportmeddelande finns i Rapportera falska positiva och falska [negativa resultat i Outlook](report-false-positives-and-false-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="e1398-138">For more information on how to report a message using the Report Message feature, see [Report false positives and false negatives in Outlook](report-false-positives-and-false-negatives.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1398-139">Vi rekommenderar inte den inbyggda rapporteringsupplevelsen i Outlook eftersom den inte kan använda principen för [användarinskicking.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="e1398-139">We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span> <span data-ttu-id="e1398-140">Vi rekommenderar att du använder tilläggen Rapportmeddelande eller Nätfiskerapport i stället.</span><span class="sxs-lookup"><span data-stu-id="e1398-140">We recommend using the Report Message add-in or the Report Phishing add-in instead.</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="e1398-141">Hämta tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="e1398-141">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e1398-142">Skaffa tillägget åt dig själv</span><span class="sxs-lookup"><span data-stu-id="e1398-142">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e1398-143">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e1398-143">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="e1398-144">Gå direkt till tillägget Rapportmeddelande genom att gå till <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="e1398-144">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="e1398-145">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="e1398-145">Click **GET IT NOW**.</span></span>

   ![Rapportmeddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="e1398-147">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="e1398-147">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e1398-148">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="e1398-148">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e1398-149">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="e1398-149">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e1398-150">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1398-150">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e1398-151">![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="e1398-151">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="e1398-152">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1398-152">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e1398-153">![Outlook på webbikonen Rapportmeddelande](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="e1398-153">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e1398-154">Hämta tillägget för din organisation</span><span class="sxs-lookup"><span data-stu-id="e1398-154">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e1398-155">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1398-155">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e1398-156">I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e1398-156">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e1398-157">Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="e1398-157">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e1398-158">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-158">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i Microsoft 365 administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e1398-160">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-160">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e1398-161">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="e1398-161">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e1398-163">På sidan **Välj tillägg som visas** klickar du i rutan **Sök,** skriver **Rapportmeddelande** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e1398-163">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e1398-164">Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="e1398-164">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="e1398-166">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="e1398-166">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e1398-167">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="e1398-167">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e1398-168">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e1398-168">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e1398-169">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="e1398-169">**Everyone** (default)</span></span>
     - <span data-ttu-id="e1398-170">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="e1398-170">**Specific users / groups**</span></span>
     - <span data-ttu-id="e1398-171">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="e1398-171">**Just me**</span></span>

   - <span data-ttu-id="e1398-172">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e1398-172">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e1398-173">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="e1398-173">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e1398-174">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="e1398-174">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e1398-175">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="e1398-175">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   <span data-ttu-id="e1398-177">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="e1398-177">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e1398-178">På **sidan Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="e1398-178">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e1398-179">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-179">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="e1398-181">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="e1398-181">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="e1398-183">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="e1398-183">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="e1398-184">I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e1398-184">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e1398-185">Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="e1398-185">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins i det nya Microsoft 365 Administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="e1398-187">Leta upp och **välj tillägget** Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="e1398-187">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="e1398-188">I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du lämpliga inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="e1398-188">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e1398-189">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e1398-189">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="e1398-191">Hämta tillägget Rapport om nätfiske</span><span class="sxs-lookup"><span data-stu-id="e1398-191">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="e1398-192">Skaffa tillägget åt dig själv</span><span class="sxs-lookup"><span data-stu-id="e1398-192">Get the add-in for yourself</span></span>

1. <span data-ttu-id="e1398-193">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e1398-193">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="e1398-194">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="e1398-194">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="e1398-195">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="e1398-195">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="e1398-196">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="e1398-196">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="e1398-197">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="e1398-197">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="e1398-198">I Outlook ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1398-198">In Outlook, the icon looks like this:</span></span>

  ![Ikonen för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="e1398-200">I Outlook på webben ser ikonen ut så här:</span><span class="sxs-lookup"><span data-stu-id="e1398-200">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e1398-201">![Outlook på webbrapportens ikon för nätfiske](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="e1398-201">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="e1398-202">Hämta tillägget för din organisation</span><span class="sxs-lookup"><span data-stu-id="e1398-202">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="e1398-203">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1398-203">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="e1398-204">I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e1398-204">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e1398-205">Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="e1398-205">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e1398-206">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-206">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i Microsoft 365 administrationscenter](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="e1398-208">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-208">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="e1398-209">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="e1398-209">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="e1398-211">På sidan **Välj tillägg som visas** klickar  du i rutan Sök, anger **Rapportfiske** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e1398-211">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="e1398-212">Leta rätt på Rapport nätfiske i **listan med resultat och** klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="e1398-212">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="e1398-213">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="e1398-213">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="e1398-214">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="e1398-214">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e1398-215">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e1398-215">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="e1398-216">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="e1398-216">**Everyone** (default)</span></span>
     - <span data-ttu-id="e1398-217">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="e1398-217">**Specific users / groups**</span></span>
     - <span data-ttu-id="e1398-218">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="e1398-218">**Just me**</span></span>

   - <span data-ttu-id="e1398-219">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="e1398-219">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="e1398-220">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="e1398-220">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="e1398-221">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="e1398-221">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="e1398-222">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="e1398-222">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="e1398-223">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="e1398-223">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="e1398-224">På sidan **Distribuera nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="e1398-224">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="e1398-225">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="e1398-225">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="e1398-226">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="e1398-226">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="e1398-227">Granska eller redigera inställningar för tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="e1398-227">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="e1398-228">I Microsoft 365 administrationscentret går du till sidan **Inställningar** tillägg \>  på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="e1398-228">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="e1398-229">Om du inte ser  tilläggssidan går du till **länken Inställningar** Tillägg för integrerade appar högst upp på sidan \>  \>  **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="e1398-229">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="e1398-230">Leta upp och **välj tillägget** Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="e1398-230">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="e1398-231">I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="e1398-231">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="e1398-232">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e1398-232">When you're finished, click **Save**.</span></span>
