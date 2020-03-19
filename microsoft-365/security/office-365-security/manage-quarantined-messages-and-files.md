---
title: Hantera meddelanden och filer i karantän som administratör i Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare. Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (transportregler).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857084"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="1b71f-104">Hantera meddelanden och filer i karantän som administratör i Office 365</span><span class="sxs-lookup"><span data-stu-id="1b71f-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="1b71f-105">Karantänen innehåller potentiellt farliga eller oönskade meddelanden i Office 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="1b71f-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="1b71f-106">Mer information finns [i Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1b71f-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1b71f-107">Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="1b71f-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="1b71f-108">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="1b71f-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="1b71f-109">Administratörer kan också rapportera falska positiva identifieringar till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1b71f-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="1b71f-110">Administratörer i organisationer med Office 365 Advance Threat Protection (ATP) kan också visa, hämta och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1b71f-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="1b71f-111">Du kan visa och hantera meddelanden i karantän i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Office 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="1b71f-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1b71f-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="1b71f-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1b71f-113">Öppna Säkerhets- & Compliance Center för Office 365 går du till <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="1b71f-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="1b71f-114">Öppna sidan Karantän direkt går <https://protection.office.com/quarantine>du till .</span><span class="sxs-lookup"><span data-stu-id="1b71f-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="1b71f-115">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1b71f-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1b71f-116">Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1b71f-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1b71f-117">Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantänrollen** i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1b71f-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="1b71f-118">Som standard tilldelas den här rollen till rollgrupperna **Organisationshantering** (Globala administratörer), **karantänadministratör**och **Säkerhetsadministratör** i säkerhets- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="1b71f-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="1b71f-119">Mer information finns [i Behörigheter i Säkerhets- & Compliance Center för Office 365.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="1b71f-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1b71f-120">Meddelanden i karantän behålls under en standardperiod innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="1b71f-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="1b71f-121">Meddelanden i karantän av policyer mot skräppost (skräppost, nätfiske och massmeddelande): 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="1b71f-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="1b71f-122">Detta är standard- och maxvärdet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-122">This is the default and maximum value.</span></span> <span data-ttu-id="1b71f-123">Mer om du vill konfigurera det här värdet finns [i Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1b71f-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="1b71f-124">Meddelanden i karantän av regler för e-postflöde (regelåtgärden är **Leverera meddelandet till den värdbaserade karantänen):** 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="1b71f-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="1b71f-125">Du kan inte ändra det här värdet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-125">You can't change this value.</span></span>

  - <span data-ttu-id="1b71f-126">Meddelanden som innehåller skadlig kod: 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="1b71f-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="1b71f-127">När ett meddelande upphör att gälla från karantänen kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="1b71f-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="1b71f-128">Använda Security & Compliance Center för att hantera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="1b71f-129">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-129">View quarantined email</span></span>

