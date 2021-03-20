---
title: Rapportera skräppost och nätfiske i Outlook på webben
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om de inbyggda alternativen för skräppost, inte skräppost och nätfiske i Outlook på webben (Outlook Web App) i Exchange Online, och hur de inaktiverar rapporteringsalternativen för användare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6caac60b32910ac06247bb89997ea6dbfc87d4f9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910636"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="11a0d-103">Rapportera skräppost och nätfiske i Outlook på webben i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="11a0d-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="11a0d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="11a0d-104">**Applies to**</span></span>
- [<span data-ttu-id="11a0d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="11a0d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="11a0d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="11a0d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="11a0d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11a0d-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="11a0d-108">I Microsoft 365-organisationer som har postlådor i Exchange Online kan du använda de inbyggda rapporteringsalternativen i Outlook på webben (kallades tidigare Outlook Web App) för att skicka falska positiva identifieringar (bra e-postmeddelanden som markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="11a0d-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11a0d-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="11a0d-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11a0d-110">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen för sändning i Säkerhets- och & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="11a0d-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="11a0d-111">Mer information finns i Använda [administratörsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="11a0d-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="11a0d-112">Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="11a0d-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="11a0d-113">Mer information finns i [avsnittet Inaktivera eller aktivera skräppostrapportering i Outlook på webben längre fram](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="11a0d-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="11a0d-114">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="11a0d-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="11a0d-115">Mer information finns i Principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="11a0d-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="11a0d-116">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="11a0d-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="11a0d-117">Rapportera skräppost och nätfiskemeddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="11a0d-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="11a0d-118">För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiske:</span><span class="sxs-lookup"><span data-stu-id="11a0d-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="11a0d-119">Markera meddelandet, klicka **på** Skräppost i verktygsfältet och välj sedan **Skräppost eller** **Nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="11a0d-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/owa-report-junk.png)

   - <span data-ttu-id="11a0d-121">Markera ett eller flera meddelanden, högerklicka och välj markera **som skräppost.**</span><span class="sxs-lookup"><span data-stu-id="11a0d-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="11a0d-122">I dialogrutan som visas klickar du på **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="11a0d-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="11a0d-123">Om du ändrar dig klickar du **på Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="11a0d-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="11a0d-124">Skräppost</span><span class="sxs-lookup"><span data-stu-id="11a0d-124">Junk</span></span>|<span data-ttu-id="11a0d-125">Fiske</span><span class="sxs-lookup"><span data-stu-id="11a0d-125">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogrutan Rapportera som skräppost](../../media/owa-report-as-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="11a0d-128">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="11a0d-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="11a0d-129">Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="11a0d-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="11a0d-130">Rapportera icke-skräppost och nätfiskemeddelanden från mappen Skräppost i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="11a0d-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="11a0d-131">Använd någon av följande metoder i mappen Skräppost för att rapportera skräppost med falska positiva resultat eller nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="11a0d-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="11a0d-132">Markera meddelandet, klicka **på Inte skräppost** i verktygsfältet och välj sedan Inte **skräppost** eller **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="11a0d-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Rapportera inte skräppost eller nätfiske i menyfliksområdet](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="11a0d-134">Markera ett eller flera meddelanden, högerklicka och välj markera **som inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="11a0d-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="11a0d-135">Läs informationen i dialogrutan som visas och klicka på **Rapport**.</span><span class="sxs-lookup"><span data-stu-id="11a0d-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="11a0d-136">Om du ändrar dig klickar du **på Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="11a0d-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="11a0d-137">Inte skräppost</span><span class="sxs-lookup"><span data-stu-id="11a0d-137">Not Junk</span></span>|<span data-ttu-id="11a0d-138">Fiske</span><span class="sxs-lookup"><span data-stu-id="11a0d-138">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogrutan Rapportera som inte skräppost](../../media/owa-report-as-not-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="11a0d-141">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="11a0d-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="11a0d-142">Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="11a0d-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="11a0d-143">Inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="11a0d-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="11a0d-144">Som standard kan användare rapportera falska positiva meddelanden som skräppost, falska negativa tal och nätfiskemeddelanden till Microsoft för analys i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="11a0d-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="11a0d-145">Administratörer kan konfigurera postlådeprinciper för Outlook på webben i Exchange Online PowerShell för att hindra användare från att rapportera skräppost som falska positiva identifieringar och falskt negativa skräppost till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11a0d-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="11a0d-146">Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11a0d-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11a0d-147">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="11a0d-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11a0d-148">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="11a0d-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="11a0d-149">Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="11a0d-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="11a0d-150">Specifikt behöver du **rollerna Mottagarprinciper** eller E-postmottagare, som tilldelas rollgrupperna **Organisationshantering** och **Mottagarhantering** som standard. </span><span class="sxs-lookup"><span data-stu-id="11a0d-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="11a0d-151">Mer information om rollgrupper i Exchange Online finns i Behörigheter [i Exchange Online](/exchange/permissions-exo/permissions-exo) och Ändra [rollgrupper i Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="11a0d-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="11a0d-152">Varje organisation har en standardprincip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="11a0d-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="11a0d-153">Anpassade principer tillämpas på begränsade användare före standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="11a0d-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="11a0d-154">Mer information om postlådeprinciper för Outlook på webben finns i [Postlådeprinciper för Outlook på webben i Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="11a0d-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="11a0d-155">Om du inaktiverar skräppostrapporteringen inaktiveras inte möjligheten att markera ett meddelande som skräppost eller inte skräppost i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="11a0d-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="11a0d-156">Om du markerar ett meddelande i mappen Skräppost och **klickar på Inte** skräppost Flyttar du fortfarande tillbaka meddelandet till \>  Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="11a0d-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="11a0d-157">Om du markerar ett meddelande  i en annan e-postmapp och klickar på Skräppost \>  flyttas det fortfarande till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="11a0d-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="11a0d-158">Vad som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="11a0d-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="11a0d-159">Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="11a0d-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="11a0d-160">Om du vill hitta dina befintliga postlådeprinciper för Outlook på webben och status för skräppostrapportering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="11a0d-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="11a0d-161">Inaktivera eller aktivera skräppostrapportering i Outlook på webben med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="11a0d-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="11a0d-162">Det här exemplet inaktiverar skräppostrapportering i standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="11a0d-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="11a0d-163">I det här exemplet möjliggörs rapportering av skräppost i den anpassade principen contoso-hanterare.</span><span class="sxs-lookup"><span data-stu-id="11a0d-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="11a0d-164">Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) och [Set-OwaMailboxPolicy.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="11a0d-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="11a0d-165">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="11a0d-165">How do you know this worked?</span></span>

<span data-ttu-id="11a0d-166">Du kan kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="11a0d-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="11a0d-167">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdet **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="11a0d-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="11a0d-168">Öppna en användares postlåda i Outlook på webben, markera ett  meddelande i Inkorgen, klicka på Skräppost och kontrollera att meddelandet inte visas eller om meddelandet ska rapporteras till \>  Microsoft.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="11a0d-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="11a0d-169">Öppna en användares postlåda i Outlook på webben, markera ett meddelande  i mappen Skräppost, klicka på Skräppost och kontrollera att meddelandet inte visas eller \>  inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="11a0d-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="11a0d-170"><sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet samtidigt som de rapporterar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="11a0d-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="11a0d-171">Så här kontrollerar du den här inställningen i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="11a0d-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="11a0d-172">Klicka **på Inställningar** i Outlook på ![ webben-inställningsikonen ](../../media/owa-settings-icon.png) \> **Visa alla Outlook-inställningar** \> **Skräppost.**</span><span class="sxs-lookup"><span data-stu-id="11a0d-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="11a0d-173">Kontrollera värdet **i** avsnittet Rapportering: Fråga **innan du skickar en rapport**.</span><span class="sxs-lookup"><span data-stu-id="11a0d-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Inställningar för rapportering av skräppost i Outlook på webben](../../media/owa-junk-email-reporting-options.png)