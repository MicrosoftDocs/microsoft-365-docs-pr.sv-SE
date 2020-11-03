---
title: Hantera meddelanden och filer i karantän som administratör
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att visa och hantera meddelanden i karantän för alla användare i Exchange Online Protection (EOP). Administratörer i organisationer med Microsoft Defender för Office 365 kan också hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.
ms.openlocfilehash: b6f6f47dc227d3bada425d02784a8aff5da8b3d3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842934"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="e3201-104">Hantera meddelanden och filer i karantän som administratör i EOP</span><span class="sxs-lookup"><span data-stu-id="e3201-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e3201-105">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor lagrar karantänen potentiellt farliga eller oönskade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3201-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e3201-106">Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e3201-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e3201-107">Administratörer kan visa, frigöra och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="e3201-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e3201-108">Endast administratörer kan hantera meddelanden som satts i karantän som skadlig program vara, högsäker nät fiske eller resultat av regler för e-postflöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="e3201-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e3201-109">Administratörer kan också rapportera falsk identifiering till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3201-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e3201-110">Administratörer i organisationer med Microsoft Defender för Office 365 kan också visa, ladda ned och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3201-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e3201-111">Du visar och hanterar meddelanden i karantän i säkerhets & efterföljandekrav eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="e3201-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e3201-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="e3201-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e3201-113">Gå till <https://protection.office.com> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="e3201-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e3201-114">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e3201-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e3201-115">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e3201-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e3201-116">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e3201-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e3201-117">Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantän** rollen i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e3201-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="e3201-118">Som standard tilldelas den här rollen **organisations hantering** (globala administratörer), **karantän administratören** och **säkerhets administratörs** rollerna för säkerhets &.</span><span class="sxs-lookup"><span data-stu-id="e3201-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator** , and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e3201-119">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e3201-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e3201-120">Meddelanden i karantän bevaras under en standard tids period innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="e3201-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="e3201-121">Meddelanden i karantän med principer för skräp post (spam, nätfiske och Mass utskick): 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="e3201-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="e3201-122">Det här är standardvärdet och Max värdet.</span><span class="sxs-lookup"><span data-stu-id="e3201-122">This is the default and maximum value.</span></span> <span data-ttu-id="e3201-123">Information om hur du konfigurerar det här värdet finns i [Konfigurera principer för skräp post](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e3201-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="e3201-124">Meddelanden som innehåller skadlig kod: 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="e3201-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="e3201-125">När ett meddelande utgår från karantän kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="e3201-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e3201-126">Hantera e-postmeddelanden med hjälp av säkerhets &</span><span class="sxs-lookup"><span data-stu-id="e3201-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e3201-127">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-127">View quarantined email</span></span>

1. <span data-ttu-id="e3201-128">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="e3201-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e3201-129">Kontrol lera att **Visa karantän** är inställt på standardvärdet för **e-post**.</span><span class="sxs-lookup"><span data-stu-id="e3201-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e3201-130">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="e3201-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e3201-131">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="e3201-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e3201-132">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e3201-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e3201-133">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-134">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-135">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-136">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-137">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-138">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-139">**Upphör**</span><span class="sxs-lookup"><span data-stu-id="e3201-139">**Expires**</span></span>
   - <span data-ttu-id="e3201-140">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="e3201-140">**Recipient**</span></span>
   - <span data-ttu-id="e3201-141">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="e3201-141">**Message ID**</span></span>
   - <span data-ttu-id="e3201-142">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="e3201-142">**Policy name**</span></span>
   - <span data-ttu-id="e3201-143">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="e3201-143">**Size**</span></span>
   - <span data-ttu-id="e3201-144">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="e3201-144">**Direction**</span></span>

   <span data-ttu-id="e3201-145">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e3201-145">When you're finished, click **Save** , or click **Set to default**.</span></span>

