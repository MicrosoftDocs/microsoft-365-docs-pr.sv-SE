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
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224559"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="26385-103">Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26385-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="26385-104">I Microsoft 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="26385-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="26385-105">När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="26385-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="26385-106">Den här funktionen fungerar med följande alternativ för meddelanderapportering:</span><span class="sxs-lookup"><span data-stu-id="26385-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="26385-107">Tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="26385-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="26385-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare kallat Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="26385-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="26385-109">Om rapporteringen har [inaktiverats i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)åsidosätter inställningen om du aktiverar användarinlämningar här och gör det möjligt för användare att rapportera meddelanden i Outlook på webben igen.</span><span class="sxs-lookup"><span data-stu-id="26385-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="26385-110">Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="26385-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="26385-111">Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="26385-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26385-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="26385-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26385-113">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="26385-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="26385-114">Om du vill gå direkt till sidan **Användares inlämningar** använder du <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="26385-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="26385-115">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="26385-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="26385-116">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="26385-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="26385-117">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="26385-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="26385-118">Om du vill konfigurera postlådan för användaröverföringar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="26385-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="26385-119">Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="26385-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="26385-120">Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar</span><span class="sxs-lookup"><span data-stu-id="26385-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="26385-121">Gå till användarinlämningar för **&-efterlevnadsprincipen** i Security & Compliance Center \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="26385-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="26385-122">På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="26385-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="26385-123">**Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="26385-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="26385-124">**Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="26385-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="26385-125">Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="26385-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="26385-126">**Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="26385-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="26385-127">Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="26385-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="26385-128">Som nämnts läggs även följande text till i anmälan:</span><span class="sxs-lookup"><span data-stu-id="26385-128">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="26385-129">Din e-post skickas som den är till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="26385-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="26385-130">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="26385-130">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="26385-131">**Efter inlämning:** Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="26385-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="26385-132">I meddelanderutorna **Rubrik** och **Bekräftelse** anger du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="26385-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="26385-133">Du kan använda variabeln %type% för att inkludera inlämningstypen.</span><span class="sxs-lookup"><span data-stu-id="26385-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="26385-134">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="26385-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="26385-135">Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="26385-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="26385-136">**Skicka de rapporterade meddelandena till**: Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="26385-136">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="26385-137">**Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="26385-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="26385-138">**Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="26385-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="26385-139">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="26385-139">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="26385-140">**Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="26385-140">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="26385-141">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="26385-141">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="26385-142">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="26385-142">When you're finished, click **Confirm**.</span></span>

     ![Skicka rapporterade meddelanden till Microsoft och en anpassad postlåda](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="26385-144">**Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="26385-144">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="26385-145">Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="26385-145">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="26385-146">I rutan som visas anger du e-postadressen till en befintlig postlåda eller e-postadressen till den postlåda som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="26385-146">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="26385-147">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="26385-147">When you're finished, click **Confirm**.</span></span>

     ![Skicka rapporterade meddelanden till en anpassad postlåda med hjälp av verktyg från tredje part](../../media/user-submission-disable-outlook-report-message.png)
