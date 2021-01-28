---
title: Installera och använda tillägget skräp post rapportering för Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Lär dig hur du installerar och använder tillägget skräp post rapportering i Microsoft för att rapportera skräp post, icke skräp post-och nät fiske meddelanden till Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 896ef89149e5ef65ea96b2b21e1010c29fa7a7fc
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029426"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="29e7d-103">Installera och använda tillägget skräp post rapportering för Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="29e7d-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="29e7d-104">Om du inte använder tillägget skräp post rapportering rekommenderar vi att du i stället lägger till [tillägget för rapport meddelanden](enable-the-report-message-add-in.md) eller [rapport](enable-the-report-phish-add-in.md) tillägget.</span><span class="sxs-lookup"><span data-stu-id="29e7d-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="29e7d-105">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="29e7d-105">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="29e7d-106">Med tillägget skräp post rapportering för Microsoft Outlook kan användarna skicka falska positiva (god e-post), falsk negativ (dålig e-post) och nätfiske-meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29e7d-106">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="29e7d-107">Om din organisation inte använder Exchange Online Protection (till exempel lokala Exchange-eller e-posttjänster som inte är Exchange Online), påverkas inte din skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="29e7d-107">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="29e7d-108">I det här avsnittet förklaras hur du installerar och använder tillägget skräp post rapportering.</span><span class="sxs-lookup"><span data-stu-id="29e7d-108">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="29e7d-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="29e7d-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="29e7d-110">Information om hur du installerar tillägget skräp post rapportering finns i avsnittet [installera tillägget skräp post rapportering](#install-the-junk-email-reporting-add-in) längre ned i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="29e7d-110">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="29e7d-111">Tillägget skräp post rapportering fungerar med följande versioner av Outlook:</span><span class="sxs-lookup"><span data-stu-id="29e7d-111">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="29e7d-112">Outlook 2013 eller senare</span><span class="sxs-lookup"><span data-stu-id="29e7d-112">Outlook 2013 or later</span></span>
  - <span data-ttu-id="29e7d-113">Outlook ingår i Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="29e7d-113">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="29e7d-114">Mer information om hur du rapporterar meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="29e7d-114">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="29e7d-115">Använda tillägget skräp post rapportering för att rapportera skräp post och nät fiske meddelanden</span><span class="sxs-lookup"><span data-stu-id="29e7d-115">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="29e7d-116">Använd någon av följande metoder för att rapportera skräp post och nät fiske meddelanden, för meddelanden i Inkorgen eller annan mapp för e-post, utom spam.</span><span class="sxs-lookup"><span data-stu-id="29e7d-116">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="29e7d-117">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="29e7d-117">Select the message or open the message.</span></span> <span data-ttu-id="29e7d-118">Klicka på **skräp post** på fliken **Start** eller **meddelande** i menyfliksområdet och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-118">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="29e7d-120">Högerklicka på meddelandet, Välj **skräp post** och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-120">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera skräp post eller nätfiske-e-postadress från höger musknapp](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="29e7d-122">Välj flera meddelanden, högerklicka och välj sedan **rapportera som skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-122">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Rapportera flera skräp post-eller nätfiske-meddelanden från höger musknapp](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="29e7d-124">Läs informationen i dialog rutan som visas och klicka på **rapportera**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-124">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="29e7d-125">Om du ändrar dig klickar du på **rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-125">If you change your mind, click **Don't Report**.</span></span>

   ![Dialog rutan rapportera som skräp post](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Dialog rutan rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="29e7d-128">De valda meddelandena skickas till Microsoft för analys och:</span><span class="sxs-lookup"><span data-stu-id="29e7d-128">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="29e7d-129">Flyttas till mappen skräp post om den rapporter ATS som skräp post.</span><span class="sxs-lookup"><span data-stu-id="29e7d-129">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="29e7d-130">Borttagen om den rapporterades som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="29e7d-130">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="29e7d-131">Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.</span><span class="sxs-lookup"><span data-stu-id="29e7d-131">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="29e7d-132">Använda tillägget skräp post rapportering för att rapportera icke-spam-och nät fiske meddelanden från mappen skräp post</span><span class="sxs-lookup"><span data-stu-id="29e7d-132">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="29e7d-133">I mappen skräp post kan du använda någon av följande metoder för att rapportera skräp post i falsk positiv eller nätfiske:</span><span class="sxs-lookup"><span data-stu-id="29e7d-133">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="29e7d-134">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="29e7d-134">Select the message or open the message.</span></span> <span data-ttu-id="29e7d-135">På fliken **Start** eller **meddelande** i menyfliksområdet klickar du på **inte skräp post** och väljer **rapportera inte som skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-135">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera inte skräp post eller nätfiske via menyfliksområdet i mappen skräp post](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="29e7d-137">Högerklicka på meddelandet, klicka på **skräp post** och välj sedan **rapportera som inte skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-137">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera inte skräp post eller nätfiske-e-postadress Högerklicka i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="29e7d-139">Välj flera meddelanden, högerklicka och välj sedan **rapportera som inte skräp post** eller **rapportera som nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-139">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Rapportera flera inte skräp post eller nätfiske-meddelanden från höger musknapp i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="29e7d-141">Läs informationen i dialog rutan som visas och klicka på **rapportera**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-141">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="29e7d-142">Om du ändrar dig klickar du på **rapportera inte**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-142">If you change your mind, click **Don't Report**.</span></span>

   ![Dialog rutan rapportera inte som skräp post](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Dialog rutan rapportera som nätfiske](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="29e7d-145">De valda meddelandena skickas till Microsoft för analys och:</span><span class="sxs-lookup"><span data-stu-id="29e7d-145">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="29e7d-146">Flyttas till mappen skräp post om den rapporter ATS som skräp post.</span><span class="sxs-lookup"><span data-stu-id="29e7d-146">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="29e7d-147">Borttagen om den rapporterades som nätfiske.</span><span class="sxs-lookup"><span data-stu-id="29e7d-147">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="29e7d-148">Bekräfta att meddelanden har skickats genom att öppna mappen **skickat** för att visa de meddelanden som skickats.</span><span class="sxs-lookup"><span data-stu-id="29e7d-148">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="29e7d-149">Installera tillägget skräp post rapportering</span><span class="sxs-lookup"><span data-stu-id="29e7d-149">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="29e7d-150">Du måste ha administratörs behörighet på den dator där du installerar tillägget.</span><span class="sxs-lookup"><span data-stu-id="29e7d-150">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="29e7d-151">Gå till <https://www.microsoft.com/download/details.aspx?id=18275> och ladda ned lämplig MSI-fil för din version av Office till en plats som är lätt att hitta:</span><span class="sxs-lookup"><span data-stu-id="29e7d-151">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="29e7d-152">**32-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="29e7d-152">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="29e7d-153">**64-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="29e7d-153">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="29e7d-154">För Outlook 2013 eller senare är det enda kravet för Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="29e7d-154">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="29e7d-155">I Windows 10 kan du inte installera .NET Framework 2,0 från en nedladdning.</span><span class="sxs-lookup"><span data-stu-id="29e7d-155">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="29e7d-156">Installera tillägget skräp post rapportering med installations guiden</span><span class="sxs-lookup"><span data-stu-id="29e7d-156">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="29e7d-157">Stäng Outlook på datorn.</span><span class="sxs-lookup"><span data-stu-id="29e7d-157">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="29e7d-158">I Windows 10 kontrollerar du att .NET Framework 2,0 är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="29e7d-158">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="29e7d-159">Anvisningar finns i [Aktivera .NET Framework 3,5 på kontroll panelen](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="29e7d-159">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="29e7d-160">Leta reda på. msi-filen du laddade ner och dubbelklicka på den.</span><span class="sxs-lookup"><span data-stu-id="29e7d-160">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="29e7d-161">Klicka på **Nästa** på sidan **Välkommen till installations programmet för skräp post** .</span><span class="sxs-lookup"><span data-stu-id="29e7d-161">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="29e7d-162">Granska licens avtalet, klicka på **Jag godkänner villkoren i licens avtalet** om du godkänner villkoren och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-162">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="29e7d-163">När guiden är klar klickar du på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-163">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="29e7d-164">Starta Outlook.</span><span class="sxs-lookup"><span data-stu-id="29e7d-164">Start Outlook.</span></span>

<span data-ttu-id="29e7d-165">Leta efter knappen **skräp post** i menyfliksområdet i Outlook.</span><span class="sxs-lookup"><span data-stu-id="29e7d-165">Look for the **Junk** button on your Outlook ribbon.</span></span> <span data-ttu-id="29e7d-166">Du kan nu Rapportera skräp post meddelanden till Microsoft genom att välja skräp post meddelanden i Inkorgen och klicka på knappen **Rapportera skräp** post.</span><span class="sxs-lookup"><span data-stu-id="29e7d-166">You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="29e7d-167">Välj nedpilen bredvid **skräp post** för fler alternativ, till exempel **rapportera som nätfiske** om du vill rapportera nät fiske meddelanden till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="29e7d-167">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft.</span></span> <span data-ttu-id="29e7d-168">I mappen skräp post kan du också välja att **rapportera inte skräp** post om ett e-postmeddelande felaktigt identifierades som skräppost.</span><span class="sxs-lookup"><span data-stu-id="29e7d-168">In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="29e7d-169">Installera Add-In för skräp post rapportering i tyst läge</span><span class="sxs-lookup"><span data-stu-id="29e7d-169">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="29e7d-170">Stäng Outlook på datorn.</span><span class="sxs-lookup"><span data-stu-id="29e7d-170">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="29e7d-171">I Windows 10 installerar du .NET Framework 2,0 genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="29e7d-171">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="29e7d-172">Om du vill installera tillägget utan några åtgärder från användaren öppnar du kommando tolken och använder följande syntax:</span><span class="sxs-lookup"><span data-stu-id="29e7d-172">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="29e7d-173">`MaxMessageSelection` anger maximalt antal meddelanden som du kan välja för en enda överföring.</span><span class="sxs-lookup"><span data-stu-id="29e7d-173">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="29e7d-174">Giltiga värden är mellan 1 och 50.</span><span class="sxs-lookup"><span data-stu-id="29e7d-174">Valid values are from 1 to 50.</span></span> <span data-ttu-id="29e7d-175">Standardvärdet är 15.</span><span class="sxs-lookup"><span data-stu-id="29e7d-175">The default value is 15.</span></span>

   - <span data-ttu-id="29e7d-176">`BccEmailAddress` anger ytterligare hemliga kopior som kommer att få en kopia av alla användar inlämningar.</span><span class="sxs-lookup"><span data-stu-id="29e7d-176">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="29e7d-177">Standardvärdet är tomt (inga fler mottagare av hemlig kopia).</span><span class="sxs-lookup"><span data-stu-id="29e7d-177">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="29e7d-178">I det här exemplet installeras 64-bitars versionen av tillägget från den angivna sökvägen med standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="29e7d-178">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="29e7d-179">I det här exemplet installeras 32-bitars versionen av tillägget från den angivna sökvägen med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="29e7d-179">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="29e7d-180">Upp till 20 meddelanden kan väljas med en enda överföring.</span><span class="sxs-lookup"><span data-stu-id="29e7d-180">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="29e7d-181">junkreports@contoso.com och hollyd@treyresearch.net ta emot kopior av alla inlägg.</span><span class="sxs-lookup"><span data-stu-id="29e7d-181">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="29e7d-182">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="29e7d-182">How do you know this worked?</span></span>

<span data-ttu-id="29e7d-183">Kontrol lera att du har installerat tillägget skräp post rapportering genom att göra något av följande i Outlook:</span><span class="sxs-lookup"><span data-stu-id="29e7d-183">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="29e7d-184">Markera meddelandet eller öppna meddelandet.</span><span class="sxs-lookup"><span data-stu-id="29e7d-184">Select the message or open the message.</span></span> <span data-ttu-id="29e7d-185">Klicka på **skräp post** på fliken **Start** eller **meddelande** i menyfliksområdet och kontrol lera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="29e7d-185">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="29e7d-186">**Rapportera som skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-186">**Report as Junk**</span></span>
  - <span data-ttu-id="29e7d-187">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="29e7d-187">**Report as Phishing**</span></span>
  - <span data-ttu-id="29e7d-188">**Alternativ för skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-188">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="29e7d-189">**Rapportera skräppost-onlinehjälp**</span><span class="sxs-lookup"><span data-stu-id="29e7d-189">**Report Junk Online Help**</span></span>

  ![Rapportera skräp post eller nätfiske via menyfliksområdet](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="29e7d-191">Högerklicka på meddelandet, Välj **skräp post** och kontrol lera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="29e7d-191">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="29e7d-192">**Rapportera som skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-192">**Report as Junk**</span></span>
  - <span data-ttu-id="29e7d-193">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="29e7d-193">**Report as Phishing**</span></span>
  - <span data-ttu-id="29e7d-194">**Alternativ för skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-194">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="29e7d-195">**Rapportera skräppost-onlinehjälp**</span><span class="sxs-lookup"><span data-stu-id="29e7d-195">**Report Junk Online Help**</span></span>

  ![Rapportera skräp post eller nätfiske-e-postadress från höger musknapp](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="29e7d-197">Välj flera meddelanden, högerklicka och kontrol lera att följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="29e7d-197">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="29e7d-198">**Rapportera som skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-198">**Report as Junk**</span></span>
  - <span data-ttu-id="29e7d-199">**Rapportera som nätfiske**</span><span class="sxs-lookup"><span data-stu-id="29e7d-199">**Report as Phishing**</span></span>

  ![Rapportera flera skräp post-eller nätfiske-meddelanden från höger musknapp](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="29e7d-201">Gör föregående åtgärder i mappen **skräp post** och kontrol lera att tidigare alternativ för **skräp** post rapportering **inte är skräp post**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-201">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Rapportera inte skräp post eller nätfiske via menyfliksområdet i mappen skräp post](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Rapportera inte skräp post eller nätfiske-e-postadress Högerklicka i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Rapportera flera inte skräp post eller nätfiske-meddelanden från höger musknapp i mappen skräp post](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="29e7d-205">Avinstallera tillägget skräp post rapportering</span><span class="sxs-lookup"><span data-stu-id="29e7d-205">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="29e7d-206">När du har stängt Outlook kan du använda någon av följande procedurer för att avinstallera tillägget skräp post rapportering:</span><span class="sxs-lookup"><span data-stu-id="29e7d-206">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="29e7d-207">**Kontroll panelen**: Tryck på Windows-tangenten + R. I dialog rutan **Kör** som öppnas anger du `control appwiz.cpl` och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-207">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="29e7d-208">Leta reda på och markera **tillägget skräp post rapportering** i listan och klicka sedan på **Avinstallera**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-208">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="29e7d-209">**Windows installations paket**: Sök eller ladda ned lämplig. msi-fil och dubbelklicka på den.</span><span class="sxs-lookup"><span data-stu-id="29e7d-209">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="29e7d-210">**32-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="29e7d-210">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="29e7d-211">**64-bitar**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="29e7d-211">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="29e7d-212">I dialog rutan som visas väljer du **ta bort Microsoft skräppost-e-postrapportering för Outlook** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="29e7d-212">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="29e7d-213">**Tyst läge**: hitta eller ladda ned lämplig. msi-fil.</span><span class="sxs-lookup"><span data-stu-id="29e7d-213">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="29e7d-214">Ersätt \<PathToFile\> med platsen för MSI-filen i kommando tolken och kör något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="29e7d-214">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="29e7d-215">**32-bitar**:</span><span class="sxs-lookup"><span data-stu-id="29e7d-215">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="29e7d-216">**64-bitar**:</span><span class="sxs-lookup"><span data-stu-id="29e7d-216">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="29e7d-217">När du öppnar Outlook när du har avinstallerat bör du inte gå vidare med alternativen för skräp post, inte skräp post och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="29e7d-217">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="29e7d-218">Felsöka tillägget skräp post rapportering</span><span class="sxs-lookup"><span data-stu-id="29e7d-218">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="29e7d-219">Ibland kan du få problem med Outlook när du har lagt till tillägget skräp post rapportering.</span><span class="sxs-lookup"><span data-stu-id="29e7d-219">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="29e7d-220">I det här avsnittet beskrivs problem som du kan stöta på, tillsammans med tips för att åtgärda problemen.</span><span class="sxs-lookup"><span data-stu-id="29e7d-220">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="29e7d-221">Fel sökning för användare</span><span class="sxs-lookup"><span data-stu-id="29e7d-221">Troubleshooting for users</span></span>

<span data-ttu-id="29e7d-222">Ett eller flera av följande problem uppstår:</span><span class="sxs-lookup"><span data-stu-id="29e7d-222">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="29e7d-223">Inget händer när du klickar på **Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="29e7d-223">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="29e7d-224">Outlook slutar svara när du har valt ett e-postmeddelande</span><span class="sxs-lookup"><span data-stu-id="29e7d-224">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="29e7d-225">Rapporterade att skräp post inte kan levereras på grund av ett "unleveransable"-svar</span><span class="sxs-lookup"><span data-stu-id="29e7d-225">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="29e7d-226">Så här löser du problemet:</span><span class="sxs-lookup"><span data-stu-id="29e7d-226">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="29e7d-227">Stäng och starta om Outlook.</span><span class="sxs-lookup"><span data-stu-id="29e7d-227">Close and restart Outlook.</span></span>
2. <span data-ttu-id="29e7d-228">Skapa och skicka ett test meddelande och kontrol lera att mottagaren fått meddelandet.</span><span class="sxs-lookup"><span data-stu-id="29e7d-228">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="29e7d-229">Om problemet kvarstår kontaktar du din administratör.</span><span class="sxs-lookup"><span data-stu-id="29e7d-229">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="29e7d-230">Andra metoder som du kan använda för att skicka meddelanden till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="29e7d-230">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="29e7d-231">Fel sökning för administratörer</span><span class="sxs-lookup"><span data-stu-id="29e7d-231">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="29e7d-232">Problem: ett fel meddelande visas hela tiden så att användarna kan kontakta sin system administratör</span><span class="sxs-lookup"><span data-stu-id="29e7d-232">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="29e7d-233">Verifiera eller ange `LoggingLevel` register nyckel för värdet "VERBOSE":</span><span class="sxs-lookup"><span data-stu-id="29e7d-233">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="29e7d-234">**32-bitars Outlook på 32-bitars versionen av Windows**:</span><span class="sxs-lookup"><span data-stu-id="29e7d-234">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="29e7d-235">**32-bitars Outlook på 64-bitars versionen av Windows**:</span><span class="sxs-lookup"><span data-stu-id="29e7d-235">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="29e7d-236">**64-bitars Outlook**:</span><span class="sxs-lookup"><span data-stu-id="29e7d-236">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="29e7d-237">Starta om Outlook och be användare rapportera tillbaka när de ser fel meddelandet.</span><span class="sxs-lookup"><span data-stu-id="29e7d-237">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="29e7d-238">Samla in logg informationen som finns på följande plats:</span><span class="sxs-lookup"><span data-stu-id="29e7d-238">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="29e7d-239">Kontakta Exchange Online Protection Technical Support och ge dem logg information.</span><span class="sxs-lookup"><span data-stu-id="29e7d-239">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="29e7d-240">Problem: användarna har markerat sig för att inte få en bekräftelse när de rapporterar meddelanden och nu vill att de ska uppmanas tillbaka</span><span class="sxs-lookup"><span data-stu-id="29e7d-240">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="29e7d-241">Skapa `ConfirmReportJunk` register nyckel med värdet "true":</span><span class="sxs-lookup"><span data-stu-id="29e7d-241">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="29e7d-242">Starta om Outlook.</span><span class="sxs-lookup"><span data-stu-id="29e7d-242">Restart Outlook.</span></span>
