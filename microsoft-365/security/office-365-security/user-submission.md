---
title: Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa hur du konfigurerar en post låda för att samla in skräp post och nätfiske som rapporteras av användare.
ms.openlocfilehash: e482399adb6304840b8286a226800e6b9dcb6813
ms.sourcegitcommit: 916fa2dacbc13287b49823176375259d7af03f86
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/04/2020
ms.locfileid: "47394729"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="95ab6-103">Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95ab6-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="95ab6-104">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en post låda som tar emot meddelanden som användare rapporterar som skadlig eller inte skadlig.</span><span class="sxs-lookup"><span data-stu-id="95ab6-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="95ab6-105">När användarna skickar meddelanden med olika rapporterings alternativ kan du använda den här post lådan för att avlyssna meddelanden (endast skicka till den anpassade post lådan) eller ta emot kopior av meddelanden (skicka till den anpassade post lådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="95ab6-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="95ab6-106">Den här funktionen fungerar med följande alternativ för meddelande rapportering:</span><span class="sxs-lookup"><span data-stu-id="95ab6-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="95ab6-107">Tillägget rapport</span><span class="sxs-lookup"><span data-stu-id="95ab6-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="95ab6-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="95ab6-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="95ab6-109">Inbyggd rapportering i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="95ab6-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="95ab6-110">Om rapportering har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), åsidosätter du den inställningen och gör att användare kan rapportera meddelanden i Outlook på webben igen.</span><span class="sxs-lookup"><span data-stu-id="95ab6-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="95ab6-111">Du kan också konfigurera meddelande rapporterings verktyg från tredje part så att meddelanden vidarebefordras till den post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="95ab6-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="95ab6-112">Om du levererar rapporter till en egen post låda i stället för direkt till Microsoft kan administratören selektivt och manuellt rapportera meddelanden till Microsoft via [Administratörs överföring](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="95ab6-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95ab6-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="95ab6-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95ab6-114">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="95ab6-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="95ab6-115">Om du vill gå direkt till sidan **användar överföring** kan du använda <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="95ab6-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="95ab6-116">Om du vill ändra konfigurationen för användar inlämningar måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="95ab6-116">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="95ab6-117">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="95ab6-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="95ab6-118">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="95ab6-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="95ab6-119">Konfigurera e-postpost lådan för användare via säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="95ab6-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="95ab6-120">Gå till användar tillägget för **Threat Management** policy i säkerhets & efterlevnad \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="95ab6-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="95ab6-121">På sidan **användar inlägg** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="95ab6-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="95ab6-122">a.</span><span class="sxs-lookup"><span data-stu-id="95ab6-122">a.</span></span> <span data-ttu-id="95ab6-123">**Aktivera funktionen rapport meddelande för Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget rapportera meddelande eller inbyggd rapportering i Outlook på webben och konfigurera sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="95ab6-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="95ab6-124">**Anpassa slutanvändarens bekräftelse meddelande**: Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="95ab6-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="95ab6-125">Konfigurera följande inställningar i den utfällda **bekräftelse meddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="95ab6-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="95ab6-126">**Före inlämning**: Ange den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tillägget rapport meddelande i rutorna **rubrik** och **bekräftelse meddelande** .</span><span class="sxs-lookup"><span data-stu-id="95ab6-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="95ab6-127">Du kan använda variabeln% Type% för att inkludera sändnings typen (skräp, inte skräp post, Phish, osv.).</span><span class="sxs-lookup"><span data-stu-id="95ab6-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="95ab6-128">Om du väljer ett alternativ som skickar det rapporterade meddelandet till Microsoft läggs även följande text till i meddelandet:</span><span class="sxs-lookup"><span data-stu-id="95ab6-128">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="95ab6-129">Din e-post skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="95ab6-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="95ab6-130">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="95ab6-130">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="95ab6-131">**Efter sändning**: Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="95ab6-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="95ab6-132">Ange den **Title** beskrivande text som användarna ser efter att de har rapporterat ett meddelande med hjälp av rapport tillägget. **Confirmation message**</span><span class="sxs-lookup"><span data-stu-id="95ab6-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="95ab6-133">Du kan använda variabel% Type% för att inkludera överförings typen.</span><span class="sxs-lookup"><span data-stu-id="95ab6-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="95ab6-134">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="95ab6-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="95ab6-135">Om du vill rensa de här värdena klickar du på **Återställ** bakåt på sidan **användar inlägg** .</span><span class="sxs-lookup"><span data-stu-id="95ab6-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="95ab6-136">**Skicka rapporterade meddelanden till**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="95ab6-136">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="95ab6-137">**Microsoft (rekommenderas)**: post lådan användar meddelanden används inte (alla rapporterade meddelanden skickas till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="95ab6-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="95ab6-138">**Microsoft och en anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="95ab6-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="95ab6-139">Distributions grupper är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="95ab6-139">Distribution groups are not allowed.</span></span> <span data-ttu-id="95ab6-140">Användar inlämningar kommer att gå till både Microsoft för analys och den anpassade post lådan för din administratör eller säkerhets åtgärd för att analysera.</span><span class="sxs-lookup"><span data-stu-id="95ab6-140">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="95ab6-141">**Anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="95ab6-141">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="95ab6-142">Distributions grupper är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="95ab6-142">Distribution groups are not allowed.</span></span> <span data-ttu-id="95ab6-143">Använd det här alternativet om du vill att meddelandet endast ska skickas till en administratör eller säkerhets åtgärds teamet för analys.</span><span class="sxs-lookup"><span data-stu-id="95ab6-143">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="95ab6-144">Meddelanden går inte till Microsoft såvida inte administratören vidarebefordrar det själva.</span><span class="sxs-lookup"><span data-stu-id="95ab6-144">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="95ab6-145">Amerikanska statliga organisationer (GCC, GCC-H och DoD) kan endast konfigurera **anpassade post lådor**.</span><span class="sxs-lookup"><span data-stu-id="95ab6-145">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="95ab6-146">De två andra alternativen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="95ab6-146">The other two options are disabled.</span></span> 

      <span data-ttu-id="95ab6-147">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="95ab6-147">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="95ab6-148">Om du har [inaktiverat skräp post rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med hjälp av Outlook på principer för Internet-postlådor, men du konfigurerar något av de föregående inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av rapport tillägget.</span><span class="sxs-lookup"><span data-stu-id="95ab6-148">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="95ab6-149">**Inaktivera funktionen rapport meddelande för Outlook**: Välj det här alternativet om du använder rapporterings verktyg från tredje part i stället för rapport tillägget eller den inbyggda rapporteringen i Outlook på webben och konfigurera sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="95ab6-149">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="95ab6-150">Välj **Använd den här anpassade post lådan för att ta emot inlämning av användare**.</span><span class="sxs-lookup"><span data-stu-id="95ab6-150">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="95ab6-151">I rutan som visas anger du e-postadressen för en befintlig post låda som redan finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="95ab6-151">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="95ab6-152">Detta måste vara en befintlig post låda i Exchange Online som kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="95ab6-152">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="95ab6-153">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="95ab6-153">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="95ab6-154">Meddelande överförings format</span><span class="sxs-lookup"><span data-stu-id="95ab6-154">Message submission format</span></span>

<span data-ttu-id="95ab6-155">Meddelanden som skickas till anpassade post lådor måste följa ett visst e-postformat.</span><span class="sxs-lookup"><span data-stu-id="95ab6-155">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="95ab6-156">Ämnets rubrik (Envelope) för sändningen ska vara i det här formatet:</span><span class="sxs-lookup"><span data-stu-id="95ab6-156">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="95ab6-157">var SafetyAPIAction är ett av följande heltals värden:</span><span class="sxs-lookup"><span data-stu-id="95ab6-157">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="95ab6-158">1: skräp post</span><span class="sxs-lookup"><span data-stu-id="95ab6-158">1: Junk</span></span>
- <span data-ttu-id="95ab6-159">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="95ab6-159">2: NotJunk</span></span>
- <span data-ttu-id="95ab6-160">3: Phish</span><span class="sxs-lookup"><span data-stu-id="95ab6-160">3: Phish</span></span>

<span data-ttu-id="95ab6-161">I följande exempel:</span><span class="sxs-lookup"><span data-stu-id="95ab6-161">In the following example:</span></span>

- <span data-ttu-id="95ab6-162">Meddelandet rapporteras som Phish.</span><span class="sxs-lookup"><span data-stu-id="95ab6-162">The message is being reported as Phish.</span></span>
- <span data-ttu-id="95ab6-163">Nätverks meddelandets ID är 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="95ab6-163">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="95ab6-164">Avsändarens IP är 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="95ab6-164">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="95ab6-165">Från-adressen är test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="95ab6-165">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="95ab6-166">Meddelandets ämnesrad är "testa Phish-sändning"</span><span class="sxs-lookup"><span data-stu-id="95ab6-166">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="95ab6-167">Meddelanden som inte följer det här formatet kommer inte att visas korrekt i portalen med inlämning.</span><span class="sxs-lookup"><span data-stu-id="95ab6-167">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
