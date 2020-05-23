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
ms.openlocfilehash: d3ff44957864e3d5e959d6252d1d538cc715ae92
ms.sourcegitcommit: 8d9509e617ede7cc5ba933c54fb9300d2d1c6344
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/22/2020
ms.locfileid: "44347813"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="1ccc9-103">Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1ccc9-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="1ccc9-104">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="1ccc9-105">När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="1ccc9-106">Den här funktionen fungerar med följande alternativ för meddelanderapportering:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="1ccc9-107">Tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="1ccc9-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="1ccc9-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare kallat Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="1ccc9-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="1ccc9-109">Om rapporteringen har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)åsidosätter inställningen om du aktiverar användarinlämningar här och gör det möjligt för användare att rapportera meddelanden i Outlook på webben igen.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="1ccc9-110">Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="1ccc9-111">Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1ccc9-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="1ccc9-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1ccc9-113">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1ccc9-114">Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="1ccc9-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="1ccc9-115">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1ccc9-116">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1ccc9-117">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1ccc9-118">Om du vill konfigurera postlådan för användaröverföringar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="1ccc9-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1ccc9-119">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="1ccc9-120">Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar</span><span class="sxs-lookup"><span data-stu-id="1ccc9-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="1ccc9-121">Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance Center \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="1ccc9-122">På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="1ccc9-123">a.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-123">a.</span></span> <span data-ttu-id="1ccc9-124">**Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="1ccc9-125">**Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="1ccc9-126">Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="1ccc9-127">**Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="1ccc9-128">Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="1ccc9-129">Som nämnts, om du väljer ett alternativ som skickar de rapporterade meddelandena till Microsoft, läggs även följande text till i meddelandet:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="1ccc9-130">Din e-post skickas som den är till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="1ccc9-131">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="1ccc9-132">**Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="1ccc9-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="1ccc9-133">I meddelanderutorna **Rubrik** och **Bekräftelse** anger du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="1ccc9-134">Du kan använda variabeln %type% för att inkludera inlämningstypen.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="1ccc9-135">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="1ccc9-136">Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="1ccc9-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="1ccc9-137">**Skicka de rapporterade meddelandena till**: Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="1ccc9-138">**Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="1ccc9-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="1ccc9-139">**Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="1ccc9-140">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="1ccc9-141">Användarinlämningar går till både Microsoft för analys och till den anpassade postlådan för din administratör eller säkerhetsoperationsteam att analysera.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="1ccc9-142">**Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="1ccc9-143">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="1ccc9-144">Använd det här alternativet om du vill att meddelandet bara ska gå till en administratör eller säkerhetsoperationsgruppen för analys först.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-144">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="1ccc9-145">Meddelanden går inte till Microsoft om inte administratören vidarebefordrar det själva.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-145">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1ccc9-146">Amerikanska regeringsorganisationer (GCC, GCC-H och DoD) kan bara konfigurera **anpassad postlåda**.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-146">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="1ccc9-147">De andra två alternativen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-147">The other two options are disabled.</span></span> 

      <span data-ttu-id="1ccc9-148">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-148">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="1ccc9-149">Om du har [inaktiverat skräppostrapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med Outlook i principerna för webbpostlådor, men konfigurerar någon av de tidigare inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-149">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="1ccc9-150">**Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-150">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="1ccc9-151">Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-151">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="1ccc9-152">I rutan som visas anger du e-postadressen till en befintlig postlåda som redan finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-152">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="1ccc9-153">Detta måste vara en befintlig postlåda i Exchange Online som kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-153">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="1ccc9-154">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-154">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="1ccc9-155">Format för meddelandeöverföring</span><span class="sxs-lookup"><span data-stu-id="1ccc9-155">Message submission format</span></span>

<span data-ttu-id="1ccc9-156">Meddelanden som skickas till anpassade postlådor måste följa ett specifikt e-postformat för inlämning.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="1ccc9-157">Ämnet (kuvertrubriken) för inlämningen bör vara i detta format:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="1ccc9-158">var SafetyAPIAction är ett av följande heltalsvärden:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-158">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="1ccc9-159">1: Skräp</span><span class="sxs-lookup"><span data-stu-id="1ccc9-159">1: Junk</span></span>
- <span data-ttu-id="1ccc9-160">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="1ccc9-160">2: NotJunk</span></span>
- <span data-ttu-id="1ccc9-161">3: Phish</span><span class="sxs-lookup"><span data-stu-id="1ccc9-161">3: Phish</span></span>

<span data-ttu-id="1ccc9-162">I följande exempel:</span><span class="sxs-lookup"><span data-stu-id="1ccc9-162">In the following example:</span></span>

- <span data-ttu-id="1ccc9-163">Meddelandet rapporteras som Phish.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="1ccc9-164">Nätverksmeddelande-ID är 49871234-6dc6-43e8-abcd-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="1ccc9-165">Avsändarens IP är 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="1ccc9-166">Från-adressen är test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="1ccc9-167">Meddelandets ämnesrad är "test phish submission"</span><span class="sxs-lookup"><span data-stu-id="1ccc9-167">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="1ccc9-168">Meddelanden som inte följer det här formatet visas inte korrekt i portalen för inlämningar.</span><span class="sxs-lookup"><span data-stu-id="1ccc9-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
