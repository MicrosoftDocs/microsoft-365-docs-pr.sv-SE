---
title: Rapportera skräppost och nätfiskemeddelanden i Outlook på webben
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om de inbyggda alternativen för skräppost, inte skräppost och rapportering av nätfiske i Outlook på webben (Outlook Web App) i Exchange Online och hur du inaktiverar dessa rapporteringsalternativ för användare.
ms.openlocfilehash: adbb4f16201e221bce2405a7b715dd6a630e9e1d
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617326"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="c39c3-103">Rapportera skräppost och nätfiskemeddelanden i Outlook på webben i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c39c3-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="c39c3-104">I Microsoft 365-organisationer med postlådor i Exchange Online kan du använda de inbyggda rapporteringsalternativen i Outlook på webben (tidigare kallat Outlook Web App) för att skicka in falska positiva identifieringar (bra e-post markerat som skräppost), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c39c3-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c39c3-105">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c39c3-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c39c3-106">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inlämningar i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="c39c3-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c39c3-107">Mer information finns i [Använda administratörsöverföring för att skicka misstänkt skräppost, phish, URL:er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c39c3-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c39c3-108">Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="c39c3-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="c39c3-109">Mer information finns i [avsnittet Inaktivera eller aktivera skräppostrapportering i Outlook på webben](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c39c3-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="c39c3-110">Du kan konfigurera rapporterade meddelanden som ska kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="c39c3-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c39c3-111">Mer information finns i [Ange en postlåda för användarinlämningar av skräppost och nätfiskemeddelanden i Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c39c3-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="c39c3-112">Mer information om hur du anmäler meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c39c3-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="c39c3-113">Rapportera skräppost och nätfiskemeddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c39c3-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="c39c3-114">För meddelanden i Inkorgen eller någon annan e-postmapp utom skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="c39c3-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="c39c3-115">Markera meddelandet, klicka på **Skräppost** i verktygsfältet och välj sedan **Skräppost** eller **Nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/owa-report-junk.png)

   - <span data-ttu-id="c39c3-117">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som skräppost**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="c39c3-118">Klicka på **Rapportera**i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c39c3-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="c39c3-119">Om du ändrar dig klickar du på **Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-119">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport som skräppostdialogruta](../../media/owa-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="c39c3-122">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="c39c3-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="c39c3-123">Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="c39c3-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="c39c3-124">Rapportera meddelanden som inte är skräppost och nätfiske från mappen Skräppost i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c39c3-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="c39c3-125">I mappen Skräppost använder du någon av följande metoder för att rapportera falska positiva skräppost eller nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="c39c3-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="c39c3-126">Markera meddelandet, klicka på **Inte skräppost** i verktygsfältet och välj sedan **Inte skräppost** eller **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="c39c3-128">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som inte skräppost**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="c39c3-129">Läs informationen i dialogrutan som visas och klicka på **Rapportera**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c39c3-130">Om du ändrar dig klickar du på **Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-130">If you change your mind, click **Don't Report**.</span></span>

   ![Rapportera som inte skräppostdialogruta](../../media/owa-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="c39c3-133">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="c39c3-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="c39c3-134">Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="c39c3-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="c39c3-135">Inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c39c3-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="c39c3-136">Som standard kan användare rapportera falska positiva skräpposter, falska negativ och nätfiskemeddelanden till Microsoft för analys i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="c39c3-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="c39c3-137">Administratörer kan konfigurera Outlook på webbpostlådeprinciperna i Exchange Online PowerShell för att förhindra att användare rapporterar falska positiva skräpposter och falska skräppost negativ till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c39c3-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="c39c3-138">Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c39c3-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c39c3-139">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c39c3-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c39c3-140">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c39c3-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c39c3-141">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="c39c3-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c39c3-142">Du behöver som standard rollerna **Mottagare eller** **E-postmottagare** i Exchange Online, som tilldelas rollgrupperna **Organisationshantering** och **Mottagarhantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="c39c3-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="c39c3-143">Mer information om rollgrupper i Exchange Online finns [i Ändra rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="c39c3-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="c39c3-144">Varje organisation har en standardprincip med namnet OwaMailboxPolicy-Default, men du kan skapa anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="c39c3-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="c39c3-145">Anpassade principer tillämpas på begränsade användare före standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="c39c3-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="c39c3-146">Mer information om Outlook i principerna för webbpostlåda finns i Outlook i principerna för [webbpostlådan i Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="c39c3-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="c39c3-147">Om du inaktiverar skräppostrapportering tas inte möjligheten att markera ett meddelande som skräppost eller inte skräppost i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="c39c3-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="c39c3-148">Om du markerar ett meddelande i mappen Skräppost och klickar på **Inte skräppost** flyttas meddelandet tillbaka till \> **Not junk** Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="c39c3-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="c39c3-149">Om du markerar ett meddelande i **Junk** en annan e-postmapp och klickar på \> **Skräppost** flyttas meddelandet fortfarande till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="c39c3-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="c39c3-150">Det som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c39c3-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="c39c3-151">Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="c39c3-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="c39c3-152">Om du vill hitta dina befintliga Outlook på webbpostlådeprinciperna och statusen för skräppostrapportering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="c39c3-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="c39c3-153">Om du vill inaktivera eller aktivera skräppostrapportering i Outlook på webben använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="c39c3-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="c39c3-154">I det här exemplet inaktiveras skräppostrapportering i standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="c39c3-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="c39c3-155">I det här exemplet kan skräppostrapportering i den anpassade principen Contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="c39c3-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="c39c3-156">Detaljerad syntax- och parameterinformation finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) och [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="c39c3-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c39c3-157">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="c39c3-157">How do you know this worked?</span></span>

<span data-ttu-id="c39c3-158">Om du vill kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben använder du något av följande:</span><span class="sxs-lookup"><span data-stu-id="c39c3-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="c39c3-159">I Exchange Online PowerShell kör du följande kommando och verifierar egenskapsvärdet **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="c39c3-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="c39c3-160">Öppna en berörd användares postlåda i Outlook på webben, **Junk** välj ett meddelande i Inkorgen, klicka på \> **Skräppost** och kontrollera uppmaningen att rapportera meddelandet till Microsoft visas eller visas inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c39c3-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="c39c3-161">Öppna en berörd användares postlåda i Outlook på webben, välj **Junk** ett meddelande i mappen Skräppost, klicka på \> **Skräppost** och kontrollera uppmaningen om att rapportera meddelandet till Microsoft visas eller visas inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c39c3-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="c39c3-162"><sup>\*</sup>Användare kan dölja uppmaningen om att rapportera meddelandet medan de fortfarande anmäler meddelandet.</span><span class="sxs-lookup"><span data-stu-id="c39c3-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="c39c3-163">Så här kontrollerar du den här inställningen i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="c39c3-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="c39c3-164">Klicka på **Inställningar** ![ Outlook på ikonen för webbinställningar Visa ](../../media/owa-settings-icon.png) \> **alla** \> **Skräppostinställningar i**Outlook .</span><span class="sxs-lookup"><span data-stu-id="c39c3-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="c39c3-165">Kontrollera värdet i avsnittet **Rapportering:** **Fråga mig innan du skickar en rapport**.</span><span class="sxs-lookup"><span data-stu-id="c39c3-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook på webben Inställningar för rapportering av skräppost](../../media/owa-junk-email-reporting-options.png)