1. <span data-ttu-id="1b71f-130">Gå till Karantän för granskning av **hothantering** \> **Review** \> **Quarantine**i säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="1b71f-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="1b71f-131">Kontrollera att **Visa i karantän** är inställt på standardvärdet **e-post**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="1b71f-132">Du kan sortera resultaten genom att klicka på ett tillgängligt kolumnhuvud.</span><span class="sxs-lookup"><span data-stu-id="1b71f-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="1b71f-133">Klicka på **Ändra kolumner** om du vill visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="1b71f-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="1b71f-134">Standardvärdena markeras med en<sup>\*</sup>asterisk ( ):</span><span class="sxs-lookup"><span data-stu-id="1b71f-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="1b71f-135">**Fått**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-136">**Avsändaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-137">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-138">**Karantän orsak**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-139">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-140">**Typ av princip**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-141">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-142">**Mottagaren**</span><span class="sxs-lookup"><span data-stu-id="1b71f-142">**Recipient**</span></span>

   - <span data-ttu-id="1b71f-143">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="1b71f-143">**Message ID**</span></span>

   - <span data-ttu-id="1b71f-144">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="1b71f-144">**Policy name**</span></span>

   - <span data-ttu-id="1b71f-145">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="1b71f-145">**Size**</span></span>

   - <span data-ttu-id="1b71f-146">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="1b71f-146">**Direction**</span></span>

   <span data-ttu-id="1b71f-147">När du är klar klickar du på **Spara**eller klickar på **Ange till standard**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="1b71f-148">Om du vill filtrera resultatet klickar du på **Filtrera**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1b71f-149">De tillgängliga filtren är:</span><span class="sxs-lookup"><span data-stu-id="1b71f-149">The available filters are:</span></span>

   - <span data-ttu-id="1b71f-150">**Förfaller tid:** Filtrera meddelanden efter när de upphör att gälla från karantän:</span><span class="sxs-lookup"><span data-stu-id="1b71f-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="1b71f-151">**Idag**</span><span class="sxs-lookup"><span data-stu-id="1b71f-151">**Today**</span></span>

     - <span data-ttu-id="1b71f-152">**Nästa 2 dagar**</span><span class="sxs-lookup"><span data-stu-id="1b71f-152">**Next 2 days**</span></span>

     - <span data-ttu-id="1b71f-153">**Nästa 7 dagar**</span><span class="sxs-lookup"><span data-stu-id="1b71f-153">**Next 7 days**</span></span>

     - <span data-ttu-id="1b71f-154">**Anpassad:** Ange ett **startdatum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1b71f-155">**Mottagen tid**: Ange ett **startdatum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1b71f-156">**Karantän orsak:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="1b71f-157">**Princip**: Meddelandet matchade villkoren för en regel för e-postflöde (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="1b71f-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="1b71f-158">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="1b71f-158">**Bulk**</span></span>

     - <span data-ttu-id="1b71f-159">**Phish**</span><span class="sxs-lookup"><span data-stu-id="1b71f-159">**Phish**</span></span>

     - <span data-ttu-id="1b71f-160">**Malware**</span><span class="sxs-lookup"><span data-stu-id="1b71f-160">**Malware**</span></span>

     - <span data-ttu-id="1b71f-161">**Spam**</span><span class="sxs-lookup"><span data-stu-id="1b71f-161">**Spam**</span></span>

     - <span data-ttu-id="1b71f-162">**Högt förtroende Phish**</span><span class="sxs-lookup"><span data-stu-id="1b71f-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="1b71f-163">**E-postmottagare**: Alla användare eller endast meddelanden som skickas till dig.</span><span class="sxs-lookup"><span data-stu-id="1b71f-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="1b71f-164">Slutanvändare kan bara hantera meddelanden i karantän som skickas till dem.</span><span class="sxs-lookup"><span data-stu-id="1b71f-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="1b71f-165">Om du vill rensa filtret klickar du på **Rensa**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="1b71f-166">Om du vill dölja det utfällbara filtret klickar du på **Filter** igen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="1b71f-167">Använd **Sortera resultat efter** **(knappen Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1b71f-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="1b71f-168">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="1b71f-168">Wildcards aren't supported.</span></span> <span data-ttu-id="1b71f-169">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="1b71f-169">You can search by the following values:</span></span>

   - <span data-ttu-id="1b71f-170">**Meddelande-ID:** Den globalt unika identifieraren för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="1b71f-171">Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du bestämmer att meddelandet sattes i karantän i stället för levererat.</span><span class="sxs-lookup"><span data-stu-id="1b71f-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="1b71f-172">Var noga med att inkludera det fullständiga meddelande-ID-värdet, som kan innehålla vinkelparenteser (\<\>).</span><span class="sxs-lookup"><span data-stu-id="1b71f-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="1b71f-173">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="1b71f-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="1b71f-174">**Avsändare e-postadress:** En enda avsändare e-postadress.</span><span class="sxs-lookup"><span data-stu-id="1b71f-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="1b71f-175">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="1b71f-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="1b71f-176">**Ämne**: Använd hela ämnet för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="1b71f-177">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="1b71f-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="1b71f-178">När du har angett sökvillkoren ![klickar](../media/scc-quarantine-refresh.png) du på Uppdatera knappen **Uppdatera** för att filtrera resultaten.</span><span class="sxs-lookup"><span data-stu-id="1b71f-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="1b71f-179">När du har hittat ett visst meddelande i karantän markerar du meddelandet för att visa information om det och vidtar åtgärder för det (till exempel visa, släpp, hämta eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="1b71f-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="1b71f-180">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="1b71f-180">Export message results</span></span>

1. <span data-ttu-id="1b71f-181">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="1b71f-182">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att hålla webbläsarfönstret öppet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="1b71f-183">När exporten är klar kan du namnge och välja hämtningsplats för CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="1b71f-184">Visa meddelandeinformation i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-184">View quarantined message details</span></span>

<span data-ttu-id="1b71f-185">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i fönstret **Utfällbara information:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1b71f-186">**Meddelande-ID:** Den globalt unika identifieraren för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="1b71f-187">**Avsändaradress**</span><span class="sxs-lookup"><span data-stu-id="1b71f-187">**Sender address**</span></span>

- <span data-ttu-id="1b71f-188">**Mottaget**: Datum/tid då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="1b71f-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="1b71f-189">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="1b71f-189">**Subject**</span></span>

- <span data-ttu-id="1b71f-190">**Karantänorsak**: Visar om ett meddelande har identifierats som **Skräppost,** **Bulk,** **Phish**, matchade en regel för e-postflöde (**transportregel**) eller har identifierats som innehållande **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="1b71f-191">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelande** eller **Visa meddelandehuvud** för att se hela listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="1b71f-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="1b71f-192">**Upphör att gälla**: Det datum/den tid då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="1b71f-193">**Släppt till**: Alla e-postadresser (om sådana finns) som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="1b71f-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="1b71f-194">**Ännu inte släppt till**: Alla e-postadresser (om några) som meddelandet ännu inte har släppts.</span><span class="sxs-lookup"><span data-stu-id="1b71f-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="1b71f-195">Vidta åtgärder på e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-195">Take action on quarantined email</span></span>

<span data-ttu-id="1b71f-196">När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1b71f-197">**Utgivningsmeddelande:** I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1b71f-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="1b71f-198">**Rapportera meddelanden till Microsoft för analys**: Detta är markerat som standard och rapporterar det felaktigt i karantän meddelandet till Microsoft som ett falskt positivt.</span><span class="sxs-lookup"><span data-stu-id="1b71f-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="1b71f-199">Om meddelandet har satts i karantän som skräppost, bulk, nätfiske eller skadlig kod rapporteras meddelandet också till Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="1b71f-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="1b71f-200">Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet kan skickas igenom.</span><span class="sxs-lookup"><span data-stu-id="1b71f-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="1b71f-201">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1b71f-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="1b71f-202">**Släpp meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="1b71f-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="1b71f-203">**Släpp meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="1b71f-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="1b71f-204">**Släpp meddelanden till andra**</span><span class="sxs-lookup"><span data-stu-id="1b71f-204">**Release messages to other people**</span></span>

  <span data-ttu-id="1b71f-205">När du är klar klickar du på **Släpp meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="1b71f-206">Anteckningar om att släppa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="1b71f-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="1b71f-207">Du kan inte släppa ett meddelande till samma mottagare mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="1b71f-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="1b71f-208">Endast mottagare som inte har tagit emot meddelandet visas i listan över potentiella mottagare.</span><span class="sxs-lookup"><span data-stu-id="1b71f-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="1b71f-209">**Visa meddelanderubrik:** Välj den här länken om du vill visa meddelanderubrikens text.</span><span class="sxs-lookup"><span data-stu-id="1b71f-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="1b71f-210">Om du vill analysera rubrikfälten och värdena på djupet kopierar du meddelandehuvudtexten till Urklipp och väljer sedan **Microsoft Message Header Analyzer** för att gå till Remote Connectivity Analyzer (högerklicka och välj **Öppna på en ny flik** om du inte vill lämna Office 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="1b71f-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="1b71f-211">Klistra in meddelandehuvudet på sidan i avsnittet Meddelandehuvudanalysator och välj **Analysera rubriker:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="1b71f-212">**Förhandsgranskningsmeddelande:** I det utfällbara fönster som visas väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1b71f-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="1b71f-213">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="1b71f-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="1b71f-214">**Textvy**: Visar meddelandetexten i oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="1b71f-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="1b71f-215">**Ta bort från karantänen**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="1b71f-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="1b71f-216">**Hämta meddelande**: I det utfällbara fönstret som visas väljer **du Jag förstår riskerna med** att hämta det här meddelandet för att spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="1b71f-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="1b71f-217">**Skicka meddelande**: I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="1b71f-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="1b71f-218">**Objekttyp**: **E-post** (standard), **URL**eller **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="1b71f-219">**Inlämningsformat**: **Nätverksmeddelande-ID** (standard, med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller **Arkiv** (bläddra till en lokal EML- eller MSG-fil).</span><span class="sxs-lookup"><span data-stu-id="1b71f-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="1b71f-220">Observera att om du väljer **Arkiv** och sedan väljer **Nätverksmeddelande-ID**är det ursprungliga värdet borta.</span><span class="sxs-lookup"><span data-stu-id="1b71f-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="1b71f-221">**Mottagare**: Skriv vid lån en ursprunglig mottagare av meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="1b71f-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="1b71f-222">Du kan också klicka på **Markera alla** och sedan selektivt ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="1b71f-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="1b71f-223">**Orsak till inlämning:** **Bör inte ha blockerats** (standard) eller **Bör ha blockerats**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="1b71f-224">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="1b71f-225">Om du inte släpper eller tar bort meddelandet tas det bort när standardlagringsperioden för karantän upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="1b71f-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="1b71f-226">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="1b71f-227">När du väljer flera meddelanden i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="1b71f-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="1b71f-228">**Utgivningsmeddelanden**: Alternativen är desamma som när du släpper ett enda meddelande, förutom att du inte kan välja **Utgivningsmeddelanden till specifika mottagare.** Du kan bara välja **Utgivningsmeddelande till alla mottagare** eller **Utgivningsmeddelanden till andra.**</span><span class="sxs-lookup"><span data-stu-id="1b71f-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="1b71f-229">**Ta bort meddelanden**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="1b71f-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="1b71f-230">När du är klar klickar du på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="1b71f-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="1b71f-231">Endast ATP: Använd Security & Compliance Center för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="1b71f-232">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för ATP Plan 1- och Plan 2-prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="1b71f-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="1b71f-233">I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1b71f-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="1b71f-234">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-234">View quarantined files</span></span>

1. <span data-ttu-id="1b71f-235">Gå till Karantän för granskning av **hothantering** \> **Review** \> **Quarantine**i säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="1b71f-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="1b71f-236">Ändra **vy i karantän** till standardvärdefilerna . **files**</span><span class="sxs-lookup"><span data-stu-id="1b71f-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="1b71f-237">Du kan sortera i ett fält genom att klicka på ett tillgängligt kolumnhuvud.</span><span class="sxs-lookup"><span data-stu-id="1b71f-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="1b71f-238">Du kan sortera resultaten genom att klicka på ett tillgängligt kolumnhuvud.</span><span class="sxs-lookup"><span data-stu-id="1b71f-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="1b71f-239">Klicka på **Ändra kolumner** om du vill visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="1b71f-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="1b71f-240">Standardkolumnerna är markerade med<sup>\*</sup>en asterisk ( ):</span><span class="sxs-lookup"><span data-stu-id="1b71f-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="1b71f-241">**Användaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-242">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-243">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-244">**URL för filer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-245">**Filstorlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-246">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-247">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1b71f-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="1b71f-248">**Detekteras av**</span><span class="sxs-lookup"><span data-stu-id="1b71f-248">**Detected by**</span></span>

   - <span data-ttu-id="1b71f-249">**Ändrad med tiden**</span><span class="sxs-lookup"><span data-stu-id="1b71f-249">**Modified by time**</span></span>

4. <span data-ttu-id="1b71f-250">Om du vill filtrera resultatet klickar du på **Filtrera**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1b71f-251">De tillgängliga filtren är:</span><span class="sxs-lookup"><span data-stu-id="1b71f-251">The available filters are:</span></span>

   - <span data-ttu-id="1b71f-252">**Förfaller tid:** Filtrera meddelanden efter när de upphör att gälla från karantän:</span><span class="sxs-lookup"><span data-stu-id="1b71f-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="1b71f-253">**Idag**</span><span class="sxs-lookup"><span data-stu-id="1b71f-253">**Today**</span></span>

     - <span data-ttu-id="1b71f-254">**Nästa 2 dagar**</span><span class="sxs-lookup"><span data-stu-id="1b71f-254">**Next 2 days**</span></span>

     - <span data-ttu-id="1b71f-255">**Nästa 7 dagar**</span><span class="sxs-lookup"><span data-stu-id="1b71f-255">**Next 7 days**</span></span>

     - <span data-ttu-id="1b71f-256">Ett anpassat datum-/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="1b71f-256">A custom date/time range.</span></span>

   - <span data-ttu-id="1b71f-257">**Mottagen tid**</span><span class="sxs-lookup"><span data-stu-id="1b71f-257">**Received time**</span></span>

   - <span data-ttu-id="1b71f-258">**Karantän orsak:** Det enda tillgängliga värdet är **Malware**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="1b71f-259">När du har hittat en viss fil i karantän markerar du filen för att visa information om den och vidtar åtgärder för den (till exempel visa, släpp, hämta eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="1b71f-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="1b71f-260">Exportera filresultat</span><span class="sxs-lookup"><span data-stu-id="1b71f-260">Export file results</span></span>

1. <span data-ttu-id="1b71f-261">Markera de filer du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="1b71f-262">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att hålla webbläsarfönstret öppet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="1b71f-263">När exporten är klar kan du namnge och välja hämtningsplats för CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="1b71f-264">Visa filinformation i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-264">View quarantined file details</span></span>

<span data-ttu-id="1b71f-265">När du markerar en fil i listan visas följande filinformation i fönstret **Utfällbara information:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1b71f-266">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="1b71f-266">**File Name**</span></span>

- <span data-ttu-id="1b71f-267">**Fil-URL**: URL som definierar platsen för filen (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="1b71f-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="1b71f-268">**Skadligt innehåll har upptäckts på** Datum/tid då filen sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="1b71f-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="1b71f-269">**Upphör att gälla**: Det datum då filen tas bort från karantänen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="1b71f-270">**Detekteras av:** ATP (Advanced Threat Protection) eller Microsofts anti-malware-motor.</span><span class="sxs-lookup"><span data-stu-id="1b71f-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="1b71f-271">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="1b71f-271">**Released?**</span></span>

- <span data-ttu-id="1b71f-272">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="1b71f-272">**Malware Name**</span></span>

- <span data-ttu-id="1b71f-273">**Dokument-ID:** En unik identifierare för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="1b71f-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="1b71f-274">**Filstorlek:** I kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="1b71f-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="1b71f-275">**Organisation** Organisationens unika ID.</span><span class="sxs-lookup"><span data-stu-id="1b71f-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="1b71f-276">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="1b71f-276">**Last modified**</span></span>

- <span data-ttu-id="1b71f-277">**Ändrad av**: Användaren som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="1b71f-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="1b71f-278">**Värde för säker hashalgoritm 256-bitars (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra ryktesbutiker eller på andra platser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="1b71f-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="1b71f-279">Vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-279">Take action on quarantined files</span></span>

<span data-ttu-id="1b71f-280">När du väljer en fil i listan kan du vidta följande åtgärder för filen i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="1b71f-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1b71f-281">**Släpp filer**: Markera (standard) eller avmarkera **rapportfiler till Microsoft för analys**och klicka sedan på Släpp **filer**.</span><span class="sxs-lookup"><span data-stu-id="1b71f-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="1b71f-282">**Ladda ner fil**</span><span class="sxs-lookup"><span data-stu-id="1b71f-282">**Download file**</span></span>

- <span data-ttu-id="1b71f-283">**Ta bort fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="1b71f-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="1b71f-284">Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="1b71f-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="1b71f-285">Åtgärder på filer i flera karantäner</span><span class="sxs-lookup"><span data-stu-id="1b71f-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="1b71f-286">När du väljer flera filer i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="1b71f-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="1b71f-287">**Släpp filer**</span><span class="sxs-lookup"><span data-stu-id="1b71f-287">**Release files**</span></span>

- <span data-ttu-id="1b71f-288">**Ta bort filer**: När du klickar på **Ja** i varningen som visas tas filerna omedelbart bort.</span><span class="sxs-lookup"><span data-stu-id="1b71f-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="1b71f-289">När du är klar klickar du på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="1b71f-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="1b71f-290">Använda Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att visa och hantera meddelanden och filer i karantän</span><span class="sxs-lookup"><span data-stu-id="1b71f-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="1b71f-291">De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:</span><span class="sxs-lookup"><span data-stu-id="1b71f-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="1b71f-292">Ta bort karantänMessage</span><span class="sxs-lookup"><span data-stu-id="1b71f-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="1b71f-293">Exportera karantänMessage</span><span class="sxs-lookup"><span data-stu-id="1b71f-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="1b71f-294">Hämta karantänMessage</span><span class="sxs-lookup"><span data-stu-id="1b71f-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="1b71f-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observera att den här cmdleten endast är för meddelanden, inte skadliga programfiler från ATP för SharePoint Online, OneDrive för företag eller Teams.</span><span class="sxs-lookup"><span data-stu-id="1b71f-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="1b71f-296">Release-KarantänMessage</span><span class="sxs-lookup"><span data-stu-id="1b71f-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
