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
ms.openlocfilehash: 126bf1f8c8ea8c16242b7b3749066131e8942304
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166141"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="cdcc1-103">Hitta och släppa meddelanden i karantän som användare i EOP</span><span class="sxs-lookup"><span data-stu-id="cdcc1-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cdcc1-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-104">**Applies to**</span></span>
- [<span data-ttu-id="cdcc1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cdcc1-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="cdcc1-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="cdcc1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="cdcc1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cdcc1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cdcc1-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="cdcc1-109">Mer information finns i [Karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cdcc1-110">Som användare kan du visa, släppa och ta bort meddelanden i karantän där du är mottagare och där meddelandet har satts i karantän som skräppost eller massutskick.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="cdcc1-111">Från och med april 2020 kan du visa eller ta bort phishing-meddelanden i karantän (ej nätfiske med hög konfidens) där du är mottagare.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="cdcc1-112">Du visar och hanterar dina meddelanden i karantän i Säkerhets- och efterlevnadscenter eller (om en administratör har konfigurerat detta) i [slutanvändarens skräppostmeddelanden](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cdcc1-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="cdcc1-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cdcc1-114">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="cdcc1-115">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="cdcc1-116">Administratörer kan konfigurera hur länge meddelanden behålls i karantän innan de tas bort permanent (principer för skräppostskydd).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="cdcc1-117">Meddelanden som har upphört att gälla och tas bort från karantänen går inte att återställa.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="cdcc1-118">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="cdcc1-119">Administratörer kan även [aktivera skräppostaviseringar för slutanvändare](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) i principer för skräppostskydd.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="cdcc1-120">Användare kan släppa skräppost i karantän direkt från dessa aviseringar.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="cdcc1-121">Användare kan granska phishing-meddelanden i karantän (inte phishing-meddelanden med hög förtroende) direkt från dessa meddelanden.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="cdcc1-122">Mer information finns i [Skräppostaviseringar för slutanvändare i EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="cdcc1-123">Meddelanden som sattes i karantän för phishing, malware eller e-postflödesregler (även kända som transportregler) är bara tillgängliga för administratörer och är inte synliga för användare.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="cdcc1-124">Mer information finns i [Hantera meddelanden och filer i karantän som administratör i EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="cdcc1-125">Du kan bara släppa ett meddelande och rapportera det som en falsk positiv identifiering (inte skräppost) en gång.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="cdcc1-126">Visa meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="cdcc1-126">View your quarantined messages</span></span>

1. <span data-ttu-id="cdcc1-127">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cdcc1-128">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cdcc1-129">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cdcc1-130">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="cdcc1-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cdcc1-131">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-132">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-133">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-134">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-135">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-136">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-137">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cdcc1-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="cdcc1-138">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-138">**Recipient**</span></span>
   - <span data-ttu-id="cdcc1-139">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-139">**Message ID**</span></span>
   - <span data-ttu-id="cdcc1-140">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-140">**Policy name**</span></span>
   - <span data-ttu-id="cdcc1-141">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-141">**Size**</span></span>
   - <span data-ttu-id="cdcc1-142">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-142">**Direction**</span></span>

   <span data-ttu-id="cdcc1-143">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="cdcc1-144">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cdcc1-145">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-145">The available filters are:</span></span>

   - <span data-ttu-id="cdcc1-146">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="cdcc1-147">**I dag**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-147">**Today**</span></span>
     - <span data-ttu-id="cdcc1-148">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-148">**Next 2 days**</span></span>
     - <span data-ttu-id="cdcc1-149">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-149">**Next 7 days**</span></span>
     - <span data-ttu-id="cdcc1-150">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cdcc1-151">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cdcc1-152">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="cdcc1-153">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="cdcc1-153">**Bulk**</span></span>
     - <span data-ttu-id="cdcc1-154">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-154">**Spam**</span></span>
     - <span data-ttu-id="cdcc1-155">**Nätfiske**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-155">**Phish**</span></span>

   - <span data-ttu-id="cdcc1-156">**Principtyp**: filtrera meddelanden efter principtyp:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="cdcc1-157">**Princip för skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="cdcc1-158">**Filterprincip för värdbaserat innehåll** (Skräppostprincip)</span><span class="sxs-lookup"><span data-stu-id="cdcc1-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="cdcc1-159">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="cdcc1-160">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="cdcc1-161">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="cdcc1-162">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-162">Wildcards aren't supported.</span></span> <span data-ttu-id="cdcc1-163">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-163">You can search by the following values:</span></span>

   - <span data-ttu-id="cdcc1-164">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="cdcc1-165">Om du väljer ett meddelande i listan visas värdet för **Meddelande-ID** i den utfällbara rutan **Information** som visas.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="cdcc1-166">Administratörer kan använda [meddelandespårning](message-trace-scc.md) för att söka efter meddelanden med motsvarande värden för meddelande-ID.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="cdcc1-167">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="cdcc1-168">**Principnamn**: använd meddelandets hela principnamn.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="cdcc1-169">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="cdcc1-170">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="cdcc1-171">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="cdcc1-172">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="cdcc1-173">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="cdcc1-174">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="cdcc1-175">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="cdcc1-175">Export message results</span></span>

1. <span data-ttu-id="cdcc1-176">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="cdcc1-177">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="cdcc1-178">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="cdcc1-179">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="cdcc1-179">View quarantined message details</span></span>

<span data-ttu-id="cdcc1-180">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cdcc1-181">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="cdcc1-182">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-182">**Sender address**</span></span>

- <span data-ttu-id="cdcc1-183">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="cdcc1-184">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="cdcc1-184">**Subject**</span></span>

- <span data-ttu-id="cdcc1-185">**Orsak till karantän**: Visar om ett meddelande har identifierats som **Skräppost**, **Bulk** (massutskick) eller **Nätfiske**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="cdcc1-186">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="cdcc1-187">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="cdcc1-188">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="cdcc1-189">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="cdcc1-190">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="cdcc1-190">Take action on quarantined email</span></span>

<span data-ttu-id="cdcc1-191">När du har valt ett meddelande finns det alternativ för vad du kan göra med meddelanden i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cdcc1-192">**Släpp meddelandet**: Välj om du vill **Rapportera meddelanden till Microsoft för analys** i den utfällbara rutan.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="cdcc1-193">Det här alternativet är markerat som standard och rapporterar meddelandet som felaktigt har satts i karantän till Microsoft som en falsk positiv identifiering.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="cdcc1-194">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="cdcc1-195">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="cdcc1-196">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="cdcc1-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="cdcc1-197">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="cdcc1-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="cdcc1-198">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="cdcc1-199">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="cdcc1-200">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="cdcc1-201">**Ta bort från karantän**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="cdcc1-202">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-202">When you're finished, click **Close**.</span></span>

<span data-ttu-id="cdcc1-203">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-203">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="cdcc1-204">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="cdcc1-204">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="cdcc1-205">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="cdcc1-205">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cdcc1-206">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-206">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="cdcc1-207">**Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-207">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="cdcc1-208">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="cdcc1-208">When you're finished, click **Close**.</span></span>
