---
title: Princip för användarinskick
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratörer kan lära sig hur de konfigurerar en postlåda för att samla in skräppost och nätfiske som rapporterats av användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 321e27f22295a4da17d0eb37b477a1dc7b779d38
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644770"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="b4aac-103">Princip för användarinskick</span><span class="sxs-lookup"><span data-stu-id="b4aac-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b4aac-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="b4aac-104">**Applies to**</span></span>
- [<span data-ttu-id="b4aac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b4aac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b4aac-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="b4aac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b4aac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4aac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b4aac-108">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="b4aac-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="b4aac-109">När användare skickar meddelanden med de olika rapportalternativen kan du använda postlådan för att snappa upp meddelanden (skicka endast till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="b4aac-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="b4aac-110">Den här funktionen fungerar med följande alternativ för meddelanderapportering:</span><span class="sxs-lookup"><span data-stu-id="b4aac-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="b4aac-111">Tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="b4aac-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="b4aac-112">Tillägget Rapport om nätfiske</span><span class="sxs-lookup"><span data-stu-id="b4aac-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="b4aac-113">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (kallades tidigare Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="b4aac-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="b4aac-114">Inbyggd rapportering i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="b4aac-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="b4aac-115">Om rapportering har [inaktiverats](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)i Outlook på webben, åsidosätts den inställningen och användare kan rapportera meddelanden i Outlook på webben igen om de har möjlighet att skicka rapporter här.</span><span class="sxs-lookup"><span data-stu-id="b4aac-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="b4aac-116">Du kan också konfigurera verktyg för meddelanderapportering från tredje part så att meddelanden vidarebefordras till den postlåda du anger.</span><span class="sxs-lookup"><span data-stu-id="b4aac-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="b4aac-117">Genom att leverera användarrapporterade meddelanden till en egen postlåda i stället för direkt till Microsoft kan dina administratörer selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av inskickad [administratör.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="b4aac-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="b4aac-118">Anpassade postlådekrav</span><span class="sxs-lookup"><span data-stu-id="b4aac-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="b4aac-119">Använd följande artiklar för att konfigurera förutsättningarna som krävs så att användarrapporterade meddelanden går till din anpassade postlåda:</span><span class="sxs-lookup"><span data-stu-id="b4aac-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="b4aac-120">Hoppa över skräppostfiltrering på den anpassade postlådan genom att skapa en regel för Exchange-e-postflöde för att ange konfidensnivån för skräppost.</span><span class="sxs-lookup"><span data-stu-id="b4aac-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="b4aac-121">Se Använda EAC för att skapa en e-postflödesregel som anger [SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) för ett meddelande till **-1.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="b4aac-122">Inaktivera genomsökning av bifogade filer för skadlig programvara i den anpassade postlådan.</span><span class="sxs-lookup"><span data-stu-id="b4aac-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="b4aac-123">Använd Konfigurera principer för säkra bifogade filer i Defender för [Office 365](set-up-safe-attachments-policies.md) för att skapa en princip för säkra bifogade filer med inställningen Av för okänd skadlig programvara för **säkra bifogade filer.** </span><span class="sxs-lookup"><span data-stu-id="b4aac-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="b4aac-124">Inaktivera URL-genomsökning av meddelanden i den anpassade postlådan.</span><span class="sxs-lookup"><span data-stu-id="b4aac-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="b4aac-125">Använd Konfigurera principer för säkra länkar i Defender för [Office 365](set-up-safe-links-policies.md) och skapa en princip för säkra länkar med inställningen Av för Välj åtgärden för okända potentiellt skadliga **URL-adresser i meddelanden.** </span><span class="sxs-lookup"><span data-stu-id="b4aac-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="b4aac-126">Skapa en princip mot skadlig programvara för att inaktivera automatisk rensning av skadlig programvara utan timme.</span><span class="sxs-lookup"><span data-stu-id="b4aac-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="b4aac-127">Se [Använda Säkerhets- & Efterlevnadscenter](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för att skapa principer för skydd mot skadlig programvara och ange Automatisk rensning under **nolltimmar till** **Av.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="b4aac-128">Skapa en policy för skräppostfilter för att inaktivera ZAP (Zero-hour Auto Purge) för skräppost och nätfiske i den anpassade postlådan.</span><span class="sxs-lookup"><span data-stu-id="b4aac-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="b4aac-129">Se [Använda Säkerhets- & efterlevnadscenter](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) för att skapa  principer för skydd mot skräppost och avmarkera kryssrutorna On för **Spam ZAP** och **Phish ZAP.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="b4aac-130">Inaktivera skräppostregeln i den anpassade postlådan.</span><span class="sxs-lookup"><span data-stu-id="b4aac-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="b4aac-131">Använd [Konfigurera skräppostinställningar för Exchange Online-postlådor för](configure-junk-email-settings-on-exo-mailboxes.md) att inaktivera skräppostregeln.</span><span class="sxs-lookup"><span data-stu-id="b4aac-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="b4aac-132">När EOP har inaktiverats kan det inte flytta meddelanden till  mappen Skräppost baserat på åtgärden skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.</span><span class="sxs-lookup"><span data-stu-id="b4aac-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="b4aac-133">När du har kontrollerat att din postlåda uppfyller alla tillämpliga krav använder du säkerhets- och [&-efterlevnadscentret](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) för att konfigurera postlådan för användarinskick (i den här artikeln).</span><span class="sxs-lookup"><span data-stu-id="b4aac-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b4aac-134">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b4aac-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b4aac-135">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b4aac-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b4aac-136">För att gå direkt till **sidan användarinskickade** uppgifter använder du <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="b4aac-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="b4aac-137">Du måste vara medlem i någon av följande rollgrupper för att kunna ändra konfigurationen för användarinskick:</span><span class="sxs-lookup"><span data-stu-id="b4aac-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="b4aac-138">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b4aac-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="b4aac-139">**Organisationshantering** i [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="b4aac-139">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b4aac-140">Du behöver åtkomst till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4aac-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="b4aac-141">Om kontot som du försöker använda inte har åtkomst till Exchange Online PowerShell får du ett felmeddelande som ser ut så här när du anger postlådan för inskickade inskickade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="b4aac-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="b4aac-142">Ange en e-postadress i din domän</span><span class="sxs-lookup"><span data-stu-id="b4aac-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="b4aac-143">Mer information om hur du aktiverar eller inaktiverar åtkomst till Exchange Online PowerShell finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="b4aac-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="b4aac-144">Aktivera eller inaktivera åtkomst till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4aac-144">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="b4aac-145">Klientåtkomstregler i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b4aac-145">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="b4aac-146">Använd Säkerhets- & kompatibilitetscenter för att konfigurera postlådan för användarinskick</span><span class="sxs-lookup"><span data-stu-id="b4aac-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="b4aac-147">Gå till användarinskick & av  hothanteringspolicyn i \>  \> **Säkerhets- och efterlevnadscenter.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="b4aac-148">På sidan **Användarinskickade** objekt som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="b4aac-148">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="b4aac-149">Aktivera funktionen Rapportmeddelande för **Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b4aac-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="b4aac-150">**Anpassa bekräftelsemeddelandet för slutanvändaren:** Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="b4aac-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="b4aac-151">I den **utfällo** för bekräftelsemeddelandet Anpassa som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b4aac-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="b4aac-152">**Före inskickning:**  I rutorna Rubrik och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske. </span><span class="sxs-lookup"><span data-stu-id="b4aac-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b4aac-153">Du kan använda variabeln %type% för att inkludera inskickad typ (skräppost, inte skräppost, phish osv.).</span><span class="sxs-lookup"><span data-stu-id="b4aac-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

          <span data-ttu-id="b4aac-154">Som nämnts läggs följande text även till i meddelandet om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b4aac-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="b4aac-155">Ditt e-postmeddelande skickas som det är till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="b4aac-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="b4aac-156">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="b4aac-156">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="b4aac-157">**Efter inskickat** meddelande : Klicka ![ på ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="b4aac-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="b4aac-158">I **rutorna** Rubrik och Bekräftelse anger du den beskrivande text som användarna ser när de rapporterar ett meddelande med hjälp av tilläggen Rapportmeddelande eller Rapport nätfiske. </span><span class="sxs-lookup"><span data-stu-id="b4aac-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="b4aac-159">Du kan använda variabeln %type% för att inkludera inskickingstypen.</span><span class="sxs-lookup"><span data-stu-id="b4aac-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="b4aac-160">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b4aac-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="b4aac-161">Om du vill ta bort dessa värden **klickar du** på Återställ på **sidan Användarinskick.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="b4aac-162">**Anpassa alternativ för rapportering av slutanvändare: Klicka** på den här länken.</span><span class="sxs-lookup"><span data-stu-id="b4aac-162">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="b4aac-163">I den **utfällande alternativ för** Anpassa rapportering för slutanvändare som visas anger du den beskrivande texten för Rapporteringsalternativ för skräppost.</span><span class="sxs-lookup"><span data-stu-id="b4aac-163">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
    
      <span data-ttu-id="b4aac-164">Under **Alternativ som visar när meddelanden rapporteras** väljer du minst ett av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="b4aac-164">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="b4aac-165">**Fråga innan du skickar en rapport**</span><span class="sxs-lookup"><span data-stu-id="b4aac-165">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="b4aac-166">**Skicka rapporter automatiskt**</span><span class="sxs-lookup"><span data-stu-id="b4aac-166">**Automatically send reports**</span></span>
        - <span data-ttu-id="b4aac-167">**Skicka aldrig rapporter**</span><span class="sxs-lookup"><span data-stu-id="b4aac-167">**Never send reports**</span></span>
       
      <span data-ttu-id="b4aac-168">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b4aac-168">When you're finished, click **Save**.</span></span>

        - <span data-ttu-id="b4aac-169">**Skicka de rapporterade meddelandena** till: Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="b4aac-169">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="b4aac-170">**Microsoft (rekommenderas)**: Användarens inskickade postlåda används inte (alla rapporterade meddelanden går till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="b4aac-170">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="b4aac-171">**Både Microsoft och en anpassad postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="b4aac-171">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="b4aac-172">Distributionsgrupper tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="b4aac-172">Distribution groups are not allowed.</span></span> <span data-ttu-id="b4aac-173">Användarinskickade användare går till både Microsoft för analys och den anpassade postlådan som administratören eller säkerhetsteamet kan analysera.</span><span class="sxs-lookup"><span data-stu-id="b4aac-173">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="b4aac-174">**Endast anpassad postlåda:** I rutan som visas anger du e-postadressen till en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="b4aac-174">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="b4aac-175">Distributionsgrupper tillåts inte.</span><span class="sxs-lookup"><span data-stu-id="b4aac-175">Distribution groups are not allowed.</span></span> <span data-ttu-id="b4aac-176">Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsgruppen för analys först.</span><span class="sxs-lookup"><span data-stu-id="b4aac-176">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="b4aac-177">Meddelanden kommer inte att gå till Microsoft om inte administratören vidarebefordrar det själva.</span><span class="sxs-lookup"><span data-stu-id="b4aac-177">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!NOTE]
          > <span data-ttu-id="b4aac-178">U.S. Government organizations (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-178">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="b4aac-179">De andra två alternativen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="b4aac-179">The other two options are disabled.</span></span>

          > [!NOTE]
          > <span data-ttu-id="b4aac-180">Om organisationer är konfigurerade att endast skicka till en anpassad postlåda skickas inte rapporterade meddelanden för sökning och resultat i portalen för användarrapporter är alltid tomma.</span><span class="sxs-lookup"><span data-stu-id="b4aac-180">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="b4aac-181">När du är klar klickar du på **Bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-181">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="b4aac-182">Om du har inaktiverat skräppostrapportering i [Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) på webben med postlådeprinciperna för Outlook på webben, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kommer användarna att kunna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av tillägget Rapportmeddelande eller tillägget Rapportfiske.</span><span class="sxs-lookup"><span data-stu-id="b4aac-182">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    2. <span data-ttu-id="b4aac-183">Inaktivera funktionen Rapportmeddelande för **Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande, tillägget Rapport nätfiske eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="b4aac-183">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

       <span data-ttu-id="b4aac-184">Välj **Använd den här anpassade postlådan för att ta emot användarrapporter**.</span><span class="sxs-lookup"><span data-stu-id="b4aac-184">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="b4aac-185">I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4aac-185">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="b4aac-186">Det måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="b4aac-186">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

       <span data-ttu-id="b4aac-187">När du är klar klickar du på **Bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="b4aac-187">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="b4aac-188">Format för meddelandeinskick</span><span class="sxs-lookup"><span data-stu-id="b4aac-188">Message submission format</span></span>

<span data-ttu-id="b4aac-189">Meddelanden som skickas till anpassade postlådor måste följa ett särskilt e-postformat för inskickade inskickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b4aac-189">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="b4aac-190">Ämne (Kuvertrubrik) för inskickat material ska vara i följande format:</span><span class="sxs-lookup"><span data-stu-id="b4aac-190">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="b4aac-191">där SafetyAPIAction är ett av följande heltalsvärden:</span><span class="sxs-lookup"><span data-stu-id="b4aac-191">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="b4aac-192">1: Skräppost</span><span class="sxs-lookup"><span data-stu-id="b4aac-192">1: Junk</span></span>
- <span data-ttu-id="b4aac-193">2: Inte skräppost</span><span class="sxs-lookup"><span data-stu-id="b4aac-193">2: Not junk</span></span>
- <span data-ttu-id="b4aac-194">3: Nätfiske</span><span class="sxs-lookup"><span data-stu-id="b4aac-194">3: Phishing</span></span>

<span data-ttu-id="b4aac-195">I följande exempel:</span><span class="sxs-lookup"><span data-stu-id="b4aac-195">In the following example:</span></span>

- <span data-ttu-id="b4aac-196">Meddelandet rapporteras som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="b4aac-196">The message is being reported as phishing.</span></span>
- <span data-ttu-id="b4aac-197">Id för nätverksmeddelande är 49871234-6dc6-43e8-abcd-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="b4aac-197">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="b4aac-198">Sender IP is 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="b4aac-198">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="b4aac-199">Från-adressen är test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b4aac-199">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="b4aac-200">Meddelandets ämnesrad är "testa nätfiske"</span><span class="sxs-lookup"><span data-stu-id="b4aac-200">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="b4aac-201">Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inskickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b4aac-201">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
