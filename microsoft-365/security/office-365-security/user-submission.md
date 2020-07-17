---
title: Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du konfigurerar en postlåda för att samla in skräppost och nätfiske e-post som rapporteras av användare.
ms.openlocfilehash: e9550ce6357ddf19041e752c17e8bd844cba1a11
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726492"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="89736-103">Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="89736-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="89736-104">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="89736-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="89736-105">När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (skicka till endast den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="89736-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="89736-106">Den här funktionen fungerar med följande alternativ för meddelanderapportering:</span><span class="sxs-lookup"><span data-stu-id="89736-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="89736-107">Tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="89736-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="89736-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare känd som Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="89736-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="89736-109">Om rapporteringen har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)åsidosätts den inställningen om du aktiverar användarinlämningar här och gör det möjligt för användare att rapportera meddelanden i Outlook på webben igen.</span><span class="sxs-lookup"><span data-stu-id="89736-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="89736-110">Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="89736-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="89736-111">Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="89736-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="89736-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="89736-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="89736-113">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="89736-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="89736-114">Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="89736-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="89736-115">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="89736-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="89736-116">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="89736-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="89736-117">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="89736-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="89736-118">Om du vill ändra konfigurationen för användaröverföringar måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="89736-118">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="89736-119">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="89736-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="89736-120">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="89736-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="89736-121">För skrivskyddad åtkomst till användarinlämningar måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="89736-121">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="89736-122">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="89736-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="89736-123">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="89736-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="89736-124">Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar</span><span class="sxs-lookup"><span data-stu-id="89736-124">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="89736-125">Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance \> **Policy** \> **Center**.</span><span class="sxs-lookup"><span data-stu-id="89736-125">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="89736-126">På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="89736-126">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="89736-127">a.</span><span class="sxs-lookup"><span data-stu-id="89736-127">a.</span></span> <span data-ttu-id="89736-128">**Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="89736-128">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="89736-129">**Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="89736-129">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="89736-130">Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="89736-130">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="89736-131">**Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="89736-131">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="89736-132">Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="89736-132">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="89736-133">Som nämnts, om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft, läggs även följande text till i meddelandet:</span><span class="sxs-lookup"><span data-stu-id="89736-133">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="89736-134">Din e-post skickas som den är till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="89736-134">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="89736-135">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="89736-135">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="89736-136">**Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="89736-136">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="89736-137">I rutorna **Rubrik** och **Bekräftelse anger** du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="89736-137">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="89736-138">Du kan använda variabeln %type% för att inkludera inlämningstypen.</span><span class="sxs-lookup"><span data-stu-id="89736-138">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="89736-139">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="89736-139">When you're finished, click **Save**.</span></span> <span data-ttu-id="89736-140">Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="89736-140">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="89736-141">**Skicka de rapporterade meddelandena till**: Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="89736-141">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="89736-142">**Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="89736-142">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="89736-143">**Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="89736-143">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="89736-144">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="89736-144">Distribution groups are not allowed.</span></span> <span data-ttu-id="89736-145">Användarinlämningar går till både Microsoft för analys och till den anpassade postlådan för din administratör eller säkerhetsoperationsteam att analysera.</span><span class="sxs-lookup"><span data-stu-id="89736-145">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="89736-146">**Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="89736-146">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="89736-147">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="89736-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="89736-148">Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsoperationsgruppen för analys först.</span><span class="sxs-lookup"><span data-stu-id="89736-148">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="89736-149">Meddelanden går inte till Microsoft om inte administratören vidarebefordrar det själva.</span><span class="sxs-lookup"><span data-stu-id="89736-149">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="89736-150">Amerikanska regeringsorganisationer (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda**.</span><span class="sxs-lookup"><span data-stu-id="89736-150">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="89736-151">De andra två alternativen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="89736-151">The other two options are disabled.</span></span> 

      <span data-ttu-id="89736-152">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="89736-152">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="89736-153">Om du har [inaktiverat skräppostrapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med Outlook på webbpostlådeprinciperna, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="89736-153">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="89736-154">**Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="89736-154">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="89736-155">Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="89736-155">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="89736-156">I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="89736-156">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="89736-157">Detta måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="89736-157">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="89736-158">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="89736-158">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="89736-159">Format för meddelandeöverföring</span><span class="sxs-lookup"><span data-stu-id="89736-159">Message submission format</span></span>

<span data-ttu-id="89736-160">Meddelanden som skickas till anpassade postlådor måste följa ett specifikt e-postformat för inlämning.</span><span class="sxs-lookup"><span data-stu-id="89736-160">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="89736-161">Ämnet (kuvertrubriken) för inlämningen bör vara i detta format:</span><span class="sxs-lookup"><span data-stu-id="89736-161">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="89736-162">var SafetyAPIAction är ett av följande heltalsvärden:</span><span class="sxs-lookup"><span data-stu-id="89736-162">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="89736-163">1: Skräp</span><span class="sxs-lookup"><span data-stu-id="89736-163">1: Junk</span></span>
- <span data-ttu-id="89736-164">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="89736-164">2: NotJunk</span></span>
- <span data-ttu-id="89736-165">3: Phish</span><span class="sxs-lookup"><span data-stu-id="89736-165">3: Phish</span></span>

<span data-ttu-id="89736-166">I följande exempel:</span><span class="sxs-lookup"><span data-stu-id="89736-166">In the following example:</span></span>

- <span data-ttu-id="89736-167">Meddelandet rapporteras som Phish.</span><span class="sxs-lookup"><span data-stu-id="89736-167">The message is being reported as Phish.</span></span>
- <span data-ttu-id="89736-168">Nätverksmeddelande-ID är 49871234-6dc6-43e8-abcd-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="89736-168">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="89736-169">Avsändare IP är 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="89736-169">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="89736-170">Från-adressen är test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="89736-170">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="89736-171">Meddelandets ämnesrad är "test phish submission"</span><span class="sxs-lookup"><span data-stu-id="89736-171">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="89736-172">Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inlämningar.</span><span class="sxs-lookup"><span data-stu-id="89736-172">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
