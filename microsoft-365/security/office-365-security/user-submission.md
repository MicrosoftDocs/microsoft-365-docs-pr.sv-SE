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
ms.openlocfilehash: 6de4c076af5b0c669625cd8edaa367f072c27598
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173350"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a><span data-ttu-id="a8929-103">Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Office 365</span><span class="sxs-lookup"><span data-stu-id="a8929-103">Specify a mailbox for user submissions of spam and phishing messages in Office 365</span></span>

<span data-ttu-id="a8929-104">I Office 365-organisationer med Exchange Online-postlådor kan du ange en postlåda för att ta emot meddelanden som användarna rapporterar som skadliga eller inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="a8929-104">In Office 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="a8929-105">När användare skickar meddelanden med de olika rapporteringsalternativen kan du använda den här postlådan för att avlyssna meddelanden (endast skicka till den anpassade postlådan) eller ta emot kopior av meddelanden (skicka till den anpassade postlådan och Microsoft).</span><span class="sxs-lookup"><span data-stu-id="a8929-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="a8929-106">Den här funktionen fungerar med följande alternativ för meddelanderapportering:</span><span class="sxs-lookup"><span data-stu-id="a8929-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="a8929-107">Tillägget Rapportmeddelande</span><span class="sxs-lookup"><span data-stu-id="a8929-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="a8929-108">[Inbyggd rapportering i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (tidigare kallat Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="a8929-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="a8929-109">Du kan också konfigurera meddelanderapporteringsverktyg från tredje part för att vidarebefordra meddelanden till den postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="a8929-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="a8929-110">Genom att leverera rapporterade meddelanden till en anpassad postlåda i stället för direkt till Microsoft kan administratörerna selektivt och manuellt rapportera meddelanden till Microsoft med hjälp av [admin-inlämning](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a8929-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a8929-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a8929-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a8929-112">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a8929-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a8929-113">Om du vill gå direkt till <https://protection.office.com/userSubmissionsReportMessage>sidan **Användares inlämningar** använder du .</span><span class="sxs-lookup"><span data-stu-id="a8929-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="a8929-114">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8929-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a8929-115">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8929-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a8929-116">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="a8929-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="a8929-117">Om du vill konfigurera postlådan för användaröverföringar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="a8929-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a8929-118">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a8929-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="a8929-119">Använda Security & Compliance Center för att konfigurera postlådan för användarinlämningar</span><span class="sxs-lookup"><span data-stu-id="a8929-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="a8929-120">Gå till **Policy** \> **användarinlämningar**för **&-efterlevnad** \> i Säkerhetsstyrningscenter .</span><span class="sxs-lookup"><span data-stu-id="a8929-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="a8929-121">På sidan **Användares inlämningar** som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="a8929-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="a8929-122">**Aktivera funktionen Rapportmeddelande för Outlook (rekommenderas):** Välj det här alternativet om du använder tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8929-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="a8929-123">**Anpassa bekräftelsemeddelandet för slutanvändare:** Klicka på den här länken.</span><span class="sxs-lookup"><span data-stu-id="a8929-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="a8929-124">Konfigurera följande inställningar i det utfällbara meddelandet **Anpassa bekräftelsemeddelandet** som visas:</span><span class="sxs-lookup"><span data-stu-id="a8929-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="a8929-125">**Innan du skickar in**: I **meddelanderutorna** **Rubrik** och Bekräftelse anger du den beskrivande text som användarna ser innan de rapporterar ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a8929-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a8929-126">Du kan använda variabeln %type% för att inkludera inlämningstypen (skräp, inte skräp, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="a8929-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="a8929-127">Som nämnts läggs även följande text till i anmälan:</span><span class="sxs-lookup"><span data-stu-id="a8929-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="a8929-128">Din e-post skickas som den är till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="a8929-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="a8929-129">Vissa e-postmeddelanden kan innehålla personlig eller känslig information.</span><span class="sxs-lookup"><span data-stu-id="a8929-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="a8929-130">**Efter inlämning:** Klicka på ![ikonen Expandera](../../media/scc-expand-icon.png).</span><span class="sxs-lookup"><span data-stu-id="a8929-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="a8929-131">I meddelanderutorna **Rubrik** och **Bekräftelse** anger du den beskrivande text som användarna ser när de har rapporterat ett meddelande med tillägget Rapportmeddelande.</span><span class="sxs-lookup"><span data-stu-id="a8929-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a8929-132">Du kan använda variabeln %type% för att inkludera inlämningstypen.</span><span class="sxs-lookup"><span data-stu-id="a8929-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="a8929-133">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a8929-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="a8929-134">Om du vill ta bort dessa värden klickar du på **Återställ** igen på sidan **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="a8929-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="a8929-135">**Skicka de rapporterade meddelandena till**: Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="a8929-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="a8929-136">**Microsoft (Rekommenderas)**: Brevlådan för användarinlämningar används inte (alla rapporterade meddelanden går till Microsoft).</span><span class="sxs-lookup"><span data-stu-id="a8929-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="a8929-137">**Microsoft och en anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="a8929-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a8929-138">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="a8929-138">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="a8929-139">**Anpassad postlåda**: Ange e-postadressen till en befintlig Exchange Online-postlåda i rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="a8929-139">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a8929-140">Distributionsgrupper är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="a8929-140">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="a8929-141">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a8929-141">When you're finished, click **Confirm**.</span></span>

     ![Skicka rapporterade meddelanden till Microsoft och en anpassad postlåda](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="a8929-143">**Inaktivera funktionen Rapportmeddelande för Outlook:** Välj det här alternativet om du använder rapporteringsverktyg från tredje part i stället för tillägget Rapportmeddelande eller den inbyggda rapporteringen i Outlook på webben och sedan konfigurerar följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a8929-143">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="a8929-144">Välj **Använd den här anpassade postlådan för att ta emot användarrapporterade inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="a8929-144">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="a8929-145">I rutan som visas anger du e-postadressen till en befintlig postlåda eller e-postadressen till den postlåda som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="a8929-145">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="a8929-146">När du är klar klickar du på **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="a8929-146">When you're finished, click **Confirm**.</span></span>

     ![Skicka rapporterade meddelanden till en anpassad postlåda med hjälp av verktyg från tredje part](../../media/user-submission-disable-outlook-report-message.png)
