---
title: Installera och använda tillägget Skräppostrapportering för Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Lär dig hur du installerar och använder tillägget Microsoft Junk Email Reporting för att rapportera skräppost, icke-skräppost och nätfiskemeddelanden till Microsoft.
ms.openlocfilehash: 5c0b802bea89a0f0f62952261bf0d2864842024f
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208833"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="3f477-103">Installera och använda tillägget Skräppostrapportering för Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="3f477-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

> [!NOTE]
> <span data-ttu-id="3f477-104">Om du för närvarande inte använder tillägget Skräppostrapportering rekommenderar vi [tillägget Rapportera meddelande i](enable-the-report-message-add-in.md) stället.</span><span class="sxs-lookup"><span data-stu-id="3f477-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span> <span data-ttu-id="3f477-105">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3f477-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="3f477-106">Add-in-tillägget för skräppostrapportering för Microsoft Outlook gör det möjligt för användare att skicka falska positiva identifieringar (bra e-post markerat som skräppost), falska negativ (felaktig e-post tillåten) och nätfiskemeddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f477-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="3f477-107">Om din organisation inte använder Exchange Online Protection (till exempel lokala Exchange- eller e-posttjänster än Exchange Online) påverkar inte överföringen av skräppostrapporten skräppostfiltreringen skräppostfiltreringen.</span><span class="sxs-lookup"><span data-stu-id="3f477-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="3f477-108">I det här avsnittet beskrivs hur du installerar och använder tillägget Rapportering av skräppost.</span><span class="sxs-lookup"><span data-stu-id="3f477-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3f477-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="3f477-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3f477-110">Om du vill installera tillägget Skräppostrapportering läser du [avsnittet Installera tillägget Rapportering av skräppost](#install-the-junk-email-reporting-add-in) senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3f477-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="3f477-111">Tillägget Skräppostrapportering fungerar med följande versioner av Outlook:</span><span class="sxs-lookup"><span data-stu-id="3f477-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="3f477-112">Outlook 2013 eller senare</span><span class="sxs-lookup"><span data-stu-id="3f477-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="3f477-113">Outlook ingår i Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="3f477-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="3f477-114">Mer information om hur du anmäler meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3f477-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="3f477-115">Använda tillägget Skräppostrapportering för att rapportera skräppost och nätfiskemeddelanden</span><span class="sxs-lookup"><span data-stu-id="3f477-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="3f477-116">För meddelanden i Inkorgen eller någon annan e-postmapp utom skräppost använder du någon av följande metoder för att rapportera skräppost och nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="3f477-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="3f477-117">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3f477-117">Select the message or open the message.</span></span> <span data-ttu-id="3f477-118">Klicka på **Skräppost**på fliken **Start** eller **Meddelande** i menyfliksområdet och välj sedan **Rapportera som skräppost** eller Rapport som **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="3f477-120">Högerklicka på meddelandet, välj **Skräppost**och välj sedan **Rapportera som skräppost** eller Rapport som **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera skräppost eller nätfiskemeddelande från högerklicka](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="3f477-122">Markera flera meddelanden, högerklicka och välj sedan **Rapportera som skräppost** eller rapport som **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera flera skräppostmeddelanden eller nätfiskemeddelanden från högerklicka](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="3f477-124">Läs informationen i dialogrutan som visas och klicka på **Rapportera**.</span><span class="sxs-lookup"><span data-stu-id="3f477-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="3f477-125">Om du ändrar dig klickar du på **Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="3f477-125">If you change your mind, click **Don't Report**.</span></span>

   ![Rapport som skräppostdialogruta](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="3f477-128">De valda meddelandena skickas till Microsoft för analys och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="3f477-128">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="3f477-129">Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="3f477-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="3f477-130">Använda tillägget Skräppostrapportering för att rapportera meddelanden som inte är skräppost och nätfiske från mappen Skräppost</span><span class="sxs-lookup"><span data-stu-id="3f477-130">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="3f477-131">I mappen Skräppost använder du någon av följande metoder för att rapportera falska positiva skräppost eller nätfiskemeddelanden:</span><span class="sxs-lookup"><span data-stu-id="3f477-131">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="3f477-132">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3f477-132">Select the message or open the message.</span></span> <span data-ttu-id="3f477-133">Klicka på **Inte skräppost**på fliken **Start** eller **Meddelande** och välj sedan Rapportera som **Inte skräppost** eller Rapport **som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-133">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="3f477-135">Högerklicka på meddelandet, klicka på **Skräppost**och välj sedan **Rapportera som Inte skräppost** eller Rapport som **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-135">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera inte skräppost eller nätfiskemeddelande från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="3f477-137">Markera flera meddelanden, högerklicka och välj sedan **Rapportera som Inte skräppost** eller Rapport som **nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="3f477-137">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera flera inte skräppost eller nätfiskemeddelanden från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="3f477-139">Läs informationen i dialogrutan som visas och klicka på **Rapportera**.</span><span class="sxs-lookup"><span data-stu-id="3f477-139">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="3f477-140">Om du ändrar dig klickar du på **Rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="3f477-140">If you change your mind, click **Don't Report**.</span></span>

   ![Rapportera som inte skräppostdialogruta](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialogrutan Rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="3f477-143">De valda meddelandena skickas till Microsoft för analys och flyttas till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="3f477-143">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder.</span></span> <span data-ttu-id="3f477-144">Om du vill bekräfta att meddelandena har skickats öppnar du mappen **Skickat för** att visa de skickade meddelandena.</span><span class="sxs-lookup"><span data-stu-id="3f477-144">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="3f477-145">Installera tillägget Rapportering av skräppost</span><span class="sxs-lookup"><span data-stu-id="3f477-145">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="3f477-146">Du måste ha administratörsbehörighet på datorn där du installerar tillägget.</span><span class="sxs-lookup"><span data-stu-id="3f477-146">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="3f477-147">Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och hämta lämplig MSI-fil för din version av Office till en plats som är lätt att hitta:</span><span class="sxs-lookup"><span data-stu-id="3f477-147">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="3f477-148">**32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="3f477-148">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="3f477-149">**64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="3f477-149">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="3f477-150">För Outlook 2013 eller senare är den enda förutsättningen Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="3f477-150">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="3f477-151">I Windows 10 installerar du inte .NET Framework 2.0 från en nedladdning.</span><span class="sxs-lookup"><span data-stu-id="3f477-151">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="3f477-152">Installera tillägget Skräppostrapportering med installationsguiden</span><span class="sxs-lookup"><span data-stu-id="3f477-152">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="3f477-153">Stäng Outlook på datorn.</span><span class="sxs-lookup"><span data-stu-id="3f477-153">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="3f477-154">I Windows 10 kontrollerar du att .NET Framework 2.0 är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="3f477-154">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="3f477-155">Instruktioner finns [i Aktivera .NET Framework 3.5 på Kontrollpanelen](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="3f477-155">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="3f477-156">Leta reda på MSI-filen du hämtade och dubbelklicka på den.</span><span class="sxs-lookup"><span data-stu-id="3f477-156">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="3f477-157">Klicka på **Nästa**på sidan **Välkommen till Microsofts inställningstillägg för skräppostrapportering.**</span><span class="sxs-lookup"><span data-stu-id="3f477-157">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="3f477-158">Granska licensavtalet, klicka på **Jag godkänner villkoren i licensavtalet** om du godkänner villkoren och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3f477-158">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="3f477-159">När guiden är klar klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="3f477-159">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="3f477-160">Starta Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f477-160">Start Outlook.</span></span>

<span data-ttu-id="3f477-161">Leta efter **skräppostknappen** i menyfliksområdet i Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f477-161">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="3f477-162">Nu kan du rapportera skräppostmeddelanden till Microsoft genom att markera skräppostmeddelandena i Inkorgen och klicka på knappen **Rapportera skräppost.**</span><span class="sxs-lookup"><span data-stu-id="3f477-162">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="3f477-163">Välj nedpilen **bredvid Skräppost** om du vill ha fler alternativ, till exempel **Rapportera som Nätfiske** om du vill rapportera e-postmeddelanden med nätfiskebedrägeri till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3f477-163">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="3f477-164">I skräppostmappen kan du också välja **Rapportera inte skräppost** om ett e-postmeddelande har identifierats felaktigt som skräppost.</span><span class="sxs-lookup"><span data-stu-id="3f477-164">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="3f477-165">Installera tillägget Skräppostrapportering med tyst läge</span><span class="sxs-lookup"><span data-stu-id="3f477-165">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="3f477-166">Stäng Outlook på datorn.</span><span class="sxs-lookup"><span data-stu-id="3f477-166">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="3f477-167">Installera .NET Framework 2.0 i Windows 10 genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="3f477-167">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="3f477-168">Om du vill installera tillägget utan någon användarinteraktion öppnar du en kommandotolk och använder följande syntax:</span><span class="sxs-lookup"><span data-stu-id="3f477-168">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="3f477-169">`MaxMessageSelection`anger det maximala antalet meddelanden som du kan välja för en enda inlämning.</span><span class="sxs-lookup"><span data-stu-id="3f477-169">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="3f477-170">Giltiga värden är från 1 till 50.</span><span class="sxs-lookup"><span data-stu-id="3f477-170">Valid values are from 1 to 50.</span></span> <span data-ttu-id="3f477-171">Standardvärdet är 15.</span><span class="sxs-lookup"><span data-stu-id="3f477-171">The default value is 15.</span></span>

   - <span data-ttu-id="3f477-172">`BccEmailAddress`anger ytterligare mottagare av hemlig kopia som ska få en kopia av alla användarinlämningar.</span><span class="sxs-lookup"><span data-stu-id="3f477-172">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="3f477-173">Standardvärdet är tomt (inga ytterligare mottagare av hemlig kopia).</span><span class="sxs-lookup"><span data-stu-id="3f477-173">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="3f477-174">I det här exemplet installeras 64-bitarsversionen av tillägget från den angivna sökvägen med standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="3f477-174">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="3f477-175">I det här exemplet installeras 32-bitarsversionen av tillägget från den angivna sökvägen med följande ytterligare inställningar:</span><span class="sxs-lookup"><span data-stu-id="3f477-175">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="3f477-176">Upp till 20 meddelanden kan väljas i en enda inlämning.</span><span class="sxs-lookup"><span data-stu-id="3f477-176">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="3f477-177">junkreports@contoso.com och hollyd@treyresearch.net ta emot hemlig kopia av alla inlagor.</span><span class="sxs-lookup"><span data-stu-id="3f477-177">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3f477-178">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="3f477-178">How do you know this worked?</span></span>

<span data-ttu-id="3f477-179">Så här kontrollerar du att du har installerat tillägget Rapportering av skräppost gör du något av följande steg i Outlook:</span><span class="sxs-lookup"><span data-stu-id="3f477-179">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="3f477-180">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3f477-180">Select the message or open the message.</span></span> <span data-ttu-id="3f477-181">Klicka på **Skräppost**på fliken **Start** eller **Meddelande** i menyfliksområdet och kontrollera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="3f477-181">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="3f477-182">**Rapportera som skräppost**</span><span class="sxs-lookup"><span data-stu-id="3f477-182">**Report as Junk**</span></span>
  - <span data-ttu-id="3f477-183">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="3f477-183">**Report as Phishing**</span></span>
  - <span data-ttu-id="3f477-184">**Alternativ för skräprapportering**</span><span class="sxs-lookup"><span data-stu-id="3f477-184">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="3f477-185">**Rapportera hjälp om skräp online**</span><span class="sxs-lookup"><span data-stu-id="3f477-185">**Report Junk Online Help**</span></span>

  ![Rapportera skräppost eller nätfiskemeddelande från menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="3f477-187">Högerklicka på meddelandet, välj **Skräppost**och kontrollera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="3f477-187">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="3f477-188">**Rapportera som skräppost**</span><span class="sxs-lookup"><span data-stu-id="3f477-188">**Report as Junk**</span></span>
  - <span data-ttu-id="3f477-189">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="3f477-189">**Report as Phishing**</span></span>
  - <span data-ttu-id="3f477-190">**Alternativ för skräprapportering**</span><span class="sxs-lookup"><span data-stu-id="3f477-190">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="3f477-191">**Rapportera hjälp om skräp online**</span><span class="sxs-lookup"><span data-stu-id="3f477-191">**Report Junk Online Help**</span></span>

  ![Rapportera skräppost eller nätfiskemeddelande från högerklicka](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="3f477-193">Markera flera meddelanden, högerklicka och kontrollera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="3f477-193">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="3f477-194">**Rapportera som skräppost**</span><span class="sxs-lookup"><span data-stu-id="3f477-194">**Report as Junk**</span></span>
  - <span data-ttu-id="3f477-195">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="3f477-195">**Report as Phishing**</span></span>

  ![Rapportera flera skräppostmeddelanden eller nätfiskemeddelanden från högerklicka](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="3f477-197">Gör tidigare åtgärder i mappen **Skräppost** och verifiera de tidigare alternativen **för skräprapportering** är nu **inte skräppost**.</span><span class="sxs-lookup"><span data-stu-id="3f477-197">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Rapportera inte skräppost eller nätfiske från menyfliksområdet i mappen Skräppost](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräppost eller nätfiskemeddelande från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera inte skräppost eller nätfiskemeddelanden från högerklicka i mappen Skräppost](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="3f477-201">Avinstallera tillägget Rapportering av skräppost</span><span class="sxs-lookup"><span data-stu-id="3f477-201">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="3f477-202">När du har stängt Outlook använder du någon av följande procedurer för att avinstallera tillägget Rapportering av skräppost:</span><span class="sxs-lookup"><span data-stu-id="3f477-202">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="3f477-203">**Kontrollpanelen:** Tryck på Windows-tangenten + R. Ange dialogrutan **Kör** som öppnas `control appwiz.cpl` och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3f477-203">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="3f477-204">Leta reda på och välj **Microsoft Junk Email Reporting Add-in i** listan och klicka sedan på **Avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="3f477-204">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="3f477-205">**Windows Installer-paketet**: Hitta eller hämta lämplig MSI-fil och dubbelklicka på den.</span><span class="sxs-lookup"><span data-stu-id="3f477-205">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="3f477-206">**32-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="3f477-206">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="3f477-207">**64-bitars:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="3f477-207">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="3f477-208">I dialogrutan som visas väljer du **Ta bort Microsofts tillägg för rapportering av skräppost för Outlook** och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="3f477-208">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="3f477-209">**Tyst läge:** Hitta eller ladda ner lämplig MSI-fil.</span><span class="sxs-lookup"><span data-stu-id="3f477-209">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="3f477-210">I ett kommandotolksfönster ersätter du \< PathToFile \> med platsen för MSI-filen och kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="3f477-210">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="3f477-211">**32-bitars:**</span><span class="sxs-lookup"><span data-stu-id="3f477-211">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="3f477-212">**64-bitars:**</span><span class="sxs-lookup"><span data-stu-id="3f477-212">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="3f477-213">När du öppnar Outlook efter avinstallationen bör alternativen för skräppost, inte skräppost och nätfiskerapportering vara borta.</span><span class="sxs-lookup"><span data-stu-id="3f477-213">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="3f477-214">Felsöka tillägget Rapportering av skräppost</span><span class="sxs-lookup"><span data-stu-id="3f477-214">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="3f477-215">Ibland kan det uppstå problem med Outlook när du har lagt till tillägget Skräppostrapportering.</span><span class="sxs-lookup"><span data-stu-id="3f477-215">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="3f477-216">I det här avsnittet beskrivs problem som kan uppstå, tillsammans med tips för att lösa dessa problem.</span><span class="sxs-lookup"><span data-stu-id="3f477-216">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="3f477-217">Felsökning för användare</span><span class="sxs-lookup"><span data-stu-id="3f477-217">Troubleshooting for users</span></span>

<span data-ttu-id="3f477-218">Du upplever ett eller flera av följande problem:</span><span class="sxs-lookup"><span data-stu-id="3f477-218">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="3f477-219">Ingenting händer när du klickar på **Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="3f477-219">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="3f477-220">Outlook slutar svara när du har valt ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="3f477-220">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="3f477-221">Rapporterad skräppost kan inte levereras på grund av ett "ej utlevererbart" svar</span><span class="sxs-lookup"><span data-stu-id="3f477-221">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="3f477-222">Så här åtgärdar du problemet:</span><span class="sxs-lookup"><span data-stu-id="3f477-222">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="3f477-223">Stäng och starta om Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f477-223">Close and restart Outlook.</span></span>
2. <span data-ttu-id="3f477-224">Skapa och skicka ett testmeddelande och kontrollera att mottagaren har tagit emot meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3f477-224">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="3f477-225">Om problemet kvarstår kontaktar du administratören.</span><span class="sxs-lookup"><span data-stu-id="3f477-225">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="3f477-226">Andra metoder som du kan använda för att skicka meddelanden till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3f477-226">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="3f477-227">Felsökning för administratörer</span><span class="sxs-lookup"><span data-stu-id="3f477-227">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="3f477-228">Problem: Ett felmeddelande visas kontinuerligt som uppmanar användare att kontakta systemadministratören</span><span class="sxs-lookup"><span data-stu-id="3f477-228">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="3f477-229">Verifiera eller ange `LoggingLevel` registernyckeln till värdet "Utförlig":</span><span class="sxs-lookup"><span data-stu-id="3f477-229">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="3f477-230">**32-bitars Outlook i 32-bitars Windows:**</span><span class="sxs-lookup"><span data-stu-id="3f477-230">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="3f477-231">**32-bitars Outlook i 64-bitars Windows:**</span><span class="sxs-lookup"><span data-stu-id="3f477-231">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="3f477-232">**64-bitars Outlook:**</span><span class="sxs-lookup"><span data-stu-id="3f477-232">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="3f477-233">Starta om Outlook och be användarna att rapportera tillbaka när de ser felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="3f477-233">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="3f477-234">Samla in logginformation som finns på följande plats:</span><span class="sxs-lookup"><span data-stu-id="3f477-234">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="3f477-235">Kontakta Exchange Online Protection Teknisk support och förse dem med logginformation.</span><span class="sxs-lookup"><span data-stu-id="3f477-235">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="3f477-236">Problem: Användare som har valt att inte få en bekräftelsefråga när de rapporterar meddelanden, och nu vill de ha snabben tillbaka</span><span class="sxs-lookup"><span data-stu-id="3f477-236">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="3f477-237">Skapa `ConfirmReportJunk` registernyckeln wih värdet "True":</span><span class="sxs-lookup"><span data-stu-id="3f477-237">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="3f477-238">Starta om Outlook.</span><span class="sxs-lookup"><span data-stu-id="3f477-238">Restart Outlook.</span></span>