4. <span data-ttu-id="e3201-146">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="e3201-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e3201-147">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="e3201-147">The available filters are:</span></span>

   - <span data-ttu-id="e3201-148">**Upphör att gälla** : Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="e3201-148">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e3201-149">**I dag**</span><span class="sxs-lookup"><span data-stu-id="e3201-149">**Today**</span></span>
     - <span data-ttu-id="e3201-150">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="e3201-150">**Next 2 days**</span></span>
     - <span data-ttu-id="e3201-151">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="e3201-151">**Next 7 days**</span></span>
     - <span data-ttu-id="e3201-152">**Anpassad** : Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="e3201-152">**Custom** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e3201-153">**Togs emot** : Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="e3201-153">**Received time** : Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e3201-154">**Orsak till karantän** :</span><span class="sxs-lookup"><span data-stu-id="e3201-154">**Quarantine reason** :</span></span>
     - <span data-ttu-id="e3201-155">**Princip** : meddelandet överensstämde med villkoren i en regel för e-postflöde (kallas även för transport regel).</span><span class="sxs-lookup"><span data-stu-id="e3201-155">**Policy** : The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="e3201-156">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="e3201-156">**Bulk**</span></span>
     - <span data-ttu-id="e3201-157">**Phish** : skräp post filtret Verdict var ett **nät fiske** meddelande eller skydd mot nätfiske ( [Spoof inställningar](set-up-anti-phishing-policies.md#spoof-settings) eller [personifieringstoken](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="e3201-157">**Phish** : The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="e3201-158">**Program**</span><span class="sxs-lookup"><span data-stu-id="e3201-158">**Malware**</span></span>
     - <span data-ttu-id="e3201-159">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="e3201-159">**Spam**</span></span>
     - <span data-ttu-id="e3201-160">**Hög exakthet Phish**</span><span class="sxs-lookup"><span data-stu-id="e3201-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e3201-161">**Principtyp** : filtrera meddelanden efter principtyp:</span><span class="sxs-lookup"><span data-stu-id="e3201-161">**Policy Type** : Filter messages by policy type:</span></span>
     - <span data-ttu-id="e3201-162">**Policy för mot skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="e3201-162">**Anti-malware policy**</span></span>
     - <span data-ttu-id="e3201-163">**Principer för säkra bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="e3201-163">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="e3201-164">**Princip för skydd mot nätfiske**</span><span class="sxs-lookup"><span data-stu-id="e3201-164">**Anti-phish policy**</span></span>
     - <span data-ttu-id="e3201-165">**Principer för värd innehålls filter** (policy för skräp post)</span><span class="sxs-lookup"><span data-stu-id="e3201-165">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="e3201-166">**Transport regel**</span><span class="sxs-lookup"><span data-stu-id="e3201-166">**Transport rule**</span></span>

   - <span data-ttu-id="e3201-167">**E-postmottagare** : alla användare eller bara meddelanden som skickas till dig.</span><span class="sxs-lookup"><span data-stu-id="e3201-167">**Email recipient** : All users or only messages sent to you.</span></span> <span data-ttu-id="e3201-168">Slutanvändare kan bara hantera skickade meddelanden till dem.</span><span class="sxs-lookup"><span data-stu-id="e3201-168">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e3201-169">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="e3201-169">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e3201-170">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="e3201-170">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e3201-171">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="e3201-171">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e3201-172">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="e3201-172">Wildcards aren't supported.</span></span> <span data-ttu-id="e3201-173">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="e3201-173">You can search by the following values:</span></span>

   - <span data-ttu-id="e3201-174">**Meddelande-ID** : Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="e3201-174">**Message ID** : The globally unique identifier of the message.</span></span>

     <span data-ttu-id="e3201-175">Du använde exempelvis [meddelande spårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i din organisation, och du fastställer att meddelandet satts i stället för att levereras.</span><span class="sxs-lookup"><span data-stu-id="e3201-175">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e3201-176">Se till att du inkluderar fullständigt meddelande-ID, som kan innehålla vinkelparenteser ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="e3201-176">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e3201-177">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="e3201-177">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e3201-178">**Avsändarens e-postadress** : En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e3201-178">**Sender email address** : A single sender's email address.</span></span>

   - <span data-ttu-id="e3201-179">**Principnamn** : använd meddelandets hela principnamn.</span><span class="sxs-lookup"><span data-stu-id="e3201-179">**Policy name** : Use the entire policy name of the message.</span></span> <span data-ttu-id="e3201-180">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="e3201-180">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e3201-181">**Mottagarens e-postadress** : En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="e3201-181">**Recipient email address** : A single recipient's email address.</span></span>

   - <span data-ttu-id="e3201-182">**Ämne** : Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="e3201-182">**Subject** : Use the entire subject of the message.</span></span> <span data-ttu-id="e3201-183">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="e3201-183">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="e3201-184">**Princip namn** : namnet på den policy som var ansvarig för quarantining meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e3201-184">**Policy name** : The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="e3201-185">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera** , så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="e3201-185">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e3201-186">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="e3201-186">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="e3201-187">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="e3201-187">Export message results</span></span>

1. <span data-ttu-id="e3201-188">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="e3201-188">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e3201-189">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="e3201-189">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e3201-190">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="e3201-190">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e3201-191">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-191">View quarantined message details</span></span>

<span data-ttu-id="e3201-192">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information** :</span><span class="sxs-lookup"><span data-stu-id="e3201-192">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e3201-193">**Meddelande-ID** : Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="e3201-193">**Message ID** : The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e3201-194">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="e3201-194">**Sender address**</span></span>

- <span data-ttu-id="e3201-195">**Mottaget** : Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="e3201-195">**Received** : The date/time when the message was received.</span></span>

- <span data-ttu-id="e3201-196">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="e3201-196">**Subject**</span></span>

- <span data-ttu-id="e3201-197">**Karantän orsak** : visar om ett meddelande har identifierats som **skräp post** , **bulk** , **Phish** , matchade en e-postregel ( **Transport regel** ) eller som innehåller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="e3201-197">**Quarantine reason** : Shows if a message has been identified as **Spam** , **Bulk** , **Phish** , matched a mail flow rule ( **Transport rule** ), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e3201-198">**Antal mottagare**</span><span class="sxs-lookup"><span data-stu-id="e3201-198">**Recipient count**</span></span>

- <span data-ttu-id="e3201-199">**Mottagare** : Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="e3201-199">**Recipients** : If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e3201-200">**Upphör** : Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="e3201-200">**Expires** : The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e3201-201">**Släppt till** : Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="e3201-201">**Released to** : All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e3201-202">**Släppt till** : Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="e3201-202">**Not yet released to** : All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e3201-203">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-203">Take action on quarantined email</span></span>

<span data-ttu-id="e3201-204">När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret utfällda **Detaljer** :</span><span class="sxs-lookup"><span data-stu-id="e3201-204">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e3201-205">**Släpp meddelande** : i fönstret som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e3201-205">**Release message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e3201-206">**Rapportera meddelanden till Microsoft för analys** : det här är markerat som standard och rapporterar det felaktiga meddelandet till Microsoft som ett falskt positivt tal.</span><span class="sxs-lookup"><span data-stu-id="e3201-206">**Report messages to Microsoft for analysis** : This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e3201-207">Om meddelandet sattes i karantän som skräp post, bulk, nätfiske eller innehåller skadlig program vara, rapporteras meddelandet också till Microsoft spam-gruppen.</span><span class="sxs-lookup"><span data-stu-id="e3201-207">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e3201-208">Beroende på vilken analys de har, kan de globala skräp post filter reglerna justeras så att de tillåter meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e3201-208">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e3201-209">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e3201-209">Choose one of the following options:</span></span>
    - <span data-ttu-id="e3201-210">**Släpp meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="e3201-210">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="e3201-211">**Släpp meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="e3201-211">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="e3201-212">**Släppa meddelanden till andra personer**</span><span class="sxs-lookup"><span data-stu-id="e3201-212">**Release messages to other people**</span></span>

  <span data-ttu-id="e3201-213">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e3201-213">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e3201-214">Anmärkningar om att frigöra meddelanden:</span><span class="sxs-lookup"><span data-stu-id="e3201-214">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e3201-215">Du kan inte frigöra ett meddelande till samma mottagare flera gånger.</span><span class="sxs-lookup"><span data-stu-id="e3201-215">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="e3201-216">Endast mottagare som inte har fått meddelandet visas i listan över potentiella mottagare.</span><span class="sxs-lookup"><span data-stu-id="e3201-216">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e3201-217">**Visa meddelandehuvud** : Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="e3201-217">**View message header** : Choose this link to see the message header text.</span></span> <span data-ttu-id="e3201-218">Om du vill analysera fälten och värden för huvuden mer ingående kopierar du meddelandehuvudets text till Urklipp och väljer sedan **Microsofts analysverktyg för meddelanderubrik** för att gå till analysverktyget för fjärranslutning (högerklicka och välj **Öppna i ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="e3201-218">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e3201-219">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="e3201-219">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers** :</span></span>

- <span data-ttu-id="e3201-220">**Förhandsgranska meddelandet** : Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="e3201-220">**Preview message** : In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e3201-221">**Källvy** : Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="e3201-221">**Source view** : Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="e3201-222">**Textvy** : Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="e3201-222">**Text view** : Shows the message body in plain text.</span></span>

- <span data-ttu-id="e3201-223">**Ta bort från karantän** : när du klickar på **Ja** i den varning som visas, tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="e3201-223">**Remove from quarantine** : After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e3201-224">**Ladda ned meddelande** : Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="e3201-224">**Download message** : In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e3201-225">**Skicka meddelande** : i fönstret som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="e3201-225">**Submit message** : In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e3201-226">**Objekt typ** : **e-post** (standard), **URL** eller **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="e3201-226">**Object type** : **Email** (default), **URL** , or **Attachment**.</span></span>

  - <span data-ttu-id="e3201-227">**Sändnings format** : **ID för nätverks meddelanden** (standard, med motsvarande värde i fältet för **nätverks meddelande-ID** ) eller **filen** (Bläddra till en lokal. eml-eller. msg-fil).</span><span class="sxs-lookup"><span data-stu-id="e3201-227">**Submission format** : **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e3201-228">Observera att om du väljer **Arkiv** och sedan **nätverks meddelande-ID** är värdet från från början borta.</span><span class="sxs-lookup"><span data-stu-id="e3201-228">Note that if you select **File** and then select **Network Message ID** , the initially value is gone.</span></span>

  - <span data-ttu-id="e3201-229">**Mottagare** : Ange en ursprunglig mottagare för meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="e3201-229">**Recipients** : Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e3201-230">Du kan också klicka på **Markera alla** och sedan ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="e3201-230">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e3201-231">**Orsak för inlämning** : **ska inte vara blockerat** (standard) eller **ha blockerats**.</span><span class="sxs-lookup"><span data-stu-id="e3201-231">**Reason for submission** : **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e3201-232">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="e3201-232">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e3201-233">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="e3201-233">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e3201-234">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-234">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e3201-235">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="e3201-235">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e3201-236">**Släpp meddelanden** : Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="e3201-236">**Release messages** : The options are the same as when you release a single message, except you can't select **Release messages to specific recipients** ; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e3201-237">Tänk på följande: john@gmail.com skickar ett meddelande till faith@contoso.com och john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3201-237">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="e3201-238">Gmail bifurcates det här meddelandet i två kopior som båda dirigeras till karantän som nätfiske i Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e3201-238">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="e3201-239">En administratör frigör båda dessa meddelanden till admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3201-239">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="e3201-240">Det första meddelandet som når administratörs post lådan levereras.</span><span class="sxs-lookup"><span data-stu-id="e3201-240">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="e3201-241">Det andra publicerade meddelandet identifieras som dubbel leverans och hoppas över.</span><span class="sxs-lookup"><span data-stu-id="e3201-241">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="e3201-242">Meddelandet identifieras som dubbletter om de har samma meddelande-ID och tid.</span><span class="sxs-lookup"><span data-stu-id="e3201-242">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="e3201-243">**Ta bort meddelanden** : När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="e3201-243">**Delete messages** :  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e3201-244">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e3201-244">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e3201-245">Endast Microsoft Defender för Office 365: Använd säkerhets & Compliance Center för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-245">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e3201-246">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2-abonnenter.</span><span class="sxs-lookup"><span data-stu-id="e3201-246">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e3201-247">I organisationer med Defender för Office 365 kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e3201-247">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="e3201-248">Information om hur du aktiverar skyddet för dessa filer finns i [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e3201-248">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e3201-249">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-249">View quarantined files</span></span>

1. <span data-ttu-id="e3201-250">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="e3201-250">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e3201-251">Ändra **vy i karantän** **till Values**.</span><span class="sxs-lookup"><span data-stu-id="e3201-251">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="e3201-252">Du kan sortera efter ett fält genom att klicka på en tillgänglig kolumn rubrik.</span><span class="sxs-lookup"><span data-stu-id="e3201-252">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e3201-253">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="e3201-253">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e3201-254">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="e3201-254">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e3201-255">Standard kolumnerna är markerade med en asterisk ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="e3201-255">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e3201-256">**Användarläge**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-256">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-257">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-257">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-258">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-258">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-259">**Fil-URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-259">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-260">**Fil storlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-260">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-261">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-261">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-262">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e3201-262">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e3201-263">**Identifieras av**</span><span class="sxs-lookup"><span data-stu-id="e3201-263">**Detected by**</span></span>
   - <span data-ttu-id="e3201-264">**Ändrad efter tid**</span><span class="sxs-lookup"><span data-stu-id="e3201-264">**Modified by time**</span></span>

4. <span data-ttu-id="e3201-265">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="e3201-265">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e3201-266">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="e3201-266">The available filters are:</span></span>

   - <span data-ttu-id="e3201-267">**Upphör att gälla** : Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="e3201-267">**Expires time** : Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e3201-268">**I dag**</span><span class="sxs-lookup"><span data-stu-id="e3201-268">**Today**</span></span>
     - <span data-ttu-id="e3201-269">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="e3201-269">**Next 2 days**</span></span>
     - <span data-ttu-id="e3201-270">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="e3201-270">**Next 7 days**</span></span>
     - <span data-ttu-id="e3201-271">Ett anpassat datum-och tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="e3201-271">A custom date/time range.</span></span>
   - <span data-ttu-id="e3201-272">**Mottaget**</span><span class="sxs-lookup"><span data-stu-id="e3201-272">**Received time**</span></span>
   - <span data-ttu-id="e3201-273">**Karantän orsak** : det enda tillgängliga värdet är **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="e3201-273">**Quarantine reason** : The only available value is **Malware**.</span></span>
   - <span data-ttu-id="e3201-274">**Principtyp**</span><span class="sxs-lookup"><span data-stu-id="e3201-274">**Policy type**</span></span>

<span data-ttu-id="e3201-275">När du har hittat en viss fil i karantän väljer du filen för att visa information om den och för att utföra en åtgärd på den (till exempel Visa, släppa, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="e3201-275">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="e3201-276">Exportera fil resultat</span><span class="sxs-lookup"><span data-stu-id="e3201-276">Export file results</span></span>

1. <span data-ttu-id="e3201-277">Välj de filer du är intresse rad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="e3201-277">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e3201-278">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="e3201-278">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e3201-279">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="e3201-279">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e3201-280">Visa fil information i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-280">View quarantined file details</span></span>

<span data-ttu-id="e3201-281">När du väljer en fil i listan visas följande fil information i fönstret **detaljerad information** :</span><span class="sxs-lookup"><span data-stu-id="e3201-281">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e3201-282">**Fil namn**</span><span class="sxs-lookup"><span data-stu-id="e3201-282">**File Name**</span></span>
- <span data-ttu-id="e3201-283">**URL: URL** som definierar filens plats (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="e3201-283">**File URL** : URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="e3201-284">**Skadligt innehåll upptäcktes på** Det datum/den tid då filen sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="e3201-284">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="e3201-285">**Upphör** : det datum då filen ska tas bort från karantänen.</span><span class="sxs-lookup"><span data-stu-id="e3201-285">**Expires** : The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="e3201-286">**Identifieras av** : Defender för Office 365 eller Microsoft-programmet mot skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="e3201-286">**Detected By** : Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="e3201-287">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="e3201-287">**Released?**</span></span>
- <span data-ttu-id="e3201-288">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="e3201-288">**Malware Name**</span></span>
- <span data-ttu-id="e3201-289">**Dokument-ID** : ett unikt ID för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e3201-289">**Document ID** : A unique identifier for the document.</span></span>
- <span data-ttu-id="e3201-290">**Fil storlek** : i KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="e3201-290">**File Size** : In kilobytes (KB).</span></span>
- <span data-ttu-id="e3201-291">**Organisation** Organisationens unika ID.</span><span class="sxs-lookup"><span data-stu-id="e3201-291">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="e3201-292">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="e3201-292">**Last modified**</span></span>
- <span data-ttu-id="e3201-293">**Ändrad av** : den användare som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="e3201-293">**Modified By** : The user who last modified the file.</span></span>
- <span data-ttu-id="e3201-294">**Secure Hash Algorithm 256-bit (SHA-256) värde** : du kan använda det här hashvärdet för att identifiera filen i andra ryktes butiker eller på andra platser i miljön.</span><span class="sxs-lookup"><span data-stu-id="e3201-294">**Secure Hash Algorithm 256-bit (SHA-256) value** : You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e3201-295">Vidta en åtgärd för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-295">Take action on quarantined files</span></span>

<span data-ttu-id="e3201-296">När du väljer en fil i listan kan du utföra följande åtgärder på filen i fönstret **detaljerad information** :</span><span class="sxs-lookup"><span data-stu-id="e3201-296">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e3201-297">**Släpp filer** : Välj (standard) eller avmarkera **rapportera filer till Microsoft för analys** och klicka sedan på **släpp filer**.</span><span class="sxs-lookup"><span data-stu-id="e3201-297">**Release files** : Select (default) or unselect **Report files to Microsoft for analysis** , and then click **Release files**.</span></span>
- <span data-ttu-id="e3201-298">**Ladda ner fil**</span><span class="sxs-lookup"><span data-stu-id="e3201-298">**Download file**</span></span>
- <span data-ttu-id="e3201-299">**Ta bort fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="e3201-299">**Remove file from quarantine**</span></span>

<span data-ttu-id="e3201-300">Om du inte släpper eller tar bort filerna tas de bort när standard perioden för karantän lagring upphör.</span><span class="sxs-lookup"><span data-stu-id="e3201-300">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e3201-301">Åtgärder på flera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="e3201-301">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e3201-302">När du markerar flera filer i karantän i listan (upp till 100) visas utfällda **Mass åtgärder** -fönstret där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="e3201-302">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e3201-303">**Släpp filer**</span><span class="sxs-lookup"><span data-stu-id="e3201-303">**Release files**</span></span>
- <span data-ttu-id="e3201-304">**Ta bort filer** : när du har klickat på **Ja** i varningen som visas tas filerna bort omedelbart.</span><span class="sxs-lookup"><span data-stu-id="e3201-304">**Delete files** :  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e3201-305">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att visa och hantera meddelanden och filer i karantänen</span><span class="sxs-lookup"><span data-stu-id="e3201-305">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e3201-306">De cmdlets som du använder för att visa och hantera meddelanden och filer i karantänen är:</span><span class="sxs-lookup"><span data-stu-id="e3201-306">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e3201-307">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e3201-307">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="e3201-308">Exportera-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e3201-308">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="e3201-309">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e3201-309">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="e3201-310">För [hands version – QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observera att denna cmdlet endast gäller för meddelanden, inte malware-filer från ATP för SharePoint Online, OneDrive för företag eller teams.</span><span class="sxs-lookup"><span data-stu-id="e3201-310">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e3201-311">Utgivning-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e3201-311">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
