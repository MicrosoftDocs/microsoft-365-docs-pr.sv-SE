---
title: Hantera meddelanden och filer i karantän som administratör
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
ms.openlocfilehash: 1ae64b71d29f9e2d973f5a73cc19790fe0736913
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635365"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="d60e9-104">Hantera meddelanden och filer i karantän som administratör</span><span class="sxs-lookup"><span data-stu-id="d60e9-104">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="d60e9-105">Karantänen innehåller potentiellt farliga eller oönskade meddelanden i Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="d60e9-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="d60e9-106">Mer information finns i [Karantän i Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="d60e9-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="d60e9-107">Administratörer kan visa, släppa och ta bort alla typer av meddelanden i karantän för alla användare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="d60e9-108">Endast administratörer kan hantera meddelanden som har satts i karantän som skadlig kod, nätfiske med högt förtroende eller som ett resultat av regler för e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="d60e9-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="d60e9-109">Administratörer kan också rapportera falska positiva identifieringar till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d60e9-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="d60e9-110">Administratörer i organisationer med Office 365 Advance Threat Protection (ATP) kan också visa, hämta och ta bort filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d60e9-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="d60e9-111">Du kan visa och hantera meddelanden i karantän i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="d60e9-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d60e9-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d60e9-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d60e9-113">Öppna säkerhets- & Compliance Center genom <https://protection.office.com>att gå till .</span><span class="sxs-lookup"><span data-stu-id="d60e9-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="d60e9-114">Om du vill öppna karantänsidan direkt går du till <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="d60e9-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="d60e9-115">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d60e9-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d60e9-116">Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d60e9-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d60e9-117">Du måste tilldelas behörigheter innan du kan hantera karantänen som administratör. Behörigheterna styrs av **karantänrollen** i Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="d60e9-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="d60e9-118">Som standard tilldelas den här rollen till rollgrupperna **Organisationshantering** (Globala administratörer), **karantänadministratör**och **Säkerhetsadministratör** i säkerhets- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="d60e9-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="d60e9-119">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d60e9-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d60e9-120">Meddelanden i karantän behålls under en standardperiod innan de tas bort automatiskt:</span><span class="sxs-lookup"><span data-stu-id="d60e9-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="d60e9-121">Meddelanden i karantän av policyer mot skräppost (skräppost, nätfiske och massmeddelande): 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="d60e9-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="d60e9-122">Detta är standard- och maxvärdet.</span><span class="sxs-lookup"><span data-stu-id="d60e9-122">This is the default and maximum value.</span></span> <span data-ttu-id="d60e9-123">Mer om du vill konfigurera det här värdet finns i [Konfigurera principer mot skräppost](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d60e9-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="d60e9-124">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="d60e9-124">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="d60e9-125">Meddelanden som innehåller skadlig kod: 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="d60e9-125">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="d60e9-126">När ett meddelande upphör att gälla från karantänen kan du inte återställa det.</span><span class="sxs-lookup"><span data-stu-id="d60e9-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="d60e9-127">Använda Security & Compliance Center för att hantera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="d60e9-128">Visa e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-128">View quarantined email</span></span>

1. <span data-ttu-id="d60e9-129">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d60e9-130">Kontrollera att **Visa i karantän** är inställt på standardvärdet **e-post**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="d60e9-131">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="d60e9-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d60e9-132">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="d60e9-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d60e9-133">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="d60e9-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d60e9-134">**Mottaget**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-134">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-135">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-135">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-136">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-136">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-137">**Orsak till karantän**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-137">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-138">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-138">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-139">**Principtyp**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-139">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="d60e9-140">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="d60e9-140">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="d60e9-141">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="d60e9-141">**Recipient**</span></span>

   - <span data-ttu-id="d60e9-142">**Meddelande-ID**</span><span class="sxs-lookup"><span data-stu-id="d60e9-142">**Message ID**</span></span>

   - <span data-ttu-id="d60e9-143">**Principnamn**</span><span class="sxs-lookup"><span data-stu-id="d60e9-143">**Policy name**</span></span>

   - <span data-ttu-id="d60e9-144">**Storlek**</span><span class="sxs-lookup"><span data-stu-id="d60e9-144">**Size**</span></span>

   - <span data-ttu-id="d60e9-145">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="d60e9-145">**Direction**</span></span>

   <span data-ttu-id="d60e9-146">Klicka på **Spara** eller på **Ställ in på standard** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d60e9-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="d60e9-147">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d60e9-148">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="d60e9-148">The available filters are:</span></span>

   - <span data-ttu-id="d60e9-149">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="d60e9-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="d60e9-150">**I dag**</span><span class="sxs-lookup"><span data-stu-id="d60e9-150">**Today**</span></span>

     - <span data-ttu-id="d60e9-151">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="d60e9-151">**Next 2 days**</span></span>

     - <span data-ttu-id="d60e9-152">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="d60e9-152">**Next 7 days**</span></span>

     - <span data-ttu-id="d60e9-153">**Anpassad**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d60e9-154">**Togs emot**: Ange ett **Startdatum** och **Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="d60e9-155">**Orsak till karantän**:</span><span class="sxs-lookup"><span data-stu-id="d60e9-155">**Quarantine reason**:</span></span>

     - <span data-ttu-id="d60e9-156">**Princip**: Meddelandet matchade villkoren för en regel för e-postflöde (kallas även transportregel).</span><span class="sxs-lookup"><span data-stu-id="d60e9-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="d60e9-157">**Bulk** (Massutskick)</span><span class="sxs-lookup"><span data-stu-id="d60e9-157">**Bulk**</span></span>

     - <span data-ttu-id="d60e9-158">**Phish**</span><span class="sxs-lookup"><span data-stu-id="d60e9-158">**Phish**</span></span>

     - <span data-ttu-id="d60e9-159">**Malware**</span><span class="sxs-lookup"><span data-stu-id="d60e9-159">**Malware**</span></span>

     - <span data-ttu-id="d60e9-160">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="d60e9-160">**Spam**</span></span>

     - <span data-ttu-id="d60e9-161">**Högt förtroende Phish**</span><span class="sxs-lookup"><span data-stu-id="d60e9-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="d60e9-162">**E-postmottagare**: Alla användare eller endast meddelanden som skickas till dig.</span><span class="sxs-lookup"><span data-stu-id="d60e9-162">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="d60e9-163">Slutanvändare kan bara hantera meddelanden i karantän som skickas till dem.</span><span class="sxs-lookup"><span data-stu-id="d60e9-163">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="d60e9-164">Tryck på **Rensa** om du vill ta bort filtret.</span><span class="sxs-lookup"><span data-stu-id="d60e9-164">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="d60e9-165">Klicka på **Filter** igen om du vill dölja den utfällbara filterrutan.</span><span class="sxs-lookup"><span data-stu-id="d60e9-165">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="d60e9-166">Använd **Sortera resultat efter** (knappen **Meddelande-ID** som standard) och ett motsvarande värde för att hitta specifika meddelanden.</span><span class="sxs-lookup"><span data-stu-id="d60e9-166">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="d60e9-167">Jokertecken stöds inte.</span><span class="sxs-lookup"><span data-stu-id="d60e9-167">Wildcards aren't supported.</span></span> <span data-ttu-id="d60e9-168">Du kan söka efter följande värden:</span><span class="sxs-lookup"><span data-stu-id="d60e9-168">You can search by the following values:</span></span>

   - <span data-ttu-id="d60e9-169">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-169">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="d60e9-170">Du använde till exempel [meddelandespårning](message-trace-scc.md) för att leta efter ett meddelande som skickades till en användare i organisationen och du bestämmer att meddelandet sattes i karantän i stället för levererat.</span><span class="sxs-lookup"><span data-stu-id="d60e9-170">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="d60e9-171">Var noga med att inkludera det fullständiga meddelande-ID-värdet, som kan innehålla vinkelparenteser (\<\>).</span><span class="sxs-lookup"><span data-stu-id="d60e9-171">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="d60e9-172">Till exempel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="d60e9-172">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="d60e9-173">**Avsändarens e-postadress**: En enskild avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d60e9-173">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="d60e9-174">**Mottagarens e-postadress**: En enskild mottagares e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d60e9-174">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="d60e9-175">**Ämne**: Använd meddelandets hela ämne.</span><span class="sxs-lookup"><span data-stu-id="d60e9-175">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="d60e9-176">Sökningen är inte skiftlägeskänslig.</span><span class="sxs-lookup"><span data-stu-id="d60e9-176">The search is not case-sensitive.</span></span>

   <span data-ttu-id="d60e9-177">När du har angett sökvillkor klickar du på ![knappen Uppdatera](../../media/scc-quarantine-refresh.png) **Uppdatera**, så filtreras resultatet.</span><span class="sxs-lookup"><span data-stu-id="d60e9-177">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="d60e9-178">När du har hittat ett specifikt meddelande i karantän väljer du meddelandet för att visa information om det och vidta åtgärder för det (till exempel visa, släpp, ladda ned eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="d60e9-178">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="d60e9-179">Exportera meddelanderesultat</span><span class="sxs-lookup"><span data-stu-id="d60e9-179">Export message results</span></span>

1. <span data-ttu-id="d60e9-180">Markera de meddelanden du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-180">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="d60e9-181">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="d60e9-181">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="d60e9-182">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="d60e9-182">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="d60e9-183">Visa information om meddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-183">View quarantined message details</span></span>

<span data-ttu-id="d60e9-184">När du väljer ett e-postmeddelande i listan visas följande meddelandeinformation i den utfällbara rutan **Information**:</span><span class="sxs-lookup"><span data-stu-id="d60e9-184">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d60e9-185">**Meddelande-ID**: Meddelandets globalt unika identifierare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-185">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="d60e9-186">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="d60e9-186">**Sender address**</span></span>

- <span data-ttu-id="d60e9-187">**Mottaget**: Datumet/tiden då meddelandet togs emot.</span><span class="sxs-lookup"><span data-stu-id="d60e9-187">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="d60e9-188">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="d60e9-188">**Subject**</span></span>

- <span data-ttu-id="d60e9-189">**Karantänorsak**: Visar om ett meddelande har identifierats som **Skräppost,** **Bulk,** **Phish**, matchade en regel för e-postflöde (**transportregel**) eller har identifierats som innehållande **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-189">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="d60e9-190">**Mottagare**: Om meddelandet innehåller flera mottagare måste du klicka på **Förhandsgranska meddelandet** eller **Visa meddelandehuvud** för att se den fullständiga listan över mottagare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-190">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="d60e9-191">**Upphör**: Datumet/tiden då meddelandet tas bort automatiskt och permanent från karantänen.</span><span class="sxs-lookup"><span data-stu-id="d60e9-191">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="d60e9-192">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="d60e9-192">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="d60e9-193">**Släppt till**: Alla e-postadresser som meddelandet har släppts till.</span><span class="sxs-lookup"><span data-stu-id="d60e9-193">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="d60e9-194">Vidta åtgärder för e-post i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-194">Take action on quarantined email</span></span>

<span data-ttu-id="d60e9-195">När du har valt ett meddelande har du flera alternativ för vad du kan göra med meddelandena i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="d60e9-195">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d60e9-196">**Utgivningsmeddelande:** I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d60e9-196">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d60e9-197">**Rapportera meddelanden till Microsoft för analys**: Detta är markerat som standard och rapporterar det felaktigt i karantän meddelandet till Microsoft som ett falskt positivt.</span><span class="sxs-lookup"><span data-stu-id="d60e9-197">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="d60e9-198">Om meddelandet har satts i karantän som skräppost, bulk, nätfiske eller skadlig kod rapporteras meddelandet också till Microsoft Spam Analysis Team.</span><span class="sxs-lookup"><span data-stu-id="d60e9-198">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="d60e9-199">Beroende på deras analys kan reglerna för skräppostfilter för hela tjänsten justeras så att meddelandet kan skickas igenom.</span><span class="sxs-lookup"><span data-stu-id="d60e9-199">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="d60e9-200">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d60e9-200">Choose one of the following options:</span></span>

    - <span data-ttu-id="d60e9-201">**Släpp meddelanden till alla mottagare**</span><span class="sxs-lookup"><span data-stu-id="d60e9-201">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="d60e9-202">**Släpp meddelanden till specifika mottagare**</span><span class="sxs-lookup"><span data-stu-id="d60e9-202">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="d60e9-203">**Släpp meddelanden till andra**</span><span class="sxs-lookup"><span data-stu-id="d60e9-203">**Release messages to other people**</span></span>

  <span data-ttu-id="d60e9-204">Klicka på **Släpp meddelandet** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d60e9-204">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="d60e9-205">Anteckningar om att släppa meddelanden:</span><span class="sxs-lookup"><span data-stu-id="d60e9-205">Notes about releasing messages:</span></span>

  - <span data-ttu-id="d60e9-206">Du kan inte släppa ett meddelande till samma mottagare mer än en gång.</span><span class="sxs-lookup"><span data-stu-id="d60e9-206">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="d60e9-207">Endast mottagare som inte har tagit emot meddelandet visas i listan över potentiella mottagare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-207">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="d60e9-208">**Visa meddelandehuvud**: Välj den här länken om du vill visa meddelandehuvudets text.</span><span class="sxs-lookup"><span data-stu-id="d60e9-208">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="d60e9-209">Om du vill analysera rubrikfälten och värdena på djupet kopierar du meddelandehuvudtexten till Urklipp och väljer sedan **Microsoft Message Header Analyzer** för att gå till Remote Connectivity Analyzer (högerklicka och välj **Öppna på en ny flik** om du inte vill lämna Microsoft 365 för att slutföra den här uppgiften).</span><span class="sxs-lookup"><span data-stu-id="d60e9-209">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="d60e9-210">Klistra in meddelandehuvudet på sidan i analysverktyget för meddelanderubrik. Välj **Analyze headers** (Analysera rubriker):</span><span class="sxs-lookup"><span data-stu-id="d60e9-210">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="d60e9-211">**Förhandsgranska meddelandet**: Välj något av följande alternativ i den utfällbara rutan som visas:</span><span class="sxs-lookup"><span data-stu-id="d60e9-211">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="d60e9-212">**Källvy**: Visar HTML-versionen av meddelandetexten med alla länkar inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="d60e9-212">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="d60e9-213">**Textvy**: Visar meddelandetexten som oformaterad text.</span><span class="sxs-lookup"><span data-stu-id="d60e9-213">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="d60e9-214">**Ta bort från karantänen**: När du klickar på **Ja** i varningen som visas tas meddelandet omedelbart bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="d60e9-214">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="d60e9-215">**Ladda ned meddelande**: Välj **Jag är medveten om riskerna om jag laddar ned meddelandet** i den utfällbara rutan som visas om du vill spara en lokal kopia av meddelandet i .eml-format.</span><span class="sxs-lookup"><span data-stu-id="d60e9-215">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="d60e9-216">**Skicka meddelande**: I det utfällbara fönster som visas väljer du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="d60e9-216">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="d60e9-217">**Objekttyp**: **E-post** (standard), **URL**eller **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-217">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="d60e9-218">**Inlämningsformat**: **Nätverksmeddelande-ID** (standard, med motsvarande värde i rutan **Nätverksmeddelande-ID)** eller **Arkiv** (bläddra till en lokal EML- eller MSG-fil).</span><span class="sxs-lookup"><span data-stu-id="d60e9-218">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="d60e9-219">Observera att om du väljer **Arkiv** och sedan väljer **Nätverksmeddelande-ID**är det ursprungliga värdet borta.</span><span class="sxs-lookup"><span data-stu-id="d60e9-219">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="d60e9-220">**Mottagare**: Skriv vid lån en ursprunglig mottagare av meddelandet eller klicka på **Markera alla** för att identifiera alla mottagare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-220">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="d60e9-221">Du kan också klicka på **Markera alla** och sedan selektivt ta bort enskilda mottagare.</span><span class="sxs-lookup"><span data-stu-id="d60e9-221">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="d60e9-222">**Orsak till inlämning:** **Bör inte ha blockerats** (standard) eller **Bör ha blockerats**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-222">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="d60e9-223">När du är klar klickar du på **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-223">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="d60e9-224">Om du inte släpper eller tar bort meddelandet tas det bort när standardtiden för att behålla i karantän går ut.</span><span class="sxs-lookup"><span data-stu-id="d60e9-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="d60e9-225">Vidta åtgärder för flera e-postmeddelanden i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="d60e9-226">När du markerar flera meddelanden i karantän i listan (upp till 100) visas den utfällbara rutan **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="d60e9-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d60e9-227">**Släpp meddelanden**: Du har samma alternativ som när du släpper ett enstaka meddelande, förutom att du inte kan välja **Släpp meddelanden till vissa mottagare**. Du kan endast välja **Släpp meddelanden till alla mottagare** eller **Släpp meddelanden till andra personer**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="d60e9-228">**Ta bort meddelanden**: När du har klickat på **Ja** i varningen som visas tas meddelandet genast bort utan att skickas till de ursprungliga mottagarna.</span><span class="sxs-lookup"><span data-stu-id="d60e9-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="d60e9-229">Klicka på **Stäng** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="d60e9-229">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="d60e9-230">Endast ATP: Använd Security & Compliance Center för att hantera filer i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-230">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="d60e9-231">Procedurerna för filer i karantän i det här avsnittet är endast tillgängliga för ATP Plan 1- och Plan 2-prenumeranter.</span><span class="sxs-lookup"><span data-stu-id="d60e9-231">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="d60e9-232">I organisationer med ATP kan administratörer hantera filer i karantän i SharePoint Online, OneDrive för företag och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d60e9-232">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="d60e9-233">Visa filer i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-233">View quarantined files</span></span>

1. <span data-ttu-id="d60e9-234">I Säkerhets- och efterlevnadscentret går du till **Hothantering** \> **Granska** \> **Karantän**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-234">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="d60e9-235">Ändra **vy i karantän** till standardvärdefilerna . **files**</span><span class="sxs-lookup"><span data-stu-id="d60e9-235">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="d60e9-236">Du kan sortera i ett fält genom att klicka på ett tillgängligt kolumnhuvud.</span><span class="sxs-lookup"><span data-stu-id="d60e9-236">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="d60e9-237">Du kan sortera resultaten genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="d60e9-237">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="d60e9-238">Klicka på **Ändra kolumner** för att visa högst sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="d60e9-238">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="d60e9-239">Standardkolumnerna är markerade med<sup>\*</sup>en asterisk ( ):</span><span class="sxs-lookup"><span data-stu-id="d60e9-239">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="d60e9-240">**Användaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-240">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-241">**Plats**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-241">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-242">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-242">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-243">**URL för filer**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-243">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-244">**Filstorlek**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-244">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-245">**Upphör**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-245">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-246">**Släppt?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d60e9-246">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="d60e9-247">**Detekteras av**</span><span class="sxs-lookup"><span data-stu-id="d60e9-247">**Detected by**</span></span>

   - <span data-ttu-id="d60e9-248">**Ändrad med tiden**</span><span class="sxs-lookup"><span data-stu-id="d60e9-248">**Modified by time**</span></span>

4. <span data-ttu-id="d60e9-249">Om du vill filtrera resultaten klickar du på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-249">To filter the results, click **Filter**.</span></span> <span data-ttu-id="d60e9-250">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="d60e9-250">The available filters are:</span></span>

   - <span data-ttu-id="d60e9-251">**Upphör att gälla**: Filtrera meddelanden efter när de kommer att upphöra från karantänen:</span><span class="sxs-lookup"><span data-stu-id="d60e9-251">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="d60e9-252">**I dag**</span><span class="sxs-lookup"><span data-stu-id="d60e9-252">**Today**</span></span>

     - <span data-ttu-id="d60e9-253">**Kommande 2 dagarna**</span><span class="sxs-lookup"><span data-stu-id="d60e9-253">**Next 2 days**</span></span>

     - <span data-ttu-id="d60e9-254">**Kommande 7 dagarna**</span><span class="sxs-lookup"><span data-stu-id="d60e9-254">**Next 7 days**</span></span>

     - <span data-ttu-id="d60e9-255">Ett anpassat datum-/tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="d60e9-255">A custom date/time range.</span></span>

   - <span data-ttu-id="d60e9-256">**Mottagen tid**</span><span class="sxs-lookup"><span data-stu-id="d60e9-256">**Received time**</span></span>

   - <span data-ttu-id="d60e9-257">**Karantän orsak:** Det enda tillgängliga värdet är **Malware**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-257">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="d60e9-258">När du har hittat en viss fil i karantän markerar du filen för att visa information om den och vidtar åtgärder för den (till exempel visa, släpp, hämta eller ta bort meddelandet).</span><span class="sxs-lookup"><span data-stu-id="d60e9-258">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="d60e9-259">Exportera filresultat</span><span class="sxs-lookup"><span data-stu-id="d60e9-259">Export file results</span></span>

1. <span data-ttu-id="d60e9-260">Markera de filer du är intresserad av och klicka på **Exportera resultat**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-260">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="d60e9-261">Klicka på **Ja** i bekräftelsemeddelandet som varnar dig om att webbläsarfönstret ska vara öppet.</span><span class="sxs-lookup"><span data-stu-id="d60e9-261">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="d60e9-262">När exporten är klar kan du namnge och välja nedladdningsplats för .csv-filen.</span><span class="sxs-lookup"><span data-stu-id="d60e9-262">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="d60e9-263">Visa filinformation i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-263">View quarantined file details</span></span>

<span data-ttu-id="d60e9-264">När du markerar en fil i listan visas följande filinformation i fönstret **Utfällbara information:**</span><span class="sxs-lookup"><span data-stu-id="d60e9-264">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d60e9-265">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="d60e9-265">**File Name**</span></span>

- <span data-ttu-id="d60e9-266">**Fil-URL**: URL som definierar platsen för filen (till exempel i SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="d60e9-266">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="d60e9-267">**Skadligt innehåll har upptäckts på** Datum/tid då filen sattes i karantän.</span><span class="sxs-lookup"><span data-stu-id="d60e9-267">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="d60e9-268">**Upphör att gälla**: Det datum då filen tas bort från karantänen.</span><span class="sxs-lookup"><span data-stu-id="d60e9-268">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="d60e9-269">**Detekteras av:** ATP (Advanced Threat Protection) eller Microsofts anti-malware-motor.</span><span class="sxs-lookup"><span data-stu-id="d60e9-269">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="d60e9-270">**Släppt?**</span><span class="sxs-lookup"><span data-stu-id="d60e9-270">**Released?**</span></span>

- <span data-ttu-id="d60e9-271">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="d60e9-271">**Malware Name**</span></span>

- <span data-ttu-id="d60e9-272">**Dokument-ID:** En unik identifierare för dokumentet.</span><span class="sxs-lookup"><span data-stu-id="d60e9-272">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="d60e9-273">**Filstorlek:** I kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="d60e9-273">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="d60e9-274">**Organisation** Organisationens unika ID.</span><span class="sxs-lookup"><span data-stu-id="d60e9-274">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="d60e9-275">**Senast ändrad**</span><span class="sxs-lookup"><span data-stu-id="d60e9-275">**Last modified**</span></span>

- <span data-ttu-id="d60e9-276">**Ändrad av**: Användaren som senast ändrade filen.</span><span class="sxs-lookup"><span data-stu-id="d60e9-276">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="d60e9-277">**Värde för säker hashalgoritm 256-bitars (SHA-256):** Du kan använda det här hash-värdet för att identifiera filen i andra ryktesbutiker eller på andra platser i din miljö.</span><span class="sxs-lookup"><span data-stu-id="d60e9-277">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="d60e9-278">Vidta åtgärder för filer i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-278">Take action on quarantined files</span></span>

<span data-ttu-id="d60e9-279">När du väljer en fil i listan kan du vidta följande åtgärder för filen i fönstret **Utfällbara informationsuppgifter:**</span><span class="sxs-lookup"><span data-stu-id="d60e9-279">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="d60e9-280">**Släpp filer**: Markera (standard) eller avmarkera **rapportfiler till Microsoft för analys**och klicka sedan på Släpp **filer**.</span><span class="sxs-lookup"><span data-stu-id="d60e9-280">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="d60e9-281">**Ladda ner fil**</span><span class="sxs-lookup"><span data-stu-id="d60e9-281">**Download file**</span></span>

- <span data-ttu-id="d60e9-282">**Ta bort fil från karantän**</span><span class="sxs-lookup"><span data-stu-id="d60e9-282">**Remove file from quarantine**</span></span>

<span data-ttu-id="d60e9-283">Om du inte släpper eller tar bort filerna tas de bort när standardlagringsperioden för karantän upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="d60e9-283">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="d60e9-284">Åtgärder på filer i flera karantäner</span><span class="sxs-lookup"><span data-stu-id="d60e9-284">Actions on multiple quarantined files</span></span>

<span data-ttu-id="d60e9-285">När du väljer flera filer i karantän i listan (upp till 100) visas det utfällbara fönstret **Massåtgärder** där du kan vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="d60e9-285">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="d60e9-286">**Släpp filer**</span><span class="sxs-lookup"><span data-stu-id="d60e9-286">**Release files**</span></span>

- <span data-ttu-id="d60e9-287">**Ta bort filer**: När du klickar på **Ja** i varningen som visas tas filerna omedelbart bort.</span><span class="sxs-lookup"><span data-stu-id="d60e9-287">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="d60e9-288">Logga in och [gå till Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md)med hjälp av ett arbets- eller skolkonto som har globala administratörsbehörighet (eller lämpliga säkerhetsroller & Compliance Center) i organisationen .</span><span class="sxs-lookup"><span data-stu-id="d60e9-288">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="d60e9-289">Använda Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för att visa och hantera meddelanden och filer i karantän</span><span class="sxs-lookup"><span data-stu-id="d60e9-289">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="d60e9-290">De cmdlets du använder för att visa och hantera meddelanden och filer i karantän är:</span><span class="sxs-lookup"><span data-stu-id="d60e9-290">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="d60e9-291">Ta bort karantänMessage</span><span class="sxs-lookup"><span data-stu-id="d60e9-291">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="d60e9-292">Exportera karantänMessage</span><span class="sxs-lookup"><span data-stu-id="d60e9-292">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="d60e9-293">Hämta karantänMessage</span><span class="sxs-lookup"><span data-stu-id="d60e9-293">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="d60e9-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observera att den här cmdleten endast är för meddelanden, inte skadliga programfiler från ATP för SharePoint Online, OneDrive för företag eller Teams.</span><span class="sxs-lookup"><span data-stu-id="d60e9-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="d60e9-295">Release-KarantänMessage</span><span class="sxs-lookup"><span data-stu-id="d60e9-295">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
