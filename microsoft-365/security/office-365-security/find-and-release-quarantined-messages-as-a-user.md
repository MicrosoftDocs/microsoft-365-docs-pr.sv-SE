---
title: Hitta och släppa meddelanden i karantän som användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du kan visa och hantera meddelanden i karantän i Säkerhets- och efterlevnadscenter för Microsoft 365.
ms.openlocfilehash: ff6cb3dbf9a0a2010bf792115c53265689873090
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173386"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="8e44e-103">Hitta och släppa meddelanden i karantän som användare</span><span class="sxs-lookup"><span data-stu-id="8e44e-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="8e44e-104">Karantänen lagrar potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="8e44e-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="8e44e-105">Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8e44e-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="8e44e-106">Som användare kan du visa, släppa och ta bort meddelanden i karantän där du är mottagare och där meddelandet har satts i karantän som skräppost eller massutskick.</span><span class="sxs-lookup"><span data-stu-id="8e44e-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="8e44e-107">Från och med april 2020 kan du visa eller ta bort phishing-meddelanden i karantän (ej nätfiske med hög konfidens) där du är mottagare.</span><span class="sxs-lookup"><span data-stu-id="8e44e-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="8e44e-108">Du visar och hanterar dina meddelanden i karantän i Säkerhets- och efterlevnadscenter eller (om en administratör har konfigurerat detta) i [slutanvändarens skräppostmeddelanden](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8e44e-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8e44e-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="8e44e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8e44e-110">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="8e44e-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="8e44e-111">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="8e44e-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="8e44e-112">Administratörer kan konfigurera hur länge meddelanden behålls i karantän innan de tas bort permanent (principer för skräppostskydd).</span><span class="sxs-lookup"><span data-stu-id="8e44e-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="8e44e-113">Meddelanden som har upphört att gälla och tas bort från karantänen går inte att återställa.</span><span class="sxs-lookup"><span data-stu-id="8e44e-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="8e44e-114">Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e44e-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="8e44e-115">Administratörer kan även [aktivera skräppostaviseringar för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="8e44e-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="8e44e-116">Användare kan släppa skräppostmeddelanden i karantän men inte nätfiskemeddelanden i karantän direkt från dessa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8e44e-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="8e44e-117">Mer information finns i artikeln om [skräppostaviseringar för slutanvändare i Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8e44e-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="8e44e-118">Meddelanden som har satts i karantän för nätfiske via e-post med hög konfidens, skadlig kod eller via e-postflödesregler (kallas även transportregler) är endast tillgängliga för administratörer.</span><span class="sxs-lookup"><span data-stu-id="8e44e-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="8e44e-119">Nätfiskemeddelanden kan granskas av användare men bara ges ut av administratörer.</span><span class="sxs-lookup"><span data-stu-id="8e44e-119">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="8e44e-120">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="8e44e-120">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="8e44e-121">Du kan bara släppa ett meddelande och rapportera det som en falsk positiv identifiering (inte skräppost) en gång.</span><span class="sxs-lookup"><span data-stu-id="8e44e-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="8e44e-122">Visa meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="8e44e-122">View your quarantined messages</span></span>

1. <span data-ttu-id="8e44e-123">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="8e44e-124">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="8e44e-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="8e44e-125">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="8e44e-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="8e44e-126">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="8e44e-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="8e44e-127">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-128">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-129">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-130">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-131">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-132">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-133">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8e44e-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="8e44e-134">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="8e44e-134">**Recipient**</span></span>

   - <span data-ttu-id="8e44e-135">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="8e44e-135">**Message ID**</span></span>

   - <span data-ttu-id="8e44e-136">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="8e44e-136">**Policy name**</span></span>

   - <span data-ttu-id="8e44e-137">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="8e44e-137">**Size**</span></span>

   - <span data-ttu-id="8e44e-138">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="8e44e-138">**Direction**</span></span>

   <span data-ttu-id="8e44e-139">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8e44e-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="8e44e-140">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="8e44e-141">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="8e44e-141">The available filters are:</span></span>

   - <span data-ttu-id="8e44e-142">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="8e44e-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="8e44e-143">**I dag**</span><span class="sxs-lookup"><span data-stu-id="8e44e-143">**Today**</span></span>

     - <span data-ttu-id="8e44e-144">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="8e44e-144">**Next 2 days**</span></span>

     - <span data-ttu-id="8e44e-145">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="8e44e-145">**Next 7 days**</span></span>

     - <span data-ttu-id="8e44e-146">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8e44e-147">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="8e44e-148">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="8e44e-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="8e44e-149">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="8e44e-149">**Bulk**</span></span>

     - <span data-ttu-id="8e44e-150">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="8e44e-150">**Spam**</span></span>

     - <span data-ttu-id="8e44e-151">**Nätfiske** (från och med april 2020)</span><span class="sxs-lookup"><span data-stu-id="8e44e-151">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="8e44e-152">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="8e44e-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="8e44e-153">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="8e44e-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="8e44e-154">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8e44e-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="8e44e-155">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="8e44e-155">Wildcards aren't supported.</span></span> <span data-ttu-id="8e44e-156">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="8e44e-156">You can search by the following values:</span></span>

   - <span data-ttu-id="8e44e-157">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="8e44e-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="8e44e-158">Om du väljer ett meddelande i listan visas värdet för **Meddelande-ID** i den utfällbara rutan **Information** som visas.</span><span class="sxs-lookup"><span data-stu-id="8e44e-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="8e44e-159">Administratörer kan använda [meddelandespårning](message-trace-scc.md) för att söka efter meddelanden med motsvarande värden för meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="8e44e-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="8e44e-160">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="8e44e-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="8e44e-161">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="8e44e-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="8e44e-162">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="8e44e-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="8e44e-163">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="8e44e-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="8e44e-164">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="8e44e-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="8e44e-165">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="8e44e-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="8e44e-166">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="8e44e-166">Export message results</span></span>

1. <span data-ttu-id="8e44e-167">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="8e44e-168">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="8e44e-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="8e44e-169">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="8e44e-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="8e44e-170">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="8e44e-170">View quarantined message details</span></span>

<span data-ttu-id="8e44e-171">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="8e44e-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8e44e-172">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="8e44e-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="8e44e-173">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="8e44e-173">**Sender address**</span></span>

- <span data-ttu-id="8e44e-174">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="8e44e-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="8e44e-175">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="8e44e-175">**Subject**</span></span>

- <span data-ttu-id="8e44e-176">**Orsak till karantän**: Visar om ett meddelande har identifierats som **Skräppost**, **Bulk** (massutskick) eller (från och med april 2020) **Nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="8e44e-177">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="8e44e-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="8e44e-178">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="8e44e-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="8e44e-179">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="8e44e-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="8e44e-180">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="8e44e-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="8e44e-181">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="8e44e-181">Take action on quarantined email</span></span>

<span data-ttu-id="8e44e-182">När du har valt ett meddelande finns det alternativ för vad du kan göra med meddelanden i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="8e44e-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="8e44e-183">**Släpp meddelandet**: Välj om du vill **Rapportera meddelanden till Microsoft för analys** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="8e44e-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="8e44e-184">Det här alternativet är markerat som standard och rapporterar meddelandet som felaktigt har satts i karantän till Microsoft som en falsk positiv identifiering.</span><span class="sxs-lookup"><span data-stu-id="8e44e-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="8e44e-185">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8e44e-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="8e44e-186">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="8e44e-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="8e44e-187">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="8e44e-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="8e44e-188">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="8e44e-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="8e44e-189">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="8e44e-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="8e44e-190">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="8e44e-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="8e44e-191">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="8e44e-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="8e44e-192">**Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="8e44e-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="8e44e-193">**Ta bort från karantän**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort.</span><span class="sxs-lookup"><span data-stu-id="8e44e-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="8e44e-194">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8e44e-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="8e44e-195">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="8e44e-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="8e44e-196">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="8e44e-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="8e44e-197">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="8e44e-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="8e44e-198">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="8e44e-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="8e44e-199">**Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="8e44e-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="8e44e-200">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="8e44e-200">When you're finished, click **Close**.</span></span>
