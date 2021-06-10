---
title: Hitta och släppa meddelanden i karantän som användare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Användare kan läsa mer om hur de visar och hanterar meddelanden i karantän i Exchange Online Protection (EOP) som borde ha levererats till dem.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4913d0c6fc34d912474bcceac8b1785c4a7e07b3
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821301"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="4f87c-103">Hitta och släppa meddelanden i karantän som användare i EOP</span><span class="sxs-lookup"><span data-stu-id="4f87c-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4f87c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4f87c-104">**Applies to**</span></span>
- [<span data-ttu-id="4f87c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4f87c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4f87c-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4f87c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4f87c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f87c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4f87c-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4f87c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="4f87c-109">Mer information finns i [Karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4f87c-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="4f87c-110">Som mottagare av ett meddelande i kvarantän, vad kan du göra med meddelandet som vanlig användare beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="4f87c-110">As a recipient of a quarantined message, what you can do to the message as a regular user is described in the following table:</span></span>

<br>

****

|<span data-ttu-id="4f87c-111">Orsak till karantän</span><span class="sxs-lookup"><span data-stu-id="4f87c-111">Quarantine reason</span></span>|<span data-ttu-id="4f87c-112">Visa</span><span class="sxs-lookup"><span data-stu-id="4f87c-112">View</span></span>|<span data-ttu-id="4f87c-113">Version</span><span class="sxs-lookup"><span data-stu-id="4f87c-113">Release</span></span>|<span data-ttu-id="4f87c-114">Radera</span><span class="sxs-lookup"><span data-stu-id="4f87c-114">Delete</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="4f87c-115">Massutskick</span><span class="sxs-lookup"><span data-stu-id="4f87c-115">Bulk</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="4f87c-119">Skräppost</span><span class="sxs-lookup"><span data-stu-id="4f87c-119">Spam</span></span>|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|<span data-ttu-id="4f87c-123">Nätfiske (inte nätfiske med högt förtroende)</span><span class="sxs-lookup"><span data-stu-id="4f87c-123">Phishing (not high confidence phishing)</span></span>|![Bockmarkering](../../media/checkmark.png)||![Bockmarkering](../../media/checkmark.png)|
|

<span data-ttu-id="4f87c-126">Du visar och hanterar dina meddelanden i karantän i Microsoft 365 Säkerhetscenter eller (om en administratör har konfigurerat detta) i [slutanvändarens skräppostmeddelanden](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4f87c-126">You view and manage your quarantined messages in the Microsoft 365 security center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4f87c-127">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4f87c-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4f87c-128">För att öppna säkerhetscenter, gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4f87c-128">To open the security center, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="4f87c-129">Om du vill öppna karantänsidan direkt går du till <https://security.microsoft.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="4f87c-129">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="4f87c-130">Administratörer kan konfigurera hur länge meddelanden behålls i karantän innan de tas bort permanent principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="4f87c-130">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="4f87c-131">Meddelanden som har upphört att gälla och tas bort från karantänen går inte att återställa.</span><span class="sxs-lookup"><span data-stu-id="4f87c-131">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="4f87c-132">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4f87c-132">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="4f87c-133">Administratörer kan även [aktivera skräppostaviseringar för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="4f87c-133">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="4f87c-134">Användare kan släppa skräppost i karantän direkt från dessa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="4f87c-134">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="4f87c-135">Användare kan granska phishing-meddelanden i karantän (inte phishing-meddelanden med hög förtroende) direkt från dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4f87c-135">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="4f87c-136">Mer information finns i [Skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4f87c-136">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="4f87c-137">Meddelanden som sattes i karantän för phishing, malware eller e-postflödesregler (även kända som transportregler) är bara tillgängliga för administratörer och är inte synliga för användare.</span><span class="sxs-lookup"><span data-stu-id="4f87c-137">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="4f87c-138">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="4f87c-138">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="4f87c-139">Du kan bara släppa ett meddelande och rapportera det som en falsk positiv identifiering (inte skräppost) en gång.</span><span class="sxs-lookup"><span data-stu-id="4f87c-139">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="4f87c-140">Visa meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4f87c-140">View your quarantined messages</span></span>

1. <span data-ttu-id="4f87c-141">I säkerhetscentret går du till **E-post och samarbete** \> **Granska** \> **Karantänen**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-141">In the security center, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="4f87c-142">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="4f87c-142">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="4f87c-143">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="4f87c-143">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="4f87c-144">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="4f87c-144">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="4f87c-145">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-145">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-146">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-146">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-147">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-147">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-148">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-148">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-149">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-149">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-150">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-150">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-151">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4f87c-151">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="4f87c-152">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="4f87c-152">**Recipient**</span></span>
   - <span data-ttu-id="4f87c-153">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="4f87c-153">**Message ID**</span></span>
   - <span data-ttu-id="4f87c-154">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="4f87c-154">**Policy name**</span></span>
   - <span data-ttu-id="4f87c-155">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="4f87c-155">**Size**</span></span>
   - <span data-ttu-id="4f87c-156">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="4f87c-156">**Direction**</span></span>

   <span data-ttu-id="4f87c-157">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4f87c-157">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="4f87c-158">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-158">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4f87c-159">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="4f87c-159">The available filters are:</span></span>

   - <span data-ttu-id="4f87c-160">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="4f87c-160">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="4f87c-161">**I dag**</span><span class="sxs-lookup"><span data-stu-id="4f87c-161">**Today**</span></span>
     - <span data-ttu-id="4f87c-162">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4f87c-162">**Next 2 days**</span></span>
     - <span data-ttu-id="4f87c-163">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="4f87c-163">**Next 7 days**</span></span>
     - <span data-ttu-id="4f87c-164">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-164">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4f87c-165">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-165">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="4f87c-166">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="4f87c-166">**Quarantine reason**:</span></span>
     - <span data-ttu-id="4f87c-167">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="4f87c-167">**Bulk**</span></span>
     - <span data-ttu-id="4f87c-168">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="4f87c-168">**Spam**</span></span>
     - <span data-ttu-id="4f87c-169">**Nätfiske**</span><span class="sxs-lookup"><span data-stu-id="4f87c-169">**Phish**</span></span>

   - <span data-ttu-id="4f87c-170">**Principtyp**: filtrera meddelanden efter principtyp:</span><span class="sxs-lookup"><span data-stu-id="4f87c-170">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="4f87c-171">**Princip för skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="4f87c-171">**Anti-malware policy**</span></span>
     - <span data-ttu-id="4f87c-172">**Principer för säkra bifogade filer** (Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="4f87c-172">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="4f87c-173">**Princip för skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="4f87c-173">**Anti-phish policy**</span></span>
     - <span data-ttu-id="4f87c-174">**Filterprincip för värdbaserat innehåll** (Skräppostprincip)</span><span class="sxs-lookup"><span data-stu-id="4f87c-174">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="4f87c-175">**Transportregel**</span><span class="sxs-lookup"><span data-stu-id="4f87c-175">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="4f87c-176">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="4f87c-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="4f87c-177">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="4f87c-177">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="4f87c-178">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="4f87c-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="4f87c-179">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="4f87c-179">Wildcards aren't supported.</span></span> <span data-ttu-id="4f87c-180">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="4f87c-180">You can search by the following values:</span></span>

   - <span data-ttu-id="4f87c-181">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="4f87c-181">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="4f87c-182">Om du väljer ett meddelande i listan visas värdet för **Meddelande-ID** i den utfällbara rutan **Information** som visas.</span><span class="sxs-lookup"><span data-stu-id="4f87c-182">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="4f87c-183">Administratörer kan använda [meddelandespårning](message-trace-scc.md) för att söka efter meddelanden med motsvarande värden för meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="4f87c-183">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="4f87c-184">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="4f87c-184">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="4f87c-185">**Principnamn**: använd meddelandets hela principnamn.</span><span class="sxs-lookup"><span data-stu-id="4f87c-185">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="4f87c-186">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="4f87c-186">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="4f87c-187">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="4f87c-187">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="4f87c-188">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="4f87c-188">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="4f87c-189">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="4f87c-189">The search is not case-sensitive.</span></span>

   <span data-ttu-id="4f87c-190">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="4f87c-190">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="4f87c-191">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="4f87c-191">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="4f87c-192">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="4f87c-192">Export message results</span></span>

1. <span data-ttu-id="4f87c-193">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-193">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="4f87c-194">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="4f87c-194">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="4f87c-195">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="4f87c-195">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="4f87c-196">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4f87c-196">View quarantined message details</span></span>

<span data-ttu-id="4f87c-197">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="4f87c-197">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4f87c-198">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="4f87c-198">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="4f87c-199">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="4f87c-199">**Sender address**</span></span>
- <span data-ttu-id="4f87c-200">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="4f87c-200">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="4f87c-201">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="4f87c-201">**Subject**</span></span>
- <span data-ttu-id="4f87c-202">**Orsak till karantän**: Visar om ett meddelande har identifierats som **Skräppost**, **Bulk** (massutskick) eller **Nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-202">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="4f87c-203">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="4f87c-203">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="4f87c-204">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="4f87c-204">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="4f87c-205">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="4f87c-205">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="4f87c-206">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="4f87c-206">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="4f87c-207">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="4f87c-207">Take action on quarantined email</span></span>

<span data-ttu-id="4f87c-208">När du har valt ett meddelande finns det alternativ för vad du kan göra med meddelanden i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="4f87c-208">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="4f87c-209">**Släpp meddelandet**: Välj om du vill **Rapportera meddelanden till Microsoft för analys** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="4f87c-209">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="4f87c-210">Det här alternativet är markerat som standard och rapporterar meddelandet som felaktigt har satts i karantän till Microsoft som en falsk positiv identifiering.</span><span class="sxs-lookup"><span data-stu-id="4f87c-210">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="4f87c-211">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4f87c-211">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="4f87c-212">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="4f87c-212">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="4f87c-213">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="4f87c-213">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="4f87c-214">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="4f87c-214">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="4f87c-215">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="4f87c-215">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="4f87c-216">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="4f87c-216">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="4f87c-217">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="4f87c-217">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="4f87c-218">**Ta bort från karantän**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort.</span><span class="sxs-lookup"><span data-stu-id="4f87c-218">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="4f87c-219">**Spärra avsändare**: Lägg till avsändaren i listan Spärrade avsändare i din postlåda.</span><span class="sxs-lookup"><span data-stu-id="4f87c-219">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="4f87c-220">Mer information finns i [Spärra e-postavsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="4f87c-220">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="4f87c-221">Lägg till avsändaren i listan Spärrade avsändare i din postlåda.</span><span class="sxs-lookup"><span data-stu-id="4f87c-221">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="4f87c-222">Mer information finns i [Spärra e-postavsändare](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="4f87c-222">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="4f87c-223">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4f87c-223">When you're finished, click **Close**.</span></span>

<span data-ttu-id="4f87c-224">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="4f87c-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="4f87c-225">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="4f87c-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="4f87c-226">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4f87c-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="4f87c-227">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="4f87c-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="4f87c-228">**Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="4f87c-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="4f87c-229">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4f87c-229">When you're finished, click **Close**.</span></span>
