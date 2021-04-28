---
title: Rapportera falska positiva och falska negativa resultat i Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Lär dig hur du rapporterar falska positiva och falska negativa resultat i Outlook och aktiverar tilläggen Rapportmeddelande och Rapportera nätfiske.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065206"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a><span data-ttu-id="5af93-103">Rapportera falska positiva och falska negativa resultat i Outlook</span><span class="sxs-lookup"><span data-stu-id="5af93-103">Report false positives and false negatives in Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5af93-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="5af93-104">**Applies to**</span></span>
- [<span data-ttu-id="5af93-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5af93-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5af93-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="5af93-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5af93-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5af93-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="5af93-108">Om du är administratör i en Microsoft 365-organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för inskickade inskickade material i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="5af93-108">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5af93-109">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-109">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5af93-110">I Microsoft 365-organisationer som har postlådor i Exchange Online eller lokala postlådor med modern hybridautentisering kan du skicka falska positiva identifieringar (bra e-post som markeras som skräppost) och falska negativa identifieringar (felaktig e-post och nätsmyckning tillåts) till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="5af93-110">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using hybrid modern authentication, you can submit false positives (good email marked as spam) and false negatives (bad email and phish allowed) to Exchange Online Protection (EOP).</span></span>

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a><span data-ttu-id="5af93-111">Saker att tänka på innan du använder funktionen Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="5af93-111">Things to remember before you use the Report Message feature</span></span>

- <span data-ttu-id="5af93-112">För bästa möjliga användarinskickning använder du tilläggen Rapportmeddelande eller Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-112">For the best user submission experience, use the Report Message add-in or the Report Phishing add-in.</span></span>

- <span data-ttu-id="5af93-113">Observera att det här tillägget fungerar för Outlook på alla plattformar– på webben, iOS, Android och skrivbordet.</span><span class="sxs-lookup"><span data-stu-id="5af93-113">Note that this add-in works for Outlook in all platforms—on the web, iOS, Android, and Desktop.</span></span>

- <span data-ttu-id="5af93-114">Om du är administratör i en organisation med Exchange Online-postlådor använder du portalen för sändning i säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="5af93-114">If you're an admin in an organization with Exchange Online mailboxes, use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5af93-115">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-115">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="5af93-116">Du kan konfigurera så att meddelanden skickas direkt till Microsoft, en postlåda som du anger eller båda.</span><span class="sxs-lookup"><span data-stu-id="5af93-116">You can configure to send messages directly to Microsoft, a mailbox you specify, or both.</span></span> <span data-ttu-id="5af93-117">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="5af93-118">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-report-message-feature"></a><span data-ttu-id="5af93-119">Använda funktionen Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="5af93-119">Use the Report Message feature</span></span>

### <a name="report-junk-and-phishing-messages"></a><span data-ttu-id="5af93-120">Rapportera skräppost och nätfiskemeddelanden</span><span class="sxs-lookup"><span data-stu-id="5af93-120">Report junk and phishing messages</span></span>

<span data-ttu-id="5af93-121">För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du följande metod för att rapportera skräppost och nätfiske:</span><span class="sxs-lookup"><span data-stu-id="5af93-121">For messages in the Inbox or any other email folder except Junk Email, use the following method to report spam and phishing messages:</span></span>

1. <span data-ttu-id="5af93-122">Klicka på **ellipsen** Fler åtgärder längst upp till höger  i det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och välj sedan **Skräppost** eller **Nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="5af93-122">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then select **Junk** or **Phishing**.</span></span>
  
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5af93-123">![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-123">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5af93-124">![Rapportmeddelande – skräppost och nätfiske](../../media/report-message-junk-phishing.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-124">![Report Message - Junk and Phishing](../../media/report-message-junk-phishing.png)</span></span>

2. <span data-ttu-id="5af93-125">De valda meddelandena skickas till Microsoft för analys och:</span><span class="sxs-lookup"><span data-stu-id="5af93-125">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="5af93-126">Flyttades till mappen Skräppost om den rapporterades som skräppost.</span><span class="sxs-lookup"><span data-stu-id="5af93-126">Moved to the Junk Email folder if it was reported as spam.</span></span>

   - <span data-ttu-id="5af93-127">Borttagna om det har rapporterats som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-127">Deleted if it was reported as phishing.</span></span>
   
### <a name="report-messages-that-are-not-junk"></a><span data-ttu-id="5af93-128">Rapportera meddelanden som inte är skräppost</span><span class="sxs-lookup"><span data-stu-id="5af93-128">Report messages that are not junk</span></span>

1. <span data-ttu-id="5af93-129">Klicka på **ellipsen** Fler åtgärder i det övre högra  hörnet av det markerade meddelandet, klicka på Rapportera meddelande i den nedrullningsbara menyn och klicka sedan **på Inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="5af93-129">Click the **More actions** ellipses on the top-right corner of the selected message, click **Report message** from the dropdown menu, and then click **Not Junk**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5af93-130">![Rapportmeddelande – fler åtgärder](../../media/report-message-more-actions.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-130">![Report Message - More actions](../../media/report-message-more-actions.png)</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5af93-131">![Rapportmeddelande – inte skräppost](../../media/report-message-not-junk.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-131">![Report Message - Not junk](../../media/report-message-not-junk.png)</span></span>

2. <span data-ttu-id="5af93-132">Det markerade meddelandet skickas till Microsoft för analys och flyttas till Inkorgen eller någon annan angiven mapp.</span><span class="sxs-lookup"><span data-stu-id="5af93-132">The selected message will be sent to Microsoft for analysis and moved to Inbox or any other specified folder.</span></span>

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a><span data-ttu-id="5af93-133">Aktivera tilläggen Rapportmeddelande och Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="5af93-133">Enable the Report Message and Report Phishing add-ins</span></span>

<span data-ttu-id="5af93-134">Med tilläggen Rapportmeddelande och Rapport nätfiske för Outlook och Outlook på webben (tidigare kallat Outlook Web App) kan användare enkelt rapportera falska positiva resultat (bra e-post markerad som dålig) eller falska negativa (felaktig e-post tillåten) till Microsoft och dess dotterbolag för analys.</span><span class="sxs-lookup"><span data-stu-id="5af93-134">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> 

<span data-ttu-id="5af93-135">Microsoft använder dessa inskickade material för att göra e-postskyddstekniken mer effektiv.</span><span class="sxs-lookup"><span data-stu-id="5af93-135">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="5af93-136">Anta till exempel att personer rapporterar många meddelanden med hjälp av tillägget Rapport om nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-136">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="5af93-137">Den här informationen visas i säkerhetspanelen och andra rapporter.</span><span class="sxs-lookup"><span data-stu-id="5af93-137">This information surfaces in the Security Dashboard and other reports.</span></span> <span data-ttu-id="5af93-138">Din organisations säkerhetsgrupp kan använda den här informationen som en indikation på att principer mot nätfiske kan behöva uppdateras.</span><span class="sxs-lookup"><span data-stu-id="5af93-138">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> 

<span data-ttu-id="5af93-139">Du kan installera antingen tillägget Rapportmeddelande eller Rapportera nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-139">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="5af93-140">Om du vill att användarna ska rapportera både skräppost och nätfiske distribuerar du tillägget Rapportmeddelande i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5af93-140">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="5af93-141">Mer information finns i Aktivera tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="5af93-141">For more information, see Enable the Report Message add-in.</span></span> 

<span data-ttu-id="5af93-142">Via tillägget Rapportmeddelande kan du rapportera både skräppost och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-142">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="5af93-143">Administratörer kan aktivera tillägget Rapportmeddelande för organisationen och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="5af93-143">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="5af93-144">Tillägget Rapport nätfiske ger möjlighet att endast rapportera nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="5af93-144">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="5af93-145">Administratörer kan aktivera tillägget Rapport nätfiske för organisationen, och enskilda användare kan installera det själva.</span><span class="sxs-lookup"><span data-stu-id="5af93-145">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span> 

<span data-ttu-id="5af93-146">Om du är enskild användare kan du aktivera båda tilläggen själv.</span><span class="sxs-lookup"><span data-stu-id="5af93-146">If you're an individual user, you can enable both the add-ins for yourself.</span></span>

<span data-ttu-id="5af93-147">om du är global administratör eller Exchange Online-administratör och Exchange är konfigurerat för OAuth-autentisering kan du aktivera tillägget Rapportmeddelande och tillägget Rapportfiske för organisationen.</span><span class="sxs-lookup"><span data-stu-id="5af93-147">f you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can enable the Report Message add-in and the Report Phishing add-in for your organization.</span></span> <span data-ttu-id="5af93-148">Båda tilläggen är nu tillgängliga via [centraliserad distribution.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-148">Both add-ins are now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5af93-149">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="5af93-149">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5af93-150">Både tillägget Rapportmeddelande och tillägget Rapportfiske fungerar med de flesta Microsoft 365-prenumerationer och följande produkter:</span><span class="sxs-lookup"><span data-stu-id="5af93-150">Both the Report Message add-in and the Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="5af93-151">Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="5af93-151">Outlook on the web</span></span>
  - <span data-ttu-id="5af93-152">Outlook 2013 SP1 eller senare</span><span class="sxs-lookup"><span data-stu-id="5af93-152">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="5af93-153">Outlook 2016 för Mac</span><span class="sxs-lookup"><span data-stu-id="5af93-153">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="5af93-154">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="5af93-154">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="5af93-155">Outlook-appen för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="5af93-155">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="5af93-156">Båda tilläggen är inte tillgängliga för delade postlådor eller postlådor i lokala Exchange-organisationer.</span><span class="sxs-lookup"><span data-stu-id="5af93-156">Both add-ins are not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="5af93-157">Din befintliga webbläsare bör fungera med tilläggen Rapportmeddelande och Rapportera nätfiske. Om du märker att tillägget inte är tillgängligt eller inte fungerar som förväntat kan du prova en annan webbläsare.</span><span class="sxs-lookup"><span data-stu-id="5af93-157">Your existing web browser should work with both the Report Message and Report Phishing add-ins. But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="5af93-158">För organisationsinstallationer måste organisationen konfigureras för att använda OAuth-autentisering.</span><span class="sxs-lookup"><span data-stu-id="5af93-158">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="5af93-159">Mer information finns i [Avgöra om centraliserad distribution av tillägg fungerar för din organisation.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-159">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="5af93-160">Administratörer måste vara medlemmar i rollgruppen Globala administratörer.</span><span class="sxs-lookup"><span data-stu-id="5af93-160">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="5af93-161">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5af93-161">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in"></a><span data-ttu-id="5af93-162">Hämta tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="5af93-162">Get the Report Message add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="5af93-163">Skaffa tillägget åt dig själv</span><span class="sxs-lookup"><span data-stu-id="5af93-163">Get the add-in for yourself</span></span>

1. <span data-ttu-id="5af93-164">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="5af93-164">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="5af93-165">Gå direkt till tillägget Rapportmeddelande genom att gå till <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="5af93-165">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="5af93-166">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="5af93-166">Click **GET IT NOW**.</span></span>

   ![Rapportmeddelande – skaffa det nu](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="5af93-168">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5af93-168">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="5af93-169">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="5af93-169">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="5af93-170">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="5af93-170">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="5af93-171">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="5af93-171">In Outlook, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5af93-172">![Ikonen för tillägget Rapportmeddelande för Outlook](../../media/OutlookReportMessageIcon.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-172">![Report Message add-in icon for Outlook](../../media/OutlookReportMessageIcon.png)</span></span>

- <span data-ttu-id="5af93-173">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="5af93-173">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5af93-174">![Tilläggsikon för meddelande i Outlook på webben](../../media/owa-report-message-icon.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-174">![Outlook on the web Report Message add-in icon](../../media/owa-report-message-icon.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="5af93-175">Hämta tillägget för din organisation</span><span class="sxs-lookup"><span data-stu-id="5af93-175">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="5af93-176">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5af93-176">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="5af93-177">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="5af93-177">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="5af93-178">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="5af93-178">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="5af93-179">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-179">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="5af93-181">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-181">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="5af93-182">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="5af93-182">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="5af93-184">På sidan **Välj tillägg som visas** klickar du i rutan **Sök,** skriver **Rapportmeddelande** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="5af93-184">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="5af93-185">Leta rätt på Rapportmeddelande i **resultatlistan och klicka** sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="5af93-185">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Välj sökresultat för tillägg](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="5af93-187">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5af93-187">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="5af93-188">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="5af93-188">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5af93-189">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5af93-189">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="5af93-190">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="5af93-190">**Everyone** (default)</span></span>
     - <span data-ttu-id="5af93-191">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="5af93-191">**Specific users / groups**</span></span>
     - <span data-ttu-id="5af93-192">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="5af93-192">**Just me**</span></span>

   - <span data-ttu-id="5af93-193">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5af93-193">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="5af93-194">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="5af93-194">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="5af93-195">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="5af93-195">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="5af93-196">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="5af93-196">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Konfigurera tilläggssida](../../media/configure-add-in.png)

   <span data-ttu-id="5af93-198">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="5af93-198">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="5af93-199">På **sidan Distribuera rapportmeddelande** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="5af93-199">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="5af93-200">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-200">After you read the information, click **Next**.</span></span>

   ![Sidan Distribuera rapportmeddelande](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="5af93-202">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="5af93-202">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Sidan Presentera tillägg](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="5af93-204">Granska eller redigera inställningar för tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="5af93-204">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="5af93-205">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="5af93-205">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="5af93-206">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="5af93-206">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Tjänster och Add-Ins i det nya administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="5af93-208">Leta upp och **välj tillägget** Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="5af93-208">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="5af93-209">I den **utfällna** menyn Redigera rapportmeddelande som visas granskar och redigerar du lämpliga inställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="5af93-209">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="5af93-210">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="5af93-210">When you're finished, click **Save**.</span></span>

   ![Inställningar för tillägget Rapportmeddelande](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a><span data-ttu-id="5af93-212">Hämta tillägget Rapport om nätfiske</span><span class="sxs-lookup"><span data-stu-id="5af93-212">Get the Report Phishing add-in</span></span>

### <a name="get-the-add-in-for-yourself"></a><span data-ttu-id="5af93-213">Skaffa tillägget åt dig själv</span><span class="sxs-lookup"><span data-stu-id="5af93-213">Get the add-in for yourself</span></span>

1. <span data-ttu-id="5af93-214">Gå till Microsoft AppSource på <https://appsource.microsoft.com/marketplace/apps> och sök efter tillägget Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-214">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="5af93-215">Klicka **på HÄMTA NU.**</span><span class="sxs-lookup"><span data-stu-id="5af93-215">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="5af93-216">I dialogrutan som visas granskar du användningsvillkoren och sekretesspolicyn och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5af93-216">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="5af93-217">Logga in med ditt arbets- eller skolkonto (för företagsanvändning) eller ditt Microsoft-konto (för personlig användning).</span><span class="sxs-lookup"><span data-stu-id="5af93-217">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="5af93-218">När tillägget har installerats och aktiverats visas följande ikoner:</span><span class="sxs-lookup"><span data-stu-id="5af93-218">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="5af93-219">Ikonen ser ut så här i Outlook:</span><span class="sxs-lookup"><span data-stu-id="5af93-219">In Outlook, the icon looks like this:</span></span>

  ![Ikon för tillägget Nätfiske för Outlook](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="5af93-221">Ikonen ser ut så här i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="5af93-221">In Outlook on the web, the icon looks like this:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5af93-222">![Outlook på webben-tillägget Nätfiske](../../media/OWA-ReportPhishing.png)</span><span class="sxs-lookup"><span data-stu-id="5af93-222">![Outlook on the web Report Phishing add-in icon](../../media/OWA-ReportPhishing.png)</span></span>

### <a name="get-the-add-in-for-your-organization"></a><span data-ttu-id="5af93-223">Hämta tillägget för din organisation</span><span class="sxs-lookup"><span data-stu-id="5af93-223">Get the add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="5af93-224">Det kan ta upp till 12 timmar innan tillägget visas i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5af93-224">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="5af93-225">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="5af93-225">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="5af93-226">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="5af93-226">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="5af93-227">Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-227">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Sidan Tjänster och tillägg i administrationscentret för Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="5af93-229">I den **utfällbaserade menyn** Distribuera ett nytt tillägg som visas granskar du informationen och klickar sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-229">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="5af93-230">Klicka på Välj från **Store på nästa sida.**</span><span class="sxs-lookup"><span data-stu-id="5af93-230">On the next page, click **Choose from the Store**.</span></span>

   ![Distribuera en ny tilläggssida](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="5af93-232">På sidan **Välj tillägg som visas** klickar  du i rutan Sök, anger **Rapportfiske** och klickar sedan på **sökikonen** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="5af93-232">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="5af93-233">Leta rätt på Rapport nätfiske i **listan med resultat och** klicka sedan på Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="5af93-233">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="5af93-234">I dialogrutan som visas granskar du licens- och sekretessinformationen och klickar sedan på **Fortsätt.**</span><span class="sxs-lookup"><span data-stu-id="5af93-234">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="5af93-235">Konfigurera **följande inställningar på sidan** Konfigurera tillägget som visas:</span><span class="sxs-lookup"><span data-stu-id="5af93-235">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5af93-236">**Tilldelade användare:** Välj ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5af93-236">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="5af93-237">**Alla** (standard)</span><span class="sxs-lookup"><span data-stu-id="5af93-237">**Everyone** (default)</span></span>
     - <span data-ttu-id="5af93-238">**Specifika användare/grupper**</span><span class="sxs-lookup"><span data-stu-id="5af93-238">**Specific users / groups**</span></span>
     - <span data-ttu-id="5af93-239">**Bara jag**</span><span class="sxs-lookup"><span data-stu-id="5af93-239">**Just me**</span></span>

   - <span data-ttu-id="5af93-240">**Distributionsmetod:** Välj något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5af93-240">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="5af93-241">**Åtgärdat (standard)**: Tillägget distribueras automatiskt till angivna användare och de kan inte ta bort det.</span><span class="sxs-lookup"><span data-stu-id="5af93-241">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="5af93-242">**Tillgängligt:** Användarna kan installera tillägget på **Fliken** Hämta \> **tillägg som hanteras** av \> **administratören.**</span><span class="sxs-lookup"><span data-stu-id="5af93-242">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="5af93-243">**Valfritt:** Tillägget distribueras automatiskt till de angivna användarna, men de kan välja att ta bort det.</span><span class="sxs-lookup"><span data-stu-id="5af93-243">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="5af93-244">När du är klar klickar du på **Distribuera.**</span><span class="sxs-lookup"><span data-stu-id="5af93-244">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="5af93-245">På sidan **Distribuera nätfiske** som visas visas en förloppsrapport följt av en bekräftelse på att tillägget har distribuerats.</span><span class="sxs-lookup"><span data-stu-id="5af93-245">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="5af93-246">När du har läst informationen klickar du på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="5af93-246">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="5af93-247">På **sidan Presentera tillägg som** visas granskar du informationen och klickar sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="5af93-247">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="5af93-248">Granska eller redigera inställningar för tillägget Rapport nätfiske</span><span class="sxs-lookup"><span data-stu-id="5af93-248">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="5af93-249">I administrationscentret för Microsoft 365 går du till **sidan** \> **Förinställningar-tillägg** på <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> .</span><span class="sxs-lookup"><span data-stu-id="5af93-249">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>.</span></span> <span data-ttu-id="5af93-250">Om du inte ser  tilläggssidan går du  till länken Inställningar Integrerade appar Tillägg högst upp på \>  \>  sidan **Integrerade** appar.</span><span class="sxs-lookup"><span data-stu-id="5af93-250">If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="5af93-251">Leta upp och **välj tillägget** Rapport nätfiske.</span><span class="sxs-lookup"><span data-stu-id="5af93-251">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="5af93-252">I den **utfällna** menyn Redigera rapport nätfiske som visas, granskar och redigerar du inställningarna efter behov för din organisation.</span><span class="sxs-lookup"><span data-stu-id="5af93-252">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="5af93-253">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="5af93-253">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="5af93-254">Visa och granska rapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="5af93-254">View and review reported messages</span></span>

<span data-ttu-id="5af93-255">Om du vill granska meddelanden som användare rapporterar till Microsoft har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="5af93-255">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="5af93-256">Använd portalen för administrationsinskick.</span><span class="sxs-lookup"><span data-stu-id="5af93-256">Use the Admin Submissions portal.</span></span> <span data-ttu-id="5af93-257">Mer information finns i [Visa användarinskick till Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="5af93-257">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="5af93-258">Skapa en e-postflödesregel (kallas även transportregel) för att skicka kopior av rapporterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="5af93-258">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="5af93-259">Anvisningar finns i Använda [e-postflödesregler för att se vad användarna rapporterar till Microsoft.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5af93-259">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>