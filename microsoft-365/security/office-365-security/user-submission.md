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
ms.openlocfilehash: 458938105d03cb82dfa4e9a7824f8b026fddec5d
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294759"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="d9081-103">Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d9081-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="d9081-104">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en post låda som tar emot meddelanden som användare rapporterar som skadlig eller inte skadlig.</span><span class="sxs-lookup"><span data-stu-id="d9081-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="d9081-105">När användarna skickar meddelanden med olika rapporterings alternativ kan du använda den här post lådan för att avlyssna meddelanden (endast skicka till den anpassade post lådan) eller ta emot kopior av meddelanden (skicka till den anpassade post lådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="d9081-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="d9081-106">Den här funktionen fungerar med följande alternativ för meddelande rapportering:</span><span class="sxs-lookup"><span data-stu-id="d9081-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="d9081-107">Tillägget rapport</span><span class="sxs-lookup"><span data-stu-id="d9081-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="d9081-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="d9081-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="d9081-109">Inbyggd rapportering i Outlook för iOS och Android</span><span class="sxs-lookup"><span data-stu-id="d9081-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="d9081-110">Om rapportering har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), åsidosätter du den inställningen och gör att användare kan rapportera meddelanden i Outlook på webben igen.</span><span class="sxs-lookup"><span data-stu-id="d9081-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="d9081-111">Du kan också konfigurera meddelande rapporterings verktyg från tredje part så att meddelanden vidarebefordras till den post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="d9081-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="d9081-112">Om du levererar rapporter till en egen post låda i stället för direkt till Microsoft kan administratören selektivt och manuellt rapportera meddelanden till Microsoft via [Administratörs överföring](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="d9081-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d9081-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d9081-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d9081-114">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d9081-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d9081-115">Om du vill gå direkt till sidan **användar överföring** kan du använda <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="d9081-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="d9081-116">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="d9081-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="d9081-117">Om du vill ändra konfigurationen för användar inlämningar måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="d9081-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="d9081-118">**[Exchange-administratör](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** i Azure AD **och organisations hantering** eller **säkerhets administratör** och i [Center för säkerhets &](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d9081-118">**[Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure AD and **Organization Management** or **Security Administrator** and in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d9081-119">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d9081-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="d9081-120">Om du vill ha skrivskyddad åtkomst till användar innehåll måste du vara medlem i båda följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="d9081-120">For read-only access to User submissions, you need to be a member of both of the following role groups:</span></span>

    - <span data-ttu-id="d9081-121">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d9081-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="d9081-122">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="d9081-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="d9081-123">Konfigurera e-postpost lådan för användare via säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="d9081-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="d9081-124">Gå till användar tillägget för **Threat Management** policy i säkerhets & efterlevnad \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="d9081-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="d9081-125">På sidan **användar inlägg** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d9081-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="d9081-126">a.</span><span class="sxs-lookup"><span data-stu-id="d9081-126">a.</span></span> <span data-ttu-id="d9081-127">**Aktivera funktionen rapport meddelande för Outlook (rekommenderas)**: Välj det här alternativet om du använder tillägget rapportera meddelande eller inbyggd rapportering i Outlook på webben och konfigurera sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d9081-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="d9081-128">**Anpassa slutanvändarens bekräftelse meddelande**: Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="d9081-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="d9081-129">Konfigurera följande inställningar i den utfällda **bekräftelse meddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="d9081-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="d9081-130">**Före inlämning**: Ange den beskrivande text som användarna ser innan de rapporterar ett meddelande med hjälp av tillägget rapport meddelande i rutorna **rubrik** och **bekräftelse meddelande** .</span><span class="sxs-lookup"><span data-stu-id="d9081-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d9081-131">Du kan använda variabeln% Type% för att inkludera sändnings typen (skräp, inte skräp post, Phish, osv.).</span><span class="sxs-lookup"><span data-stu-id="d9081-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="d9081-132">Om du väljer ett alternativ som skickar det rapporterade meddelandet till Microsoft läggs även följande text till i meddelandet:</span><span class="sxs-lookup"><span data-stu-id="d9081-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="d9081-133">Din e-post skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="d9081-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="d9081-134">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="d9081-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="d9081-135">**Efter sändning**: Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="d9081-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="d9081-136">Ange den **Title** beskrivande text som användarna ser efter att de har rapporterat ett meddelande med hjälp av rapport tillägget. **Confirmation message**</span><span class="sxs-lookup"><span data-stu-id="d9081-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="d9081-137">Du kan använda variabel% Type% för att inkludera överförings typen.</span><span class="sxs-lookup"><span data-stu-id="d9081-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="d9081-138">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d9081-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="d9081-139">Om du vill rensa de här värdena klickar du på **Återställ** bakåt på sidan **användar inlägg** .</span><span class="sxs-lookup"><span data-stu-id="d9081-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="d9081-140">**Skicka rapporterade meddelanden till**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="d9081-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="d9081-141">**Microsoft (rekommenderas)**: post lådan användar meddelanden används inte (alla rapporterade meddelanden skickas till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="d9081-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="d9081-142">**Microsoft och en anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="d9081-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d9081-143">Distributions grupper är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="d9081-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="d9081-144">Användar inlämningar kommer att gå till både Microsoft för analys och den anpassade post lådan för din administratör eller säkerhets åtgärd för att analysera.</span><span class="sxs-lookup"><span data-stu-id="d9081-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="d9081-145">**Anpassad post låda**: i rutan som visas anger du e-postadressen för en befintlig Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="d9081-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="d9081-146">Distributions grupper är inte tillåtet.</span><span class="sxs-lookup"><span data-stu-id="d9081-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="d9081-147">Använd det här alternativet om du vill att meddelandet endast ska skickas till en administratör eller säkerhets åtgärds teamet för analys.</span><span class="sxs-lookup"><span data-stu-id="d9081-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="d9081-148">Meddelanden går inte till Microsoft såvida inte administratören vidarebefordrar det själva.</span><span class="sxs-lookup"><span data-stu-id="d9081-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d9081-149">Amerikanska statliga organisationer (GCC, GCC-H och DoD) kan endast konfigurera **anpassade post lådor**.</span><span class="sxs-lookup"><span data-stu-id="d9081-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="d9081-150">De två andra alternativen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="d9081-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="d9081-151">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="d9081-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="d9081-152">Om du har [inaktiverat skräp post rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) med hjälp av Outlook på principer för Internet-postlådor, men du konfigurerar något av de föregående inställningarna för att rapportera meddelanden till Microsoft, kan användarna rapportera meddelanden till Microsoft i Outlook på webben med hjälp av rapport tillägget.</span><span class="sxs-lookup"><span data-stu-id="d9081-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="d9081-153">**Inaktivera funktionen rapport meddelande för Outlook**: Välj det här alternativet om du använder rapporterings verktyg från tredje part i stället för rapport tillägget eller den inbyggda rapporteringen i Outlook på webben och konfigurera sedan följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d9081-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="d9081-154">Välj **Använd den här anpassade post lådan för att ta emot inlämning av användare**.</span><span class="sxs-lookup"><span data-stu-id="d9081-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="d9081-155">I rutan som visas anger du e-postadressen för en befintlig post låda som redan finns i Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9081-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="d9081-156">Detta måste vara en befintlig post låda i Exchange Online som kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="d9081-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="d9081-157">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="d9081-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="d9081-158">Meddelande överförings format</span><span class="sxs-lookup"><span data-stu-id="d9081-158">Message submission format</span></span>

<span data-ttu-id="d9081-159">Meddelanden som skickas till anpassade post lådor måste följa ett visst e-postformat.</span><span class="sxs-lookup"><span data-stu-id="d9081-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="d9081-160">Ämnets rubrik (Envelope) för sändningen ska vara i det här formatet:</span><span class="sxs-lookup"><span data-stu-id="d9081-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="d9081-161">var SafetyAPIAction är ett av följande heltals värden:</span><span class="sxs-lookup"><span data-stu-id="d9081-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="d9081-162">1: skräp post</span><span class="sxs-lookup"><span data-stu-id="d9081-162">1: Junk</span></span>
- <span data-ttu-id="d9081-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="d9081-163">2: NotJunk</span></span>
- <span data-ttu-id="d9081-164">3: Phish</span><span class="sxs-lookup"><span data-stu-id="d9081-164">3: Phish</span></span>

<span data-ttu-id="d9081-165">I följande exempel:</span><span class="sxs-lookup"><span data-stu-id="d9081-165">In the following example:</span></span>

- <span data-ttu-id="d9081-166">Meddelandet rapporteras som Phish.</span><span class="sxs-lookup"><span data-stu-id="d9081-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="d9081-167">Nätverks meddelandets ID är 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="d9081-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="d9081-168">Avsändarens IP är 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="d9081-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="d9081-169">Från-adressen är test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d9081-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="d9081-170">Meddelandets ämnesrad är "testa Phish-sändning"</span><span class="sxs-lookup"><span data-stu-id="d9081-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="d9081-171">Meddelanden som inte följer det här formatet kommer inte att visas korrekt i portalen med inlämning.</span><span class="sxs-lookup"><span data-stu-id="d9081-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
