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
ms.openlocfilehash: bd22e7f08ae420adf2923d4da731494a0f6af3e3
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166741"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="26b5b-103">Rapportera skräppost och nätfiske i Outlook på webben i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26b5b-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="26b5b-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="26b5b-104">**Applies to**</span></span>
- [<span data-ttu-id="26b5b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="26b5b-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="26b5b-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="26b5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="26b5b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="26b5b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="26b5b-108">I Microsoft 365-organisationer med postlådor i Exchange Online kan du använda de inbyggda rapporteringsalternativen i Outlook på webben (tidigare Outlook Web App) för att skicka falska positiva identifieringar (bra e-post som markerats som skräppost), falska negativa identifieringar (felaktig e-post tillåts) och nätfiskemeddelanden till Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="26b5b-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26b5b-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="26b5b-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26b5b-110">Om du är administratör i en organisation med Exchange Online-postlådor rekommenderar vi att du använder portalen Inskickade i Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="26b5b-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="26b5b-111">Mer information finns i Använda administratörs inskickat material för att skicka misstänkt [skräppost, phish, URL:er och filer till Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="26b5b-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="26b5b-112">Administratörer kan inaktivera eller aktivera möjligheten för användare att rapportera meddelanden till Microsoft i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="26b5b-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="26b5b-113">Mer information finns i avsnittet [Inaktivera eller aktivera skräppostrapportering i Outlook på webben senare](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="26b5b-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="26b5b-114">Du kan konfigurera rapporterade meddelanden så att de kopieras eller omdirigeras till en postlåda som du anger.</span><span class="sxs-lookup"><span data-stu-id="26b5b-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="26b5b-115">Mer information finns i principer [för användarinskick.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="26b5b-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="26b5b-116">Mer information om hur du rapporterar meddelanden till Microsoft finns [i Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="26b5b-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="26b5b-117">Rapportera skräppost och nätfiskemeddelanden i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="26b5b-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="26b5b-118">För meddelanden i Inkorgen eller någon annan e-postmapp utom Skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiske:</span><span class="sxs-lookup"><span data-stu-id="26b5b-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="26b5b-119">Markera meddelandet, klicka **på Skräppost** i verktygsfältet och välj sedan **Skräppost** eller **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Rapportera skräppost och nätfiske i menyfliksområdet](../../media/owa-report-junk.png)

   - <span data-ttu-id="26b5b-121">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som skräppost.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="26b5b-122">Klicka på Rapport i dialogrutan **som visas.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="26b5b-123">Om du ändrar dig klickar du **på Rapportera inte.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="26b5b-124">Skräppost</span><span class="sxs-lookup"><span data-stu-id="26b5b-124">Junk</span></span>|<span data-ttu-id="26b5b-125">Fiske</span><span class="sxs-lookup"><span data-stu-id="26b5b-125">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogrutan Rapportera som skräppost](../../media/owa-report-as-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="26b5b-128">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="26b5b-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="26b5b-129">Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="26b5b-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="26b5b-130">Rapportera icke-skräppost och nätfiskemeddelanden från mappen Skräppost i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="26b5b-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="26b5b-131">Använd någon av följande metoder i mappen Skräppost för att rapportera skräppost med falska positiva resultat eller nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="26b5b-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="26b5b-132">Markera meddelandet, klicka **på Inte skräppost** i verktygsfältet och välj sedan Inte **skräppost** eller **nätfiske.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Rapportera inte skräppost eller inte nätfiskemeddelande från menyfliksområdet](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="26b5b-134">Markera ett eller flera meddelanden, högerklicka och välj sedan **Markera som inte skräppost.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="26b5b-135">Läs informationen i dialogrutan som visas och klicka på **Rapport.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="26b5b-136">Om du ändrar dig klickar du **på Rapportera inte.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="26b5b-137">Inte skräppost</span><span class="sxs-lookup"><span data-stu-id="26b5b-137">Not Junk</span></span>|<span data-ttu-id="26b5b-138">Fiske</span><span class="sxs-lookup"><span data-stu-id="26b5b-138">Phishing</span></span>|
   |:---:|:---:|
   |![Dialogrutan Rapportera som inte skräppost](../../media/owa-report-as-not-junk-dialog.png)|![Dialogrutan Rapportera som nätfiske](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="26b5b-141">De valda meddelandena skickas till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="26b5b-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="26b5b-142">Bekräfta att meddelandena har skickats genom att öppna mappen **Skickat för** att visa skickade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="26b5b-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="26b5b-143">Inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="26b5b-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="26b5b-144">Standardinställningen är att användare kan rapportera skräppost med falska positiva meddelanden, falska negativa meddelanden och nätfiskemeddelanden till Microsoft för analys i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="26b5b-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="26b5b-145">Administratörer kan konfigurera principer för postlådor i Outlook på webben i Exchange Online PowerShell för att hindra användare från att rapportera skräppost som falska positiva identifieringar och skräppost till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26b5b-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="26b5b-146">Du kan inte inaktivera möjligheten för användare att rapportera nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26b5b-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26b5b-147">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="26b5b-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26b5b-148">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="26b5b-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="26b5b-149">Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="26b5b-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="26b5b-150">Specifikt behöver du **rollerna Mottagarprinciper** och E-postmottagare, som är tilldelade **rollgrupperna** Organisationshantering och  **Mottagarhantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="26b5b-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="26b5b-151">Mer information om rollgrupper i Exchange Online finns i Behörigheter [i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) och Ändra [rollgrupper i Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="26b5b-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="26b5b-152">Varje organisation har en standardprincip som heter OwaMailboxPolicy-Default, men du kan skapa anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="26b5b-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="26b5b-153">Anpassade principer tillämpas på begränsade användare före standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="26b5b-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="26b5b-154">Mer information om postlådeprinciper för Outlook på webben finns i [postlådeprinciperna för Outlook](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)på webben i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26b5b-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="26b5b-155">Om du inaktiverar skräppostrapportering tas inte möjligheten att markera ett meddelande som skräppost eller inte som skräppost i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="26b5b-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="26b5b-156">Om du markerar ett meddelande i mappen Skräppost och **klickar på Inte** skräppost flyttas meddelandet tillbaka till \>  Inkorgen.</span><span class="sxs-lookup"><span data-stu-id="26b5b-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="26b5b-157">Om du markerar ett meddelande  i en annan e-postmapp och klickar på Skräppost \>  flyttas meddelandet fortfarande till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="26b5b-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="26b5b-158">Det som inte längre är tillgängligt är alternativet att rapportera meddelandet till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26b5b-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="26b5b-159">Använda Exchange Online PowerShell för att inaktivera eller aktivera skräppostrapportering i Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="26b5b-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="26b5b-160">Om du vill hitta dina befintliga postlådeprinciper för Outlook på webben och status för skräppostrapportering kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="26b5b-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="26b5b-161">Om du vill inaktivera eller aktivera skräppostrapportering i Outlook på webben använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="26b5b-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="26b5b-162">I det här exemplet inaktiveras skräppostrapportering i standardprincipen.</span><span class="sxs-lookup"><span data-stu-id="26b5b-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="26b5b-163">I det här exemplet möjliggörs rapportering av skräppost i den anpassade principen contoso Managers.</span><span class="sxs-lookup"><span data-stu-id="26b5b-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="26b5b-164">Detaljerad information om syntax och parametrar finns i [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) [och Set-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="26b5b-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="26b5b-165">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="26b5b-165">How do you know this worked?</span></span>

<span data-ttu-id="26b5b-166">Kontrollera att du har aktiverat eller inaktiverat skräppostrapportering i Outlook på webben genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="26b5b-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="26b5b-167">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdet **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="26b5b-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="26b5b-168">Öppna en användares postlåda i Outlook på webben, markera ett  meddelande i Inkorgen, klicka på Skräppost och kontrollera att meddelandet inte visas eller \>  inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="26b5b-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="26b5b-169">Öppna en användares postlåda i Outlook på webben, markera ett meddelande  i mappen Skräppost, klicka på Skräppost och kontrollera att meddelandet visas eller \>  inte.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="26b5b-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="26b5b-170"><sup>\*</sup> Användare kan dölja uppmaningen att rapportera meddelandet medan du fortfarande rapporterar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="26b5b-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="26b5b-171">Så här kontrollerar du den här inställningen i Outlook på webben:</span><span class="sxs-lookup"><span data-stu-id="26b5b-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="26b5b-172">Klicka **på Inställningar** i Outlook på ![ webbinställningsikonen ](../../media/owa-settings-icon.png) \> **Visa alla Outlook-inställningar** för \> **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="26b5b-173">Kontrollera värdet **i** avsnittet Rapportering: Fråga **innan du skickar en rapport.**</span><span class="sxs-lookup"><span data-stu-id="26b5b-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Inställningar för rapportering av skräppost i Outlook på webben](../../media/owa-junk-email-reporting-options.png)
