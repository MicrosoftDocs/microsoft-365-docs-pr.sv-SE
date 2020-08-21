---
title: Rapportera skräp post och nätfiske i Outlook på webben
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig mer om de inbyggda alternativen för skräp post, inte skräp post och nätfiske i Outlook på webben (Outlook Web App) i Exchange Online och hur du inaktiverar dessa rapporterings alternativ för användare.
ms.openlocfilehash: 947f9bb9c1c686b549d83b27c262e86eda0d5008
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826547"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="7ec2a-103">Rapportera skräp post och nätfiske i Outlook på webben i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7ec2a-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

<span data-ttu-id="7ec2a-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan du använda de inbyggda rapporterings alternativen i Outlook på webben (tidigare Outlook Web App) för att skicka falska positiva (e-postmeddelanden markerade som skräp post), falskt negativ (dålig e-post) och nätfiske-meddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ec2a-105">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="7ec2a-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ec2a-106">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7ec2a-107">Mer information finns i [använda administratörs överföring för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="7ec2a-108">Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="7ec2a-109">Mer information finns i [Aktivera eller inaktivera rapportering av skräp post i Outlook på webben](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) längre ned i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="7ec2a-110">Du kan konfigurera vilka meddelanden som ska kopieras eller dirigeras om till en post låda som du anger.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7ec2a-111">Mer information finns i [Ange en post låda för användar överföringar av skräp post och nät fiske meddelanden i Exchange Online](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="7ec2a-112">Mer information om hur du rapporterar meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="7ec2a-113">Rapportera skräp post och nät fiske meddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="7ec2a-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="7ec2a-114">Använd någon av följande metoder för att rapportera skräp post och nät fiske meddelanden, för meddelanden i Inkorgen eller annan mapp för e-post utom skräp posten:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="7ec2a-115">Markera meddelandet, klicka på **skräp post** i verktygsfältet och välj sedan **skräp post** eller **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/owa-report-junk.png)

   - <span data-ttu-id="7ec2a-117">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som skräp post**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="7ec2a-118">Klicka på **rapport**i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="7ec2a-119">Om du ändrar dig klickar du på **rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="7ec2a-120">Mappen</span><span class="sxs-lookup"><span data-stu-id="7ec2a-120">Junk</span></span>|<span data-ttu-id="7ec2a-121">Fiske</span><span class="sxs-lookup"><span data-stu-id="7ec2a-121">Phishing</span></span>|
   |:---:|:---:|
   |![Dialog rutan rapportera som skräp post](../../media/owa-report-as-junk-dialog.png)|![Dialog rutan rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="7ec2a-124">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="7ec2a-125">Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="7ec2a-126">Rapportera icke-spam-och nät fiske meddelanden från mappen skräp post i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="7ec2a-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="7ec2a-127">I mappen skräp post kan du använda någon av följande metoder för att rapportera skräp post i falsk positiv eller nätfiske:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="7ec2a-128">Markera meddelandet, klicka på **inte skräp post** i verktygsfältet och välj **inte skräp post** eller **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="7ec2a-130">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som inte skräp post**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="7ec2a-131">Läs informationen i dialog rutan som visas och klicka på **rapportera**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="7ec2a-132">Om du ändrar dig klickar du på **rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="7ec2a-133">Inte skräp post</span><span class="sxs-lookup"><span data-stu-id="7ec2a-133">Not Junk</span></span>|<span data-ttu-id="7ec2a-134">Fiske</span><span class="sxs-lookup"><span data-stu-id="7ec2a-134">Phishing</span></span>|
   |:---:|:---:|
   |![Dialog rutan rapportera inte som skräp post](../../media/owa-report-as-not-junk-dialog.png)|![Dialog rutan rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="7ec2a-137">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="7ec2a-138">Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7ec2a-139">Inaktivera eller aktivera rapportering av skräp post i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="7ec2a-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="7ec2a-140">Som standard kan användare rapportera skräp post i falsk positiv, falsk negativ och nätfiske till Microsoft för analys i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="7ec2a-141">Administratörer kan konfigurera Outlook på webbens post lådans principer i Exchange Online PowerShell för att förhindra att användare rapporterar skräp post falsk positiv och skräp post till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="7ec2a-142">Du kan inte inaktivera möjligheten för användare att rapportera nät fiske meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ec2a-143">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="7ec2a-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ec2a-144">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7ec2a-145">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-145">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="7ec2a-146">Specifikt du behöver **mottagar principer** eller **e-postmottagare** roller i Exchange Online, som är tilldelade till roll grupperna **organisations hantering** och **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="7ec2a-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="7ec2a-147">Mer information om roll grupper i Exchange Online finns i [ändra roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-147">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="7ec2a-148">Varje organisation har en standard princip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="7ec2a-149">Anpassade principer tillämpas på användare med begränsad räckvidd före standard principen.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="7ec2a-150">Mer information om Outlook på principer för webb post lådor finns i [Outlook på principer för Internet post lådor i Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="7ec2a-151">Om du inaktiverar skräp post rapportering tas inte möjligheten att markera ett meddelande som skräp post eller inte skräp post i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="7ec2a-152">Om du markerar ett meddelande i mappen skräp post och klickar på **inte skräp** \> **post** flyttas meddelandet tillbaka till Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="7ec2a-153">Om du markerar ett meddelande i en annan e-postmapp och sedan klickar på **skräp** \> **post** flyttas meddelandet till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="7ec2a-154">Det går inte längre att rapportera meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7ec2a-155">Använda Exchange Online PowerShell för att inaktivera eller aktivera rapportering av skräp post i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="7ec2a-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="7ec2a-156">Om du vill hitta dina befintliga Outlook-principer och status för skräp post rapportering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="7ec2a-157">Om du vill inaktivera eller aktivera skräp post rapportering i Outlook på webben kan du använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="7ec2a-158">I det här exemplet inaktive ras skräp post rapportering i standard policyn.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="7ec2a-159">I det här exemplet aktive ras skräp post rapportering i den anpassade principen med contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="7ec2a-160">Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) och [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="7ec2a-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7ec2a-161">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="7ec2a-161">How do you know this worked?</span></span>

<span data-ttu-id="7ec2a-162">Gör så här för att kontrol lera att du har aktiverat eller inaktiverat skräp post rapportering i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="7ec2a-163">Kör följande kommando i Exchange Online PowerShell och kontrol lera värdet för egenskapen **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="7ec2a-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="7ec2a-164">Öppna en användares post låda i Outlook på webben, Välj ett meddelande i Inkorgen, klicka på **skräp** \> **post** och bekräfta uppmaningen att rapportera meddelandet till Microsoft är eller visas inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ec2a-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="7ec2a-165">Öppna en användares post låda i Outlook på webben, Välj ett meddelande i mappen skräp post, klicka på **skräp** \> **post** och bekräfta uppmaningen att rapportera meddelandet till Microsoft, eller så visas det inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7ec2a-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="7ec2a-166"><sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet medan det rapporteras.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="7ec2a-167">Så här kontrollerar du inställningen i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="7ec2a-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="7ec2a-168">Klicka på **Inställningar** ![ i Outlook på webb inställnings ikonen ](../../media/owa-settings-icon.png) \> **Visa alla** \> **skräp post**i Outlook-inställningar.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="7ec2a-169">Kontrol lera värdet i avsnittet **rapportering** **innan du skickar en rapport**.</span><span class="sxs-lookup"><span data-stu-id="7ec2a-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Inställningar för skräp post rapportering i Outlook på webben](../../media/owa-junk-email-reporting-options.png)
